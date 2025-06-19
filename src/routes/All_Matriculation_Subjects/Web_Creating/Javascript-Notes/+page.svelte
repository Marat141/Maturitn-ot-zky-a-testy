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
			<div class="JavaScript-Notes">
				<h1>JavaScript – poznámky</h1>

				<h2>Co je JavaScript?</h2>
				<p>
					JavaScript je programovací jazyk pro webové stránky. Umožňuje vytvářet interaktivitu –
					klikání, změny obsahu, formuláře, výpočty a dynamiku.
				</p>

				<h2>Základní syntaxe</h2>
				<pre><code
						>let jmeno = "Petr";
const vek = 18;
var prijmeni = "Novák";</code
					></pre>
				<p>
					<em
						>Deklarace proměnných – <code>let</code> a <code>const</code> jsou moderní a doporučené.</em
					>
				</p>

				<h2>Datové typy</h2>
				<ul>
					<li><code>string</code> – text (např. <code>"ahoj"</code>)</li>
					<li><code>number</code> – číslo (např. <code>42</code>)</li>
					<li><code>boolean</code> – pravda/nepravda (<code>true</code>, <code>false</code>)</li>
					<li><code>null</code> a <code>undefined</code></li>
					<li><code>object</code>, <code>array</code>, <code>function</code></li>
				</ul>

				<h2>Operátory</h2>
				<pre><code
						>+  -  *  /  %   // matematika
== === != !==  // porovnání
&& || !        // logické
++ -- += -=    // zkrácené zápisy</code
					></pre>
				<p>
					<em>Rozdíl: <code>===</code> porovnává i datový typ, <code>==</code> jen hodnotu.</em>
				</p>

				<h2>Podmínky</h2>
				<pre><code
						>if (vek &gt;= 18) &#123;
	console.log("Dospělý");
&#125; else &#123;
	console.log("Nezletilý");
&#125;</code
					></pre>
				<p>
					<em>Rozhodovací konstrukce – <code>if</code>, <code>else if</code>, <code>else</code>.</em
					>
				</p>

				<h2>Cyklus for</h2>
				<pre><code
						>for (let i = 0; i &lt; 5; i++) &#123;
	console.log(i);
&#125;</code
					></pre>
				<p><em>Cyklus s počítadlem – provede kód 5× (i = 0 až 4).</em></p>

				<h2>Cyklus while</h2>
				<pre><code
						>let i = 0;
while (i &lt; 3) &#123;
	console.log(i);
	i++;
&#125;</code
					></pre>
				<p><em>Opakuje kód, dokud je podmínka pravdivá.</em></p>

				<h2>Funkce</h2>
				<pre><code
						>function secti(a, b) &#123;
	return a + b;
&#125;</code
					></pre>
				<p><em>Funkce = pojmenovaný blok kódu, který může vracet hodnotu.</em></p>

				<h2>Události</h2>
				<pre><code
						>&lt;button onclick="pozdrav()"&gt;Klikni&lt;/button&gt;

&lt;script&gt;
	function pozdrav() &#123;
		alert("Ahoj!");
	&#125;
&lt;/script&gt;</code
					></pre>
				<p><em>Interaktivita pomocí událostí (např. <code>onclick</code>).</em></p>

				<h2>Práce s DOM</h2>
				<pre><code>document.getElementById("nadpis").innerText = "Změněno";</code></pre>
				<p><em>Manipulace s HTML – změní text v elementu s ID "nadpis".</em></p>

				<h2>Pole (Array)</h2>
				<pre><code
						>let ovoce = ["jablko", "banán", "hruška"];
console.log(ovoce[1]); // "banán"</code
					></pre>
				<p><em>Pole = seznam hodnot. Indexování začíná od 0.</em></p>

				<h2>Objekt</h2>
				<pre><code
						>let osoba = &#123;
	jmeno: "Petr",
	vek: 20
&#125;;
console.log(osoba.jmeno);</code
					></pre>
				<p><em>Objekt uchovává více hodnot pomocí klíč–hodnota.</em></p>

				<h2>Moderní zápis – Arrow funkce</h2>
				<pre><code>const secti = (a, b) =&gt; a + b;</code></pre>
				<p><em>Zkrácený zápis funkce pomocí tzv. "šipek".</em></p>

				<h2>Shrnutí – proč je JS důležitý?</h2>
				<ul>
					<li>Umožňuje interaktivní web</li>
					<li>Reaguje na kliknutí, vstupy, formuláře</li>
					<li>Umí načítat data a dynamicky měnit obsah</li>
					<li>Je univerzální – používá se i na serveru (Node.js)</li>
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

	.JavaScript-Notes {
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
		background-color: #fef3c7;
		border-radius: 4px;
		padding: 2px 6px;
		font-family: 'Fira Code', monospace;
		font-size: 0.95rem;
		color: #92400e;
	}

	pre {
		background-color: #1e293b;
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

	em {
		color: #475569;
		display: block;
		margin-top: -1rem;
		margin-bottom: 1.5rem;
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
