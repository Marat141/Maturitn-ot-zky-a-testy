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

<!-- ... tvojí <script> sekce zůstává beze změny -->

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="CSS-Notes">
				<h1>CSS – poznámky</h1>

				<h2>Co je CSS?</h2>
				<p>
					CSS (Cascading Style Sheets) určuje vzhled HTML prvků – barvy, písma, rozvržení, animace…
				</p>

				<h2>Proč „kaskádové“?</h2>
				<p>Styly se dědí a přepisují podle priority:</p>
				<ol>
					<li>Výchozí prohlížeče</li>
					<li>Externí CSS <code>&lt;link&gt;</code></li>
					<li>Interní CSS <code>&lt;style&gt;</code></li>
					<li>Inline <code>style=""</code></li>
					<li><code>!important</code> má nejvyšší prioritu</li>
				</ol>

				<h2>Jak připojit CSS</h2>
				<ul>
					<li>Externě: <code>&lt;link rel="stylesheet" href="style.css"&gt;</code></li>
					<li>
						Interně:
						<pre><code
								>&lt;style&gt;
  body &#123; background-color: lightblue; &#125;
&lt;/style&gt;
</code></pre>
						<p><em>Vložený CSS styl, který nastaví světle modré pozadí pro celou stránku.</em></p>
					</li>
					<li>Inline: <code>&lt;p style="color:red;"&gt;</code></li>
				</ul>

				<h2>Základní syntaxe</h2>
				<pre><code
						>selektor &#123;
  vlastnost: hodnota;
&#125;</code
					></pre>
				<p><em>Obecná struktura CSS pravidla – definuje, jak se mají prvky chovat.</em></p>

				<h2>Barvy</h2>
				<pre><code
						>color: red;
background-color: #f0f0f0;</code
					></pre>
				<p><em>Nastaví červenou barvu textu a světle šedé pozadí.</em></p>

				<h2>Text</h2>
				<pre><code
						>font-family: Arial, sans-serif;
font-size: 18px;
font-weight: bold;
text-align: center;
text-decoration: underline;</code
					></pre>
				<p>
					<em>Nastaví písmo Arial, velikost 18px, tučný styl, zarovnání na střed a podtržení.</em>
				</p>

				<h2>Okraje a výplně</h2>
				<pre><code
						>margin: 20px;     /* vnější mezera */
padding: 10px;    /* vnitřní mezera */
border: 1px solid black;</code
					></pre>
				<p><em>Ohraničí prvek černým rámečkem, přidá mezery uvnitř i vně prvku.</em></p>

				<h2>Velikost a pozice</h2>
				<pre><code
						>width: 300px;
height: auto;
position: relative / absolute / fixed / sticky;</code
					></pre>
				<p><em>Nastavuje šířku prvku a typ pozicování v layoutu.</em></p>

				<h2>Zobrazovací režimy (display)</h2>
				<pre><code
						>display: block;
display: inline;
display: flex;
display: grid;</code
					></pre>
				<p>
					<em>Určuje, jak se prvek zobrazí – jako blok, řádkový, flexbox nebo grid kontejner.</em>
				</p>

				<h2>Flexbox</h2>
				<pre><code
						>.container &#123;
  display: flex;
  justify-content: center;
  align-items: center;
&#125;</code
					></pre>
				<p><em>Flexbox zarovná vnitřní prvky doprostřed vodorovně i svisle.</em></p>

				<h2>Grid Layout</h2>
				<pre><code
						>.container &#123;
  display: grid;
  grid-template-columns: 1fr 2fr;
&#125;</code
					></pre>
				<p><em>Grid rozloží prvky do dvou sloupců – první má 1 díl, druhý 2 díly prostoru.</em></p>

				<h2>Responsivní design</h2>
				<pre><code
						>@media (max-width: 600px) &#123;
  body &#123;
    background-color: pink;
  &#125;
&#125;</code
					></pre>
				<p><em>Při zmenšení obrazovky pod 600px změní pozadí stránky na růžovou.</em></p>

				<h2>Animace a přechody</h2>
				<pre><code
						>button &#123;
  transition: background-color 0.3s ease;
&#125;
button:hover &#123;
  background-color: yellow;
&#125;</code
					></pre>
				<p>
					<em>Při přejetí myší se barva tlačítka plynule změní na žlutou během 0.3 sekundy.</em>
				</p>

				<h2>!important</h2>
				<pre><code
						>p &#123;
  color: red !important;
&#125;</code
					></pre>
				<p>
					<em
						>Nutí prohlížeč použít červenou barvu textu i přes ostatní konkurenční styly. Má
						nejvyšší prioritu.</em
					>
				</p>

				<h2>Důležité pojmy pro maturitu</h2>
				<ul>
					<li><strong>CSS (Cascading Style Sheets)</strong> – jazyk pro popis vzhledu HTML</li>
					<li>
						<strong>Selektor</strong> – vybere HTML prvek (např. <code>p</code>, <code>#id</code>,
						<code>.trida</code>)
					</li>
					<li>
						<strong>Vlastnost (property)</strong> – co chceme změnit (např. <code>color</code>)
					</li>
					<li><strong>Hodnota (value)</strong> – konkrétní nastavení (např. <code>red</code>)</li>
					<li>
						<strong>Box model</strong> – každý prvek má
						<code>margin → border → padding → content</code>
					</li>
					<li><strong>Responzivní design</strong> – přizpůsobení webu různým zařízením</li>
					<li>
						<strong>Display</strong> – způsob zobrazení prvku (např. <code>block</code>,
						<code>inline</code>, <code>flex</code>)
					</li>
					<li><strong>Flexbox</strong> – snadné zarovnání prvků v kontejneru</li>
					<li><strong>Grid</strong> – rozložení prvků do mřížky</li>
					<li>
						<strong>Pseudo-třídy</strong> – stavové styly (např. <code>:hover</code>,
						<code>:focus</code>)
					</li>
					<li><strong>Přechody (transitions)</strong> – animace mezi dvěma stavy</li>
					<li><strong>Media Queries</strong> – podmíněné styly podle velikosti obrazovky</li>
					<li>
						<strong>Priorita stylů</strong> – <code>!important</code> přebije vše, jinak platí pořadí
						stylů
					</li>
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

	.CSS-Notes {
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

	ul,
	ol {
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

	@media (max-width: 768px) {
		.layout {
			flex-direction: column;
		}

		.content {
			padding: 24px;
		}
	}
</style>
