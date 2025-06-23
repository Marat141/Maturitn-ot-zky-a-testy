<script lang="ts">
	import Navigation from '$lib/Components/Navigation.svelte';

	interface Heading{
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
				<h1>Windows – část 3: Příkazový řádek (CMD)</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3/Exam-Operacni_systemy_Win_3"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📟 Základy CMD</h2>
				<ul>
					<li><strong>CLI (Command Line Interface)</strong> v systému Windows je textové rozhraní, které umožňuje uživatelům zadávat příkazy přímo systému a tím provádět různé operace, jako je práce se soubory, správou systému, skriptováním a automatizací úloh</li>
					<li>Příkazový řádek (cmd.exe) je textové rozhraní pro zadávání příkazů</li>
					<li><strong>Interní příkazy:</strong> Příkazy zabudované přímo do příkazového shellu (např. <code>cd</code>, <code>dir</code>, <code>echo</code>)</li>
					<li><strong>Externí příkazy:</strong> Samostatné programy nebo nástroje, které jsou spouštěny prostřednictvím CLI (např. <code>ping</code>, <code>ipconfig</code>, <code>notepad</code>)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧾 Argumenty a volby (options)</h2>
				<ul>
					<li>Argumenty jsou hodnoty, které se přidávají za příkaz a určují, nad čím má příkaz pracovat</li>
					<li>Argumenty specifikují vstup (např. <code>copy zdroj cíl</code>)</li>
					<li>Options mění chování příkazu – např. <code>dir /w</code>, <code>ping /n 4</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>🔁 Historie a aliasy</h2>
				<ul>
					<li>Šipkami nahoru/dolů lze procházet předchozí příkazy</li>
					<li><code>doskey /history</code> zobrazí všechny příkazy</li>
					<li><code>doskey alias=prikaz</code> vytvoří alias (např. <code>doskey dirlist=dir /B</code>)</li>
				</ul>
			</section>

			<section class="note">
				<h2>📦 Proměnné a PATH</h2>
				<ul>
					<li><strong>Místní proměnné:</strong> <code>set PROM=hodnota</code> — platné pouze pro aktuální relaci CLI</li>
					<li><strong>Globální proměnné prostředí:</strong> např. <code>PATH</code>, <code>TEMP</code>, <code>USERNAME</code></li>
					<li><code>setx</code> uloží proměnnou trvale pro budoucí relace — <code>setx PROM "hodnota"</code></li>
					<li><code>echo %PROM%</code> — zobrazí obsah proměnné</li>
				</ul>
				<h3>🧭 Nastavení přes GUI:</h3>
				<ol>
					<li>Otevři <em>Vlastnosti systému</em> &rarr; <em>Pokročilé</em> &rarr; <em>Proměnné prostředí</em></li>
					<li>V sekci <strong>Systémové proměnné</strong> klikni na <code>Nová...</code></li>
					<li>Zadej jméno a hodnotu proměnné a potvrď</li>
				</ol>
			</section>

			<section class="note">
				<h2>🗑️ Odstranění proměnné</h2>
				<ul>
					<li><code>setx PROMENNA ""</code> — trvalé odstranění z prostředí</li>
					<li><code>set PROMENNA=</code> — odstranění pouze pro aktuální relaci</li>
				</ul>
			</section>

			<section class="note">
				<h2>📂 Proměnná PATH</h2>
				<ul>
					<li>PATH určuje, kde se hledají spustitelné soubory</li>
					<li><code>echo %PATH%</code> — vypíše obsah</li>
					<li><code>set PATH=%PATH%;C:\NovaCesta</code> — přidá novou složku</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔎 Interní a externí příkazy</h2>
				<ul>
					<li><strong>Interní:</strong> Příkazy, které jsou přímo zabudované do shellu (cmd.exe). Nevyžadují žádné externí programy pro jejich spuštění. Příklady:</li>
					<ul>
						<li><code>dir:</code> Zobrazí seznam souborů a složek</li>
						<li><code>cd:</code> Změní aktuální adresář</li>
						<li><code>copy:</code> Kopíruje soubory</li>
						<li><code>echo:</code> Zobrazuje zprávy nebo hodnoty proměnných</li>
						<li><code>set:</code> Správa proměnných</li>
					</ul>
					<li><strong>Externí:</strong> Externí příkazy jsou samostatné programy nebo nástroje, které nejsou přímo integrovány do příkazového řádku. Aby mohly být spuštěny, musí být v cestě systému nebo zadány s plnou cestou. Příklady:</li>
					<ul>
						<li><code>notepad:</code> Spouští aplikaci Poznámkový blok</li>
						<li><code>ping:</code> Testuje dosah síťových připojení</li>
						<li><code>ipconfig:</code> Zobrazuje konfiguraci sítě</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>📑 Aliasy</h2>
				<ul>
					<li>Aliasy jsou alternativní názvy pro příkazy, které můžete použít ke zkrácení dlouhých příkazů nebo vytvoření vlastních zkratek</li>
					<li>Alias pomocí <code>doskey</code>: <code>doskey dirlist=dir /B</code></li>
					<li>Zkrácení často používaných příkazů</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔣 Řídicí a speciální znaky v CMD</h2>
				<ul>
					<li><code>" "</code> — uvozovky pro cesty s mezerami (<code>cd "C:\Program Files"</code>)</li>
					<li><code>' '</code> — nemá speciální význam (jen znak)</li>
					<li><code>%</code> — přístup k proměnným (<code>%USERNAME%</code>, <code>%1</code> v dávkových souborech)</li>
					<li><code>/</code> — přepínač (např. <code>dir /w</code>)</li>
					<li><code>\</code> — oddělovač složek (<code>C:\Windows</code>), <code>\\</code> pro síťové cesty</li>
					<li><code>|</code> — pipe: výstup → vstup (<code>dir | find "txt"</code>)</li>
					<li><code>&gt;</code>, <code>&gt;&gt;</code> — přesměrování výstupu (<code>echo text &gt; soubor.txt</code>)</li>
					<li><code>&lt;</code> — přesměrování vstupu (<code>sort &lt; soubor.txt</code>)</li>
					<li><code>&</code> — více příkazů na řádce (<code>echo A & echo B</code>)</li>
					<li><code>&&</code> — druhý příkaz jen při úspěchu prvního</li>
					<li><code>||</code> — druhý příkaz při chybě prvního</li>
					<li><code>^</code> — escape znak (<code>echo Toto je ^|</code>)</li>
					<li><code>:</code> — štítek v dávkových souborech (<code>:start</code>)</li>
					<li><code>?</code> — zástupný znak pro jeden znak (<code>soubor?.txt</code>)</li>
					<li><code>*</code> — zástupný znak pro více znaků (<code>*.txt</code>)</li>
					<li><code>@</code> — potlačení výpisu příkazu (<code>@echo off</code>)</li>
				</ul>
			</section>


			<a href="/PDF/Operacni_systemy_Win_3.pdf" class="ButtonExam" download>
				📄 Stáhnout PDF
			</a>
		</div>
	</div>
</main>

<style>
	/* stejné styly jako v předchozím kódu */
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
