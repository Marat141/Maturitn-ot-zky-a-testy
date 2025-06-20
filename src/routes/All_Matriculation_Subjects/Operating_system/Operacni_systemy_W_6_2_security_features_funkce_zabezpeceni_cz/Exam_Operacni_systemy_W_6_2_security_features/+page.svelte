<script lang="ts">
	type ChoiceOption = { id: string; text: string };

	type Question =
		| {
				id: number;
				type: 'choice';
				text: string;
				options: ChoiceOption[];
				correct: string;
				answer: string | null;
		  }
		| {
				id: number;
				type: 'text';
				text: string;
				correct: string;
				answer: string;
		  };

	let questions = $state<Question[]>([
		{
			id: 1,
			type: 'choice',
			text: 'Co je hlavním účelem funkce Windows Defender Antivirus?',
			options: [
				{ id: 'a', text: 'Optimalizace výkonu systému' },
				{ id: 'b', text: 'Zálohování dat' },
				{ id: 'c', text: 'Ochrana proti virům a malwaru' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 2,
			type: 'choice',
			text: 'Jaká technologie umožňuje šifrování celého disku ve Windows?',
			options: [
				{ id: 'a', text: 'Firewall' },
				{ id: 'b', text: 'BitLocker' },
				{ id: 'c', text: 'Defender Guard' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 3,
			type: 'choice',
			text: 'K čemu slouží funkce Secure Boot?',
			options: [
				{ id: 'a', text: 'Zrychluje start systému' },
				{ id: 'b', text: 'Zabraňuje spuštění neautorizovaného softwaru při startu' },
				{ id: 'c', text: 'Zálohuje boot sektor' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			type: 'choice',
			text: 'Jaká funkce umožňuje biometrické přihlašování?',
			options: [
				{ id: 'a', text: 'Firewall' },
				{ id: 'b', text: 'Windows Hello' },
				{ id: 'c', text: 'Credential Guard' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 5,
			type: 'choice',
			text: 'Jak funguje Windows Sandbox?',
			options: [
				{ id: 'a', text: 'Virtuální desktop pro bezpečné testování' },
				{ id: 'b', text: 'Zálohovací systém' },
				{ id: 'c', text: 'Skener hrozeb' }
			],
			correct: 'a',
			answer: null as string | null
		},
		{
			id: 6,
			type: 'text',
			text: 'Jaký nástroj slouží k centrální správě zásad zabezpečení ve firemním prostředí?',
			correct: 'Group Policy',
			answer: ''
		},
		{
			id: 7,
			type: 'text',
			text: 'Jak se jmenuje funkce, která odděluje firemní a osobní data na zařízení?',
			correct: 'Windows Information Protection',
			answer: ''
		},
		{
			id: 8,
			type: 'text',
			text: 'Jaká funkce chrání LSA procesy a přihlašovací údaje?',
			correct: 'Credential Guard',
			answer: ''
		},
		{
			id: 9,
			type: 'text',
			text: 'Jak se nazývá ochranná technologie, která filtruje nebezpečné weby a stahování v Edge?',
			correct: 'SmartScreen',
			answer: ''
		},
		{
			id: 10,
			type: 'text',
			text: 'Která funkce systému Windows pomáhá detekovat a reagovat na pokročilé hrozby na koncových zařízeních?',
			correct: 'Microsoft Defender for Endpoint',
			answer: ''
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
		<h1>🧠 Test – Windows Funkce zabezpečení</h1>

		{#each questions as q}
			<section class="question">
				<h2>{q.text}</h2>

				{#if q.type === 'choice'}
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
				{:else if q.type === 'text'}
					<input type="text" bind:value={q.answer} placeholder="Doplň správnou odpověď" />
				{/if}

				{#if showResults}
					{#if q.type === 'choice'}
						<p class={q.answer === q.correct ? 'correct' : 'wrong'}>
							{q.answer === q.correct
								? '✅ Správně!'
								: `❌ Špatně. Správná odpověď je: ${q.options.find((o) => o.id === q.correct)?.text}`}
						</p>
					{:else if q.type === 'text'}
						<p
							class={q.answer?.trim().toLowerCase() === q.correct.toLowerCase()
								? 'correct'
								: 'wrong'}
						>
							{q.answer?.trim().toLowerCase() === q.correct.toLowerCase()
								? '✅ Správně!'
								: `❌ Špatně. Správná odpověď je: ${q.correct}`}
						</p>
					{/if}
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
	background: #fefefe;
	border-radius: 16px;
	box-shadow: 0 12px 28px rgba(0, 0, 0, 0.12);
	font-family: system-ui, sans-serif;
}

h1 {
	color: #1d4ed8;
	margin-bottom: 32px;
	text-align: center;
	font-size: 2rem;
}

.question {
	margin-bottom: 40px;
	padding-bottom: 20px;
	border-bottom: 1px solid #e5e7eb;
}

.question h2 {
	margin-bottom: 16px;
	font-size: 1.2rem;
	color: #111827;
}

label {
	display: block;
	padding: 10px 14px;
	border: 1px solid #d1d5db;
	border-radius: 8px;
	margin-bottom: 8px;
	cursor: pointer;
	transition: all 0.3s ease;
	background-color: #f9fafb;
}

label:hover {
	background-color: #f3f4f6;
}

label.selected {
	background-color: #e0f2fe;
	border-color: #3b82f6;
	font-weight: 500;
}

input[type='radio'] {
	margin-right: 8px;
	accent-color: #2563eb;
}

input[type='text'] {
	width: 100%;
	padding: 10px 12px;
	border: 1px solid #d1d5db;
	border-radius: 6px;
	font-size: 1rem;
	transition: border-color 0.2s ease;
	background-color: #f9fafb;
}

input[type='text']:focus {
	border-color: #2563eb;
	outline: none;
	background-color: #fff;
}

.correct {
	color: #059669;
	font-weight: 500;
	margin-top: 10px;
}

.wrong {
	color: #dc2626;
	font-weight: 500;
	margin-top: 10px;
}

.controls {
	display: flex;
	justify-content: center;
	gap: 16px;
	margin-top: 40px;
	flex-wrap: wrap;
}

.ButtonExam {
	background-color: #2563eb;
	color: white;
	padding: 12px 20px;
	border-radius: 8px;
	font-weight: 600;
	border: none;
	cursor: pointer;
	transition: background-color 0.2s ease;
	font-size: 1rem;
	box-shadow: 0 4px 10px rgba(37, 99, 235, 0.2);
}

.ButtonExam:hover {
	background-color: #1e3a8a;
}

@media (max-width: 600px) {
	.exam-container {
		padding: 20px;
	}

	h1 {
		font-size: 1.5rem;
	}

	.controls {
		flex-direction: column;
		gap: 12px;
	}
}

</style>
