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
			<div class="Links">
				<p>Zde najdete odkazy na stránky s procvičováním všeho možného z mluvnice</p>
				<a href="https://www.umimecesky.cz/">umimecesky.cz</a>
				<a
					href="https://wordwall.net/cs-cz/community/%C4%8Desk%C3%BD-jazyk/procvi%C4%8Dov%C3%A1n%C3%AD"
					>Wordwall čeština</a
				>
				<a href="https://www.umimecesky.cz/cesky-jazyk-detail-stredni-skola-1">umimecesky.cz</a>
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
		flex: 1 1 700px;
		background-color: #ffffff;
		padding: 32px;
		border-radius: 12px;
		box-shadow: 0 4px 16px rgba(0, 0, 0, 0.05);
	}

	.Links {
		background-color: #f3f4f6;
		padding: 24px;
		border-radius: 12px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.03);
	}

	.Links p {
		margin-bottom: 16px;
		font-size: 16px;
	}

	.Links a {
		display: block;
		margin-bottom: 12px;
		color: #2563eb;
		font-weight: 500;
		text-decoration: none;
		padding: 10px 16px;
		background-color: #e0e7ff;
		border-radius: 8px;
		transition: background-color 0.2s ease;
	}

	.Links a:hover {
		background-color: #c7d2fe;
		text-decoration: underline;
	}
</style>
