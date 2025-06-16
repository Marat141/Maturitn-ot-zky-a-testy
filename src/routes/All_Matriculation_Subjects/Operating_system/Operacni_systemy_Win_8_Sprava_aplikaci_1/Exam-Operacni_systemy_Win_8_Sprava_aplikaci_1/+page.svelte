<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Co je hlavním účelem AppLockeru?',
			options: [
				{ id: 'a', text: 'Omezení přístupu na internet' },
				{ id: 'b', text: 'Řízení, které aplikace se mohou spouštět' },
				{ id: 'c', text: 'Zrychlení systému' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Na základě čeho lze v AppLockeru tvořit pravidla?',
			options: [
				{ id: 'a', text: 'Velikosti aplikace' },
				{ id: 'b', text: 'Digitálního podpisu, cesty nebo hash kódu' },
				{ id: 'c', text: 'Barevné schématu ikony' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Která služba musí být spuštěná, aby AppLocker fungoval?',
			options: [
				{ id: 'a', text: 'Windows Update' },
				{ id: 'b', text: 'Application Identity (AppIDSvc)' },
				{ id: 'c', text: 'Print Spooler' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'Jaký příkaz aktualizuje skupinové politiky?',
			options: [
				{ id: 'a', text: 'gpedit /refresh' },
				{ id: 'b', text: 'secpol /sync' },
				{ id: 'c', text: 'gpupdate /force' }
			],
			correct: 'c',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Jaký režim doporučuje Microsoft pro testování pravidel AppLocker?',
			options: [
				{ id: 'a', text: 'Monitor Mode' },
				{ id: 'b', text: 'Audit Mode' },
				{ id: 'c', text: 'Silent Mode' }
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
		<h1>🧠 Test – AppLocker</h1>

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
