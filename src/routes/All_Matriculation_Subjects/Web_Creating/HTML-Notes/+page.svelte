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
		{
			id: 1,
			text: 'Tvorba webových stránek',
			level: 1,
			path: '/All_Matriculation_Subjects/Web_Creating'
		},
		{ id: 2, text: 'HTML', level: 1, path: '/All_Matriculation_Subjects/Web_Creating/HTML-Notes' },
		{ id: 3, text: 'CSS', level: 1, path: '/All_Matriculation_Subjects/Web_Creating/CSS-Notes' },
		{
			id: 4,
			text: 'JavaScript',
			level: 1,
			path: '/All_Matriculation_Subjects/Web_Creating/Javascript-Notes'
		},
		{ id: 5, text: 'PHP', level: 1, path: '/All_Matriculation_Subjects/Web_Creating/PHP-Notes' }
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="HTML-Notes">
				<h1>HTML - poznámky</h1>
				<h2>Co je HTML</h2>
				<p>
					HTML (HyperText Markup Language) je značkovací jazyk, který slouží k tvorbě a
					strukturování obsahu webových stránek. Nevytváří "design", ale strukturu – říká, co je
					nadpis, co je obrázek, co je odkaz apod.
				</p>
				<h2>Historie HTML</h2>
				<ul>
					<li><strong>HTML 1.0 (1991)</strong> – základní značky</li>
					<li><strong>HTML 4.01 (1999)</strong> – formuláře, tabulky, skriptování</li>
					<li><strong>HTML5 (2014)</strong> – nové sémantické značky, video/audio, responzivita</li>
				</ul>
				<h2>Vlastnosti HTML</h2>
				<ul>
					<li>Nezávislé na platformě (běží v každém prohlížeči)</li>
					<li>Strukturuje obsah: nadpisy, odstavce, seznamy, tabulky</li>
					<li>Podpora multimédií (obrázky, video, audio)</li>
					<li>Umožňuje vkládání skriptů (např. JavaScript)</li>
					<li>Spolupráce s CSS a JavaScriptem</li>
				</ul>

				<h2>Tagy (značky)</h2>
				<p>
					HTML používá otevírací a zavírací tagy, např. <code>&lt;h1&gt;Titulek&lt;/h1&gt;</code>
				</p>
				<p>
					Některé tagy jsou samouzavírací, např. <code>&lt;br&gt;</code> nebo
					<code>&lt;img&gt;</code>
				</p>

				<h2>Sémantika HTML</h2>
				<p>
					Sémantické HTML používá tagy s významem: <code>&lt;article&gt;</code> (článek),
					<code>&lt;nav&gt;</code>
					(navigace), <code>&lt;footer&gt;</code> (patička), <code>&lt;section&gt;</code> (sekce)
				</p>

				<h2>Struktura HTML dokumentu</h2>
				<ul>
					<li><code>&lt;!DOCTYPE html&gt;</code> – definuje HTML5</li>
					<li><code>&lt;html&gt;</code> – začátek dokumentu</li>
					<li><code>&lt;head&gt;</code> – hlavička (meta, title, CSS, JS)</li>
					<li><code>&lt;body&gt;</code> – tělo stránky</li>
				</ul>

				<h2>Vnořování tagů</h2>
				<p>
					Tagy mohou být vnořené, např. <code
						>&lt;p&gt;Tohle je &lt;strong&gt;důležité&lt;/strong&gt; slovo.&lt;/p&gt;</code
					>
				</p>

				<h2>Formuláře</h2>
				<p>HTML umožňuje vytvářet formuláře pomocí tagu <code>&lt;form&gt;</code>.</p>
				<pre><code
						>&lt;form action="/odeslat" method="post"&gt;
  &lt;label for="jmeno"&gt;Jméno:&lt;/label&gt;
  &lt;input type="text" id="jmeno" name="jmeno"&gt;
  &lt;input type="submit" value="Odeslat"&gt;
&lt;/form&gt;
</code></pre>

				<h2>Tabulky</h2>
				<p>
					Tabulky se tvoří pomocí <code>&lt;table&gt;</code>, <code>&lt;tr&gt;</code> (řádky),
					<code>&lt;td&gt;</code>
					(buňky), <code>&lt;th&gt;</code> (záhlaví).
				</p>
				<pre><code
						>&lt;table&gt;
  &lt;thead&gt;
    &lt;tr&gt;&lt;th&gt;Jméno&lt;/th&gt;&lt;th&gt;Věk&lt;/th&gt;&lt;/tr&gt;
  &lt;/thead&gt;
  &lt;tbody&gt;
    &lt;tr&gt;&lt;td&gt;Anna&lt;/td&gt;&lt;td&gt;20&lt;/td&gt;&lt;/tr&gt;
  &lt;/tbody&gt;
