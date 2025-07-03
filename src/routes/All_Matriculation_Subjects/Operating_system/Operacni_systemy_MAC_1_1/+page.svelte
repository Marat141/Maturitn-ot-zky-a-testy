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
            level: 2,
            text: 'Linux DHCP',
            parent: 2,
            path: '/All_Matriculation_Subjects/Operating_system/LinuxOp_20_1_DHCP'
        },
        {
            id: 26,
            level: 2,
            text: 'Windows Server DHCP',
            parent: 2,
            path:  '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_Server_14_DHCP',       
        },
		{
			id: 27,
			level: 1,
			text: 'Opravné zkoušky',
			path: '/All_Matriculation_Subjects/Operating_system/Opravne-Zkousky-OS'
		},

        ]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Mac OS – část 1</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1/Exam_Operacni_systemy_MAC_1_1"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📅 Vývoj Mac OS</h2>
				<ul>
					<p>Operační systém Mac provází počítače Macintosh od společnosti Apple od jejich počátku v 80. letech. Je znám pro své <strong>grafické uživatelské rozhraní</strong>, které v době svého vzniku předběhlo konkurenci, a postupnou integraci s hardwarem Apple</p>
					<li><strong>System 1–6 (1984–1991):</strong> První GUI, ovládání myší, základní multitasking</li>
					<ul>
						<li><strong>System 1</strong> - První verze operačního systému pro původní Macintosh 128K. Přinesla revoluční grafické rozhraní ovládané myší v době, kdy bylo u konkurenčních počítačů běžné textové rozhraní</li>
						<li><strong>Pokročilé verze System 2–6:</strong> Byly postupně rozšiřovány o nové funkce, například virtuální paměť, kooperativní multitasking nebo podporu barev (Macintosh II)</li>
					</ul>
					<li><strong>System 7  (1991–1997):</strong> Zásadní upgrade, který přinesl true color (plnou barevnou hloubku), zlepšenou správu paměti a nově koncipovanou plochu, AppleTalk síťování, sdílení souborů</li>
					<li><strong>Mac OS 8  (1997)/9 (1999):</strong> Lepší výkon, 3D grafika, internetové funkce, příprava na OS X</li>
					<ul>
						<li><strong>Mac OS 8:</strong> Přinesl vylepšené uživatelské rozhraní a podstatně svižnější reakce systému</li>
						<li>Součástí byly technologie jako QuickDraw 3D a Open Transport pro síťovou komunikaci</li>
						<li><strong>Mac OS 9:</strong> Označovaný také jako “Classic” – zahrnuje pozdější éru “klasického” Mac OS</li>
						<li>Přinesl rozšířenou podporu pro internet (například iTools), lepší správu uživatelů a přípravu na přechod k dalšímu systému</li>
					</ul>
					<li><strong>Mac OS X (2001) – přechod na UNIXový základ:</strong> UNIX základ, jádro Mach, Přinesl Aqua uživatelské rozhraní s výraznou vizuální identitou, paměťová ochrana</li>
					<li><strong>Přejmenování na “OS X” a další verze (2012–2016):</strong> Yosemite, El Capitan, Sierra – integrace iCloud/iOS</li>
					<ul>
						<li>Systém se v marketingové komunikaci postupně přestal nazývat “Mac OS X” a Apple začal používat kratší “OS X”</li>
						<li>Každá z nich přinesla dílčí vylepšení, například integraci s iCloudem, lepší napojení na iOS a modernizaci designu</li>
					</ul>
					<li><strong>macOS (od 2016):</strong> Nové názvy (High Sierra → Ventura), podpora M1 čipů</li>
					<ul>
						<li>V těchto verzích Apple postupně přidal funkce jako tmavý režim (Dark Mode), nové bezpečnostní prvky, pokračující integraci iOS ekosystému a podporu vlastních Apple procesorů (M1 a novější).</li>
					</ul>
					<li><strong>Přechod na ARM a procesory Apple Silicon (od roku 2020):</strong> Apple začal nahrazovat procesory Intel vlastními čipy založenými na architektuře ARM (Apple Silicon, např. M1, M2), Rosetta 2, běh iOS aplikací</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧱 Architektury Maců</h2>
				<ul>
					<li><strong>Motorola 68k (1984–1998):</strong> První Macintoshe, System 1 → částečně Mac OS 8.1 (poslední kompatibilní verze pro některé 68k Macy)</li>
					<li><strong>PowerPC (1994–2006):</strong> System 7.1.2 → Mac OS 9; první verze Mac OS X (10.0–10.3, plus univerzální 10.4)</li>
					<li><strong>Intel (2006–2020):</strong> Od Mac OS X 10.4.4 (Tiger) univerzální, samostatně Intel-only od 10.6 (Snow Leopard) až do macOS 10.15 (Catalina)</li>
					<li><strong>Apple Silicon ARM (od 2020):</strong> macOS 11 Big Sur a novější (univerzální binárky pro Intel i ARM), s nativní podporou v Apple čipech řady M</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Příprava před instalací</h2>
				<ul>
					<li><strong>Důvody:</strong> zpomalení systému, pády aplikací, změna verze, prodej zařízení</li>
					<li><strong>Záloha:</strong> Time Machine (nejlepší), iCloud, Dropbox, ruční kopírování dat</li>
					<li><strong>Kontrola:</strong> kompatibilita, min. 20–35 GB místa, aktualizovaný firmware</li>
					<li><strong>Další:</strong> odhlásit iCloud, znát Apple ID, mít Mac připojený k napájení</li>
				</ul>
			</section>

			<section class="note">
				<h2>💽 Metody instalace macOS</h2>
				<ul>
					<li><strong>Recovery Mode:</strong> Cmd + R (Intel), podrž Power (Apple Silicon)</li>
					<li><strong>Internet Recovery:</strong> Cmd + Option + R – stáhne původní macOS</li>
					<li><strong>USB instalátor:</strong> createinstallmedia přes Terminál, min. 16 GB USB</li>
					<li><strong>Clean Install:</strong> smazání disku v Disk Utility → nová instalace</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Postup čisté instalace</h2>
				<ul>
					<li>Spustit Recovery nebo USB boot</li>
					<li>Otevřít Disk Utility, vybrat hlavní disk (např. Macintosh HD)</li>
					<li>Formát: <strong>APFS</strong>, potvrdit vymazání</li>
					<li>Poté vybrat „Reinstall macOS“</li>
					<li>Počkej na stažení a instalaci (20–60 min)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔧 Nastavení po instalaci</h2>
				<ul>
					<li><strong>Region, jazyk, Apple ID, migrace dat</strong> (Time Machine, externí disk, jiný Mac)</li>
					<li><strong>Vytvoření uživatelů, iCloud, FileVault, Firewall</strong></li>
					<li><strong>Doporučené:</strong> aktualizace systému, instalace softwaru, nastavení záloh</li>
				</ul>
			</section>

			<section class="note">
				<h2>💡 Tipy a klávesové zkratky</h2>
				<ul>
					<li><strong>Cmd + R:</strong> vestavěná Recovery</li>
					<li><strong>Cmd + Option + R:</strong> Internet Recovery</li>
					<li><strong>Apple Silicon:</strong> držet Power → nabídka volby disku</li>
					<li><strong>Zálohuj pravidelně!</strong> Time Machine může výrazně ušetřit čas i data</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_MAC_1_1.pdf" class="ButtonExam" download>📄 Stáhnout PDF</a>
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
		margin-top: 0;
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
