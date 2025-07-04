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
				<h1>Windows – část 4: PowerShell</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4/Exam-Operacni_systemy_Win_4"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🔑 Klíčové pojmy</h2>
				<ul>
					<li>Windows Powershell</li>
					<li>Argumentypříkazů</li>
					<li>Options</li>
					<li>Historie v powershell</li>
					<li>Místní proměnné</li>
					<li>Proměnné prostředí</li>
					<li>Proměnná Path</li>
					<li>Interní příkazy</li>
					<li>Externí příkazy </li>
					<li>Aliasy</li>
					<li>Nejpoužívanější cmdlety</li>
				</ul>
			</section>

			<section class="note">
				<h2>🖥️ Co je PowerShell</h2>
				<ul>
					<li>PowerShell je pokročilé příkazové řádkové rozhraní a skriptovací prostředí vyvinuté společností Microsoft</li>
					<li>PowerShell je objektově orientovaný shell a skriptovací prostředí</li>
					<li>Umožňuje automatizaci administrativních úloh na platformě Windows</li>
					<li>Využívá cmdlety (např. <code>Get-Process</code>, <code>Set-Date</code>)</li>
					<li>
						Příkazy mají strukturu <code>Sloveso-PodstatnéJméno</code> (např. <code>New-Item</code>)
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Cmdlety – příkazy</h2>
				<ul>
					<li><code>Get-Process</code> – zobrazí běžící procesy</li>
					<li><code>Set-Date</code> – nastaví systémové datum a čas</li>
					<li><code>New-Item</code> – vytvoří soubor nebo složku</li>
					<li><code>Remove-Item</code> – odstraní soubor nebo složku</li>
					<li><code>Get-Command</code> – najde dostupné cmdlety</li>
					<li><code>Get-Help</code> – zobrazí nápovědu k příkazu (např. <code>Get-Help Get-Process -Detailed</code>)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔡 Argumenty a volby v PowerShell</h2>
				<ul>
					<li>
						<strong>Argumenty</strong> jsou hodnoty, které cmdlet přijímá jako vstup. Můžou být zadány:
						<ul>
							<li><strong>pozičně</strong>: <code>Get-Process notepad</code></li>
							<li><strong>pomocí parametru</strong>: <code>Get-Process -Name notepad</code></li>
						</ul>
					</li>
					<li>
						<strong>Volby (parametry)</strong> začínají pomlčkou a mění chování příkazu.
						<ul>
							<li>Např. <code>-Name</code> u <code>Get-Process</code> filtruje podle názvu procesu</li>
							<li>Parametr může mít <strong>hodnotu</strong> (<code>-Name "notepad"</code>) nebo být samostatný přepínač (<code>-Force</code>)</li>
						</ul>
					</li>
					<li>Cmdlety často podporují více parametrů najednou</li>
				</ul>
			</section>

			<section class="note">
				<h2>📜 Historie příkazů</h2>
				<ul>
					<li><code>Get-History</code> – zobrazí všechny dříve zadané příkazy v relaci</li>
					<li><code>Invoke-History -Id 3</code> – znovu spustí příkaz s ID 3 z historie</li>
					<li>Šipky nahoru/dolů fungují pro rychlé procházení historie</li>
				</ul>
			</section>

			<section class="note">
				<h2>💾 Proměnné</h2>
				<ul>
					<li>Proměnné začínají znakem <code>$</code> (např. <code>$x = 5</code>)</li>
					<li><strong>Místní proměnné</strong>: platné jen v rámci aktuální relace nebo skriptu</li>
					<li><strong>Prostředí (environment)</strong> proměnné: <code>$env:NAZEV</code>
						<ul>
							<li><code>$env:USERNAME</code>, <code>$env:PATH</code></li>
							<li>Změna např. <code>$env:PATH += ";C:\NovaCesta"</code></li>
							<li>Trvalá změna pro uživatele:
								<pre><code>[Environment]::SetEnvironmentVariable("PATH", "$env:PATH;C:\NovaCesta", "User")</code></pre>
							</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📛 Aliasy v PowerShell</h2>
				<ul>
					<li><strong>Alias</strong> je zkrácené jméno cmdletu</li>
					<li>Příklad: <code>Set-Alias ll Get-ChildItem</code></li>
					<li>Voláním <code>ll</code> získáš výpis souborů (jako <code>ls</code>)</li>
					<li>Aliasy se hodí pro pohodlnější psaní příkazů nebo skriptů</li>
				</ul>
			</section>

			<section class="note">
				<h2>🌐 Proměnná PATH</h2>
				<ul>
					<li><code>$env:PATH</code> obsahuje seznam složek, kde PowerShell hledá programy</li>
					<li><strong>Dočasné přidání složky:</strong> <code>$env:PATH += ";C:\MyTools"</code></li>
					<li><strong>Trvalé přidání pro uživatele:</strong>
						<pre><code>[Environment]::SetEnvironmentVariable("PATH", "$env:PATH;C:\MyTools", "User")</code></pre>
					</li>
					<li><strong>Trvalé přidání pro všechny uživatele (vyžaduje práva):</strong>
						<pre><code>[Environment]::SetEnvironmentVariable("PATH", "$env:PATH;C:\MyTools", "Machine")</code></pre>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📂 Interní vs. externí příkazy</h2>
				<ul>
					<li><strong>Interní příkazy (cmdlety):</strong> PowerShell funkce (např. <code>Get-Process</code>, <code>Set-Location</code>)</li>
					<li><strong>Externí příkazy:</strong> Spustitelné programy mimo PowerShell (např. <code>notepad.exe</code>, <code>ping.exe</code>)</li>
					<li>PowerShell automaticky rozpozná typ a spustí odpovídající příkaz</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧠 Nejčastější cmdlety (prakticky)</h2>
				<ul>
					<li><code>Get-Process</code> – vypíše běžící procesy</li>
					<li><code>Stop-Process -Name notepad</code> – ukončí proces</li>
					<li><code>Get-Service</code>, <code>Start-Service</code>, <code>Stop-Service</code> – správa služeb</li>
					<li><code>New-Item</code>, <code>Copy-Item</code>, <code>Move-Item</code>, <code>Remove-Item</code> – práce se soubory</li>
					<li><code>Set-Location</code>, <code>Get-ChildItem</code> – pohyb v adresáři</li>
					<li><code>Get-Content</code>, <code>Set-Content</code>, <code>Add-Content</code> – práce s obsahem souborů</li>
					<li><code>Set-Variable</code>, <code>Get-Variable</code>, <code>Clear-Variable</code> – práce s proměnnými</li>
				</ul>
			</section>

			<section class="note">
				<h2>📚 Nejpoužívanější cmdlety</h2>
				<ul>
					<li><code>Get-Process</code>, <code>Stop-Process</code>, <code>Get-Service</code></li>
					<li><code>Copy-Item</code>, <code>Move-Item</code>, <code>Remove-Item</code>, <code>New-Item</code></li>
					<li><code>Set-Location</code> (změna adresáře), <code>Get-Content</code>, <code>Set-Content</code>, <code>Add-Content</code></li>
					<li><code>Get-Variable</code>, <code>Set-Variable</code>, <code>Clear-Variable</code></li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_4.pdf" class="ButtonExam" download> 📄 Stáhnout PDF </a>
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
