<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Jaký je rozdíl mezi interním a externím příkazem v cmd?',
			options: [
				{ id: 'a', text: 'Interní potřebuje internet, externí nikoliv' },
				{ id: 'b', text: 'Interní je součást shellu, externí je samostatný program' },
				{ id: 'c', text: 'Interní se týká síťových nastavení, externí disku' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Jak vytvoříš globální proměnnou prostředí dostupnou i po restartu?',
			options: [
				{ id: 'a', text: 'set mojePromenna=hodnota' },
				{ id: 'b', text: 'setx mojePromenna "hodnota"' },
				{ id: 'c', text: 'echo mojePromenna=hodnota' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Co znamená příkaz: echo %USERNAME% ?',
			options: [
				{ id: 'a', text: 'Vypíše název proměnné %USERNAME%' },
				{ id: 'b', text: 'Zobrazí aktuální uživatelské jméno' },
				{ id: 'c', text: 'Vytvoří nového uživatele' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'K čemu slouží znak | (pipe) v cmd?',
			options: [
				{ id: 'a', text: 'Oddělení příkazů' },
				{ id: 'b', text: 'Zkombinování více proměnných' },
				{ id: 'c', text: 'Předání výstupu jednoho příkazu jako vstup druhému' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Jaký příkaz zobrazí historii příkazů v aktuální relaci?',
			options: [
				{ id: 'a', text: 'history' },
				{ id: 'b', text: 'cmd /history' },
				{ id: 'c', text: 'doskey /history' }
			],
			correct: 'c',
			answer: null as string | null
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
		<h1>🧠 Test – Správce zařízení (Device Manager)</h1>

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
		background: #ffffff;
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
