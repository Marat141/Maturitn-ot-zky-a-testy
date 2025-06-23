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
		{ id: 1, level: 1, text: 'Úvod do OS', path: '/All_Matriculation_Subjects/Operating_system'},
		{ id: 2, level: 1, text: 'IT3B PDF soubory' },
        { id: 3, level: 2, text: 'Aplikační protokoly', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Aplikacni-protokoly' },
        { id: 4, level: 2, text: 'Arduino 1-15-1 pohyb přerušení', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Arduino-1_15' },
        { id: 5, level: 2, text: 'Arduino 10 7 segment 4 digits s DHT11', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Arduino-10-7'},
        { id: 6, level: 2, text: 'GDPR souhrn', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'},
		{ id: 7, level: 2, text: 'GDPR Technická opatření', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni' },
		{ id: 8, level: 2, text: 'Operační systémy základní součásti operačního systému', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system' },
		{ id: 9, level: 2, text: 'Mac OS část 1', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1' },
		{ id: 10, level: 2, text: 'Mac OS část 1.2', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2' },
		{ id: 11, level: 2, text: 'Mac OS část 1.4', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail' },
		{ id: 12, level: 2, text: 'Mac OS část 1.7', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal' },
		{ id: 13, level: 2, text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz' },
		{ id: 14, level: 2, text: 'Operační systémy Windows Ovladače zařízení', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager' },
		{ id: 15, level: 2, text: 'Operační systémy Win_1', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1' },
		{ id: 16, level: 2, text: 'Operační systémy Win_2', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2' },
		{ id: 17, level: 2, text: 'Operační systémy Win_3', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3' },
		{ id: 18, level: 2, text: 'Operační systémy Win_4_2', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2' },
		{ id: 19, level: 2, text: 'Operační systémy Win_4', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4' },
		{ id: 20, level: 2, text: 'Operační systémy Win_5_MMC', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC' },
		{ id: 21, level: 2, text: 'Operační systémy Win_7_1_sit_1_cz', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz' },
		{ id: 22, level: 2, text: 'Operační systémy Win_7_1_sit_3_cz', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz' },
		{ id: 23, level: 2, text: 'Operační systémy Win_7_Windows_Server', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server' },
		{ id: 24, level: 2, text: 'Operační systémy Win_8_Sprava_aplikaci_1', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1' },
		{ id: 25, level: 2, text: 'Operační systémy Win_9_1_Firewall', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall' },
		{ id: 26, level: 2, text: 'Souborove systemy 1_Windows', parent: 2, path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows' }
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Windows – část 4: PowerShell – zástupné znaky</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2/Exam-Operacni_systemy_Win_4_2"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🔡 Zástupné znaky v PowerShellu</h2>
				<ul>
					<li><strong>Zástupné znaky (wildcards)</strong> v PowerShellu umožňují flexibilní a efektivní hledání, filtrování a manipulaci se soubory a složkami na základě vzorů</li>
					<li><strong>*</strong> – libovolný počet znaků (<code>Get-ChildItem -Path *.txt</code>)</li>
					<ul>
						<li style="font-size: 14px;"><strong>Popis:</strong> Reprezentuje libovolný počet znaků, včetně žádného znaku. Používá se pro široké vyhledávání souborů a složek.</li>
					</ul>
					<li><strong>?</strong> – jeden libovolný znak (<code>Get-ChildItem -Path ?????.txt</code>)</li>
					<ul>
						<li style="font-size: 14px;"><strong>Popis:</strong> Reprezentuje libovolný počet znaků, včetně žádného znaku. Používá se pro široké vyhledávání souborů a složek.</li>
					</ul>
					<li><strong>[]</strong> – jeden znak z množiny (<code>Get-ChildItem -Path ?[abc]*.txt</code>)</li>
					<ul>
						<li style="font-size: 14px;"><strong>Popis:</strong> Reprezentují libovolný jeden znak ze specifikovaného rozsahu nebo množiny znaků</li>
					</ul>
					<li><strong>[! ] nebo [^ ]</strong> – negace, znak který <em>není</em> ve specifikované množině (<code>Get-ChildItem -Path ??[!xy]*.txt</code>)</li>
					<ul>
						<li style="font-size: 14px;"><strong>Popis:</strong> Reprezentují libovolný jeden znak, který není ve specifikované množině.</li>
					</ul>
					<li> <strong>&#123;&#125;</strong> – složené závorky pro výběr z více možností (např. <code>Get-ChildItem -Path &quot;*.&#123;jpg,png&#125;&quot;</code>)</li>
						<ul>
							<li style="font-size: 14px;"><strong>Popis:</strong> Umožňují zadat více možností najednou. Například <code>report&#123;1..3&#125;.docx</code> expanduje na <code>report1.docx</code>, <code>report2.docx</code>, <code>report3.docx</code>.</li>
						</ul>
					<li><strong>`</strong> – escape znak (<code>Get-ChildItem -Path "Data`[2024`].txt"</code>)</li>
					<ul>
						<li style="font-size: 14px;"><strong>Popis:</strong> Používá se k úniku speciálních znaků, které mají v PowerShellu speciální význam, aby byly interpretovány doslovně</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🔁 Kombinace zástupných znaků</h2>
				<ul>
					<li><strong>Popis:</strong> Kombinací různých zástupných znaků můžete vytvořit složitější vzory pro vyhledávání</li>
					<li><code>Get-ChildItem -Path "*2023*.txt", "*2024*.txt"</code> – více vzorů</li>
					<li><code>Get-ChildItem -Path "Report?.docx"</code> – libovolný znak mezi</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Wildcardy v parametrech cmdletů</h2>
				<ul>
					<li><strong>Popis:</strong> Zástupné znaky mohou být použity v různých parametrech PowerShell cmdletů pro filtrování výsledků</li>
					<li><code>Get-ChildItem -Path "C:\Logs\*.log" -Recurse</code> – hledání včetně podadresářů</li>
					<li><code>Select-String -Path "C:\Logs\*.log" -Pattern "Error"</code> – hledání textu ve více souborech</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_4_2.pdf" class="ButtonExam" download>
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