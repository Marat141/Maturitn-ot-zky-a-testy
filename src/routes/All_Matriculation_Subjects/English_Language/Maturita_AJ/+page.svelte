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
		{ id: 1, text: 'Anglický jazyk', level: 1, path: '/All_Matriculation_Subjects/English_Language' },
        { id: 2, text: 'Maturita Anglický jazyk', level: 1, path: '/All_Matriculation_Subjects/English_Language/Maturita_AJ' },
	]);
</script>

<main>
    <div class="layout">
        <Navigation {headings} />
        <div class="content">

        </div>
    </div>
</main>