<script lang="ts">
	type QuestionChoice = {
		id: number;
		type: 'choice';
		question: string;
		options: string[];
		answer: number;
	};

	type QuestionInput = {
		id: number;
		type: 'input';
		question: string;
		answer: string;
	};

	type QuestionMulti = {
		id: number;
		type: 'multi';
		question: string;
		options: string[];
		answers: number[];
	};

	type Question = QuestionChoice | QuestionInput | QuestionMulti;

	const originalQuestions: Question[] = [
		{
			id: 1,
			type: 'choice',
			question: 'Na jakém portu běží HTTP?',
			options: ['443', '80', '21'],
			answer: 1
		},
		{
			id: 2,
			type: 'input',
			question: 'Jaký protokol slouží pro zabezpečený vzdálený přístup na zařízení?',
			answer: 'SSH'
		},
		{
			id: 3,
			type: 'multi',
			question: 'Které protokoly slouží pro sdílení souborů?',
			options: ['SMB', 'FTP', 'NFS', 'DNS'],
			answers: [0, 2]
		},
		{
			id: 4,
			type: 'input',
			question: 'Co je port 873 a k čemu slouží?',
			answer: 'rsync'
		},
		{
			id: 5,
			type: 'choice',
			question: 'Který protokol se používá pro přenos e-mailů mezi servery?',
			options: ['SMTP', 'IMAP', 'POP3'],
			answer: 0
		},
		{
			id: 6,
			type: 'input',
			question: 'Jaký protokol se používá pro přenos webových stránek? A jaký je jeho port?',
			answer: 'HTTP, port 80'
		},
		{
			id: 7,
			type: 'multi',
			question: 'Které z následujících protokolů jsou šifrované?',
			options: ['HTTPS', 'FTP', 'SSH', 'Telnet'],
			answers: [0, 2]
		},
		{
			id: 8,
			type: 'input',
			question: 'Jaký protokol se používá pro přenos souborů mezi počítači v síti?',
			answer: 'FTP'
		},
		{
			id: 9,
			type: 'input',
			question:
				'Jaký je hlavní rozdíl mezi IMAP a POP3? (Tuto otázku budu číst a ohodnotím ji sám)',
			answer:
				'IMAP umožňuje synchronizaci e-mailů mezi více zařízeními, zatímco POP3 stahuje e-maily na jedno zařízení.'
		},
		{
			id: 10,
			type: 'choice',
			question: 'Který protokol používá port 3389 pro vzdálený přístup k desktopům?',
			options: ['SSH', 'RDP', 'VNC'],
			answer: 1
		},
		{
			id: 11,
			type: 'input',
			question: 'Na co slouží protokol NTP?',
			answer: 'synchronizace času'
		},
		{
			id: 12,
			type: 'multi',
			question: 'Které protokoly používají port 22?',
			options: ['SSH', 'SFTP', 'Telnet', 'FTP'],
			answers: [0, 1]
		},
		{
			id: 13,
			type: 'input',
			question: 'Jaký protokol překládá doménová jména na IP adresy?',
			answer: 'DNS'
		},
		{
			id: 14,
			type: 'choice',
			question: 'Který protokol se běžně používá pro IoT zařízení?',
			options: ['FTP', 'MQTT', 'SMTP'],
			answer: 1
		},
		{
			id: 15,
			type: 'multi',
			question: 'Které protokoly slouží k přenosu e-mailů?',
			options: ['SMTP', 'IMAP', 'POP3', 'DNS'],
			answers: [0, 1, 2]
		},
		{
			id: 16,
			type: 'input',
			question: 'Jaký je zabezpečený protokol pro přenos souborů, který využívá SSL/TLS?',
			answer: 'FTPS'
		},
		{
			id: 17,
			type: 'choice',
			question: 'Jaký port používá protokol SNMP?',
			options: ['23', '161', '445'],
			answer: 1
		},
		{
			id: 18,
			type: 'input',
			question: 'Jaký protokol je nástupcem Telnetu a poskytuje šifrovaný přístup?',
			answer: 'SSH'
		},
		{
			id: 19,
			type: 'multi',
			question: 'Které protokoly se používají ke sdílení souborů v síti?',
			options: ['SMB', 'NFS', 'HTTP', 'IMAP'],
			answers: [0, 1]
		},
		{
			id: 20,
			type: 'input',
			question: 'Protokol pro vzdálený šifrovaný přístup a správu serverů (běží na portu 22):',
			answer: 'SSH'
		},
		{
			id: 21,
			type: 'input',
			question: 'Jaký protokol slouží pro překlad doménových jmen na IP adresy?',
			answer: 'DNS'
		},
		{
			id: 22,
			type: 'input',
			question: 'Protokol pro synchronizaci času mezi zařízeními v síti (port 123):',
			answer: 'NTP'
		},
		{
			id: 23,
			type: 'input',
			question: 'Jaký je protokol, který umožňuje sdílet a spravovat soubory přes HTTP/HTTPS?',
			answer: 'WebDav'
		},
		{
			id: 24,
			type: 'input',
			question: 'Protokol, který umožňuje připojit vzdálený disk jako lokální (port 3260):',
			answer: 'iSCSI'
		},
		{
			id: 25,
			type: 'input',
			question: 'Na jakém portu běží SMTP?',
			answer: '25'
		},
		{
			id: 26,
			type: 'input',
			question: 'Jaký protokol používá port 445 a je běžný ve Windows pro sdílení souborů?',
			answer: 'SMB'
		},
		{
			id: 27,
			type: 'choice',
			question: 'Co dělá protokol IMAP?',
			options: [
				'Umožňuje příjem e-mailů a jejich správu na serveru',
				'Odesílá e-maily mezi servery',
				'Synchronizuje soubory mezi zařízeními'
			],
			answer: 0
		},
		{
			id: 28,
			type: 'choice',
			question: 'Co umožňuje protokol DHCP?',
			options: [
				'Překlad doménových jmen',
				'Automatické přidělování IP adres klientům v síti',
				'Sdílení tiskáren'
			],
			answer: 1
		}
	];

	let questions: Question[] = shuffle([...originalQuestions]);

	let currentIndex = $state(0);
	let selected: Record<number, number | string> = $state({});
	let multiSelected: Record<number, number[]> = $state({});
	let showResults = $state(false);
	let score = $state(0);

	function shuffle<T>(array: T[]): T[] {
		for (let i = array.length - 1; i > 0; i--) {
			const j = Math.floor(Math.random() * (i + 1));
			[array[i], array[j]] = [array[j], array[i]];
		}
		return array;
	}

	function next() {
		if (currentIndex < questions.length - 1) currentIndex++;
	}

	function prev() {
		if (currentIndex > 0) currentIndex--;
	}

	function GoHome() {
		window.location.href = '/All_Matriculation_Subjects/Operating_system/Aplikacni-protokoly';
	}

	function evaluate() {
		let correct = 0;

		for (let q of questions) {
			const user = selected[q.id];

			if (q.type === 'choice') {
				if (user === q.answer) correct++;
			} else if (q.type === 'input') {
				if ((user as string)?.trim().toLowerCase() === q.answer.trim().toLowerCase()) correct++;
			} else if (q.type === 'multi') {
				const userAnswers = multiSelected[q.id] ?? [];
				const correctAnswers = q.answers;
				const isSameLength = userAnswers.length === correctAnswers.length;
				const isSameContent = userAnswers.every((a) => correctAnswers.includes(a));
				if (isSameLength && isSameContent) correct++;
			}
		}

		score = correct;
		showResults = true;
	}

	function toggleMulti(questionId: number, index: number) {
		let selectedIndexes = multiSelected[questionId] ?? [];
		if (selectedIndexes.includes(index)) {
			multiSelected[questionId] = selectedIndexes.filter((i) => i !== index);
		} else {
			multiSelected[questionId] = [...selectedIndexes, index];
		}
	}
