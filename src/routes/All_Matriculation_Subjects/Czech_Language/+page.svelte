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
		{ id: 1, text: 'Český jazyk', level: 1, path: '/All_Matriculation_Subjects/Czech_Language' }
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
                    <li><a href="/CJ-Documents/Ceska-literatura-1.-pol.-20.stoleti.docx" download>Česká literatura 1.polovina 20.století</a></li>
                    <li><a href="/CJ-Documents/Exprecionismus.docx">Exprecionismus</a></li>
                    <li><a href="/CJ-Documents/Imaginativni-proza.docx">Imaginativni proza</a></li>
                    <li><a href="/CJ-Documents/Katolicky-orientovana-literatura.docx">Katolicky orientovana literatura</a></li>
                    <li><a href="/CJ-Documents/Kriticky-spolecenska-proza.docx">Kritický společenská próza</a></li>
                    <li><a href="/CJ-Documents/Legionarska-literatura.docx">Legionařská literatura</a></li>
                    <li><a href="/CJ-Documents/Poetismus.docx">Poetismus</a></li>
                    <li><a href="/CJ-Documents/Prazska-nemecka-literatura.docx">Pražská německa literatura</a></li>
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
                    <li><a href="/CJ-Documents/4 - Anglický realismus - ES2, RS2.pptx">Anglický realismus</a></li>
                    <li><a href="/CJ-Documents/Národní obrození - 1. fáze - IT2.pptx">Národní obrození 1.fáze</a></li>
                    <li><a href="/CJ-Documents/4 - Národní obrození - 3. fáze - IT2.pptx">Národní obrození 3.fáze</a></li>
                    <li><a href="/CJ-Documents/5 - Národní obrození - 4. fáze - IT2.pptx"></a></li>
                    <li><a href="/CJ-Documents/Karel Hynek Mácha - IT1.pptx"></a></li>
                    <li><a href="/CJ-Documents/Klasicismus, osvícenství, preromantismus - IT1 (2).pptx"></a></li>
                    <li><a href="/CJ-Documents/Literární teorie - IT1.pptx"></a></li>
                    <li><a href="/CJ-Documents/Národní obrození - IT2.pptx"></a></li>
                    <li><a href="/CJ-Documents/Romantismus.pptx"></a></li>
                    <li><a href="/CJ-Documents/Sloh.pptx"></a></li>
                    <li><a href="/CJ-Documents/Jan_Neruda_Povidky_Malostranske.docx"></a></li>

                </ul>
			</div>
		</div>
	</div>
</main>
