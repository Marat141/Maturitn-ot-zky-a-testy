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
			<div class="PHP-Notes">
				<h1>PHP – poznámky</h1>

				<h2>Co je PHP?</h2>
				<p>PHP (Hypertext Preprocessor) je serverový jazyk určený pro dynamické webové aplikace.</p>

				<h2>Základní syntaxe</h2>
				<pre><code
						>&lt;?php
  echo "Ahoj světe!";
?&gt;</code
					></pre>

				<h2>Proměnné</h2>
				<pre><code
						>$nazev = "hodnota";
$cena = 150;</code
					></pre>

				<h2>Operátory</h2>
				<pre><code
						>$a = 5;
$b = 2;
$c = $a + $b; // 7
$d = $a === 5; // true (porovnání typu i hodnoty)
$e = ($a &gt; 3 &amp;&amp; $b &lt; 5); // true</code
					></pre>

				<h2>Podmínky</h2>
				<pre><code
						>if ($cena &gt; 100) &#123;
  echo "Drahé";
&#125; else &#123;
  echo "Levné";
&#125;</code
					></pre>

				<h2>Cykly</h2>
				<pre><code
						>for ($i = 0; $i &lt; 5; $i++) &#123;
  echo $i;
&#125;</code
					></pre>

				<h2>Funkce</h2>
				<pre><code
						>function secti($a, $b) &#123;
  return $a + $b;
&#125;

$vysledek = secti(2, 3);</code
					></pre>

				<h2>Formuláře</h2>
				<pre><code
						>&lt;form method="POST"&gt;
  &lt;input name="jmeno" /&gt;
&lt;/form&gt;

&lt;?php
  $jmeno = $_POST["jmeno"] ?? "";
?&gt;</code
					></pre>

				<h2>Pole a foreach</h2>
				<pre><code
						>$pole = ["jablko", "hruška"];
foreach ($pole as $ovoce) &#123;
  echo $ovoce;
&#125;</code
					></pre>

				<h2>Funkce pro práci s polem</h2>
				<pre><code
						>$ovoce = ["jablko", "banán"];
array_push($ovoce, "hruška");
$pocet = count($ovoce);</code
					></pre>

				<h2>Asociativní pole</h2>
				<pre><code
						>$osoba = ["jmeno" =&gt; "Karel", "vek" =&gt; 20];
echo $osoba["jmeno"];</code
					></pre>

				<h2>Superglobální proměnné</h2>
				<pre><code
						>$_GET, $_POST, $_SESSION, $_COOKIE, $_FILES, $_SERVER

echo $_SERVER["REQUEST_METHOD"];</code
					></pre>

				<h2>Validace a bezpečnost</h2>
				<pre><code
						>if (isset($_POST["email"])) &#123;
  $email = filter_var($_POST["email"], FILTER_VALIDATE_EMAIL);
&#125;

$jmeno = htmlspecialchars($_POST["jmeno"] ?? "");</code
					></pre>

				<h2>SQL Injection – ochrana</h2>
				<pre><code
						>$stmt = $conn-&gt;prepare("SELECT * FROM uzivatele WHERE email = ?");
$stmt-&gt;bind_param("s", $email);
$stmt-&gt;execute();</code
					></pre>

				<h2>Soubory</h2>
				<pre><code
						>$s = fopen("soubor.txt", "r");
$text = fread($s, filesize("soubor.txt"));
fclose($s);</code
					></pre>

				<h2>MySQLi</h2>
				<pre><code
						>$conn = new mysqli("localhost", "root", "", "skola");
$res = $conn-&gt;query("SELECT * FROM tabulka");
while ($radek = $res-&gt;fetch_assoc()) &#123;
  echo $radek["jmeno"];
&#125;</code
					></pre>

				<h2>Session a Cookie</h2>
				<pre><code
						>session_start();
$_SESSION["uzivatel"] = "Petr";

setcookie("jazyk", "cz", time() + 3600);</code
					></pre>

				<h2>Include a require</h2>
				<pre><code
						>include "hlavicka.php";
require "pripojeni.php";</code
					></pre>

				<h2>OOP – třídy</h2>
				<pre><code
						>class Auto &#123;
  public $barva;

  function nastavBarvu($b) &#123;
    $this-&gt;barva = $b;
  &#125;
&#125;

$moje = new Auto();
$moje-&gt;nastavBarvu("modrá");</code
					></pre>

				<h2>Důležité pojmy k maturitě</h2>
				<ul>
					<li><strong>PHP</strong> – serverový jazyk pro weby</li>
					<li><strong>Formuláře</strong> – <code>$_POST</code>, <code>$_GET</code></li>
					<li>
						<strong>Validace</strong> – <code>isset()</code>, <code>htmlspecialchars()</code>,
						<code>filter_var()</code>
					</li>
					<li><strong>Session</strong>, <strong>Cookie</strong></li>
					<li><strong>Databáze</strong> – MySQLi + prepared statements</li>
					<li><strong>Bezpečnost</strong> – XSS, SQL injection</li>
					<li><strong>OOP</strong> – třídy, objekty, metody</li>
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

	.PHP-Notes {
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

	@media (max-width: 768px) {
		.layout {
			flex-direction: column;
		}

		.content {
			padding: 24px;
		}
	}
</style>
