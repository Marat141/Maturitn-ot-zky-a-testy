<script lang="ts">
	import Navigation from '$lib/Components/Navigation.svelte';

	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
		path?: string;
	}

	let headings: Heading[] = [
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
		}
	];
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Arduino: Detekce pohybu – PIR HC-SR501 + 7-segmentový displej</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Arduino-1_15/Exam_Arduino-1_15"
					class="ButtonExam">Napsat si test</a
				>
			</div>
			<section>
				<h2>🧪 Varianta 1 – Zobrazení „1111“ při pohybu</h2>
				<p>
					Projekt detekuje pohyb pomocí senzoru <strong>HC-SR501</strong> a na čtyřmístném
					7-segmentovém displeji zobrazí <strong>„1111“</strong>. Jakmile pohyb zmizí, zobrazí se
					<strong>„0000“</strong>.
				</p>

				<ul>
					<li><strong>OUT</strong> pin senzoru je připojen na <code>D5</code></li>
					<li>Displej je řízen pomocí knihovny <code>SevSeg</code></li>
					<li>Používá se přerušení: <code>attachInterrupt(...)</code></li>
				</ul>

				<pre><code>
// ISR funkce
void ISR_PIR() &#123;
	pohybDetekovan = true;
&#125;

// Hlavní smyčka
if (pohybDetekovan) &#123;
	sevseg.setNumber(1111);
	delay(5000);
	pohybDetekovan = false;
&#125; else &#123;
	sevseg.setNumber(0000);
&#125;
				</code></pre>
			</section>

			<section>
				<h2>⏱️ Varianta 2 – Čas od posledního pohybu</h2>
				<p>
					Tato varianta zobrazuje na displeji počet sekund od poslední detekce pohybu. Nový pohyb
					resetuje displej zpět na <strong>„0000“</strong>.
				</p>

				<pre><code>
unsigned long casOdPoslednihoPohybu = (millis() - posledniPohybCas) / 1000;
sevseg.setNumber(casOdPoslednihoPohybu);
				</code></pre>

				<p>
					Zobrazovaný čas se aktualizuje každou sekundu pomocí <code>delay(1000)</code>. Velmi dobré
					jako základ pro měření prostojů nebo reakční doby.
				</p>
			</section>

			<section>
				<h2>📚 Shrnutí</h2>
				<table>
					<thead>
						<tr>
							<th>Vlastnost</th>
							<th>Varianta 1</th>
							<th>Varianta 2</th>
						</tr>
					</thead>
					<tbody>
						<tr>
							<td>Zobrazení</td>
							<td>„1111“ / „0000“</td>
							<td>Čas od pohybu (v s)</td>
						</tr>
						<tr>
							<td>Přerušení</td>
							<td>✔️</td>
							<td>✔️</td>
						</tr>
						<tr>
							<td>Složitost</td>
							<td>základní</td>
							<td>pokročilá (časování)</td>
						</tr>
					</tbody>
				</table>
			</section>
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

	.header-with-button h1 {
		margin: 0;
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
</style>
