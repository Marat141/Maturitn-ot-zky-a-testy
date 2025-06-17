<script lang="ts">
	import all from '$lib/pdf-summary-content.json';

	const hardwareTopics = all.filter((item) => item.category === 'hardware');
</script>

<h1>Hardware – Témata</h1>

<ul>
	{#each hardwareTopics as topic}
		<li>
			<a href={`/All_Matriculation_Subjects/Hardware/PDF/${topic.slug}`}>
				{topic.title}
			</a>
		</li>
	{/each}
</ul>
