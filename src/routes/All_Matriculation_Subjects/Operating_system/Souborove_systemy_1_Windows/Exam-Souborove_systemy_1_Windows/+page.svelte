<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Který souborový systém je výchozí pro Windows?',
			options: [
				{ id: 'a', text: 'FAT32' },
				{ id: 'b', text: 'NTFS' },
				{ id: 'c', text: 'exFAT' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Jaká je maximální velikost souboru ve FAT32?',
			options: [
				{ id: 'a', text: '2 GB' },
				{ id: 'b', text: '8 TB' },
				{ id: 'c', text: '4 GB' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'K čemu slouží žurnálování v souborových systémech?',
			options: [
				{ id: 'a', text: 'Zrychluje zápis dat' },
				{ id: 'b', text: 'Zajišťuje zpětnou kompatibilitu' },
				{ id: 'c', text: 'Zaznamenává změny pro obnovení při chybě' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'Který souborový systém je vhodný pro velké servery a nabízí automatickou opravu chyb?',
			options: [
				{ id: 'a', text: 'ReFS' },
				{ id: 'b', text: 'FAT32' },
				{ id: 'c', text: 'exFAT' }
			],
			correct: 'a',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Jaký příkaz slouží ke kontrole a opravě chyb disku ve Windows?',
			options: [
				{ id: 'a', text: 'CHKDSK' },
				{ id: 'b', text: 'DISKINIT' },
				{ id: 'c', text: 'FSFIX' }
			],
			correct: 'a',
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
		<h1>🧠 Test – Souborové systémy (Windows)</h1>

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
