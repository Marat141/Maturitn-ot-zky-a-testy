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
			id: 28,
			level: 2,
			text: 'Operační systémy Windows 6.1 Správce zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
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
				<h1>Windows – část 6.1: Správce zařízení</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager/Exam-Operacni_systemy_W10_6_1_device_manager"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🔧 Ovladače zařízení</h2>
				<ul>
					<li>
						Ovladač zařízení (device driver) je softwarová komponenta umožňující operačnímu systému
						Windows komunikovat s fyzickým hardwarem.
					</li>
					<li>
						Funguje jako prostředník mezi OS a zařízením – překládá příkazy operačního systému na
						nízkoúrovňové instrukce, kterým zařízení rozumí (např. WRITE SECTOR).
					</li>
					<li>
						Bez správného ovladače není zařízení funkční, nebo může fungovat špatně či omezeně.
					</li>
					<li>
						<strong>Funkce:</strong>
						<ul>
							<li>
								<strong>Komunikace mezi OS a Hardwarem:</strong> Ovladače umožňují operačnímu systému
								přistupovat k funkcím a datům zařízení bez nutnosti znát detaily jeho fungování.
							</li>
							<li>
								<strong>Překlad Příkazů:</strong> Převádějí vysokou úroveň příkazů z operačního systému
								na nízkoúrovňové instrukce, které zařízení rozumí.
							</li>
							<li>
								<strong>Správa Zdrojů:</strong> Pomáhají při správě systémových zdrojů, jako je paměť,
								procesorový čas a přerušení, které zařízení využívá.
							</li>
							<li>
								<strong>Zajištění Kompatibility:</strong> Umožňují, aby starší zařízení fungovala s novějšími
								verzemi operačního systému a naopak
							</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧩 Příklady zařízení a ovladačů</h2>
				<ul>
					<li>
						<strong>Přenos Dat na Pevný disk:</strong>
						<ol>
							<li>Aplikace požaduje zápis dat pomocí API (např. WriteFile).</li>
							<li>OS předá požadavek ovladači disku.</li>
							<li>Ovladač překládá příkaz na nízkoúrovňové instrukce typu WRITE SECTOR.</li>
							<li>Diskový řadič vykonává instrukce a zapisuje data na pevný disk.</li>
							<li>Diskový řadič potvrzuje operaci ovladači.</li>
							<li>Ovladač disku informuje operační systém o úspěšném zápisu.</li>
							<li>Operační systém informuje aplikaci o dokončení operace</li>
						</ol>
					</li>
					<li>
						<strong>Síťová karta / Síťový Adaptér:</strong>
						<ol>
							<li>Aplikace odešle data pomocí socketu.</li>
							<li>Ovladač vytvoří síťové pakety (např. TCP/IP), přidá hlavičky.</li>
							<li>Přes fyzické médium (Wi-Fi, Ethernet) dojde k přenosu.</li>
							<li>Řadič potvrdí přenos ovladači.</li>
						</ol>
					</li>
					<li>
						<strong>Grafická karta:</strong>
						<ol>
							<li>Aplikace (např. hra) kreslí obraz.</li>
							<li>Ovladač převádí instrukce na specifické GPU příkazy.</li>
							<li>GPU zpracuje a vykreslí obraz, informuje zpět ovladač a OS.</li>
						</ol>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔗 API (Application Programming Interface)</h2>
				<ul>
					<li>API je rozhraní, které umožňuje komunikaci mezi různými softwarovými částmi – například mezi aplikací a operačním systémem, nebo mezi dvěma programy.</li>
					<li><strong>Představ si API jako:</strong>
						<ul>
							<li>Jídelní lístek v restauraci – ty si vybereš jídlo (požadavek), číšník (API) předá objednávku kuchyni (programu) a přinese ti jídlo (odpověď).</li>
							<li>Most mezi tím, co chceš, a tím, co to skutečně vykoná.</li>
						</ul>
					</li>

					<li><strong>Příklad ve Windows:</strong>
						<ul>
							<li>Když program chce zapsat data na disk, nekomunikuje přímo s hardwarem, ale použije API operačního systému (např. WriteFile).</li>
							<li>OS pak předá příkaz ovladači disku, který zapíše data.</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧪 Možné Nízkouúrovňové Instrukce</h2>
				<ul>
					<li>
						<strong>WRITE SECTOR:</strong> Instrukce pro zápis dat do konkrétního sektoru na disku.
					</li>
					<li>
						<strong>READ SECTOR:</strong> Instrukce pro čtení dat z konkrétního sektoru na disku.
					</li>
					<li>
						<strong>SEND PACKET:</strong> Instrukce pro odeslání síťového paketu prostřednictvím síťového
						adaptéru.
					</li>
					<li>
						<strong>RECEIVE PACKET:</strong> Instrukce pro příjem síťového paketu prostřednictvím síťového
						adaptéru
					</li>
					<li>
						<strong>DRAW PIXEL:</strong> Instrukce pro vykreslení jednotlivého pixelu na obrazovku pomocí
						grafické karty.
					</li>
					<li><strong>LOAD TEXTURE:</strong> Instrukce pro načtení textury do paměti GPU.</li>
					<li><strong>EXECUTE SHADER:</strong> Instrukce pro spuštění shader programu na GPU.</li>
				</ul>
			</section>

			<section class="note">
				<h2>📋 Správce zařízení</h2>
				<ul>
					<li>
						Správce zařízení je nástroj ve Windows, který zobrazuje a spravuje všechna zařízení a
						ovladače v systému.
					</li>
					<li>
						Je součástí Microsoft Management Console (MMC) – poskytuje centralizovaný a organizovaný
						přehled o hardwaru nainstalovaném v počítači.
					</li>
					<li>
						<strong>Zobrazuje informace jako:</strong>
						<ul>
							<li>Typ zařízení</li>
							<li>Stav zařízení</li>
							<li>Výrobce a specifické vlastnosti</li>
							<li>Informace o ovladači zařízení</li>
						</ul>
					</li>
					<li><strong>Umožňuje:</strong>
						<ul>
							<li>Konfigurovat hardware</li>
							<li>Aktualizovat, zakazovat nebo odinstalovat ovladače</li>
							<li>Řešit konflikty mezi zařízeními</li>
						</ul>
					</li>
					<li>
						<strong>Spuštění:</strong>
						<ul>
							<li><code>devmgmt.msc</code> (Win + R)</li>
							<li>Pravý klik na "Tento počítač" → Spravovat → Správce zařízení</li>
							<li>Win + X → Správce zařízení</li>
						</ul>
					</li>
					<li>
						Lze jej chápat jako základní přehled všech zařízení, kterým Windows rozumí – veškerý
						hardware lze spravovat z tohoto místa.
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Funkce Správce zařízení</h2>
				<ul>
					<li>Aktualizace ovladačů (vyhledání online nebo ruční výběr).</li>
					<li>Přeinstalace nebo vrácení ovladače na starší verzi.</li>
					<li>Dočasné zakázání nebo úplné odinstalování ovladače.</li>
					<li>Zobrazení skrytých zařízení, jako jsou systémové ovladače.</li>
					<li>Identifikace problémů – zařízení s chybou je označeno žlutým trojúhelníkem.</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧪 Driver Verifier Manager</h2>
				<ul>
					<li>
						Pokročilý nástroj pro testování ovladačů – slouží k detekci nestability nebo chyb.
					</li>
					<li>
						Spuštění pomocí <code>verifier</code> v dialogu Spustit nebo přes příkazový řádek jako administrátor.
					</li>
					<li>
						Možnosti výběru:
						<ul>
							<li>Automaticky vybrat nepodepsané ovladače.</li>
							<li>Ovladače určené pro starší verze Windows.</li>
							<li>Všechny ovladače v systému.</li>
						</ul>
					</li>
					<li>Po nastavení vyžaduje restart a začne sledovat chování ovladačů v reálném čase.</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_W10_6_1_device_manager.pdf" class="ButtonExam" download>
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
