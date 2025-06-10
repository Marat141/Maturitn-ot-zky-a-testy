<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Od kdy je účinné GDPR?',
			options: ['1. ledna 2016', '25. května 2018', '1. července 2020', '31. prosince 2017'],
			answer: 1
		},
		{
			id: 2,
			text: 'Jaký je maximální postih za porušení GDPR?',
			options: [
				'10 mil. EUR nebo 2 % obratu',
				'1 mil. EUR nebo 1 % obratu',
				'20 mil. EUR nebo 4 % obratu',
				'500 tis. EUR nebo 5 % obratu'
			],
			answer: 2
		},
		{
			id: 3,
			text: 'Co znamená pseudonymizace?',
			options: [
				'Odstranění všech osobních údajů',
				'Náhrada identifikátorů jinými hodnotami',
				'Šifrování dat',
				'Změna formátu údajů'
			],
			answer: 1
		},
		{
			id: 4,
			text: 'Kdy je nutné hlásit únik dat Úřadu pro ochranu osobních údajů?',
			options: ['Ihned', 'Do 7 dnů', 'Do 24 hodin', 'Do 72 hodin'],
			answer: 3
		}
	]);

	let userAnswers = $state<number[]>([]);
	let submitted = $state(false);
	let score = $derived.by(() => questions.filter((q, i) => userAnswers[i] === q.answer).length);

	function submit() {
		submitted = true;
	}

	function goBack() {
		window.history.back();
	}
</script>

<main class="exam">
	<h1>🧪 Test: GDPR Souhrn</h1>

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
						? '✅ Správně'
						: `❌ Špatně (Správně: ${question.options[question.answer]})`}
				</p>
			{/if}
		</div>
	{/each}

	{#if !submitted}
		<button class="submit" onclick={submit}>Odeslat test</button>
	{:else}
		<h2>📊 Výsledek: {score} / {questions.length}</h2>
	{/if}
	<button class="GoBack" onclick={goBack}>Zpět</button>
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
