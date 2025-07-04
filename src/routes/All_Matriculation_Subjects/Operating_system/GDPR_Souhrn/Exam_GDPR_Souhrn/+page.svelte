<script lang="ts">
	type ChoiceQuestion = {
		id: number;
		type: 'choice';
		text: string;
		options: string[];
		answer: number;
	};

	type FillQuestion = {
		id: number;
		type: 'fill';
		text: string;
		answer: string[];
	};

	type Question = ChoiceQuestion | FillQuestion;

	let questions: Question[] = $state([
		{
			id: 1,
			type: 'choice',
			text: 'Od kdy je účinné GDPR?',
			options: ['1. ledna 2016', '25. května 2018', '1. července 2020', '31. prosince 2017'],
			answer: 1
		},
		{
			id: 2,
			type: 'choice',
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
			type: 'choice',
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
			type: 'choice',
			text: 'Kdy je nutné hlásit únik dat Úřadu pro ochranu osobních údajů?',
			options: ['Ihned', 'Do 7 dnů', 'Do 24 hodin', 'Do 72 hodin'],
			answer: 3
		},
		{
			id: 5,
			type: 'fill',
			text: 'Vyjmenuj alespoň dvě zásady zpracování osobních údajů dle GDPR.',
			answer: [
				'zákonnost',
				'účelové omezení',
				'minimalizace údajů',
				'přesnost',
				'omezené uložení',
				'integrita a důvěrnost',
				'odpovědnost správce'
			]
		},
		{
			id: 6,
			type: 'fill',
			text: 'Jaké právo umožňuje jedinci žádat smazání jeho údajů?',
			answer: ['právo na výmaz', 'být zapomenut']
		},
		{
			id: 7,
			type: 'fill',
			text: 'Napiš mi něco o Zákonnosti, korektnosti a transaparentnosti zpracování osobních údajů.',
			answer: [
				'Osobní údaje musí být zpracovávány zákonným způsobem, férově a transparentně. Subjekt údajů musí být informován, kdo a proč údaje zpracovává'
			]
		},
		{
			id: 8,
			type: 'choice',
			text: 'Co je správně posaná definice Právo na informace?',
			options:[
				'Subjekt může žádat smazání údajů',
				'Subjekt může kdykoli vznést námitku proti zpracování na základě oprávněného zájmu správce nebo při přímém marketingu',
				'Subjekt musí být informován, kdo, jak a proč jeho údaje zpracovává. To zahrnuje např. dobu uchování, zdroj údajů a příjemce',
				'Subjekt má právo žádat jejich opravu nebo doplnění'
			],
			answer: 2
		}
		

	]);

	let userAnswers = $state<(number | string)[]>([]);
	let submitted = $state(false);

	let score = $derived.by(
		() =>
			questions.filter((q, i) => {
				const answer = userAnswers[i];
				if (q.type === 'choice') {
					return answer === q.answer;
				}
				if (q.type === 'fill' && typeof answer === 'string') {
					return q.answer.some((a: string) => answer.toLowerCase().includes(a.toLowerCase()));
				}
				return false;
			}).length
	);

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

			{#if question.type === 'choice'}
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
			{:else if question.type === 'fill'}
				<input
					type="text"
					bind:value={userAnswers[i]}
					placeholder="Doplň odpověď"
					disabled={submitted}
					class="fill-input"
				/>
			{/if}

			{#if submitted}
				<p class="result">
					{#if question.type === 'choice'}
						{userAnswers[i] === question.answer
							? '✅ Správně'
							: `❌ Špatně (Správně: ${question.options[question.answer]})`}
					{:else if question.type === 'fill'}
						{question.answer.some((a) =>
							typeof userAnswers[i] === 'string' && userAnswers[i].toLowerCase().includes(a.toLowerCase())
						)
							? '✅ Správně'
							: `❌ Špatně (Příklad správné odpovědi: ${question.answer[0]})`}
					{/if}
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
	margin: 40px auto;
	padding: 32px;
	background: #ffffff;
	border-radius: 12px;
	box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
	font-family: system-ui, sans-serif;
}

h1 {
	text-align: center;
	font-size: 2rem;
	margin-bottom: 2rem;
	color: #1f2937;
}

.question {
	margin-bottom: 2rem;
	padding: 1.5rem;
	border: 1px solid #e5e7eb;
	border-radius: 10px;
	background: #f9fafb;
	transition: background 0.3s;
}

.question:hover {
	background: #f3f4f6;
}

.option {
	display: block;
	margin: 6px 0 6px 1rem;
	cursor: pointer;
	color: #374151;
}

.option input {
	margin-right: 8px;
}

.fill-input {
	display: block;
	margin-top: 10px;
	padding: 10px 14px;
	width: 100%;
	max-width: 500px;
	border: 1px solid #d1d5db;
	border-radius: 8px;
	font-size: 1rem;
}

.fill-input:focus {
	outline: none;
	border-color: #3b82f6;
	box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.3);
}

.submit,
.GoBack {
	display: inline-block;
	margin-top: 1.5rem;
	padding: 12px 24px;
	background: #3b82f6;
	color: #ffffff;
	border: none;
	border-radius: 8px;
	font-size: 1rem;
	cursor: pointer;
	transition: background 0.2s ease;
}

.submit:hover,
.GoBack:hover {
	background: #2563eb;
}

.result {
	margin-top: 0.75rem;
	font-weight: 600;
	color: #1f2937;
}

.result:before {
	display: inline-block;
	margin-right: 6px;
}

h2 {
	text-align: center;
	font-size: 1.5rem;
	color: #111827;
	margin-top: 2rem;
}
</style>

