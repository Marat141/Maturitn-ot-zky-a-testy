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
			<div class="Notes-Area">
				<h1>Tvorba webových stránek</h1>
				<div class="FronBack">
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
									<li>
										<strong>API(Application Programming Interface)</strong> umožňuje aplikacím vzájemně
										se "bavit" a sdílet informace nebo provádět akce.
									</li>
								</ul>
							</li>
						</ul>

						<h3>🧪 Používané technologie</h3>
						<ul>
							<li><strong>Node.js</strong>, <strong>PHP</strong>, <strong>Python</strong></li>
							<li><strong>Java</strong>, <strong>Ruby</strong></li>
						</ul>
					</div>
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
							stránce nebo aplikaci přímo vidí a používá. UI design ovlivňuje, jak celá aplikace
							působí vizuálně.
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
				<div class="URL-structure-container">
					<h2>🌐 Struktura URL</h2>
					<!--<img src="/URL-Structure.png" alt="" />-->
					<div class="URL-structure-description">
						<h3 style="text-align: center;">Vysvětlení</h3>
						<ul>
							<li>
								<strong>Protocol</strong> – Určuje způsob přenosu dat, například
								<code>https://</code>
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
								<strong>TLD</strong> – Top-Level Domain, tedy koncovka domény, jako
								<code>.com</code>,
								<code>.cz</code> apod.
							</li>
							<li>
								<strong>Subfolder</strong> – Cesta k určité složce na webu, např.
								<code>/blog/</code>.
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
							Hlavní část stránky obsahuje veškerý obsah, který je pro uživatele důležitý. Může to
							být text, obrázky, videa nebo formuláře.
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
							Je obvykle statická, což znamená, že obsah se nemění dynamicky podle uživatelského
							chování nebo vstupů.
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

	.Notes-Area h1 {
		font-size: 2rem;
		margin-bottom: 1rem;
		color: #0f172a;
	}

	h2 {
		color: #1e40af;
		margin-top: 2rem;
		font-size: 1.5rem;
	}

	h3 {
		color: #475569;
		margin-top: 1.25rem;
	}

	ul {
		margin-left: 1.5rem;
		list-style: disc;
	}

	ul ul {
		list-style: circle;
	}

	.frontend, .backend, .UX, .UI {
		margin-bottom: 2rem;
		background: #f1f5f9;
		padding: 16px;
		border-radius: 12px;
	}

	.URL-structure-container, .StructureOfWeb {
		margin-top: 2rem;
		background: #e2e8f0;
		padding: 24px;
		border-radius: 12px;
	}

	.web-info-cards {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
		gap: 16px;
		margin-top: 2rem;
	}

	.card {
		background-color: #f8fafc;
		border: 1px solid #cbd5e1;
		border-radius: 12px;
		padding: 16px;
		text-align: center;
		transition: transform 0.2s ease;
	}

	.card:hover {
		transform: translateY(-4px);
		box-shadow: 0 4px 12px rgba(0, 0, 0, 0.05);
	}

	.icon {
		font-size: 2rem;
		margin-bottom: 8px;
	}

	.icon.orange { color: #ea580c; }
	.icon.gray { color: #64748b; }
	.icon.yellow { color: #ca8a04; }
	.icon.blue { color: #2563eb; }

	code {
		background-color: #e2e8f0;
		padding: 2px 6px;
		border-radius: 4px;
		font-family: 'Fira Code', monospace;
	}

	.URL-structure-description ul {
		margin-top: 1rem;
	}
</style>