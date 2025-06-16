<script lang="ts">
	let questions = $state([
		{
			id: 1,
			text: 'Jaký je výchozí port pro FTP server?',
			options: [
				{ id: 'a', text: '20' },
				{ id: 'b', text: '21' },
				{ id: 'c', text: '22' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 2,
			text: 'Který nástroj použijeme k pokročilé správě firewallu ve Windows?',
			options: [
				{ id: 'a', text: 'Správce zařízení' },
				{ id: 'b', text: 'Windows Defender Firewall s pokročilým zabezpečením' },
				{ id: 'c', text: 'Správce aktualizací' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 3,
			text: 'Jaký příkaz v PowerShellu vytvoří nové firewall pravidlo?',
			options: [
				{ id: 'a', text: 'Add-FirewallRule' },
				{ id: 'b', text: 'New-NetFirewallRule' },
				{ id: 'c', text: 'Enable-Firewall' }
			],
			correct: 'b',
			answer: null as string | null
		},
		{
			id: 4,
			text: 'Na který port musíme změnit nastavení, pokud FTP poběží na portu 2121?',
			options: [
				{ id: 'a', text: 'Na portu firewallu i v FileZilla Serveru' },
				{ id: 'b', text: 'Pouze v systému BIOS' },
				{ id: 'c', text: 'Pouze v klientském počítači' }
			],
			correct: 'a',
			answer: null as string | null
		},
		{
			id: 5,
			text: 'Co znamená parametr -Direction Inbound v PowerShellu?',
			options: [
				{ id: 'a', text: 'Odchozí provoz' },
				{ id: 'b', text: 'Příchozí provoz' },
				{ id: 'c', text: 'Blokování pravidel' }
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
		<h1>🧠 Test – Windows Firewall (9.1)</h1>

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
