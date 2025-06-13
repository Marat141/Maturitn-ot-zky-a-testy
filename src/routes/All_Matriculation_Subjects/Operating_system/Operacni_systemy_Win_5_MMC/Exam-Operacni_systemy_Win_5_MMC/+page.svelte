<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'K čemu slouží Microsoft Management Console (MMC)?',
			options: [
				{ id: 'a', text: 'Je to antivirový nástroj od Microsoftu' },
				{ id: 'b', text: 'Slouží ke správě systému pomocí modulů snap-in' },
				{ id: 'c', text: 'Zajišťuje síťové připojení v systému Windows' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Co je „snap-in“ v rámci MMC?',
			options: [
				{ id: 'a', text: 'Rozšíření pro Edge' },
				{ id: 'b', text: 'Správní nástroj integrovaný do MMC' },
				{ id: 'c', text: 'Nástroj pro aktualizaci systému' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Jaký příkaz spustí MMC z příkazové řádky?',
			options: [
				{ id: 'a', text: 'console' },
				{ id: 'b', text: 'mmc' },
				{ id: 'c', text: 'adminconsole' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'Jaký je hlavní přínos vytváření vlastní MMC konzole?',
			options: [
				{ id: 'a', text: 'Lepší grafika systému' },
				{ id: 'b', text: 'Zrychlení herního výkonu' },
				{ id: 'c', text: 'Přístup k relevantním nástrojům z jednoho místa' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Jakým způsobem přidáš snap-in do MMC?',
			options: [
				{ id: 'a', text: 'Pomocí nastavení systému' },
				{ id: 'b', text: 'Přes „Přidat/odebrat modul snap-in“ v nabídce Soubor' },
				{ id: 'c', text: 'Spuštěním .exe souboru snap-inu' }
			],
			correct: 'b',
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
		<h1>🧠 Test – Microsoft Management Console (MMC)</h1>

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
