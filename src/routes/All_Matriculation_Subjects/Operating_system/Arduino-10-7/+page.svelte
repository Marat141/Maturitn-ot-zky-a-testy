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
				<h1>Arduino: 4místný 7segmentový displej s čidlem DHT11</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Arduino-10-7/Exam_Arduino-10-7"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section>
				<h2>📟 Cíl projektu</h2>
				<p>
					Zobrazit aktuální teplotu ze senzoru <strong>DHT11</strong> na
					<strong>4místném 7segmentovém displeji</strong> pomocí Arduina.
				</p>
			</section>

			<section>
				<h2>🔌 Zapojení komponent</h2>

				<h3>Displej (typ 5641AS)</h3>
				<ul>
					<li><strong>Typ:</strong> společná katoda</li>
					<li><strong>Napětí:</strong> 1.8–2.2 V</li>
					<li><strong>Rezistory:</strong> 330Ω na každý segment</li>
				</ul>

				<h4>Piny pro číslice:</h4>
				<ul>
					<li>Pin 12 → D12</li>
					<li>Pin 9 → D9</li>
					<li>Pin 8 → D8</li>
					<li>Pin 6 → D6</li>
				</ul>

				<h4>Piny pro segmenty (přes 330Ω):</h4>
				<ul>
					<li>A (pin 11) → D11</li>
					<li>B (pin 7) → D7</li>
					<li>C (pin 4) → D4</li>
					<li>D (pin 2) → D3</li>
					<li>E (pin 1) → A1</li>
					<li>F (pin 10) → A2</li>
					<li>G (pin 5) → A3</li>
					<li>DP (pin 3) → A4</li>
				</ul>

				<h3>Senzor DHT11:</h3>
				<ul>
					<li>DATA (levý) → D5</li>
					<li>VCC (střední) → 5V</li>
					<li>GND (pravý) → GND</li>
				</ul>
			</section>

			<section>
				<h2>📚 Použité knihovny</h2>
				<ul>
					<li class="Arduino-DHT">
						<strong>DHT Sensor Library:</strong>
						<a
							href="https://www.arduino.cc/reference/en/libraries/dht-sensor-library/"
							target="_blank">Arduino DHT</a
						>
					</li>
					<li>
						<strong>SevSeg:</strong>
						<a href="https://github.com/DeanIsMe/SevSeg" target="_blank">GitHub – SevSeg</a>
					</li>
				</ul>
			</section>

			<section>
				<h2>💾 Ukázka kódu</h2>
				<pre><code>
#include &lt;DHT.h&gt;
#include &lt;SevSeg.h&gt;

#define DHTPIN 5
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);
SevSeg sevseg;

void setup() &#123;
	byte numDigits = 4;
	byte digitPins[] = &#123;12, 9, 8, 6&#125;;
	byte segmentPins[] = &#123;11, 7, 4, 3, A1, A2, A3, A4&#125;;

	bool resistorsOnSegments = true;
	byte hardwareConfig = COMMON_CATHODE;

	sevseg.begin(hardwareConfig, numDigits, digitPins, segmentPins, resistorsOnSegments);
	sevseg.setBrightness(90);

	dht.begin();
&#125;

void loop() &#123;
	float teplota = dht.readTemperature();
	sevseg.setNumber(teplota, 1); // zobrazí např. 23.1
	sevseg.refreshDisplay();
	delay(500);
&#125;
				</code></pre>
			</section>

			<section>
				<h2>🧠 Shrnutí</h2>
				<table>
					<thead>
						<tr>
							<th>Komponenta</th>
							<th>Funkce</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>7segmentový displej</td>
							<td>Zobrazuje teplotu</td>
						</tr>
						<tr>
							<td>DHT11</td>
							<td>Měří teplotu (°C)</td>
						</tr>
						<tr>
							<td>SevSeg</td>
							<td>Knihovna pro řízení segmentů</td>
						</tr>
					</tbody>
				</table>
			</section>
			<a href="/PDF/Arduino_10_7_segment_4_digits_s_DHT11.pdf" class="ButtonExam" download>
				📄 Stáhnout PDF
			</a>
		</div>
	</div>
</main>

<style>
	.layout {
		display: flex;
		gap: 32px;
	}
	.content {
		flex: 1;
		padding: 32px;
		background: rgba(255, 255, 255, 0.85);
		border-radius: 16px;
		box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
		font-family: 'Inter', system-ui, sans-serif;
		color: #1f2937;
	}
	h1 {
		font-size: 2rem;
		margin-bottom: 1rem;
	}
	h2 {
		color: #d35;
		margin-top: 2rem;
	}
	pre {
		background-color: #f0f0f0;
		padding: 1rem;
		border-radius: 5px;
		overflow-x: auto;
	}
	code {
		font-family: 'Fira Code', monospace;
		white-space: pre;
	}
	table {
		width: 100%;
		border-collapse: collapse;
		margin-top: 1rem;
	}
	th,
	td {
		padding: 0.5rem;
		border: 1px solid #ccc;
		text-align: left;
	}
	.header-with-button {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 16px;
	}

	.Arduino-DHT {
		margin-bottom: 20px;
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
