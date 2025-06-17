<script lang="ts">
	import { page } from '$app/stores';
	import all from '$lib/pdf-summary-content.json';

	let current: {
		title: string;
		sections: { heading: string; bullets: string[] }[];
		pdfPath: string;
		slug: string;
		category: string;
	} | undefined;
	$: {
		const slug = $page.params.slug;
		current = all.find((d) => d.slug === slug && d.category === 'hardware');
	}
</script>

{#if current}
	<h1>{current.title}</h1>

	{#each current.sections as section}
		<section class="note">
			<h2>{section.heading}</h2>
			<ul>
				{#each section.bullets as bullet}
					<li>{bullet}</li>
				{/each}
			</ul>
		</section>
	{/each}

	<a href={current.pdfPath} class="ButtonExam" download>📄 Stáhnout PDF</a>
{:else}
	<p>Souhrn nenalezen.</p>
{/if}

<style>
	.note {
		margin-bottom: 2rem;
		padding: 1rem;
		background-color: #f3f4f6;
		border-left: 4px solid #2563eb;
		border-radius: 6px;
	}
	.ButtonExam {
		background: #2563eb;
		color: white;
		padding: 0.5rem 1rem;
		border-radius: 5px;
		text-decoration: none;
	}
</style>
