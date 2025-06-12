<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Co je hlavním účelem nabídky Start ve Windows?',
			options: [
				{ id: 'a', text: 'Spouštění BIOSu' },
				{ id: 'b', text: 'Přístup k aplikacím a nastavením' },
				{ id: 'c', text: 'Otevírání webových stránek' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Jaká je funkce jádra operačního systému?',
			options: [
				{ id: 'a', text: 'Zajišťuje komunikaci mezi hardwarem a softwarem' },
				{ id: 'b', text: 'Zobrazuje ikony na ploše' },
				{ id: 'c', text: 'Odesílá e-maily' }
			],
			correct: 'a',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Jak lze otevřít Příkazový řádek (CMD)?',
			options: [
				{ id: 'a', text: 'Win + R → cmd' },
				{ id: 'b', text: 'Ctrl + Alt + Del' },
				{ id: 'c', text: 'F12' }
			],
			correct: 'a',
			answer: null as string | null
		},
        {
			id: 4,
			text: 'K čemu slouží nástroj BitLocker?',
			options: [
				{ id: 'a', text: 'Zrychlení počítače' },
				{ id: 'b', text: 'Šifrování disků a ochrana dat' },
				{ id: 'c', text: 'Aktualizace systému' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Co ukládá Windows Hello při rozpoznání obličeje?',
			options: [
				{ id: 'a', text: 'Fotografii obličeje' },
				{ id: 'b', text: 'Šifrovaný biometrický profil' },
				{ id: 'c', text: 'Heslo uživatele' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 6,
			text: 'Jak se chrání data u přihlášení pomocí PINu?',
			options: [
				{ id: 'a', text: 'PIN je uložen v cloudu' },
				{ id: 'b', text: 'PIN je propojen s konkrétním zařízením a uložen lokálně' },
				{ id: 'c', text: 'PIN se odesílá Microsoftu' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 7,
			text: 'Který nástroj chrání před phishingem a malwarem?',
			options: [
				{ id: 'a', text: 'Windows Paint' },
				{ id: 'b', text: 'SmartScreen' },
				{ id: 'c', text: 'Windows Update' }
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