&lt;/table&gt;
</code></pre>

				<h2>Vkládání videa a audia</h2>
				<pre><code
						>&lt;video controls width="300"&gt;
  &lt;source src="video.mp4" type="video/mp4"&gt;
&lt;/video&gt;

&lt;audio controls&gt;
  &lt;source src="zvuk.mp3" type="audio/mpeg"&gt;
&lt;/audio&gt;
</code></pre>

				<h2>Komentáře</h2>
				<p>V HTML píšeme komentáře takto:</p>
				<pre><code>&lt;!-- Toto je komentář --&gt;</code></pre>

				<h2>Odkazy</h2>
				<pre><code>&lt;a href="https://example.com" target="_blank"&gt;Externí odkaz&lt;/a&gt;</code
					></pre>

				<h2>Seznamy</h2>
				<p>HTML podporuje očíslované i nečíslované seznamy:</p>
				<pre><code
						>&lt;ul&gt;
  &lt;li&gt;První položka&lt;/li&gt;
  &lt;li&gt;Druhá položka&lt;/li&gt;
&lt;/ul&gt;

&lt;ol&gt;
  &lt;li&gt;Krok 1&lt;/li&gt;
  &lt;li&gt;Krok 2&lt;/li&gt;
&lt;/ol&gt;
</code></pre>

				<h2>Rozdíl HTML vs. CSS vs. JavaScript</h2>
				<table>
					<thead>
						<tr><th>Jazyk</th><th>Účel</th></tr>
					</thead>
					<tbody>
						<tr><td>HTML</td><td>Struktura stránky</td></tr>
						<tr><td>CSS</td><td>Vzhled stránky</td></tr>
						<tr><td>JavaScript</td><td>Interaktivita a funkčnost</td></tr>
					</tbody>
				</table>

				<h2>Validita HTML</h2>
				<p>
					Kód by měl být validní (bez chyb), lze ověřit např. na <a
						href="https://validator.w3.org"
						target="_blank">validator.w3.org</a
					>
				</p>

				<h2>Proč je HTML důležité</h2>
				<ul>
					<li>Základ webových stránek</li>
					<li>Zajišťuje přístupnost (čtečky obrazovky atd.)</li>
					<li>Umožňuje strukturovat a upravit design pomocí CSS</li>
				</ul>
			</div>
		</div>
	</div>
</main>

<style>
	main {
		font-family: 'Inter', sans-serif;
		color: #1e293b; 
		background-color: #f8fafc;
		padding: 40px 24px;
	}

	.layout {
		display: flex;
		flex-wrap: wrap;
		gap: 32px;
		align-items: flex-start;
	}

	.content {
		flex: 3 1 600px;
		background: #ffffff;
		padding: 32px;
		border-radius: 16px;
		box-shadow: 0 6px 24px rgba(0, 0, 0, 0.06);
	}

	.HTML-Notes {
		max-width: 100%;
	}

	h1 {
		font-size: 2.25rem;
		margin-bottom: 1.5rem;
		color: #0f172a; 
		border-bottom: 3px solid #38bdf8; 
		padding-bottom: 0.5rem;
	}

	h2 {
		font-size: 1.5rem;
		margin-top: 2.5rem;
		margin-bottom: 1rem;
		color: #0369a1; 
	}

	p {
		line-height: 1.7;
		margin-bottom: 1rem;
	}

	ul {
		margin-left: 1.5rem;
		margin-bottom: 1rem;
	}

	li {
		margin-bottom: 0.5rem;
	}

	code {
		background-color: #f1f5f9; 
		border-radius: 4px;
		padding: 2px 6px;
		font-family: 'Fira Code', monospace;
		font-size: 0.95rem;
		color: #dc2626;
	}

	pre {
		background-color: #0f172a; 
		color: #f8fafc; 
		padding: 1rem;
		border-radius: 10px;
		overflow-x: auto;
		margin-bottom: 1.5rem;
		font-size: 0.95rem;
	}

	pre code {
		background: none;
		color: inherit;
		padding: 0;
	}

	table {
		width: 100%;
		border-collapse: collapse;
		margin: 1.5rem 0;
	}

	thead {
		background-color: #e0f2fe; 
	}

	th,
	td {
		border: 1px solid #cbd5e1; 
		padding: 8px 12px;
		text-align: left;
	}

	th {
		color: #0c4a6e; 
    }

	a {
		color: #0284c7; 
		text-decoration: underline;
	}

	a:hover {
		color: #0369a1;
		text-decoration: none;
	}

	@media (max-width: 768px) {
		.layout {
			flex-direction: column;
		}

		.content {
			padding: 24px;
		}
	}
</style>
