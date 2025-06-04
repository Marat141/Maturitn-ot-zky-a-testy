<script lang="ts">
	import Navigation from '$lib/Components/Navigation.svelte';

	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
	}

	let headings: Heading[] = [
		{ id: 1, level: 1, text: 'Úvod do ASP' },
		{ id: 2, level: 2, text: 'Co to je?', parent: 1 },
        { id: 3, level: 1, text: 'Maturitní otázky'},
        { id: 4, level: 2, text: 'Databázový procesor', parent: 3 }, 
        { id: 5, level: 2, text: 'Software', parent: 3},
        { id: 6, level: 2, text: 'Software pro plánování činností a plánování', parent: 3},
        { id: 7, level: 2, text: 'Tabulkový procesor', parent: 3},
        { id: 8, level: 2, text: 'Webový klient', parent: 3},
        
	];
</script>

<div class="layout">
	<Navigation {headings} />

	<div class="content">

	</div>
</div>

<style>
	.layout {
		display: flex;
	}
	.content {
		flex: 1;
		padding: 0.5rem;
	}
</style>
