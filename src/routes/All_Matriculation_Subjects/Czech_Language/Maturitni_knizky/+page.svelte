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
			id: 'Shakespeare',
			title: 'Hamlet',
			url: 'https://docs.google.com/document/d/17YU3_mwd5YP2CdK4Sy5kp8NJ86jIsCLM/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true"'
		},
		{
			id: 'Moliere',
			title: 'Lakomec',
			url: 'https://docs.google.com/document/d/1p9VV19atOt3Uo0Rxi3_KtpArYD-qBQJc/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Shakespeare2',
			title: 'Romeo a Julie',
			url: 'https://docs.google.com/document/d/1d1HmfNXgfr3jXIONlOnf5UabjJds2grk/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Nemcova',
			title: 'Divá Bára',
			url: 'https://docs.google.com/document/d/1lyRtdxhFs7kMyvLPA4OTA5WLj7xlJo94/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Maupassant',
			title: 'Kulička',
			url: 'https://docs.google.com/document/d/1zH8n92mavoITtmUoNiyV37irh1Ec2JUv/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Erben',
			title: 'Kytice',
			url: 'https://docs.google.com/document/d/1B1g-928IwbcuoQ49JyBOzapI3xb1x3Re/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Mrstikove',
			title: 'Marysa',
			url: 'https://docs.google.com/document/d/1h7DKyfdgsJqwSeokvg6Tme9Nwz6iLTtn/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Dumas',
			title: 'Tři mušketýři',
			url: 'https://docs.google.com/document/d/1cBHdqsU1U-f77cVxfe7GmSGh3NawaMSQ/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Halas',
			title: 'Torzo naděje',
			url: 'https://docs.google.com/document/d/1Ijp8NsjscaijtreP4e8CnsRA7NxgbsBE/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Capek1',
			title: 'R.U.R',
			url: 'https://docs.google.com/document/d/13xGIvibLs6MLhd4LAnaULt_x11IWoGdr/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Polacek',
			title: 'Bylo nás pět',
			url: 'https://docs.google.com/document/d/1Vp-QC7oMIdgmTMwjWBISRfcBl9k_mHY8/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Smojlák, Svěrák',
			title: 'Blaník',
			url: 'https://docs.google.com/document/d/1X365yQPE2AR8I2ov7uzSHiFITSa083TR/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Capek2',
			title: 'Bílá nemoc',
			url: 'https://docs.google.com/document/d/1Hl0Pt9GBsXkeYXl05xyEjq0lB5wUQUY1/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Drda',
			title: 'Němá barikáda',
			url: 'https://docs.google.com/document/d/1WcB8vyxfFRYCSbImF8jjZgjnOWboVzz8/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Hrabal',
			title: 'Ostře sledované vlaky',
			url: 'https://docs.google.com/document/d/13t20msqsVpAafmJ_8A7ML5uzEcmnmvGk/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Antonie',
			title: 'Malý princ',
			url: 'https://docs.google.com/document/d/1g5GegRuYxwPxDQTwqoZQOTzcju7TBdY0/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Remarque',
			title: 'Na západní frontě klid',
			url: 'https://docs.google.com/document/d/1wJpoW4Oo3vdR7JtJZg5RUjT7rt7vwb0J/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Rolland',
			title: 'Petr a Lucie',
			url: 'https://docs.google.com/document/d/1m7zsNSQrQji2C61WFzXmMvc3gALo9A7G/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Hemingway',
			title: 'Sbohem armádo',
			url: 'https://docs.google.com/document/d/1iBxQCr-qof4sErqO5k5LuWqwBroC_zBg/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Fitzgerald',
			title: 'Velký Gatsby',
			url: 'https://docs.google.com/document/d/1sRObI7-vVdGWk47BBoVVsyEahPefk_W7/preview?usp=drive_link&ouid=113494242568922904409&rtpof=true&sd=true'
		}
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
			<h3>18.století</h3>
			<ul>
				<li>Hamlet - Shakespeare</li>
				<li>Lakomec - Moleire</li>
				<li>Romeo a Julie - Shakespeare</li>
			</ul>
			<h3>19.století</h3>
			<ul>
				<li>Divá Bára - Němcová</li>
				<li>Kulička - Guy de Maupassant</li>
				<li>Kytice - Erben</li>
				<li>Marysa - Mrštíkové</li>
				<li>Tři mušketýři - Dumas</li>
			</ul>
			<h3>20 a 21.století Česká literatura</h3>
			<ul>
				<li>Torzo naděje - František Halas</li>
				<li>R.U.R - Čapek</li>
				<li>Bylo nás pět - Poláček</li>
				<li>Blaník - Smolják, Svěrák</li>
				<li>Bílá nemoc - Čapek</li>
				<li>Němá barikáda - Drda</li>
				<li>Ostře sledované vlaky - Hrabal</li>
			</ul>
			<h3>20 a 21.století Světová literatura</h3>
			<ul>
				<li>Malý princ - Antonie</li>
				<li>Na západní frontě klid - Erich Maria Remarque</li>
				<li>Petr a Lucie - Romain Rolland</li>
				<li>Sbohem armádo - Hemingway</li>
				<li>Velký Gatsby - Francis Scott Fitzgerald</li>
			</ul>
			{#each books as book}
				<button onclick={() => toggle(book.id)} class="book-button">
					📖 {book.title}
				</button>
				{#if openId === book.id}
					<div class="iframe-container">
						<!-- svelte-ignore a11y_missing_attribute -->
						<iframe src={book.url} style="width:100%; height:1000px;" frameborder="0"> </iframe>
					</div>
				{/if}
			{/each}
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
		flex: 1 1 700px;
		background-color: #ffffff;
		padding: 32px;
		border-radius: 12px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
	}

	h1 {
		color: #1d4ed8;
		margin-bottom: 16px;
	}

	h3 {
		margin-top: 32px;
		color: #111827;
		font-size: 18px;
	}

	p {
		margin-bottom: 24px;
		line-height: 1.6;
	}

	ul {
		padding-left: 20px;
		margin-bottom: 16px;
	}

	li {
		margin-bottom: 6px;
		line-height: 1.6;
	}
	.book-button {
		width: 100%;
		text-align: left;
		padding: 12px 16px;
		margin: 8px 0;
		border: none;
		background-color: #f3f4f6;
		border-radius: 8px;
		cursor: pointer;
		font-size: 16px;
		color: #1f2937;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.05);
		transition: background-color 0.2s ease;
	}

	.book-button:hover {
		background-color: #e5e7eb;
	}
	.iframe-container {
		margin: 24px 0;
		box-shadow: 0 2px 12px rgba(0, 0, 0, 0.08);
		border-radius: 12px;
		overflow: hidden;
	}
</style>