</script>

<main>
	{#if !showResults}
		<h1>Test z aplikačních protokolů</h1>
		<p>Otázka {currentIndex + 1}: {questions[currentIndex].question}</p>

		<!-- Otázky -->
		{#if questions[currentIndex].type === 'choice'}
			{#each (questions[currentIndex] as QuestionChoice).options as option, i}
				<label>
					<input
						type="radio"
						name="q{questions[currentIndex].id}"
						checked={selected[questions[currentIndex].id] === i}
						onchange={() => (selected[questions[currentIndex].id] = i)}
					/>
					{option}
				</label><br />
			{/each}
		{:else if questions[currentIndex].type === 'multi'}
			{#each (questions[currentIndex] as QuestionMulti).options as option, i}
				<label>
					<input
						type="checkbox"
						checked={(multiSelected[questions[currentIndex].id] ?? []).includes(i)}
						onchange={() => toggleMulti(questions[currentIndex].id, i)}
					/>
					{option}
				</label><br />
			{/each}
		{:else if questions[currentIndex].type === 'input'}
			{@const inputQ = questions[currentIndex] as QuestionInput}
			<input type="text" bind:value={selected[inputQ.id]} placeholder="Napiš odpověď" />
		{/if}

		<!-- Navigace -->
		<div class="nav-container">
			<div class="nav-left">
				<button onclick={GoHome}>Domů</button>
				<button onclick={prev} disabled={currentIndex === 0}>Zpět</button>
				{#if currentIndex < questions.length - 1}
					<button onclick={next}>Další</button>
				{/if}
			</div>

			<div class="nav-right">
				<button
					class="evaluate-button"
					disabled={currentIndex !== questions.length - 1}
					onclick={evaluate}
				>
					Vyhodnotit test
				</button>
			</div>
		</div>
	{:else}
		<h1>Výsledky testu</h1>
		<p>Správně: {score} z {questions.length}</p>

		{#each questions as q}
			<div class="result-block">
				<h3>{q.question}</h3>
				{#if q.type === 'choice'}
					<p><strong>Tvoje odpověď:</strong> {q.options[selected[q.id] as number] ?? '–'}</p>
					<p><strong>Správná odpověď:</strong> {q.options[q.answer]}</p>
				{:else if q.type === 'input'}
					<p><strong>Tvoje odpověď:</strong> {selected[q.id] ?? '–'}</p>
					<p><strong>Správná odpověď:</strong> {q.answer}</p>
				{:else if q.type === 'multi'}
					<p>
						<strong>Tvoje odpovědi:</strong>
						{#each multiSelected[q.id] ?? [] as idx, i}
							{q.options[idx]}{i < (multiSelected[q.id]?.length ?? 1) - 1 ? ', ' : ''}
						{/each}
					</p>
					<p>
						<strong>Správné odpovědi:</strong>
						{#each q.answers as a, i}
							{q.options[a]}{i < q.answers.length - 1 ? ', ' : ''}
						{/each}
					</p>
				{/if}
				<hr />
			</div>
		{/each}

		<button onclick={GoHome}>Zpět na úvod</button>
	{/if}
</main>

<style>
	/* Stylování exam komponenty (Svelte 5 scoped) */

	main {
		font-family: system-ui, sans-serif;
		background: #ffffff;
		border-radius: 12px;
		box-shadow: 0 6px 24px rgba(0, 0, 0, 0.06);
		padding: 2rem;
		max-width: 800px;
		margin: 2rem auto;
		color: #2c3e50;
	}

	/* Nadpis */
	h1 {
		font-size: 2rem;
		text-align: center;
		margin-bottom: 1.5rem;
	}

	/* Otázka */
	p {
		font-size: 1.1rem;
		margin: 1rem 0;
		line-height: 1.6;
	}

	/* Odpovědi */
	label {
		display: block;
		padding: 0.6rem 1rem;
		margin: 0.3rem 0;
		background: #f4f6f8;
		border-radius: 6px;
		cursor: pointer;
		transition: background 0.2s ease;
		font-size: 1rem;
	}

	label:hover {
		background: #eaf3fb;
	}

	input[type='radio'],
	input[type='checkbox'] {
		margin-right: 0.6rem;
		vertical-align: middle;
		transform: scale(1.2);
	}

	input[type='text'] {
		width: 100%;
		padding: 0.7rem;
		font-size: 1rem;
		border: 1px solid #ccc;
		border-radius: 6px;
		margin-top: 0.5rem;
		transition: border-color 0.2s;
	}

	input[type='text']:focus {
		border-color: #0077cc;
		outline: none;
	}

	/* Navigační tlačítka */
	.nav-container {
		display: flex;
		justify-content: space-between;
		flex-wrap: wrap;
		margin-top: 2rem;
		gap: 1rem;
	}

	.nav-left,
	.nav-right {
		display: flex;
		gap: 0.5rem;
	}

	button {
		background-color: #0077cc;
		color: white;
		padding: 0.65rem 1.2rem;
		border: none;
		border-radius: 6px;
		cursor: pointer;
		font-size: 1rem;
		transition: background 0.2s ease;
	}

	button:hover:not(:disabled) {
		background-color: #005fa3;
	}

	button:disabled {
		background-color: #ccc;
		cursor: not-allowed;
	}

	/* Výsledkový blok */
	.result-block {
		background: #f1f6fa;
		padding: 1rem;
		border-left: 5px solid #0077cc;
		margin-top: 1rem;
		border-radius: 6px;
	}

	.result-block h3 {
		margin: 0 0 0.5rem 0;
	}

	hr {
		border: none;
		border-top: 1px solid #dcdcdc;
		margin: 1rem 0;
	}
</style>
