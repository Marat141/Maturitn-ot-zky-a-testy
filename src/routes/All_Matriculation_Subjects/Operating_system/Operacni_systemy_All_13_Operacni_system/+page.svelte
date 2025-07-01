<script lang="ts">
	import Navigation from '$lib/Components/Navigation.svelte';

	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
		path?: string;
	}

	let headings: Heading[] = $state([
		{ id: 1, level: 1, text: 'Úvod do OS', path: '/All_Matriculation_Subjects/Operating_system' },
		{ id: 2, level: 1, text: 'IT3B PDF soubory' },
		{
			id: 3,
			level: 2,
			text: 'Aplikační protokoly',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Aplikacni-protokoly'
		},
		{
			id: 4,
			level: 2,
			text: 'GDPR souhrn',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'
		},
		{
			id: 5,
			level: 2,
			text: 'GDPR Technická opatření',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni'
		},
		{
			id: 6,
			level: 2,
			text: 'Operační systémy základní součásti operačního systému',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system'
		},
		{
			id: 7,
			level: 2,
			text: 'Mac OS část 1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1'
		},
		{
			id: 8,
			level: 2,
			text: 'Mac OS část 1.2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2'
		},
		{
			id: 9,
			level: 2,
			text: 'Mac OS část 1.4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail'
		},
		{
			id: 10,
			level: 2,
			text: 'Mac OS část 1.7',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal'
		},
		{
			id: 11,
			level: 2,
			text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz'
		},
		{
			id: 12,
			level: 2,
			text: 'Operační systémy Windows Ovladače zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
		},
		{
			id: 13,
			level: 2,
			text: 'Operační systémy Win_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1'
		},
		{
			id: 14,
			level: 2,
			text: 'Operační systémy Win_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2'
		},
		{
			id: 15,
			level: 2,
			text: 'Operační systémy Win_3',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3'
		},
		{
			id: 16,
			level: 2,
			text: 'Operační systémy Win_4_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2'
		},
		{
			id: 17,
			level: 2,
			text: 'Operační systémy Win_4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4'
		},
		{
			id: 18,
			level: 2,
			text: 'Operační systémy Win_5_MMC',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC'
		},
		{
			id: 19,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_1_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz'
		},
		{
			id: 20,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_3_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz'
		},
		{
			id: 21,
			level: 2,
			text: 'Operační systémy Win_7_Windows_Server',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server'
		},
		{
			id: 22,
			level: 2,
			text: 'Operační systémy Win_8_Sprava_aplikaci_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1'
		},
		{
			id: 23,
			level: 2,
			text: 'Operační systémy Win_9_1_Firewall',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall'
		},
		{
			id: 24,
			level: 2,
			text: 'Souborove systemy 1_Windows',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows'
		},
		{
			id: 25,
			level: 1,
			text: 'Opravné zkoušky',
			path: '/All_Matriculation_Subjects/Operating_system/Opravne-Zkousky-OS'
		}
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Operační systémy: Základní součásti</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system/Exam_Operacni_systemy_All_13_Operacni_system"
					class="ButtonExam">Napsat si test</a
				>
			</div>

			<section class="note">
				<h2>🔑 Klíčové pojmy</h2>
				<ul>
					<li>
						<strong>Proces:</strong> Běžící instance programu. Má vlastní paměť, identifikátor (PID)
						a může obsahovat jedno nebo více vláken.
					</li>
					<li>
						<strong>Vlákno (Thread):</strong> Nejmenší jednotka provádění uvnitř procesu. Sdílí paměť
						s ostatními vlákny téhož procesu.
					</li>
					<li>
						<strong>Správa paměti:</strong> Řídí přidělování a uvolňování paměti pro aplikace a jádro
						OS.
					</li>
					<li>
						<strong>Souborový systém:</strong> Umožňuje ukládání a organizaci dat na disku (např. NTFS,
						ext4, ZFS).
					</li>
					<li>
						<strong>I/O systémy:</strong> Komunikace mezi OS a zařízeními – pomocí ovladačů a plánovače
						vstupně-výstupních operací.
					</li>
					<li>
						<strong>Plánování procesů:</strong> Určuje, který proces běží kdy, podle algoritmů jako Round-Robin,
						FIFO atd.
					</li>
					<li>
						<strong>Synchronizace:</strong> Zajišťuje bezpečný přístup více procesů/vláken ke sdíleným
						zdrojům (pomocí mutexů, semaforů...)
					</li>
					<li>
						<strong>Deadlock:</strong> Situace, kdy procesy navzájem čekají na uvolnění zdrojů a systém
						se zacyklí.
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>👨‍💻 Významné osobnosti vývoje OS</h2>
				<ul>
					<li>
						<strong>Ken Thompson:</strong> Spolutvůrce Unixu. Citát:
						<em>"You can't trust code you did not totally create yourself..."</em>
					</li>
					<li>
						<strong>Dennis Ritchie:</strong> Spoluautor Unixu a jazyka C.
						<em>"UNIX is simple, but requires genius to understand its simplicity."</em>
					</li>
					<li>
						<strong>Bill Gates:</strong> Zakladatel Microsoftu.
						<em>"Your most unhappy customers are your greatest source of learning."</em>
					</li>
					<li><strong>Paul Allen:</strong> Spoluzakladatel Microsoftu.</li>
					<li>
						<strong>Andrew S. Tanenbaum:</strong> Autor knihy <em>Modern Operating Systems</em>,
						tvůrce systému MINIX.
					</li>
					<li>
						<strong>Linus Torvalds:</strong> Autor Linuxu.
						<em>"Talk is cheap. Show me the code."</em>
					</li>
					<li><strong>Steve Jobs:</strong> Apple, macOS a GUI revoluce.</li>
				</ul>
			</section>

			<section class="note">
				<h2>🖥️ Přehled operačních systémů</h2>
				<ul>
					<li>
						<strong>UNIX:</strong> Víceuživatelský, multitaskingový systém z 60. let. Základ pro Linux,
						macOS atd.
					</li>
					<li><strong>MS-DOS:</strong> Textový OS Microsoftu, rozšířený v 80. letech.</li>
					<li>
						<strong>Windows:</strong> GUI systém od Microsoftu – dominantní na osobních počítačích.
					</li>
					<li>
						<strong>Linux:</strong> Open-source alternativa, inspirována UNIXem. Běžný na serverech a
						nově i desktopu.
					</li>
					<li><strong>macOS:</strong> Od Apple. UNIXový základ + moderní grafické prostředí.</li>
				</ul>
			</section>

			<section class="note">
				<h2>🎯 Cíl studia OS</h2>
				<p>
					Získat porozumění základním principům fungování operačních systémů (procesy, paměť, I/O,
					souborové systémy atd.) a dovednosti nutné k jejich efektivní správě a využívání.
				</p>
			</section>

			<section class="note">
				<h2>⚙️ Procesy vs. vlákna</h2>
				<ul>
					<li>
						<strong>Proces:</strong> Izolovaná jednotka s vlastní pamětí. Komunikace mezi procesy je
						složitější (pipes, sockets...)
					</li>
					<li>
						<strong>Vlákno:</strong> Běží v rámci procesu, sdílí paměť. Komunikace je rychlá, ale méně
						bezpečná.
					</li>
					<li><strong>Vytvoření vlákna je levnější</strong> než spuštění procesu.</li>
				</ul>

				<details class="details-block">
					<summary>📄 Příklad – vícevláknové stahování v Pythonu</summary>
					<div class="details-content">
						<pre><code
								>import threading
			import requests

			def download(url, filename):
				r = requests.get(url)
				with open(filename, 'wb') as f:
					f.write(r.content)

			urls = [("http://example.com/f1.zip", "f1.zip")]
			threads = [threading.Thread(target=download, args=(u, f)) for u, f in urls]

			for t in threads: t.start()
			for t in threads: t.join()</code
							></pre>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🧠 Správa paměti</h2>
				<ul>
					<li>
						<strong>Virtuální paměť:</strong> Procesy vidí větší paměť, než ve skutečnosti je. Podporováno
						stránkováním a swapem.
					</li>
					<li>
						<strong>Windows:</strong> pagefile.sys, RAMMap, <code>tasklist</code>,
						<code>resmon</code>
					</li>
					<li>
						<strong>Linux:</strong> <code>free -h</code>, <code>vmstat</code>, <code>htop</code>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📂 Souborové systémy</h2>
				<ul>
					<li>
						<strong>Windows:</strong> NTFS (šifrování, komprese), exFAT (externí disky), FAT32 (kompatibilita)
					</li>
					<li><strong>Linux:</strong> ext4 (standard), XFS (výkon), Btrfs (snapshoty, RAID)</li>
					<li><strong>Unix:</strong> UFS, FFS, ZFS (komprese, kontrolní součty)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ I/O subsystém</h2>
				<ul>
					<li><strong>Windows:</strong> I/O Manager, Plug and Play, power management, async I/O</li>
					<li><strong>Linux:</strong> VFS (abstrakce FS), aio_read, ovladače, buffer cache</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔒 Synchronizace</h2>
				<ul>
					<li><strong>Mutex:</strong> Zajišťuje exkluzivní přístup ke zdroji</li>
					<li><strong>Semafor:</strong> Umožňuje více přístupů (omezený počet)</li>
					<li><strong>Podmínkové proměnné:</strong> Vlákna čekají na určitou podmínku</li>
					<li><strong>Read/Write Lock:</strong> Mnoho čtenářů, jen jeden zapisovač</li>
				</ul>
			</section>
			<a href="/PDF/Operacni_systemy_All_13_Operacni_system.pdf" class="ButtonExam" download>
					📄 Stáhnout PDF
			</a>
		</div>
	</div>
</main>

<style>
	.layout {
		display: flex;
		gap: 32px;
		background-color: #f9fafb;
		min-height: 100vh;
	}

	.content {
		flex: 1;
		padding: 32px;
		background: #ffffff;
		border-radius: 16px;
		box-shadow: 0 12px 32px rgba(0, 0, 0, 0.08);
		font-family: 'Inter', system-ui, sans-serif;
		color: #1f2937;
		transition: all 0.3s ease;
	}

	.content h1,
	.content h2 {
		color: #2563eb;
	}

	.header-with-button {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 24px;
	}

	.note {
		background-color: #f3f4f6;
		border-left: 4px solid #9ca3af;
		padding: 16px 24px;
		border-radius: 8px;
		margin-bottom: 24px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
		transition: background-color 0.3s ease;
	}

	.note:hover {
		background-color: #e5e7eb;
	}

	.content ul {
		padding-left: 24px;
		list-style-type: disc;
		margin-bottom: 24px;
	}

	.content li {
		margin-bottom: 10px;
		line-height: 1.6;
	}

	.content a {
		display: inline-block;
		color: #2563eb;
		background-color: #f0f9ff;
		padding: 8px 12px;
		margin: 4px 0;
		border-radius: 6px;
		text-decoration: none;
		transition:
			background-color 0.25s,
			color 0.25s;
		font-size: 15px;
	}

	.content a:hover {
		background-color: #dbeafe;
		color: #1d4ed8;
	}
	.ButtonExam {
		display: inline-block;
		color: #ffffff;
		background-color: #2563eb;
		padding: 8px 16px;
		border-radius: 6px;
		text-decoration: none;
		font-weight: 500;
		transition: background-color 0.3s ease;
		font-size: 15px;
	}

	.ButtonExam:hover {
		background-color: #1d4ed8;
	}

	.details-block summary {
		cursor: pointer;
		font-weight: 600;
		color: #2563eb;
		margin-top: 12px;
		margin-bottom: 8px;
		user-select: none;
		transition: color 0.2s ease;
	}

	.details-block[open] summary {
		color: #1d4ed8;
	}

	.details-content {
		margin-left: 20px;
		padding: 10px 0 0 8px;
		border-left: 2px solid #cbd5e1;
		font-size: 15px;
	}

	.details-content h3 {
		margin-top: 12px;
		margin-bottom: 6px;
		color: #111827;
		font-size: 15px;
	}

	.details-content ul {
		list-style: disc;
		padding-left: 24px;
		margin-bottom: 8px;
	}

	.details-content li {
		margin-bottom: 6px;
	}

	@media (max-width: 768px) {
		.layout {
			flex-direction: column;
			gap: 24px;
		}

		.content {
			padding: 24px;
		}
	}
</style>
