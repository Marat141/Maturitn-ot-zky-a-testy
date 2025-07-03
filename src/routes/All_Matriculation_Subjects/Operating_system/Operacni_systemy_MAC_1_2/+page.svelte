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
				<h1>Mac OS – část 1.2: GUI a spouštění aplikací</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2/Exam_Operacni_systemy_MAC_1_2"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🧭 Způsoby spouštění aplikací v macOS</h2>
				<ul>
					<li><strong>Dock:</strong> Kliknutí na ikonu ve spodní části obrazovky</li>
					<ul>
						<li><strong>Co to je:</strong> Řada ikon aplikací ve spodní (nebo boční) části obrazovky. Standardně tam Apple umisťuje ikony základních aplikací</li>
						<li><strong>Jak to funguje:</strong> Stačí kliknout na ikonu aplikace v Docku a ta se otevře</li>
						<li><strong>Tip:</strong> Ikony lze z Docku odebírat nebo do něj přidávat přetažením (drag & drop) aplikací z/na Dock</li>
					</ul>
					<li><strong>Launchpad:</strong> Přehled všech aplikací (ikona nebo F4)</li>
					<ul>
						<li><strong>Co to je:</strong> Rozhraní s ikonami všech nainstalovaných aplikací</li>
						<li><strong>Jak ho vyvolat:</strong></li>
						<ol>
							<li>Ikonou „Launchpad“ v Docku</li>
							<li>Na některých klávesnicích Apple bývá vyhrazená klávesa (F4) s ikonou Launchpadu</li>
						</ol>
						<li><strong>Jak spustit aplikaci:</strong> Kliknete na Launchpad, vyhledáte ikonu aplikace a tu otevřete kliknutím</li>
					</ul>
					<li><strong>Finder:</strong> Aplikace → dvojklik (zkratka: ⌘ + Shift + A)</li>
					<ul>
						<li><strong>Co to je:</strong> Základní aplikace macOS pro správu souborů</li>
						<li><strong>Jak aplikace spouštět:</strong></li>
						<ol>
							<li>Otevřít Finder(ikona „usmívající se tváře“ v Docku)</li>
							<li>V levé části okna vybrat Applications(Aplikace) nebo použít zkratku Command+Shift+A(pokud jste již v aktivním okně Finderu)</li>
							<li>V seznamu aplikací najít požadovanou aplikaci a dvojitým kliknutím ji spustit</li>
						</ol>
					</ul>
					<li><strong>Spotlight:</strong> ⌘ + mezerník → název aplikace → Enter</li>
					<ul>
						<li><strong>Co to je:</strong> Vestavěný vyhledávací nástroj macOS (lupa vpravo nahoře na liště)</li>
						<li><strong>Jak ho vyvolat:</strong></li>
						<ol>
							<li><strong>Zkratka:</strong> Command + mezerník (Space)</li>
							<li>Nebo kliknout na ikonu lupy v pravém horním rohu obrazovky</li>
						</ol>
						<li><strong>Spuštění aplikace:</strong></li>
						<ol>
							<li>Vyvolat Spotlight</li>
							<li>Začít psát název aplikace (např. „Safari“, „Mail“, „Notes“ atd.)</li>
							<li>Ve výsledcích vyhledávání stisknout Enter na zvolené aplikaci</li>
						</ol>
					</ul>
					<li><strong>Apple menu:</strong> Nedávné položky – rychlý přístup</li>
					<ul>
						<li>Zde se aplikace přímo nespouštějí, nicméně přes Apple menu > Nedávné položky (Recent Items)je možné rychle otevřít naposledy používané aplikace</li>
						<li>Také je zde „O tomto Macu“ (About This Mac) či „Nastavení systému“ (System Settings), ale ty jsou spíš pro informace a konfigurac</li>
					</ul>
					<li><strong>Lišta & zkratky:</strong> Např. Siri, Time Machine, vlastní zkratky</li>
					<ul>
						<li>Některé aplikace mají v macOS určité zkratky nebo ikony na liště (menu bar) nahoře na obrazovce</li>
						<ul>
							<li><strong>Time Machine:</strong> Může mít ikonu hodin vpravo na liště, odkud lze spouštět zálohování nebo otevřít rozhraní pro obnovu</li>
							<li><strong>Siri</strong> (pokud je zapnutá): Má ikonu napravo na liště, případně lze používat nastavenou klávesovou zkratku</li>
							<li><strong>FaceTime, Zprávy, Mail:</strong> Tyto aplikace běžně žádnou univerzální klávesovou zkratku k okamžitému spuštění nemají. Otevírají se z Docku, Launchpadu, Finderu či Spotlightu</li>
						</ul>
					</ul>
					<li>Většina vestavěných aplikací (např. Mail, Safari, atd.) nemá výchozí univerzální klávesovou zkratku pro spuštění. Pokud chcete, můžete si ale v Nastavení systému > Klávesnice > Zkratky vytvořit vlastní, která konkrétní aplikaci otevře</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔗 Odkazy na oficiální nápovědu</h2>
				<ul>
					<li>
						<a href="https://support.apple.com/cs-cz/guide/mac-help/mh35859/mac" target="_blank"
							>Dock</a
						>
					</li>
					<li>
						<a href="https://support.apple.com/cs-cz/guide/mac-help/mh35840/mac" target="_blank"
							>Launchpad</a
						>
					</li>
					<li>
						<a href="https://support.apple.com/cs-cz/guide/mac-help/mchlp2605/mac" target="_blank"
							>Finder</a
						>
					</li>
					<li>
						<a href="https://support.apple.com/cs-cz/guide/mac-help/mchlp1008/mac" target="_blank"
							>Spotlight</a
						>
					</li>
					<li>
						<a href="https://support.apple.com/cs-cz/guide/mac-help/mchlp1130/mac" target="_blank"
							>Apple menu</a
						>
					</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_MAC_1_2.pdf" class="ButtonExam" download>📄 Stáhnout PDF</a>
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
