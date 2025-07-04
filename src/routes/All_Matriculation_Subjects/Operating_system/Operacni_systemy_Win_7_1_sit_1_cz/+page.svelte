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
				<h1>Windows – část 7: Konfigurace sítě</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz/Exam-Operacni_systemy_Win_7_1_sit_1_cz"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📡 Úvod do sítí</h2>
				<ul>
					<li>Síťová konektivita je základní součástí každého moderního operačního systému</li>
					<li>Umožňuje přístup k internetu, e-mailům, sdílení souborů a další komunikaci</li>
					<li>Pro zajištění těchto funkcí je nutné mít správně <strong>nastavenou síťovou konfiguraci</strong></li>
					<li>Windows nabízí nástroje ke <strong>sledování a správě sítě</strong></li>
				</ul>
			</section>

			<section class="note">
				<h2>🧠 Základní síťová terminologie</h2>
				<ul>
					<li><strong>Hostitel:</strong> jakékoli zařízení připojené do sítě (PC, mobil, tiskárna...)</li>
					<li><strong>Síť:</strong> skupina dvou a více hostitelů propojených kabelem nebo bezdrátově</li>
					<li><strong>Internet:</strong> veřejná globální síť spojující miliony zařízení</li>
					<li><strong>Wi-Fi:</strong> bezdrátová síťová technologie</li>
					<li><strong>Server:</strong> zařízení poskytující služby klientům (např. webový, e-mailový server)</li>
					<li><strong>Služba:</strong> konkrétní funkce serveru (např. zobrazení webu, odeslání e-mailu)</li>
					<li><strong>Klient:</strong> zařízení, které službu využívá (např. prohlížeč, který načítá web)</li>
					<li><strong>Směrovač (router):</strong> propojuje různé sítě a umožňuje přístup do internetu</li>
				</ul>
			</section>

			<section class="note">
				<h2>📦 Síťové pojmy a protokoly</h2>
				<ul>
					<li><strong>Paket:</strong> datová jednotka pro přenos přes síť</li>
					<li><strong>IP adresa:</strong> jedinečný číselný identifikátor zařízení v síti</li>
					<li><strong>Maska sítě:</strong> určuje, které IP adresy patří do stejné podsítě</li>
					<li><strong>Hostname:</strong> srozumitelný název zařízení (např. <code>server1</code>) překládán přes DNS</li>
					<li><strong>URL:</strong> webová adresa pro přístup ke zdrojům (<code>https://www.example.com</code>)</li>
					<li><strong>DHCP:</strong> server automaticky přiděluje IP adresy a další informace klientům</li>
					<li><strong>DNS:</strong> systém pro převod názvů na IP adresy</li>
					<li><strong>Ethernet:</strong> standard kabelového propojení zařízení v síti (např. 100 Mbps, 1 Gbps)</li>
					<li><strong>TCP/IP:</strong> základní sada protokolů pro síťovou komunikaci</li>
				</ul>
			</section>

			<section class="note">
				<h2>🌍 IP adresování – IPv4 vs. IPv6</h2>
				<ul>
					<li><strong>IPv4:</strong> 32bitová adresa, běžně např. <code>192.168.1.100</code></li>
					<li><strong>IPv6:</strong> 128bitová adresa např. <code>2001:0db8::1</code>, řeší nedostatek adres</li>
					<li>IPv6 nabízí větší adresní prostor a další výhody (efektivita, bezpečnost, správa)</li>
					<li><strong>NAT (Network Address Translation):</strong> sdílení jedné veřejné IP pro více zařízení</li>
					<li><strong>Portování:</strong> postupný přechod ze starší IPv4 na modernější IPv6</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Konfigurace síťových zařízení</h2>
				<ul>
					<li><strong>Typ připojení:</strong> kabelové vs. bezdrátové (Wi-Fi)</li>
					<li><strong>DHCP:</strong> automatická konfigurace (běžné u Wi-Fi a mobilních zařízení)</li>
					<li><strong>Statická IP:</strong> ručně zadané IP adresy (často u serverů a sítí LAN)</li>
					<li><strong>Bezdrátová zařízení:</strong> často vyžadují dodatečné nastavení (např. zabezpečení WPA2)</li>
					<li>Stolní PC většinou používají <strong>Ethernet + statická IP</strong> nebo <strong>DHCP</strong></li>
					<li>Notebooky typicky používají <strong>Wi-Fi + DHCP</strong></li>
				</ul>
			</section>

			<section class="note">
				<h2>💻 Rychlý přehled – co si pamatovat</h2>
				<ul>
					<li>Každé zařízení v síti má svou IP adresu (statickou nebo přidělenou přes DHCP)</li>
					<li>DNS překládá jména na IP adresy (např. <code>seznam.cz</code> → <code>77.75.77.53</code>)</li>
					<li>IPv4 je nejrozšířenější, ale IPv6 je budoucnost</li>
					<li>Přes NAT může více zařízení používat jednu IP adresu</li>
					<li>Konfigurace sítě se může lišit podle typu zařízení a účelu</li>
				</ul>
			</section>


			<section class="note">
				<h2>🖥️ Konfigurace sítě přes grafické rozhraní</h2>
				<ol>
					<li>Otevři <strong>Centrum síťových připojení a sdílení</strong></li>
					<li>Klikni na <strong>Změnit nastavení adaptéru</strong></li>
					<li>Vyber síťové připojení, klikni pravým a zvol <strong>Vlastnosti</strong></li>
					<li>Vyber <strong>Protokol IP verze 4 (TCP/IPv4)</strong> a klikni na <strong>Vlastnosti</strong></li>
					<li>Nastavení IP a DNS:
						<ul>
							<li><strong>DHCP (automaticky):</strong> získat IP a DNS automaticky</li>
							<li><strong>Statické DNS:</strong> IP automaticky, DNS zadat ručně</li>
							<li><strong>Statická IP:</strong> IP a DNS zadat ručně</li>
						</ul>
					</li>
				</ol>
			</section>

			<section class="note">
				<h2>📟 Netsh – konfigurace v příkazovém řádku</h2>
				<ul>
					<li><code>netsh interface ip set address "NÁZEV" static IP MASKA BRÁNA 1</code><br />
						<span style="font-size: 14px;">Nastavení statické IP, např.:
							<code>netsh interface ip set address name="Ethernet" static 192.168.1.100 255.255.255.0 192.168.1.1 1</code></span>
					</li>
					<li><code>netsh interface ip set address "NÁZEV" dhcp</code> – přepne síťovou kartu na DHCP</li>
					<li><code>netsh interface ip set dns "NÁZEV" static 8.8.8.8</code> – nastaví statický DNS server</li>
					<li><code>netsh interface ip set dns "NÁZEV" dhcp</code> – DNS automaticky přes DHCP</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧾 Import a export nastavení sítě</h2>
				<ul>
					<li><code>netsh -c interface dump > C:\MySettings.txt</code> – exportuje konfiguraci sítě</li>
					<li><code>netsh -f C:\MySettings.txt</code> – načte konfiguraci zpět (import)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧱 Brána firewall – řízení přes netsh</h2>
				<ul>
					<li><strong>Zapnout:</strong> <code>netsh advfirewall set allprofiles state on</code></li>
					<li><strong>Vypnout:</strong> <code>netsh advfirewall set allprofiles state off</code></li>
					<li><strong>Zkontrolovat stav:</strong> <code>netsh advfirewall show all</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>🗂️ Export/import brány firewall</h2>
				<ul>
					<li><code>netsh advfirewall export "C:\backup\firewall.wfw"</code> – export pravidel</li>
					<li><code>netsh advfirewall import "C:\backup\firewall.wfw"</code> – import pravidel</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛑 Příkazy pro blokování/povolení provozu</h2>
				<ul>
					<li><strong>Blokovat ping:</strong>
						<code>netsh advfirewall firewall add rule name="Blok ping" dir=in action=block protocol=icmpv4</code></li>
					<li><strong>Povolit ping:</strong>
						<code>netsh advfirewall firewall add rule name="Povolit ping" dir=in action=allow protocol=icmpv4</code></li>
					<li><strong>Blok IP rozsah (IN):</strong>
						<code>netsh advfirewall firewall add rule name="Blok IN" dir=in action=block remoteip=192.168.2.1-192.168.2.10</code></li>
					<li><strong>Blok IP rozsah (OUT):</strong>
						<code>netsh advfirewall firewall add rule name="Blok OUT" dir=out action=block remoteip=192.168.2.1-192.168.2.10</code></li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_7_1_sit_1_cz.pdf" class="ButtonExam" download>
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
