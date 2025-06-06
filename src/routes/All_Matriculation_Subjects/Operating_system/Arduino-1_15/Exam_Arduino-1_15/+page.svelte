<script lang="ts">
	type Question = {
		id: number;
		question: string;
		options: string[];
		correct: number;
		selected?: number;
	};

	let questions: Question[] = [
		{
			id: 1,
			question: 'Co se zobrazí na 7-segmentovém displeji při detekci pohybu (varianta 1)?',
			options: ['0000', '1111', '2222', '9999'],
			correct: 1
		},
		{
			id: 2,
			question: 'Který pin Arduina je použit pro výstup z PIR senzoru HC-SR501?',
			options: ['D2', 'A0', 'D5', 'D11'],
			correct: 2
		},
		{
			id: 3,
			question: 'Jak se jmenuje knihovna použitá pro práci s 7-segmentovým displejem?',
			options: ['SegmentLib', 'LedDisplay', 'SevSeg', 'SerialOut'],
			correct: 2
		},
		{
			id: 4,
			question: 'Co dělá funkce ISR_PIR() v programu?',
			options: [
				'Resetuje displej',
				'Vypíná senzor',
				'Nastaví proměnnou, že byl detekován pohyb',
				'Odešle signál do PC'
			],
			correct: 2
		},
		{
			id: 5,
			question: 'Co se zobrazuje ve variantě 2 programu?',
			options: [
				'Rychlost pohybu v m/s',
				'Počet detekovaných osob',
				'Počet sekund od posledního pohybu',
				'Teplota'
			],
			correct: 2
		}
	];

	let submitted = false;
	let correctCount = 0;

	function submit() {
		submitted = true;
		correctCount = questions.filter((q) => q.selected === q.correct).length;
	}
</script>

<main>
	<h1>Test: Arduino + PIR senzor HC-SR501 + 7-segmentový displej</h1>

	{#each questions as q, i}
		<section class="question">
			<h2>{i + 1}. {q.question}</h2>
			{#each q.options as option, j}
				<label class:selected={q.selected === j}>
					<input
						type="radio"
						name={'q' + q.id}
						value={j}
						on:change={() => (q.selected = j)}
						disabled={submitted}
					/>
					{option}
				</label>
			{/each}

			{#if submitted}
				<p class={q.selected === q.correct ? 'correct' : 'wrong'}>
					{q.selected === q.correct
						? '✅ Správně'
						: `❌ Špatně — správná odpověď: ${q.options[q.correct]}`}
				</p>
			{/if}
		</section>
	{/each}

	{#if !submitted}
		<button class="submit" on:click={submit}>Odeslat test</button>
	{:else}
		<p class="result">Výsledek: {correctCount} / {questions.length} správně</p>
	{/if}
</main>

<style>
	main {
		max-width: 800px;
		margin: 2rem auto;
		padding: 1rem;
		font-family: system-ui, sans-serif;
		color: #1f2937;
	}

	h1 {
		text-align: center;
		margin-bottom: 2rem;
	}

	.question {
		margin-bottom: 2rem;
		background: #f9f9f9;
		padding: 1rem;
		border-radius: 8px;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
	}

	h2 {
		font-size: 1.1rem;
		margin-bottom: 0.5rem;
	}

	label {
		display: block;
		margin: 0.5rem 0;
		cursor: pointer;
		padding: 0.3rem;
		border-radius: 4px;
		transition: background 0.2s;
	}

	label.selected {
		background-color: #dbeafe;
	}

	.correct {
		color: green;
		font-weight: bold;
	}

	.wrong {
		color: red;
		font-weight: bold;
	}

	.submit {
		display: block;
		margin: 2rem auto;
		padding: 0.5rem 1.5rem;
		font-size: 1rem;
		border: none;
		background-color: #2563eb;
		color: white;
		border-radius: 6px;
		cursor: pointer;
	}

	.result {
		text-align: center;
		font-size: 1.2rem;
		font-weight: bold;
		color: #111827;
		margin-top: 2rem;
	}
</style>
