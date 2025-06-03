<script lang="ts">
	let { children } = $props();
	import Header from '$lib/Components/Header.svelte';
</script>

<Header />







{@render children()}
