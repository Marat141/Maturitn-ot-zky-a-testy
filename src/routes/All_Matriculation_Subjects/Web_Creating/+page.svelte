<script>
</script>

<main>
	<h1>Tvorba webových stránek</h1>

	<div class="note-area">
		<div class="frontend">
			<h2>🌐 Frontend (klientská strana)</h2>
			<ul>
				<li>Část aplikace, kterou <strong>vidí a používá uživatel</strong></li>
				<li>Zahrnuje <strong>grafické rozhraní</strong>, obsah a interakce</li>
				<li>Funguje v <strong>prohlížeči uživatele</strong></li>
				<li>
					Odpovídá za:
					<ul>
						<li>Animace, přechody, responzivní design</li>
					</ul>
				</li>
			</ul>

			<h3>🛠️ Používané technologie</h3>
			<ul>
				<li><strong>HTML</strong> – kostra a obsah stránky</li>
				<li><strong>CSS</strong> – stylování vzhledu</li>
				<li><strong>JavaScript</strong> – chování a dynamika</li>
				<li><strong>SvelteKit, Vue, Angular</strong> – moderní frameworky</li>
			</ul>
		</div>

		<div class="backend">
			<h2>🖥️ Backend (serverová strana)</h2>
			<ul>
				<li>Část aplikace, kterou <strong>uživatel nevidí</strong></li>
				<li>Běží na serveru, zajišťuje logiku a správu dat</li>
				<li>
					Odpovídá za:
					<ul>
						<li>Ukládání, čtení a úpravu dat</li>
						<li>Autentizaci uživatelů</li>
						<li>Bezpečnost a oprávnění</li>
						<li>Komunikace přes API</li>
						<li><strong>API(Application Programming Interface)</strong> umožňuje aplikacím vzájemně se "bavit" a sdílet informace nebo provádět akce.</li>
					</ul>
				</li>
			</ul>

			<h3>🧪 Používané technologie</h3>
			<ul>
				<li><strong>Node.js</strong>, <strong>PHP</strong>, <strong>Python</strong></li>
				<li><strong>Java</strong>, <strong>Ruby</strong></li>
			</ul>
		</div>
		<div class="UXandUI-container">
			<div class="UX">
				<h2>👣 UX – User Experience</h2>
				<p>
					User Experience se zaměřuje na <strong>celkový dojem uživatele</strong> z používání aplikace
					nebo webu. Cílem je, aby byl uživatel spokojený, vše snadno našel a ovládání bylo přirozené.
				</p>
				<ul>
					<li>Struktura webu (informační architektura)</li>
					<li>Logika navigace a interakcí (např. nákupní košík)</li>
					<li>Minimalizace frustrace – intuitivnost, jednoduchost</li>
					<li>Testování použitelnosti (např. user testing, heatmapy)</li>
					<li>Zaměření na potřeby uživatele (UX výzkum, dotazníky)</li>
					<li>Prototypování (wireframy, návrhy před grafikou)</li>
					<li>A/B testování – porovnání dvou variant řešení</li>
				</ul>
			</div>

			<div class="UI">
				<h2>🎨 UI – User Interface</h2>
				<p>
					User Interface se týká <strong>vzhledu a ovládacích prvků</strong>, které uživatel na
					stránce nebo aplikaci přímo vidí a používá. UI design ovlivňuje, jak celá aplikace působí
					vizuálně.
				</p>
				<ul>
					<li>Grafické rozhraní (barvy, písmo, ikony, rozvržení)</li>
					<li>Styl prvků – tlačítka, přepínače, formuláře</li>
					<li>Responzivní design pro mobil, tablet, PC</li>
					<li>Animace, přechody, micro interactions</li>
					<li>Estetika, konzistence napříč aplikací</li>
					<li>Zpětná vazba – hover, kliknutí, načítání</li>
					<li>Přístupnost (barvoslepost, čtečky obrazovky)</li>
					<li>Design systémy – např. Material UI, Tailwind UI</li>
				</ul>
			</div>
		</div>
	</div>
	<div class="URL-structure-container">
		<h2>🌐 Struktura URL</h2>
		<img src="/URL-Structure.png" alt="" />
		<div class="URL-structure-description">
			<h3 style="text-align: center;">Vysvětlení</h3>
			<ul>
				<li>
					<strong>Protocol</strong> – Určuje způsob přenosu dat, například <code>https://</code>
					nebo <code>http://</code>.
				</li>
				<li>
					<strong>Subdomain</strong> – Poddoména, například <code>www</code> nebo
					<code>blog</code>, která je částí domény.
				</li>
				<li>
					<strong>Domain</strong> – Hlavní doménové jméno, například <code>example</code> v
					<code>www.example.com</code>.
				</li>
				<li>
					<strong>TLD</strong> – Top-Level Domain, tedy koncovka domény, jako <code>.com</code>,
					<code>.cz</code> apod.
				</li>
				<li>
					<strong>Subfolder</strong> – Cesta k určité složce na webu, např. <code>/blog/</code>.
				</li>
				<li>
					<strong>Slug</strong> – Přátelská URL pro konkrétní stránku nebo obsah, např.
					<code>/jak-na-svelte</code>.
				</li>
				<li>
					<strong>Parameters</strong> – Dotazy nebo proměnné předávané v URL, např.
					<code>?id=123</code>
					nebo <code>&utm_source=google</code>.
				</li>
			</ul>
		</div>
	</div>
	<div class="note-area">
		<div class="StructureOfWeb">
			<h2>Základní struktura webové stránky</h2>
			<section class="Example-Header">
				<h3>Header (hlavička)</h3>
				<ul>
					<li>Menu</li>
					<li>Logo</li>
					<li>Název menu</li>
				</ul>
				<p>
					Header obsahuje věci jako menu neboli navigaci, potom zde najdeme logo stránky a poté
					název stránky.
				</p>
			</section>
			<section class="Example-main">
				<h3>Obsahová část stránky (main)</h3>
				<ul>
					<li>Hlavní obsah</li>
					<li>Články, obrázky, videa</li>
					<li>Formuláře</li>
				</ul>
				<p>
					Hlavní část stránky obsahuje veškerý obsah, který je pro uživatele důležitý. Může to být
					text, obrázky, videa nebo formuláře.
				</p>
			</section>
			<section class="Example-Footer">
				<h3>Patička (footer)</h3>
				<ul>
					<li>Kontaktní informace</li>
					<li>Odkazy na sociální sítě</li>
					<li>Copyright</li>
				</ul>
				<p>
					Patička stránky obvykle obsahuje kontaktní informace, odkazy na sociální sítě a
					copyrightové informace.
				</p>
			</section>
		</div>
		<h1>Webová stránka</h1>
		<div class="web-info-cards">
			<div class="card">
				<div class="icon orange">📁</div>
				<p>
					Webová stránka je jednoduchý dokument nebo soubor, který je zobrazován v webovém
					prohlížeči.
				</p>
			</div>
			<div class="card">
				<div class="icon gray">🧠</div>
				<p>
					Je obvykle statická, což znamená, že obsah se nemění dynamicky podle uživatelského chování
					nebo vstupů.
				</p>
			</div>
			<div class="card">
				<div class="icon yellow">🎤</div>
				<p>
					Webové stránky jsou často používány k zobrazování informací, jako jsou texty, obrázky,
					odkazy a další obsah.
				</p>
			</div>
			<div class="card">
				<div class="icon blue">📰</div>
				<p>
					Příklady zahrnují webové stránky novinových článků, osobních blogů nebo statických
					prezentací.
				</p>
			</div>
		</div>
	</div>
