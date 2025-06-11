<!-- file: Exam_GDPR_Technicka_opatreni.svelte -->
<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Co je hlavním účelem nastavení NTFS práv v kontextu GDPR?',
			options: [
				'Omezení velikosti souborů',
				'Zajištění šifrování dat',
				'Omezení přístupu jen na oprávněné osoby',
				'Zrychlení systému'
			],
			answer: 2
		},
		{
			id: 2,
			text: 'Jak pomáhají diskové kvóty naplnit požadavky GDPR?',
			options: [
				'Šifrují osobní údaje',
				'Zabraňují přístupu neautorizovaných uživatelů',
				'Minimalizují zbytečné uchovávání dat',
				'Zajišťují přesnost údajů'
			],
			answer: 2
		},
		{
			id: 3,
			text: 'Proč je šifrování dat důležité z pohledu GDPR?',
			options: [
				'Zvyšuje výkon serveru',
				'Chrání data při úniku nebo zcizení',
				'Umožňuje anonymizaci údajů',
				'Pomáhá s aktualizací systému'
			],
			answer: 1
		},
		{
			id: 4,
			text: 'Jaká technická opatření pomáhají zabránit neoprávněnému kopírování dat?',
			options: [
				'Zálohování dat',
				'Nastavení diskových kvót',
				'Omezení periferních zařízení (např. USB porty)',
				'Aktualizace systému'
			],
			answer: 2
		},
		{
			id: 5,
			text: 'Které opatření slouží k obnově dat po havárii systému?',
			options: ['Šifrování', 'Komprimace', 'Záloha OS', 'Pseudonymizace'],
			answer: 2
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
	<h1>🧪 Test: GDPR Technická opatření</h1>

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
		margin-top: 16px;
	}
</style>
