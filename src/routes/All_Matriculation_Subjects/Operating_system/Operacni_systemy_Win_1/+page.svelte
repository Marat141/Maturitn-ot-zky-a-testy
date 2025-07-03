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
				<h1>Windows – část 1: Historie</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1/Exam-Operacni_systemy_Win_1"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>💾 MS-DOS (1981)</h2>
				<ul>
					<li><strong>První verze:</strong> 1981</li>
					<li><strong>Hlavní rysy:</strong> Textové rozhraní, používání příkazové řádky, jednoduchá správa souborů a složek, podpora pevných disků.</li>
					<li>MS-DOS byl základem pro mnoho počítačů IBM PC a kompatibilních zařízení</li>
					<li><strong>Vývojářské technologie:</strong> MS-DOS byl vyvinut na základě operačního systému QDOS a neměl grafické uživatelské rozhraní (GUI)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🪟 Windows 1.0 (1985)</h2>
				<ul>
					<li><strong>První verze:</strong> 1985</li>
					<li><strong>Hlavní rysy:</strong> První grafické uživatelské rozhraní od Microsoftu (GUI), podpora myši, okna s možností překrývání.</li>
					<li>První pokus Microsoftu o vytvoření grafického prostředí nad DOSem</li>
					<li><strong>Vývojářské technologie:</strong> Windows běžel jako rozšíření nad MS-DOS. Programy byly stále psané primárně pro DOS.</li>
					<li><strong>V této verzi Windows začal Microsoft používat DLL (Dynamic Link Library)</strong></li>
				</ul>
			</section>

			<section class="note">
				<h2>📚 Co je DLL?</h2>
				<ul>
					<li><strong>Modulární knihovny sdílené mezi aplikacemi</strong></li>
					<ul>
						<li style="font-size: 14px;">Knihovna DLL obsahuje funkce, proměnné, třídy nebo zdroje (např. ikony nebo texty), které může využívat více aplikací. Programy si načtou požadovaný kód z DLL při svém spuštění nebo během běhu</li>
					</ul>
					<li><strong>Načítají se dynamicky za běhu</strong></li>
					<ul>
						<li style="font-size: 14px;">Kód v DLL souborech není zahrnut přímo ve spustitelném souboru (EXE), ale je do programu dynamicky načítán během jeho běhu. Program při spuštění (nebo v průběhu běhu) volá funkce z DLL knihovny prostřednictvím API</li>
					</ul>
					<li>Snižují nároky na paměť</li>
					<li>Př. kernel32.dll, user32.dll, gdi32.dll, shell32.dll</li>
				</ul>
			</section>

			<section class="note">
				<h2>🖼️ Windows 3.x (1990–1992)</h2>
				<ul>
					<li><strong>První verze:</strong> 1990 (Windows 3.0), 1992 (Windows 3.1)</li>
					<li>Vylepšené GUI, podpora multitaskingu, podpora správy paměti a síťových funkcí</li>
					<li>TrueType fonty, síťové funkce</li>
					<li>Nadále běželo nad MS-DOS</li>
					<li><strong>Vývojářské technologie: </strong>Využití rozšířených paměťových modelů (Extended Memory) pro lepší správu paměti a multitasking</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧱 Windows 95 (1995)</h2>
				<ul>
					<li><strong>První verze:</strong> 1995</li>
					<li><strong>Hlavní rysy:</strong> Nové uživatelské rozhraní s tlačítkem Start, podpora dlouhých názvů souborů, 32bitové aplikace, podpora Plug and Play, představení Internet Exploreru</li>
					<li>Masivní přechod k 32bitové architektuře, integrace GUI a MS-DOS, příchod internetu do domácností. Windows 95 se při bootování krátce opíral o MS-DOS (verze 7.0), aby inicializoval základní úlohy systému, jako je správa hardwaru a základní souborové operace</li>
					<li><strong>Preemptivní multitasking</strong> je spravován operačním systémem, který zajišťuje efektivní rozdělení procesorového času a vyšší stabilitu systému. Dnes je standardem</li>
					<li><strong>Vývojářské technologie:</strong> Windows API (Win32 API) se stalo hlavním rozhraním pro vývoj aplikací. Windows 95 obsahoval MS-DOS, ale běžel jako samostatný OS</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧩 Windows 98 (1998)</h2>
				<ul>
					<li><strong>První verze:</strong> 1998</li>
					<li><strong>Hlavní rysy:</strong> Vylepšený Internet Explorer, podpora USB, vylepšený systém Plug and Play, Active Desktop (integrování webového obsahu na pracovní plochu)</li>
					<li>Windows 98 se stal populárním operačním systémem pro multimediální a domácí uživatele</li>
					<li><strong>Vývojářské technologie:</strong> Důraz na webové technologie jako ActiveX, Internet Explorer se stal více integrovanou součástí systému</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧪 Windows ME (2000)</h2>
				<ul>
					<li><strong>První verze:</strong> 2000</li>
					<li><strong>Hlavní rysy:</strong> Zlepšená multimediální podpora, systém ochrany souborů, rychlejší spuštění, nová funkce Obnovení systému</li>
					<li>Poslední operační systém v řadě založený na jádru MS-DOS. Neúspěšný z hlediska stability</li>
					<li><strong>Vývojářské technologie:</strong> Pokračování ve využívání staršího jádra MS-DOS, omezený přístup k profesionálním funkcím jako v NT řadě</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔒 Windows NT & 2000</h2>
				<ul>
					<li><strong>První verze:</strong> 1993</li>
					<li><strong>Hlavní rysy:</strong> Multitasking, podpora víceprocesorových systémů, vyšší bezpečnost, plná 32bitová architektura</li>
					<li>Windows NT bylo zaměřeno na podnikové použití a servery. Zavedení 32bitové architektury bez závislosti na MS-DOS.</li>
					<li><strong>Vývojářské technologie:</strong> NT architektura poskytovala stabilnější a bezpečnější platformu s možností předběžného zpracování úloh (preemptivní multitasking) a plné podpory sítě</li>
					<li>Určeno pro podnikové prostředí</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Windows 2000</h2>
				<ul>
					<li><strong>První verze:</strong> 2000</li>
					<li><strong>Hlavní rysy:</strong> Stabilita, spolehlivost, správa souborů, zabezpečení, NTFS, Active Directory</li>
					<li>Podnikové prostředí, přechod na NTFS, široké rozšíření</li>
					<li><strong>Vývojářské technologie:</strong> Podpora internetových protokolů, Active Directory</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧱 NTFS (New Technology File System)</h2>
				<ul>
					<li>souborový systém, který byl poprvé představen s operačním systémem Windows NT 3.1, který vyšel v roce 1993, což byla první verze řady Windows NT</li>
					<li>Klíčové vlastnosti NTFS ve Windows NT 3.x</li>
					<ul>
						<li><strong>Podpora dlouhých názvů souborů:</strong> NTFS podporoval delší názvy souborů než tehdy používaný systém FAT (File Allocation Table), který omezoval názvy na formát 8.3 (osm znaků pro název a tři pro příponu)</li>
						<li><strong>Zvýšená bezpečnost:</strong> NTFS obsahoval pokročilé funkce pro řízení přístupu a zabezpečení dat, jako jsou přístupová práva a šifrování</li>
						<li><strong>Žurnálování:</strong>NTFS zahrnoval žurnálování souborového systému, což znamenalo, že si zaznamenával změny před jejich skutečným provedením. To umožňuje rychlejší obnovu po selhání systému a větší spolehlivost ve srovnání se souborovými systémy jako FAT</li>
						<li><strong>Podpora velkých disků a souborů:</strong> NTFS mohl pracovat s většími pevnými disky a podporoval soubory větší než 4 GB, což bylo omezení u systému FAT. To umožňovalo využívat diskové úložiště efektivněji</li>
						<li><strong>Komprese souborů:</strong> NTFS podporoval kompresi souborů na úrovni souborového systému, což umožňovalo snížit velikost souborů uložených na disku bez nutnosti speciálního softwaru</li>
						<li><strong>Podpora RAID:</strong> NTFS měl také integrovanou podporu pro zrcadlení disků (RAID 1) a další pokročilé funkce správy disků</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🎨 Windows XP</h2>
				<ul>
					<li><strong>První verze:</strong> 2001</li>
					<li><strong>Hlavní rysy:</strong> Rozhraní Luna, stabilita NT jádra, hardwarová akcelerace, režim spánku</li>
					<li>Populární mezi uživateli, jednoduché ovládání</li>
					<li><strong>Vývojářské technologie:</strong> DirectX, multimédia, bezpečnost, kompatibilita</li>
				</ul>
			</section>

			<section class="note">
				<h2>🌁 Windows Vista</h2>
				<ul>
					<li><strong>První verze:</strong> 2006</li>
					<li><strong>Hlavní rysy:</strong> Vzhled Aero, User Account Control, moderní hardware, Windows Search</li>
					<li>Kritika výkonu a kompatibility</li>
					<li><strong>Vývojářské technologie:</strong> .NET Framework 3.0, podpora grafiky</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧩 .NET Framework</h2>
				<ul>
					<li>Vývojová platforma vytvořená společností Microsoft, která poskytuje prostředky a nástroje pro tvorbu a spouštění aplikací na platformě Windows</li>
					<li>.NET Framework byl poprvé představen v roce 2002 a jeho cílem bylo poskytnout sjednocené prostředí pro vývoj různých typů aplikací, včetně desktopových, webových a mobilních aplikací, s důrazem na zjednodušení programování a zlepšení efektivity vývojářů</li>
					<li>V průběhu let byl .NET Framework průběžně aktualizován a vylepšován, ale od verze .NET Framework 4.8, která byla vydána v roce 2019, již Microsoft neplánuje vydávat nové verze .NET Frameworku</li>
				</ul>
			</section>

			<section class="note">
				<h2>🚀 Windows 7</h2>
				<ul>
					<li><strong>První verze:</strong> 2009</li>
					<li><strong>Hlavní rysy:</strong> Rychlost, stabilita, podpora dotyku, nová hlavní lišta, sítě</li>
					<li>Oblíbený u uživatelů i firem</li>
					<li><strong>Vývojářské technologie:</strong> DirectX 11, virtualizace, bezpečnost</li>
				</ul>
			</section>

			<section class="note">
				<h2>📱 Windows 8 / 8.1</h2>
				<ul>
					<li><strong>První verze:</strong> 2012 (8), 2013 (8.1)</li>
					<li><strong>Hlavní rysy:</strong> Metro UI, dotyková optimalizace, rychlé spuštění, Windows Store</li>
					<li>Absence nabídky Start, smíšené přijetí</li>
					<li><strong>Vývojářské technologie:</strong> WinRT, integrace s cloudem</li>
				</ul>
			</section>

			<section class="note">
				<h2>🌍 Windows 10</h2>
				<ul>
					<li><strong>První verze:</strong> 2015</li>
					<li><strong>Hlavní rysy:</strong> Kombinace prvků z W7 a W8, návrat Start, univerzální aplikace, dotyk</li>
					<li>„Poslední“ verze s průběžnými aktualizacemi</li>
					<li><strong>Vývojářské technologie:</strong> UWP, DirectX 12, bezpečnost</li>
				</ul>
			</section>

			<section class="note">
				<h2>🪟 Windows 11</h2>
				<ul>
					<li><strong>První verze:</strong> 2021</li>
					<li><strong>Hlavní rysy:</strong> Nové rozhraní, moderní hardware, Android aplikace, Snap Layouts</li>
					<li>Moderní vzhled, vylepšení pro hybridní práci</li>
					<li><strong>Vývojářské technologie:</strong> WSL, TPM 2.0, bezpečnostní vylepšení</li>
				</ul>
			</section>


			<a href="/PDF/Operacni_systemy_Win_1.pdf" class="ButtonExam" download> 📄 Stáhnout PDF </a>
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
