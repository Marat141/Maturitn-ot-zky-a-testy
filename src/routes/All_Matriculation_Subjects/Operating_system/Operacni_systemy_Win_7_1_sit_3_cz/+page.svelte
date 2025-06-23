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
			text: 'Arduino 1-15-1 pohyb přerušení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-1_15'
		},
		{
			id: 5,
			level: 2,
			text: 'Arduino 10 7 segment 4 digits s DHT11',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-10-7'
		},
		{
			id: 6,
			level: 2,
			text: 'GDPR souhrn',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'
		},
		{
			id: 7,
			level: 2,
			text: 'GDPR Technická opatření',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni'
		},
		{
			id: 8,
			level: 2,
			text: 'Operační systémy základní součásti operačního systému',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system'
		},
		{
			id: 9,
			level: 2,
			text: 'Mac OS část 1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1'
		},
		{
			id: 10,
			level: 2,
			text: 'Mac OS část 1.2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2'
		},
		{
			id: 11,
			level: 2,
			text: 'Mac OS část 1.4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail'
		},
		{
			id: 12,
			level: 2,
			text: 'Mac OS část 1.7',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal'
		},
		{
			id: 13,
			level: 2,
			text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz'
		},
		{
			id: 14,
			level: 2,
			text: 'Operační systémy Windows Ovladače zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
		},
		{
			id: 15,
			level: 2,
			text: 'Operační systémy Win_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1'
		},
		{
			id: 16,
			level: 2,
			text: 'Operační systémy Win_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2'
		},
		{
			id: 17,
			level: 2,
			text: 'Operační systémy Win_3',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3'
		},
		{
			id: 18,
			level: 2,
			text: 'Operační systémy Win_4_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2'
		},
		{
			id: 19,
			level: 2,
			text: 'Operační systémy Win_4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4'
		},
		{
			id: 20,
			level: 2,
			text: 'Operační systémy Win_5_MMC',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC'
		},
		{
			id: 21,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_1_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz'
		},
		{
			id: 22,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_3_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz'
		},
		{
			id: 23,
			level: 2,
			text: 'Operační systémy Win_7_Windows_Server',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server'
		},
		{
			id: 24,
			level: 2,
			text: 'Operační systémy Win_8_Sprava_aplikaci_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1'
		},
		{
			id: 25,
			level: 2,
			text: 'Operační systémy Win_9_1_Firewall',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall'
		},
		{
			id: 26,
			level: 2,
			text: 'Souborove systemy 1_Windows',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows'
		}
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Windows – část 7.3: Diagnostika sítě – Ping a Tracert</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz/Exam-Operacni_systemy_Win_7_1_sit_3_cz"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📶 Příkaz <code>ping</code> – test dostupnosti sítě</h2>
				<ul>
					<li>Slouží ke zjištění, zda je cílový počítač (host) dosažitelný</li>
					<li>Odesílá pakety ICMP(na určitou IP adresu v síti) zprávy typu <code>Echo Request</code> a čeká na <code>Echo Reply</code></li>
					<li><strong>Užitečný pro:</strong>
						<ul>
							<li>Diagnostiku síťových problémů</li>
							<li>Zjištění latence (odezvy v ms)</li>
							<li>Kontrolu ztráty paketů</li>
						</ul>
					</li>
					<li>Příklad: <code>ping www.seznam.cz</code> nebo <code>ping 8.8.8.8</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>Poznámky k <code>ping</code></h2>
				<ul>
					<li><strong>ICMP (Internet Control Message Protocol)</strong> je protokol sítě TCP/IP používaný pro odesílání chybových a stavových zpráv (např. „hostitel nedostupný“)</li>
					<li>Na rozdíl od TCP/UDP není určen pro přenos dat, ale pro diagnostiku a řízení sítě</li>
					<li>Příkaz <code>ping</code> využívá ICMP zprávy <code>Echo Request</code> a <code>Echo Reply</code> ke zjištění:
						<ul>
							<li>zda je cílový počítač dosažitelný</li>
							<li>jak dlouho trvá doručení a návrat paketů (latence)</li>
						</ul>
					</li>
					<li>Funguje podobně jako sonar: pošle "ozvěnu" a čeká na odpověď</li>
					<li>Používá se pro testování připojení v místní síti i na internetu</li>
					<li><strong>Odezva</strong> ukáže rychlost spojení a případnou ztrátu paketů</li>
					<li>Lze použít ve Windows (CMD, PowerShell), macOS (Terminál) i Linuxu</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Pokročilé použití <code>ping</code></h2>
				<ul>
					<li><code>-t</code> – pingování bez konce (zastavíš Ctrl + C)</li>
					<li><code>-4</code> – použije protokol IPv4</li>
					<li><code>-6</code> – použije protokol IPv6</li>
					<li>Kombinace parametrů: <code>ping seznam.cz -4 -t</code></li>
					<li><code>/?</code> – zobrazí dostupné parametry příkazu <code>ping</code></li>
					<li>Přesměrování výstupu do souboru: <code>ping seznam.cz > vysledek.txt</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>📈 Význam výstupu příkazu <code>ping</code></h2>
				<ul>
					<li><strong>Odezva:</strong> měří čas (v ms), za který paket dorazí zpět</li>
					<li><strong>Ztráta paketů:</strong> vyjádřena v % – např. 25 % = 1 z 4 paketů nedošel</li>
					<li><strong>TTL (Time To Live):</strong> určuje počet "hopů", které paket může projít</li>
					<li><strong>Vysoké RTT</strong> nebo <strong>ztráta paketů</strong> = slabá nebo přetížená síť</li>
				</ul>
			</section>

			<section class="note">
				<h2>📊 Analýza ztráty paketů</h2>
				<ul>
					<li><strong>32 % ztráta</strong> = velmi špatné spojení</li>
					<li>Možné příčiny:
						<ul>
							<li>Slabý Wi-Fi signál nebo rušení</li>
							<li>Vadné kabely nebo síťové karty</li>
							<li>Přetížená síť (např. v určitou denní dobu)</li>
							<li>Vadný nebo přetížený router</li>
						</ul>
					</li>
					<li>Testuj na různých místech, s různými zařízeními a v různý čas</li>
				</ul>
			</section>

			<section class="note">
				<h2>📡 Příkaz <code>tracert</code> – sledování cesty paketů</h2>
				<ul>
					<li>Ukazuje cestu, kterou paket urazí přes směrovače až ke svému cíli</li>
					<li>Pomáhá identifikovat:
						<ul>
							<li>kde dochází ke zpoždění</li>
							<li>kde se pakety ztrácí</li>
							<li>jak dlouho trvá překonat jednotlivé routery (latence)</li>
						</ul>
					</li>
					<li>Příklad: <code>tracert google.com</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>🧾 Parametry příkazu <code>tracert</code></h2>
				<ul>
					<li><code>-d</code> – nezobrazuje názvy hostitelů, jen IP adresy (rychlejší)</li>
					<li><code>-h X</code> – nastaví maximální počet skoků (např. <code>-h 20</code>)</li>
					<li><code>-w X</code> – nastaví timeout v milisekundách (např. <code>-w 2000</code>)</li>
					<li><code>-4</code> / <code>-6</code> – vynutí použití IPv4 nebo IPv6</li>
					<li>Příklad kombinace: <code>tracert -h 15 -w 2000 example.com</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>🔁 Co jsou hops (skoky) a TTL</h2>
				<ul>
					<li><strong>Hop:</strong> jeden router, přes který paket projde</li>
					<li><strong>TTL (Time To Live):</strong> každým hopem se TTL sníží o 1</li>
					<ul>
						<li>Omezuje životnost paketů v síti</li>
					</ul>
					<li>Když TTL dosáhne 0, paket je zahozen → Tracert z toho získá odezvu</li>
					<li>Tracert zvyšuje TTL po jednom a tím mapuje cestu přes všechny routery</li>
					<li><strong>Příklad:</strong> TTL=1 → 1. router odpoví; TTL=2 → 2. router odpoví atd.</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_7_1_sit_3_cz.pdf" class="ButtonExam" download>
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
