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
			text: 'Anglický jazyk',
			level: 1,
			path: '/All_Matriculation_Subjects/English_Language'
		},
		{
			id: 2,
			text: 'Maturita Anglický jazyk',
			level: 1,
			path: '/All_Matriculation_Subjects/English_Language/Maturita_AJ'
		},
		{
			id: 3,
			text: 'Info Maturita',
			level: 2,
			parent: 2,
			path: '/All_Matriculation_Subjects/English_Language/Info-Maturita'
		}
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<h1>Zde uvidíte PDF, které si budete moct i stáhnout.</h1>
			<div class="PDF-AJ">
				<a href="https://www.souepl.cz/wp-content/uploads/2024/08/MZ_anglicky-jazyk.pdf" target="_blank">SOUEPL Anglický jazyk</a>
				<!-- svelte-ignore a11y_missing_attribute -->
				<iframe
					src="https://www.souepl.cz/wp-content/uploads/2024/08/MZ_anglicky-jazyk.pdf"
					frameborder=""
					allowfullscreen
				></iframe>
			</div>
		</div>
	</div>
</main>

<style>
	main {
		background: linear-gradient(to bottom right, #f2f6fa, #eaf2f8);
		min-height: 100vh;
		padding: 2rem 0;
	}

	.layout {
		display: flex;
		gap: 2rem;
		max-width: 1400px;
		margin: 0 auto;
		padding: 2rem;
		background: white;
		border-radius: 16px;
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.06);
	}

	.content {
		flex: 1;
	}

	h1 {
		font-size: 1.8rem;
		color: #1f2d3d;
		margin-bottom: 1rem;
	}

	.PDF-AJ {
		display: flex;
		flex-direction: column;
		gap: 1rem;
	}

	.PDF-AJ a {
		align-self: flex-start;
		background: #007acc;
		color: white;
		text-decoration: none;
		padding: 0.75rem 1.25rem;
		border-radius: 6px;
		font-weight: 500;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
		transition: background 0.2s ease;
	}

	.PDF-AJ a:hover {
		background: #005fa3;
	}

	.PDF-AJ iframe {
		width: 100%;
		height: 650px;
		border: 1px solid #ccc;
		border-radius: 8px;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.08);
	}
</style>
