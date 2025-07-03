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
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_Server_14_DHCP'
		},
		{
			id: 27,
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
				<h1 id="dhcp">Windows Server: DHCP</h1>
				<a href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_Server_14_DHCP/Exam-Operacni_systemy_Win_Server_14_DHCP" class="ButtonExam">Napsat si test</a>
			</div>

			<section id="co-je-dhcp" class="note">
				<h2>📘 Co je DHCP</h2>
				<p>
					DHCP (<strong>Dynamic Host Configuration Protocol</strong>) je síťová služba, která
					automaticky přiděluje IP adresy a další síťové informace zařízením v síti.
				</p>
				<ul>
					<li>Zajišťuje automatizaci konfigurace IP adres</li>
					<li>Bez DHCP by správce musel vše nastavovat ručně (IP, masku, bránu, DNS...)</li>
				</ul>
			</section>

			<section id="funkce-dhcp" class="note">
				<h2>🛠️ Základní funkce DHCP serveru</h2>
				<ul>
					<li>Přiděluje IP adresy z předdefinovaného rozsahu (<em>scope</em>)</li>
					<li>
						Poskytuje:
						<ul>
							<li>Masku podsítě</li>
							<li>Výchozí bránu (default gateway)</li>
							<li>DNS servery</li>
							<li>Doménové jméno</li>
							<li>Volitelné parametry</li>
						</ul>
					</li>
				</ul>
			</section>

			<section id="dora" class="note">
				<h2>🔄 DHCP proces – DORA</h2>
				<table>
					<thead>
						<tr>
							<th>Fáze</th>
							<th>Zpráva</th>
							<th>Popis</th>
						</tr>
					</thead>
					<tbody>
						<tr><td>1️⃣</td><td><strong>Discover</strong></td><td>Klient hledá DHCP server</td></tr>
						<tr><td>2️⃣</td><td><strong>Offer</strong></td><td>DHCP server nabízí IP adresu</td></tr>
						<tr
							><td>3️⃣</td><td><strong>Request</strong></td><td>Klient žádá o konkrétní nabídku</td
							></tr
						>
						<tr
							><td>4️⃣</td><td><strong>Acknowledgement</strong></td><td
								>DHCP server potvrzuje přidělení</td
							></tr
						>
					</tbody>
				</table>
			</section>

			<section id="pojmy" class="note">
				<h2>🔑 Klíčové pojmy DHCP</h2>
				<ul>
					<li><strong>Scope (rozsah):</strong> Definuje, jaké IP adresy se přidělují</li>
					<li><strong>Lease (pronájem):</strong> Časově omezené přidělení adresy</li>
					<li>
						<strong>Reservation (rezervace):</strong> Pevné přiřazení IP konkrétnímu zařízení (na základě
						MAC)
					</li>
					<li><strong>Options:</strong> Dodatečné parametry jako DNS, gateway, WINS atd.</li>
					<li><strong>Exclusion:</strong> Adresy, které se přidělovat nesmí</li>
				</ul>
			</section>

			<section id="ipv4-ipv6" class="note">
				<h2>🌐 Podpora IPv4 a IPv6</h2>
				<h3>📦 Přehled</h3>
				<table>
					<thead>
						<tr><th>Verze</th><th>Režimy</th><th>IP přiděluje</th><th>DNS přiděluje</th></tr>
					</thead>
					<tbody>
						<tr><td>IPv4</td><td>Stateful</td><td>DHCP</td><td>DHCP</td></tr>
						<tr
							><td>IPv6</td><td>Stateful, Stateless, SLAAC</td><td>DHCP / Klient</td><td
								>DHCP / RA</td
							></tr
						>
					</tbody>
				</table>

				<h3>🧠 Režimy přidělování v IPv6</h3>

				<ul>
					<li>
						<strong>Stateful DHCPv6</strong> – DHCP server přiděluje IP, DNS, doménu i čas pronájmu.
					</li>
					<li>
						<strong>Stateless DHCPv6 (SLAAC + DHCP)</strong> – IP si klient vygeneruje, DHCP poskytne
						jen DNS/doménu.
					</li>
					<li>
						<strong>SLAAC (bez DHCPv6)</strong> – klient si vše nastaví sám podle RA zprávy (bez DHCP).
					</li>
				</ul>
			</section>

			<section id="vyhody" class="note">
				<h2>✅ Výhody DHCP</h2>
				<ul>
					<li>Automatizace správy adres</li>
					<li>Snížení chybovosti při nastavování</li>
					<li>Snadné řízení rozsahů</li>
					<li>Podpora pro mobilní i dočasná zařízení</li>
				</ul>
			</section>

			<section id="nevyhody" class="note">
				<h2>⚠️ Nevýhody a rizika</h2>
				<ul>
					<li>Závislost na dostupnosti serveru</li>
					<li>Riziko neautorizovaného DHCP serveru</li>
					<li>Obtížnější sledování bez rezervací</li>
				</ul>
			</section>

			<section id="pouziti" class="note">
				<h2>🏢 Použití v praxi</h2>
				<ul>
					<li>Firemní sítě – řízený DHCP server s rezervacemi</li>
					<li>Domácnosti – DHCP funkce často zabudovaná v routeru</li>
					<li>Datová centra – DHCP kombinované se statickým přidělením pro servery</li>
				</ul>
			</section>

			<section id="konfigurace" class="note">
				<h2>🧰 Základní konfigurace DHCP na Windows Serveru</h2>
				<ol>
					<li>Otevři <strong>Server Manager</strong></li>
					<li>Vyber „Add roles and features“</li>
					<li>Zvol <em>„Role-based or feature-based installation“</em></li>
					<li>Vyber server, zaškrtni <strong>DHCP Server</strong>, dokonči průvodce</li>
				</ol>
				<p><strong>Powershell instalace:</strong></p>
				<pre><code
						>Install-WindowsFeature -Name DHCP -IncludeManagementTools
Add-DhcpServerInDC -DnsName "NAZEV.DOMENY" -IPAddress "IP_ADRESA_SERVERU"</code
					></pre>
			</section>

			<section id="scope-reservace" class="note">
				<h2>📐 Scope & rezervace</h2>
				<h3>🎯 Vytvoření rozsahu (scope)</h3>
				<ul>
					<li>Otevři <code>dhcpmgmt.msc</code> > pravým na IPv4 > <em>New Scope…</em></li>
					<li>Nastav název, IP rozsah, výjimky, lease time, gateway, DNS…</li>
				</ul>
				<h3>🔒 Rezervace (Reservations)</h3>
				<ul>
					<li>Pravým na „Reservations“ > <em>New Reservation…</em></li>
					<li>Zadej název, MAC adresu a cílovou IP</li>
				</ul>
			</section>

			<section id="zalohy" class="note">
				<h2>💾 Záloha & obnova DHCP</h2>
				<p><strong>Záloha:</strong></p>
				<pre><code>Backup-DhcpServer -ComputerName "localhost" -Path "C:\DHCP_Backup"</code></pre>
				<p><strong>Obnova:</strong></p>
				<pre><code>Restore-DhcpServer -ComputerName "localhost" -Path "C:\DHCP_Backup" -Force</code
					></pre>
			</section>

			<section id="monitoring" class="note">
				<h2>📊 Monitoring a správa</h2>
				<ul>
					<li>Logy: <code>C:\Windows\System32\dhcp</code></li>
					<li>
						Event Viewer: <em>Applications and Services Logs > Microsoft > Windows > DHCP-Server</em
						>
					</li>
					<li>Aktivní pronájmy: <code>Get-DhcpServerv4Lease</code></li>
				</ul>
			</section>
			<a href="/PDF/Operacni_systemy_Win_Server_14_DHCP.pdf" class="ButtonExam" download
				>📄 Stáhnout PDF</a
			>
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
		font-family:
			'Inter',
			system-ui,
			-apple-system,
			'Segoe UI',
			Roboto,
			sans-serif;
		color: #1f2937;
		transition: all 0.3s ease;
	}
	.content h1,
	.content h2 {
		color: #2563eb;
		margin-top: 0;
	}

	.content h2 {
		margin-top: 32px;
		margin-bottom: 16px;
		font-size: 1.4rem;
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

	.content table {
		width: 100%;
		border-collapse: collapse;
		margin: 16px 0;
		font-size: 15px;
	}

	.content th,
	.content td {
		border: 1px solid #d1d5db;
		padding: 8px 12px;
		text-align: left;
	}

	.content th {
		background-color: #e0e7ff;
		color: #1e3a8a;
	}

	.content tr:nth-child(even) {
		background-color: #f9fafb;
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

	.details-content ul {
		list-style: disc;
		padding-left: 24px;
		margin-bottom: 8px;
	}

	.details-content li {
		margin-bottom: 6px;
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
