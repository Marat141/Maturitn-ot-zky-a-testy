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
				<h1>Windows – část 7: Konfigurace sítě</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Network/Exam-Operacni_systemy_Win_7_Network"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🌐 Základní pojmy</h2>
				<ul>
					<li><strong>Hostitel</strong> – zařízení připojené k síti (PC, mobil, tiskárna...)</li>
					<li><strong>Server</strong> – poskytuje služby klientům (např. web, e-mail)</li>
					<li><strong>Klient</strong> – využívá služby serveru</li>
					<li><strong>Směrovač (router)</strong> – propojuje sítě, umožňuje přístup k internetu</li>
					<li><strong>Wi-Fi</strong> – bezdrátové připojení</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔢 Síťové adresování</h2>
				<ul>
					<li><strong>IP adresa:</strong> identifikuje zařízení v síti</li>
					<li><strong>Maska sítě:</strong> určuje rozsah sítě</li>
					<li><strong>Hostname:</strong> jméno hostitele (překládané na IP)</li>
					<li><strong>DHCP:</strong> přiděluje IP adresy automaticky</li>
					<li><strong>DNS:</strong> překládá názvy na IP adresy</li>
				</ul>
			</section>

			<section class="note">
				<h2>🌍 IPv4 vs IPv6</h2>
				<ul>
					<li><strong>IPv4:</strong> 32bitová, např. 192.168.0.1</li>
					<li><strong>IPv6:</strong> 128bitová, např. 2001:0db8::1</li>
					<li>IPv6 řeší nedostatek adres a má další výhody</li>
					<li><strong>NAT:</strong> umožňuje sdílení jedné veřejné IP adresy</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Konfigurace sítě</h2>
				<ul>
					<li><strong>GUI:</strong> Ovládací panely &rarr; Centrum síťových připojení &rarr; vlastnosti adaptéru</li>
					<li><strong>Volby:</strong> DHCP vs statická IP</li>
				</ul>
			</section>

			<section class="note">
				<h2>📜 Příkazy netsh</h2>
				<ul>
					<li><code>netsh interface ip set address ...</code> – statická IP</li>
					<li><code>netsh interface ip set dns ...</code> – nastavení DNS</li>
					<li><code>netsh advfirewall set allprofiles state on/off</code> – zapnout/vypnout firewall</li>
					<li><code>netsh -c interface dump > ...</code> – export nastavení</li>
					<li><code>netsh -f config.txt</code> – import nastavení</li>
				</ul>
			</section>

			<section class="note">
				<h2>🚫 Brána firewall</h2>
				<ul>
					<li>Povolení: <code>netsh advfirewall set allprofiles state on</code></li>
					<li>Zakázání: <code>netsh advfirewall set allprofiles state off</code></li>
					<li>Povolení pingu: <code>action=allow protocol=icmpv4</code></li>
					<li>Blokování IP: <code>remoteip=192.168.2.1-192.168.2.10</code></li>
				</ul>
			</section>
		</div>
	</div>
</main>

