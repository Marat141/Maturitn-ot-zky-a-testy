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
				<h1>Windows – část 8: AppLocker</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server/Exam-Operacni_systemy_Win_7_Windows_Server"
					class="ButtonExam">Napsat si test</a>
			</div>

			<section class="note">
				<h2>📌 Co je AppLocker</h2>
				<p>
					AppLocker je bezpečnostní nástroj integrovaný ve Windows, který slouží k řízení, jaké aplikace smí být spuštěny na konkrétních počítačích. Pravidla lze vytvořit na základě:
				</p>
				<ul>
					<li><strong>Publisher (vydavatel):</strong> podle digitálního podpisu aplikace</li>
					<li><strong>Cesta:</strong> podle umístění souboru v systému</li>
					<li><strong>Hash:</strong> podle kontrolního součtu souboru (vhodné pro nepodepsané aplikace)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Požadavky pro použití AppLockeru</h2>
				<ul>
					<li><strong>Windows edice:</strong> pouze Pro, Enterprise, Education</li>
					<li><strong>Oprávnění:</strong> je potřeba být administrátor</li>
					<li><strong>Digitální podpis:</strong> aplikace musí být podepsaná certifikátem vydavatele</li>
					<li><strong>AppLocker musí být aktivní:</strong> služba <code>Application Identity</code> musí být spuštěná</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔧 Nastavení AppLocker pravidel (GUI)</h2>
				<ol>
					<li>Spusť <code>gpmc.msc</code> (pro doménu) nebo <code>secpol.msc</code> (pro lokální PC)</li>
					<li>Najdi cestu: <code>Computer Configuration &gt; Windows Settings &gt; Security Settings &gt; Application Control Policies &gt; AppLocker</code></li>
					<li>Spusť <strong>Configure rule enforcement</strong> a aktivuj typy pravidel (Executable, Script, Installer, Packaged apps)</li>
				</ol>
			</section>

			<section class="note">
				<h2>✅ Pravidlo Allow – Mozilla Thunderbird</h2>
				<ol>
					<li><code>Executable Rules → Create New Rule</code></li>
					<li>Akce: <strong>Allow</strong></li>
					<li>Skupina: <strong>Everyone</strong> nebo konkrétní skupina</li>
					<li>Podmínka: <strong>Publisher</strong></li>
					<li>Vyber <code>thunderbird.exe</code> (např. <code>C:\Program Files\Mozilla Thunderbird</code>)</li>
					<li>Zkontroluj vydavatele (Mozilla Corporation)</li>
					<li>Volitelně přidej výjimky</li>
					<li>Pojmenuj pravidlo např. <code>Allow Mozilla Thunderbird</code></li>
				</ol>
			</section>

			<section class="note">
				<h2>⛔ Pravidlo Deny – zakázání jiných aplikací</h2>
				<ul>
					<li>Vytvoř nové pravidlo s akcí <strong>Deny</strong></li>
					<li>Skupina: např. <strong>Everyone</strong></li>
					<li>Podmínka: <strong>Publisher</strong> (jiný než Mozilla)</li>
					<li>Zvol libovolný spustitelný soubor od jiného vydavatele</li>
					<li>Pojmenuj např. <code>Deny All Other Publishers</code></li>
					<li><strong>POZOR:</strong> pravidlo Allow musí být výše než Deny</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔄 Aplikace a test pravidel</h2>
				<ul>
					<li><strong>Aktualizace Group Policy:</strong> <code>gpupdate /force</code></li>
					<li><strong>Test:</strong>
						<ol>
							<li>Thunderbird se musí spustit</li>
							<li>Jiné aplikace musí být zablokovány</li>
						</ol>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧰 Řešení problémů</h2>
				<ul>
					<li>Zkontroluj, že běží služba <code>Application Identity</code> (<code>services.msc</code>)</li>
					<li>Auditní logy: Event Viewer → <code>Windows Logs → Security → AppLocker → EXE and DLL</code></li>
					<li>Audit Mode: Sleduj bez vynucení pravidla (před ostrým nasazením)</li>
				</ul>
			</section>

			<section class="note">
				<h2>💡 Tipy pro administrátory</h2>
				<ul>
					<li><strong>Zálohuj pravidla</strong> před každou změnou</li>
					<li><strong>Testuj v režimu auditování</strong> pro ověření bez omezení</li>
					<li><strong>Pravidelně aktualizuj</strong> seznam povolených aplikací dle změn ve firmě</li>
					<li><strong>Správně řaď pravidla:</strong> povolující pravidla výše než zakazující</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_8_Sprava_aplikaci_1.pdf" class="ButtonExam" download>
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