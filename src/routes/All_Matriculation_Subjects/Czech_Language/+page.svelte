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
		{ id: 1, text: 'Český jazyk', level: 1, path: '/All_Matriculation_Subjects/Czech_Language' },
		{
			id: 2,
			text: 'Maturitní knížky',
			level: 1,
			path: '/All_Matriculation_Subjects/Czech_Language/Maturitni_knizky'
		},
		{
			id: 3,
			text: 'Český jazyk mluvnice',
			level: 1,
			path: '/All_Matriculation_Subjects/Czech_Language/Czech_Language_grammar'
		}
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="Docuemnts">
				<h1>Český jazyk</h1>
				<p>
					Zde na hlávní stránce najdete informace a soubroy ohledně zápisku z ČJ. Dokumenty Word,
					PowerPoint.
				</p>
				<h2>IT3B zápisky</h2>
				<ul>
					<li>
						<a href="/CJ-Documents/Ceska-literatura-1.-pol.-20.stoleti.docx" download
							>Česká literatura 1.polovina 20.století</a
						>
					</li>
					<li><a href="/CJ-Documents/Exprecionismus.docx">Exprecionismus</a></li>
					<li><a href="/CJ-Documents/Imaginativni-proza.docx">Imaginativni proza</a></li>
					<li>
						<a href="/CJ-Documents/Katolicky-orientovana-literatura.docx"
							>Katolicky orientovana literatura</a
						>
					</li>
					<li>
						<a href="/CJ-Documents/Kriticky-spolecenska-proza.docx">Kritický společenská próza</a>
					</li>
					<li><a href="/CJ-Documents/Legionarska-literatura.docx">Legionařská literatura</a></li>
					<li><a href="/CJ-Documents/Poetismus.docx">Poetismus</a></li>
					<li>
						<a href="/CJ-Documents/Prazska-nemecka-literatura.docx">Pražská německa literatura</a>
					</li>
					<li><a href="/CJ-Documents/Psychologicka-proza.docx">Psychologická próza</a></li>
					<li><a href="/CJ-Documents/Surrealismus.docx">Surrealismus</a></li>
				</ul>
				<h3>Autoři/Spisovatele</h3>
				<ul>
					<li><a href="/CJ-Documents/Eduard-Bass.docx">Eduard Bass</a></li>
					<li><a href="/CJ-Documents/Karel-Capek.docx">Karel Čapek</a></li>
					<li><a href="/CJ-Documents/Karel-Polacek.docx">Karel Poláček</a></li>
				</ul>
				<h2>IT2B zápisky</h2>
				<ul>
					<li>
						<a href="/CJ-Documents/4 - Anglický realismus - ES2, RS2.pptx">Anglický realismus</a>
					</li>
					<li>
						<a href="/CJ-Documents/Národní obrození - 1. fáze - IT2.pptx">Národní obrození 1.fáze</a
						>
					</li>
					<li>
						<a href="/CJ-Documents/4 - Národní obrození - 3. fáze - IT2.pptx"
							>Národní obrození 3.fáze</a
						>
					</li>
					<li>
						<a href="/CJ-Documents/5 - Národní obrození - 4. fáze - IT2.pptx"
							>Národní obrození 4.fáze</a
						>
					</li>
					<li><a href="/CJ-Documents/Národní obrození - IT2.pptx">Národní obrození</a></li>
					<li><a href="/CJ-Documents/Karel Hynek Mácha - IT1.pptx">Karel Hynek Mácha</a></li>
					<li>
						<a href="/CJ-Documents/Klasicismus, osvícenství, preromantismus - IT1 (2).pptx"
							>Klasicismus, osvícenství, preromantismus</a
						>
					</li>
					<li><a href="/CJ-Documents/Literární teorie - IT1.pptx">Literární teorie</a></li>
					<li><a href="/CJ-Documents/Romantismus.pptx">Romantismus</a></li>
					<li><a href="/CJ-Documents/Sloh.pptx">Sloh</a></li>
					<li>
						<a href="/CJ-Documents/Jan_Neruda_Povidky_Malostranske.docx"
							>Jan Neruda Povidky Malostranske</a
						>
					</li>
				</ul>
			</div>
		</div>
	</div>
</main>

<style>
	main {
		font-family: 'Inter', sans-serif;
		color: #1f2937;
		padding: 32px;
	}

	.layout {
		display: flex;
		gap: 24px;
		align-items: flex-start;
		flex-wrap: wrap;
	}

	.content {
		flex: 3 1 600px;
		background-color: #ffffff;
		padding: 32px;
		border-radius: 12px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
	}

	.Docuemnts h1 {
		color: #1d4ed8;
		margin-bottom: 16px;
	}

	.Docuemnts h2 {
		color: #2563eb;
		margin-top: 32px;
		margin-bottom: 12px;
		font-size: 20px;
	}

	.Docuemnts h3 {
		color: #111827;
		margin-top: 24px;
		font-size: 18px;
	}

	.Docuemnts p {
		margin-bottom: 24px;
		line-height: 1.6;
	}

	.Docuemnts ul {
		padding-left: 20px;
		margin-bottom: 16px;
	}

	.Docuemnts li {
		margin-bottom: 8px;
		line-height: 1.6;
	}

	.Docuemnts a {
		color: #1d4ed8;
		text-decoration: none;
		transition: color 0.2s ease;
	}

	.Docuemnts a:hover {
		color: #2563eb;
		text-decoration: underline;
	}
</style>
