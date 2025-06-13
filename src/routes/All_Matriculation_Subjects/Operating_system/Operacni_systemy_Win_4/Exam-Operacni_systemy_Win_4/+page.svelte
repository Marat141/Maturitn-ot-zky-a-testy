<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Jaká je hlavní výhoda PowerShellu oproti CMD?',
			options: [
				{ id: 'a', text: 'Podpora pro HTML výstup' },
				{ id: 'b', text: 'Používá objektově orientovaný přístup' },
				{ id: 'c', text: 'Funguje jen na Linuxu' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Který příkaz zobrazí běžící procesy?',
			options: [
				{ id: 'a', text: 'Show-Process' },
				{ id: 'b', text: 'List-Tasks' },
				{ id: 'c', text: 'Get-Process' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Jak vytvoříš alias pro příkaz Get-ChildItem?',
			options: [
				{ id: 'a', text: 'alias ll = Get-ChildItem' },
				{ id: 'b', text: 'Set-Alias ll Get-ChildItem' },
				{ id: 'c', text: 'New-Alias ll = Get-ChildItem' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'Jak vypíšeš historii příkazů v PowerShellu?',
			options: [
				{ id: 'a', text: 'Show-History' },
				{ id: 'b', text: 'Get-History' },
				{ id: 'c', text: 'History-List' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Jak nastavíš novou hodnotu proměnné prostředí trvale?',
			options: [
				{ id: 'a', text: 'Set $env:PATH = "cesta"' },
				{ id: 'b', text: 'Set-Path -Value "cesta"' },
				{ id: 'c', text: '[Environment]::SetEnvironmentVariable(...)' }
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
		<h1>🧠 Test – PowerShell (Win_4)</h1>

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