</main>

<style>
	main {
		text-align: center;
		padding: 32px;
		font-family: 'Inter', sans-serif;
		color: #1f2937;
	}

	h1 {
		color: #2563eb;
		margin-bottom: 24px;
	}

	.note-area {
		display: flex;
		gap: 32px;
		justify-content: center;
		background-color: #f3f4f6;
		padding: 32px;
		border-radius: 12px;
		box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
		flex-wrap: wrap;
	}

	.frontend,
	.backend {
		background-color: #ffffff;
		padding: 24px;
		border-radius: 12px;
		flex: 1 1 300px;
		max-width: 500px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
		text-align: left;
	}

	h2 {
		color: #1d4ed8;
		margin-bottom: 16px;
	}

	h3 {
		margin-top: 16px;
		color: #111827;
	}

	ul {
		padding-left: 20px;
		margin-bottom: 16px;
	}

	ul ul {
		margin-top: 8px;
	}

	li {
		margin-bottom: 6px;
		line-height: 1.5;
	}

	/* UX + UI odděleně pod note-area */
	.UXandUI-container {
		padding: 32px;
		margin-top: 32px;
		border-radius: 12px;
		display: flex;
		flex-wrap: wrap;
		justify-content: space-around;
		text-align: left;
	}

	.UX,
	.UI {
		background-color: #ffffff;
		padding: 24px;
		border-radius: 12px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
		flex: 1 1 400px;
		max-width: 600px;
		margin: 12px;
	}

	.UX h2,
	.UI h2 {
		color: #1d4ed8;
		margin-bottom: 16px;
	}

	.UX p,
	.UI p {
		margin-bottom: 16px;
		line-height: 1.5;
	}

	.UX ul,
	.UI ul {
		padding-left: 20px;
		margin-bottom: 16px;
	}

	.UX li,
	.UI li {
		margin-bottom: 6px;
		line-height: 1.5;
	}

	.URL-structure-container {
		width: 100%;
		margin-top: 32px;
		padding: 32px 16px;
		background-color: #f3f4f6;
		border-radius: 12px;
		box-shadow: 0 8px 20px rgba(0, 0, 0, 0.05);
		border-radius: 12px;
		text-align: left;
	}

	.URL-structure-container h2 {
		color: #0c4a6e;
		margin-bottom: 16px;
		text-align: center;
	}

	.URL-structure-container img {
		display: block;
		margin: 0 auto 24px auto;
		max-width: 100%;
		height: auto;
	}

	.URL-structure-description {
		background-color: #ffffff;
		padding: 24px;
		border-radius: 12px;
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
		max-width: 700px;
		margin: 0 auto;
		text-align: left;
	}

	.URL-structure-description ul {
		padding-left: 20px;
	}

	.URL-structure-description li {
		margin-bottom: 8px;
		line-height: 1.6;
	}
	.StructureOfWeb {
		background-color: #ffffff;
		padding: 24px;
		border-radius: 12px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
		flex: 1 1 100%;
		max-width: 100%;
		text-align: left;
		margin-top: 32px;
	}

	.StructureOfWeb h2 {
		color: #1d4ed8;
		margin-bottom: 24px;
		text-align: center;
	}

	.StructureOfWeb section {
		margin-bottom: 24px;
		background-color: #f9fafb;
		padding: 16px;
		border-radius: 8px;
		box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.03);
	}

	.StructureOfWeb h3 {
		color: #111827;
		margin-bottom: 12px;
	}

	.StructureOfWeb ul {
		padding-left: 20px;
		margin-bottom: 12px;
	}

	.StructureOfWeb li {
		margin-bottom: 6px;
		line-height: 1.5;
	}

	.StructureOfWeb p {
		line-height: 1.6;
		color: #374151;
	}

	.web-info-cards {
		display: flex;
		flex-wrap: wrap;
		gap: 32px;
		justify-content: center;
		margin-top: 32px;
		width: 100%;
	}

	.web-info-cards .card {
		background-color: #ffffff;
		padding: 24px;
		border-radius: 12px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
		flex: 1 1 240px;
		max-width: 300px;
		text-align: center;
		color: #1f2937;
	}

	.web-info-cards .icon {
		width: 64px;
		height: 64px;
		margin: 0 auto 16px auto;
		display: flex;
		align-items: center;
		justify-content: center;
		border-radius: 12px;
		font-size: 32px;
		color: #ffffff;
	}

	.icon.orange {
		background-color: #f97316;
	}

	.icon.gray {
		background-color: #6b7280;
	}

	.icon.yellow {
		background-color: #facc15;
		color: #000;
	}

	.icon.blue {
		background-color: #3b82f6;
	}
</style>
