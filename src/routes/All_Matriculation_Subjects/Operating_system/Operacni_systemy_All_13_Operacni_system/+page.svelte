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
			text: 'Arduino 1-15-1 pohyb přerušení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-1_15'
		},
		{
			id: 5,
			level: 2,
			text: 'Arduino 10 7 segment 4 digits s DHT11',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-10-7'
		},
		{
			id: 6,
			level: 2,
			text: 'GDPR souhrn',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'
		},
		{
			id: 7,
			level: 2,
			text: 'GDPR Technická opatření',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni'
		},
		{
			id: 8,
			level: 2,
			text: 'Operační systémy základní součásti operačního systému',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system'
		},
		{
			id: 9,
			level: 2,
			text: 'Mac OS část 1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1'
		},
		{
			id: 10,
			level: 2,
			text: 'Mac OS část 1.2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2'
		},
		{
			id: 11,
			level: 2,
			text: 'Mac OS část 1.4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail'
		},
		{
			id: 12,
			level: 2,
			text: 'Mac OS část 1.7',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal'
		},
		{
			id: 13,
			level: 2,
			text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz'
		},
		{
			id: 14,
			level: 2,
			text: 'Operační systémy Windows Ovladače zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
		},
		{
			id: 15,
			level: 2,
			text: 'Operační systémy Win_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1'
		},
		{
			id: 16,
			level: 2,
			text: 'Operační systémy Win_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2'
		},
		{
			id: 17,
			level: 2,
			text: 'Operační systémy Win_3',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3'
		},
		{
			id: 18,
			level: 2,
			text: 'Operační systémy Win_4_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2'
		},
		{
			id: 19,
			level: 2,
			text: 'Operační systémy Win_4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4'
		},
		{
			id: 20,
			level: 2,
			text: 'Operační systémy Win_5_MMC',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC'
		},
		{
			id: 21,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_1_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz'
		},
		{
			id: 22,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_3_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz'
		},
		{
			id: 23,
			level: 2,
			text: 'Operační systémy Win_7_Windows_Server',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server'
		},
		{
			id: 24,
			level: 2,
			text: 'Operační systémy Win_8_Sprava_aplikaci_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1'
		},
		{
			id: 25,
			level: 2,
			text: 'Operační systémy Win_9_1_Firewall',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall'
		},
		{
			id: 26,
			level: 2,
			text: 'Souborove systemy 1_Windows',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows'
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
					<li><strong>Proces:</strong> Program v běhu, zahrnuje aktuální stav programu a data</li>
					<li><strong>Vlákno (Thread):</strong> Menší jednotka procesu, může běžet paralelně</li>
					<li><strong>Správa paměti:</strong> Alokace a dealokace paměti operačním systémem</li>
					<li><strong>Souborový systém:</strong> Struktura pro ukládání a organizaci souborů</li>
					<li><strong>I/O systémy:</strong> Komunikace mezi počítačem a periferiemi</li>
					<li><strong>Plánování procesů:</strong> Určuje pořadí vykonávání procesů</li>
					<li><strong>Synchronizace:</strong> Řízení přístupu ke sdíleným prostředkům</li>
					<li>
						<strong>Deadlock:</strong> Blokace, kdy se procesy vzájemně čekají na uvolnění zdrojů
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>👨‍💻 Významné osobnosti vývoje OS</h2>
				<ul>
					<li>Ken Thompson – „You can't trust code…“</li>
					<li>Dennis Ritchie – „UNIX is basically a simple…“</li>
					<li>Bill Gates, Paul Allen, Andrew S. Tanenbaum</li>
					<li>Linus Torvalds – „Talk is cheap…“</li>
					<li>Steve Jobs</li>
				</ul>
			</section>

			<section class="note">
				<h2>🖥️ Operační systémy</h2>
				<ul>
					<li>UNIX – první víceuživatelský, multitaskingový systém</li>
					<li>MS-DOS – dominantní v 80. letech</li>
					<li>Windows – standardní OS pro osobní počítače</li>
					<li>Linux – open-source alternativa k UNIXu</li>
					<li>Mac OS – intuitivní GUI, od Apple</li>
				</ul>
			</section>

			<section class="note">
				<h2>🎯 Cíle studia OS</h2>
				<p>
					Pochopení základních funkcí a mechanismů OS pro efektivní využití a správu výpočetních
					systémů.
				</p>
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
