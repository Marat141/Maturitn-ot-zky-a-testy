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
					<summary>📄 Podrobnější zápisky</summary>
					<div class="details-content">
						<h2>⚙️ Proces x vlákno</h2>
						<h3>Procesy:</h3>
						<ul>
							<li><strong>Izolace:</strong> Každý proces běží ve svém vlastním paměťovém prostoru, což znamená, že procesy jsou izolované od sebe navzájem. To zvyšuje bezpečnost a stabilitu, protože chyby v jednom procesu neovlivní ostatní procesy.</li>
							<li><strong>Přepínání kontextu:</strong> Přepínání mezi procesy (context switching) je náročnější na zdroje, protože zahrnuje změnu celého paměťového prostoru a registrů procesoru.</li>
							<li><strong>Komunikace:</strong> Procesy komunikují mezi sebou pomocí mechanismů jako jsou roury (pipes), fronty zpráv (message queues) nebo sdílená paměť (shared memory), což může být složitější a pomalejší než komunikace mezi vlákny</li>
							<li><strong>Vytváření:</strong>  Vytvoření nového procesu je náročnější na zdroje, protože zahrnuje alokaci nového paměťového prostoru a inicializaci všech potřebných struktur.</li>
						</ul>
						<h3>Vlákna:</h3>
						<ul>
							<li><strong>Sdílení paměti:</strong> Vlákna v rámci jednoho procesu sdílejí stejný paměťový prostor, což umožňuje rychlejší a jednodušší komunikaci mezi vlákny. To však také znamená, že chyby v jednom vlákně mohou ovlivnit ostatní vlákna v rámci stejného procesu.</li>
							<li><strong>Přepínání kontextu:</strong> Přepínání mezi vlákny je méně náročné na zdroje než přepínání mezi procesy, protože vlákna sdílejí stejný paměťový prostor a mnoho systémových prostředků.</li>
							<li><strong>Komunikace:</strong> Vlákna mohou snadno komunikovat a synchronizovat se pomocí mechanismů jako jsou mutexy, semafory a podmínkové proměnné.</li>
							<li><strong>Vytváření:</strong> Vytvoření nového vlákna je méně náročné na zdroje než vytvoření nového procesu, protože vlákna sdílejí mnoho systémových prostředků.</li>

						</ul>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🎞️ Procesy</h2>
				<p>V <strong>MS Windows</strong> je správa procesů zajišťována několika nástroji a mechanismy:</p>
				<ul>
					<li><strong>Správce úloh:</strong> : Tento nástroj umožňuje uživatelům sledovat a spravovat běžící procesy. Můžete jej spustit pomocí klávesové zkratky Ctrl+Shift+Esc nebo přes kontextovou nabídku hlavního panelu. Správce úloh zobrazuje využití procesoru, paměti, disku a sítě jednotlivými procesy</li>
					<li><strong>PowerShell:</strong> : Pomocí PowerShellu lze spravovat procesy pomocí příkazů jako <em>GetProcess,Stop-Process</em> a <em>Start-Process</em>. Tyto příkazy umožňují získávat informace o procesech, zastavovat je a spouštět nové procesy</li>
					<li><strong>Process Explorer:</strong> Tento nástroj od Sysinternals poskytuje detailní informace o procesech a umožňuje sledovat problémy s knihovnami DLL nebo úniky paměti</li>
				</ul>
				<p>V <strong>Linuxu</strong> je správa procesů prováděna pomocí různých příkazů a nástrojů:</p>
				<ul>
					<li><strong>ps:</strong> Tento příkaz zobrazuje seznam běžících procesů. Můžete jej použít s různými přepínači, jako je <em>ps -e</em> pro zobrazení všech procesů nebo <em>ps -u</em> pro zobrazení procesů konkrétního uživatele</li>
					<li><strong>top:</strong> Tento interaktivní nástroj zobrazuje aktuální stav systému, včetně běžících procesů, využití CPU a paměti. Umožňuje také ukončovat procesy</li>
					<li><strong>htop:</strong> Vylepšená verze příkazu <em>top</em>, která poskytuje barevné rozhraní a další funkce pro správu procesů </li>
					<li><strong>nice a renice:</strong> Tyto příkazy slouží k nastavení a změně priority procesů. Příkaz <em>nice</em> spouští proces s upravenou prioritou, zatímco <em>renice</em> mění prioritu již běžícího procesu</li>
					<li><strong>kill:</strong> Tento příkaz slouží k zasílání signálů procesům, například k jejich ukončení. Příkaz <em>kill -9 PID</em> ukončí proces s daným PID</li>
				</ul>
				<p>V <strong>Unixu</strong> jsou procesy spravovány podobně jako v Linuxu, protože Linux je odvozen od Unixu</p>
			</section>

			<section class="note">
				<h2>🧠 Správa paměti</h2>
				<ul>
					<li>
						<strong>Virtuální paměť:</strong> Windows používá virtuální paměť, která umožňuje programům používat více paměti, než je fyzicky dostupné. Podporováno stránkováním a swapem.
					</li>
					<li>
						Správa paměti v <strong>MS Windows</strong> zahrnuje několik klíčových mechanismů:
						<ul>
							<li>Virtuální paměť</li>
							<li>Správce paměti</li>
							<li>Správce úloh</li>
							<li>Optimalizace paměti</li>
						</ul>
					</li>
					<li>
						<strong>Linux:</strong>
						<ul>
							<li>Virtuální paměť</li>
							<li>Alokace paměti</li>
							<li>Správa paměti jádra</li>
							<li>Ochrana paměti</li>
						</ul>
					</li>
				</ul>
				<details class="details-block">
					<summary>📄 Podrobnější zápisky</summary>
					<div class="details-content">
						<h2>Správa paměti v OS</h2>
						<p><strong>MS Windows</strong></p>
						<p>Správa paměti v MS Windows zahrnuje několik klíčových mechanismů:</p>
						<ul>
							<li><strong>Virtuální paměť:</strong>  Windows používá virtuální paměť, která umožňuje programům používat více paměti, než je fyzicky dostupné. Toho je dosaženo pomocí stránkovacího souboru (page file) na disku.</li>
							<li><strong>Správce paměti:</strong> Windows má správce paměti, který přiděluje a uvolňuje paměť pro procesy a aplikace. Tento správce také monitoruje využití paměti a optimalizuje její rozdělení.</li>
							<li><strong>Správce úloh:</strong> Nástroj, který umožňuje uživatelům sledovat a spravovat využití paměti jednotlivými procesy. Uživatelé mohou ukončovat procesy, které spotřebovávají příliš mnoho paměti.</li>
							<li><strong>Optimalizace paměti:</strong> Windows poskytuje nástroje jako RAMMap a CleanMem, které pomáhají optimalizovat využití paměti a uvolňovat zbytečně obsazenou paměť</li>
						</ul>
						<p><strong>Linux</strong></p>
						<ul>
							<li><strong>Virtuální paměť:</strong> Linux používá virtuální paměť, která umožňuje procesům používat více paměti, než je fyzicky dostupné. To je dosaženo pomocí stránkování a swapování</li>
							<li><strong>Alokace paměti:</strong> Linux poskytuje dvě hlavní metody pro alokaci paměti: statickou a dynamickou. Dynamická alokace umožňuje procesům získat paměť podle potřeby</li>
							<li><strong>Správa paměti jádra:</strong>  Linuxové jádro má vlastní mechanismy pro správu paměti, včetně alokátorů paměti a algoritmů pro stránkování</li>
							<li><strong>Ochrana paměti:</strong>  Linux zajišťuje, že každý proces má přístup pouze k paměti, která mu byla přidělena, což zvyšuje bezpečnost a stabilitu systému</li>
						</ul>
					</div>
				</details>
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
				<details class="details-block">
					<summary>📄 Podrobnější zápisky</summary>
					<div class="details-content">
						<h3>Souborové systémy</h3>
						<p><strong>MS Windows</strong></p>
						<ul>
							<li><strong>FAT (File Allocation Table):</strong> Starší souborový systém, který se používá hlavně na menších discích a vyměnitelných médiích. Má omezení velikosti souborů a diskových oddílů</li>
							<li><strong>NTFS (New Technology File System):</strong> Moderní souborový systém, který nabízí pokročilé funkce jako šifrování, kompresi, kvóty a podporu velkých souborů a diskových oddílů. NTFS je standardním souborovým systémem pro většinu verzí Windows</li>
							<li><strong>exFAT</strong>  (Extended File Allocation Table): Navržený pro flash disky a externí úložiště. Podporuje větší soubory než FAT32 a je kompatibilní s více operačními systémy</li>
						</ul>
						<p><strong>Linux</strong></p>
						<ul>
							<li><strong>ext4 (Fourth Extended Filesystem):</strong> Nejrozšířenější souborový systém v Linuxu, který nabízí vysoký výkon, spolehlivost a podporu velkých souborů a diskových oddílů</li>
							<li><strong>XFS:</strong>  Vysoce výkonný souborový systém, který je vhodný pro servery a aplikace náročné na I/O operace. Podporuje velké soubory a diskové oddíly</li>
							<li><strong>Btrfs (B-tree File System):</strong>  Moderní souborový systém s pokročilými funkcemi jako snapshoty, kontrolní součty a podpora RAID. Je navržen pro vysokou spolehlivost a snadnou správu</li>
						</ul>
						<p><strong>Unix</strong></p>
						<ul>
							<li><strong>UFS (Unix File System):</strong> : Tradiční souborový systém používaný v mnoha Unixových systémech. Nabízí spolehlivost a výkon, ale má omezenou podporu pro moderní funkce</li>
							<li><strong>ZFS (Zettabyte File System):</strong> Pokročilý souborový systém s funkcemi jako snapshoty, kontrolní součty, komprese a podpora velkých souborů a diskových oddílů. Je navržen pro vysokou spolehlivost a snadnou správu</li>
							<li><strong>FFS (Fast File System):</strong>  Vylepšená verze UFS, která byla vyvinuta pro zvýšení výkonu a snížení fragmentace</li>
						</ul>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🛠️ I/O subsystém</h2>
				<ul>
					<li><strong>Windows:</strong> I/O Manager, Plug and Play, power management, async I/O</li>
					<li><strong>Linux:</strong> VFS (abstrakce FS), aio_read, ovladače, buffer cache</li>
				</ul>
				<details class="details-block">
					<summary>📄 Podrobnější zápisky</summary>
					<div class="details-content">
						<h3>Vstupně-výstupní (I/O) systémy</h3>
						<p><strong>MS Windows</strong></p>
						<ul>
							<li><strong>I/O Manager:</strong> Spravuje všechny I/O operace a poskytuje jednotné rozhraní pro komunikaci s hardwarem. Zajišťuje, že I/O požadavky jsou správně směrovány a zpracovány</li>
							<li><strong>Asynchronní I/O:</strong> Windows podporuje asynchronní I/O, což umožňuje aplikacím pokračovat v práci, zatímco I/O operace probíhá na pozadí. To zvyšuje výkon a efektivitu aplikací</li>
							<li><strong>Plug and Play (PnP):</strong> Umožňuje automatickou detekci a konfiguraci nově připojených zařízení bez nutnosti restartu systému</li>
							<li><strong>Power Management:</strong> Správa napájení umožňuje systému a jednotlivým zařízením přecházet do nízkopříkonových stavů, což šetří energii</li>
						</ul>
						<p><strong>Linux</strong></p>
						<ul>
							<li><strong>Virtuální souborový systém (VFS):</strong> Abstraktní vrstva, která poskytuje jednotné rozhraní pro různé souborové systémy. Umožňuje aplikacím pracovat s různými typy souborových systémů bez nutnosti specifických úprav</li>
							<li><strong>Asynchronní I/O:</strong> Linux podporuje asynchronní I/O pomocí systémových volání jako aio_read a aio_write, což umožňuje efektivní zpracování I/O operací na pozadí</li>
							<li><strong>Device Drivers:</strong>  Ovladače zařízení v Linuxu jsou modulární a mohou být načítány a uvolňovány za běhu systému, což zvyšuje flexibilitu a rozšiřitelnost</li>
							<li><strong>Buffer Cache:</strong>  Linux používá buffer cache pro ukládání často přistupovaných dat, což zvyšuje výkon systému tím, že minimalizuje počet přístupů na disk</li>
						</ul>
					</div>
				</details>
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
