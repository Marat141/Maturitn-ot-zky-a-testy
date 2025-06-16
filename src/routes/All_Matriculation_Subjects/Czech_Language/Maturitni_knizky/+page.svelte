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
		}
	]);

	let books = $state([
		{
			id: 'romeo',
			title: 'Hamlet',
			url: 'https://docs.google.com/document/d/17YU3_mwd5YP2CdK4Sy5kp8NJ86jIsCLM/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true"'
		},
		{
			id: 'capek',
			title: 'Válka s Mloky',
			url: 'https://tvujweb.cz/CJ-Documents/valka-s-mloky.docx'
		}
		// ...přidej další
	]);

	let openId = $state<string | null>(null);

	function toggle(id: string) {
		openId = openId === id ? null : id;
	}
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<h1>Maturitní knížky</h1>
			<p>
				Na této stránce naleznete seznam maturitních knížek, které jsem si vybral já a potom se zde
				můžou objevit i jiné knížky od jiných lidí.
			</p>
			<h3>Pravidla pro maturní knížky</h3>
			<ul>
				<li>minimalně 2 knížky z 18 století</li>
				<li>minimálně 3 knížky z 19 století</li>
				<li>minimálně 5 knížek z České literatury z 20 a 21 století</li>
				<li>minimálně 4 knížky ze světové literatury 20 a 21 století</li>
				<li>
					Minimálně <strong>2 díly musí být v seznamu zastoupena poezie a 2 díly drama</strong>. V
					seznamu lze použít <strong>maximálně 2 díla od 1 autora.</strong>
				</li>
			</ul>
			<div class="MaturniKnizky">
				<h1>Knížky z 18 století</h1>
				<h3>William Shakespeare Hamlet</h3>
				<!-- svelte-ignore a11y_missing_attribute -->
				<iframe
					src="https://docs.google.com/document/d/17YU3_mwd5YP2CdK4Sy5kp8NJ86jIsCLM/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true"
					style="width:80%; height:1000px;"
					frameborder="0"
				></iframe>
			</div>
		</div>
	</div>
</main>
