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
				<h1>Souborové systémy – část 1: Windows</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows/Exam-Souborove_systemy_1_Windows"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📁 Co je souborový systém</h2>
				<ul>
					<li>Softwarová vrstva operačního systému pro správu dat na discích</li>
					<li>Umožňuje čtení, zápis, úpravu a mazání souborů</li>
					<li>Poskytuje strukturu a pravidla pro ukládání a organizaci dat</li>
					<li>Zajišťuje přístupová práva a ochranu integrity dat</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧩 Hlavní souborové systémy ve Windows</h2>
				<ul>
					<li>
						<strong>FAT32:</strong> velmi kompatibilní, ideální pro USB a SD karty, max. soubor 4 GB, oddíl do 2 TB
					</li>
					<li>
						<strong>NTFS:</strong> podporuje šifrování, kompresi, kvóty, žurnálování, velikost až 256 TB – výchozí pro Windows
					</li>
					<li>
						<strong>exFAT:</strong> pro externí disky, bez omezení velikosti souboru/oddílu, kompatibilní s macOS a Linuxem
					</li>
					<li>
						<strong>ReFS:</strong> moderní pro servery, odolnost proti chybám, samoopravné schopnosti, max. velikost 35 PB
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📊 Tabulka srovnání</h2>
				<ul>
					<li><strong>FAT32:</strong> max. soubor 4 GB, žádné šifrování, žádné kvóty, neprovádí žurnálování</li>
					<li><strong>NTFS:</strong> max. soubor 256 TB, podporuje šifrování, kvóty i žurnálování</li>
					<li><strong>exFAT:</strong> max. soubor 16 EB, jednoduchý a kompatibilní, bez žurnálování</li>
					<li><strong>ReFS:</strong> vysoká spolehlivost, samoopravné mechanismy, šifrování, max. soubor 16 EB</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧠 Výhody a nevýhody</h2>
				<ul>
					<li><strong>FAT32:</strong> jednoduchost, široká podpora, ale omezená bezpečnost a velikost souboru</li>
					<li><strong>NTFS:</strong> bezpečný, moderní, výkonný, ale méně kompatibilní (např. s macOS)</li>
					<li><strong>exFAT:</strong> kompromis mezi kompatibilitou a výkonem, vhodný pro flash disky</li>
					<li><strong>ReFS:</strong> ideální pro servery a úložiště, vysoká ochrana, ale není plně podporován všude</li>
				</ul>
			</section>

			<section class="note">
				<h2>📒 Žurnálování</h2>
				<ul>
					<li>Pomáhá ochránit systém při výpadku (např. při pádu napájení)</li>
					<li>Zaznamenává změny do žurnálu před jejich provedením</li>
					<li><strong>Typy:</strong>
						<ul>
							<li><strong>Plné žurnálování:</strong> zaznamenává data i metadata (vyšší bezpečnost, nižší výkon)</li>
							<li><strong>Žurnálování metadat:</strong> zaznamenává jen metadata (rychlejší, ale méně bezpečné)</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧹 Fragmentace</h2>
				<ul>
					<li>Při ukládání dat mohou být soubory uloženy na nesouvislých místech disku</li>
					<li>Zpomaluje čtení a zápis, hlavně u klasických HDD</li>
					<li>U SSD disků fragmentace nevadí</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Utility pro práci se souborovými systémy</h2>
				<ul>
					<li><strong>CHKDSK:</strong> kontrola a oprava chyb disku</li>
					<li><strong>CONVERT:</strong> převod FAT32 na NTFS (bez ztráty dat)</li>
					<li><strong>DISKPART:</strong> nástroj pro správu diskových oddílů</li>
					<li><strong>ICACLS:</strong> správa oprávnění k souborům</li>
					<li><strong>DEFRAG:</strong> defragmentace disku</li>
				</ul>
			</section>

			<a href="/PDF/Souborove_systemy_1_Windows.pdf" class="ButtonExam" download>
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
