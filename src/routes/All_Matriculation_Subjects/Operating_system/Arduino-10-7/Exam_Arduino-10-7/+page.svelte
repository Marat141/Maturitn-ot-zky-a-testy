<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Jaký typ displeje se v projektu používá?',
			options: ['Společná anoda', 'Společná katoda', 'OLED', 'LCD'],
			answer: 1
		},
		{
			id: 2,
			text: 'Jaký pin je použit pro DATA z DHT11?',
			options: ['D3', 'D5', 'A4', 'D8'],
			answer: 1
		},
		{
			id: 3,
			text: 'Která knihovna je zodpovědná za zobrazení čísel na displeji?',
			options: ['LiquidCrystal', 'DisplayLib', 'SevSeg', 'Wire'],
			answer: 2
		},
		{
			id: 4,
			text: 'Jaké napětí potřebují segmenty displeje?',
			options: ['5V', '3.3V', '1.8–2.2V', '0.7V'],
			answer: 2
		}
	]);

	let userAnswers = $state<number[]>([]);
	let submitted = $state(false);
	let score = $derived.by(() => {
		return questions.filter((q, i) => userAnswers[i] === q.answer).length;
	});

	function submit() {
		submitted = true;
	}

    function GoBack() {
        window.history.back();
    }
</script>

<main class="exam">
	<h1>🧪 Test: Arduino 7segment + DHT11</h1>

	{#each questions as question, i}
		<div class="question">
			<p><strong>{i + 1}. {question.text}</strong></p>
			{#each question.options as option, j}
				<label class="option">
					<input
						type="radio"
						name={'question-' + i}
						value={j}
						checked={userAnswers[i] === j}
						disabled={submitted}
						onchange={() => (userAnswers[i] = j)}
					/>
					{option}
				</label>
			{/each}

			{#if submitted}
				<p class="result">
					{userAnswers[i] === question.answer
						? 'Správně'
						: `Špatně (Správná: ${question.options[question.answer]})`}
				</p>
			{/if}
		</div>
	{/each}

	{#if !submitted}
		<button class="submit" onclick={submit}>Odeslat test</button>
	{:else}
		<h2>📊 Výsledek: {score} / {questions.length}</h2>
	{/if}
    <button class="GoBack" onclick="{GoBack}">Zpět</button>
</main>

<style>
	.exam {
		max-width: 800px;
		margin: 20px auto;
		padding: 32px;
		font-family: system-ui, sans-serif;
		background: #fff;
		border-radius: 12px;
		box-shadow: 0 0 20px rgba(0, 0, 0, 0.1);
	}

	.question {
		margin-bottom: 1.5rem;
		padding: 1rem;
		border: 1px solid #ccc;
		border-radius: 8px;
	}

	.option {
		display: block;
		margin-left: 1rem;
		margin-top: 4px;
	}

	.submit {
		background: #2563eb;
		color: white;
		border: none;
		padding: 10px 20px;
		border-radius: 6px;
		font-size: 1rem;
		cursor: pointer;
	}
	.submit:hover {
		background: #1d4ed8;
	}

	.result {
		margin-top: 0.5rem;
		font-weight: bold;
	}

    .GoBack {
        background: #163cf9;
        color: white;
        border: none;
        padding: 10px 20px;
        border-radius: 6px;
        font-size: 1rem;
        cursor: pointer;
    }
</style>
