<script lang="ts">
	interface QuestionOption {
		id: string;
		text: string;
	}

	interface Question {
		id: number;
		text: string;
		options: QuestionOption[];
		correct: string;
		answer: string | null; // 💡 Oprava tady
	}

	let questions: Question[] = $state([
		{
			id: 1,
			text: 'Co je proces v operačním systému?',
			options: [
				{ id: 'a', text: 'Soubor uložený na disku' },
				{ id: 'b', text: 'Program v běhu' },
				{ id: 'c', text: 'Hardware komponenta' }
			],
			correct: 'b',
			answer: null
		},
		{
			id: 2,
			text: 'Který OS je známý pro své open-source jádro a vychází z UNIXu?',
			options: [
				{ id: 'a', text: 'Windows' },
				{ id: 'b', text: 'Mac OS' },
				{ id: 'c', text: 'Linux' }
			],
			correct: 'c',
			answer: null
		},
		{
			id: 3,
			text: 'Co je to deadlock?',
			options: [
				{ id: 'a', text: 'Zacyklení vstupního zařízení' },
				{ id: 'b', text: 'Ztráta dat při vstupu' },
				{ id: 'c', text: 'Zablokování procesů čekajících na vzájemné zdroje' }
			],
			correct: 'c',
			answer: null
		}
	]);

	let showResults = $state(false);

	function evaluate() {
		showResults = true;
	}

	function GoBack() {
        window.history.back();
	}
</script>

<main>
	<div class="exam-container">
		<h1>📝 Test: Základní součásti operačního systému</h1>

		{#each questions as q}
			<section class="question">
				<h2>{q.text}</h2>
				{#each q.options as opt}
					<label class:selected={q.answer === opt.id}>
						<input
							type="radio"
							name={`question-${q.id}`}
							value={opt.id}
							checked={q.answer === opt.id}
							onchange={() => (q.answer = opt.id)}
						/>
						{opt.text}
					</label>
				{/each}
				{#if showResults}
					<p class={q.answer === q.correct ? 'correct' : 'wrong'}>
						{q.answer === q.correct
							? '✅ Správně!'
							: `❌ Špatně. Správná odpověď je: ${q.options.find((o) => o.id === q.correct)?.text}`}
					</p>
				{/if}
			</section>
		{/each}

		<div class="controls">
			<button class="ButtonExam" onclick={evaluate}>Vyhodnotit test</button>
			<button onclick={GoBack}>Zpět</button>
		</div>
	</div>
</main>

<style>
	.exam-container {
		max-width: 800px;
		margin: auto;
		padding: 32px;
		background: white;
		border-radius: 12px;
		box-shadow: 0 12px 24px rgba(0, 0, 0, 0.1);
	}

	h1 {
		color: #2563eb;
		margin-bottom: 32px;
	}

	.question {
		margin-bottom: 24px;
	}

	.question h2 {
		margin-bottom: 12px;
		font-size: 1.2rem;
	}

	label {
		display: block;
		padding: 8px;
		border: 1px solid #ddd;
		border-radius: 6px;
		margin-bottom: 6px;
		cursor: pointer;
		transition: background-color 0.3s ease;
	}

	label.selected {
		background-color: #f0f9ff;
		border-color: #2563eb;
	}

	.correct {
		color: green;
		margin-top: 8px;
	}

	.wrong {
		color: red;
		margin-top: 8px;
	}

	.controls {
		display: flex;
		gap: 12px;
		margin-top: 24px;
	}

	.ButtonExam {
		background-color: #2563eb;
		color: white;
		padding: 10px 16px;
		border-radius: 6px;
		font-weight: 500;
		border: none;
		cursor: pointer;
		transition: background-color 0.2s ease;
	}

	.ButtonExam:hover {
		background-color: #1e40af;
	}
</style>
