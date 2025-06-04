<script lang="ts">
	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
	}

	let { headings }: { headings: Heading[] } = $props();
	let open = $state<Record<number, boolean>>({});

	function toggle(id: number) {
		open[id] = !open[id];
	}
</script>

<nav class="nav">
	{#each headings.filter(h => h.level === 1) as h1}
		<div>
			<!-- svelte-ignore a11y_click_events_have_key_events -->
			<!-- svelte-ignore a11y_no_static_element_interactions -->
			<div class="heading" onclick={() => toggle(h1.id)}>
				{h1.text}
				{#if headings.some(h => h.parent === h1.id)}
					<span class="arrow">{open[h1.id] ? '▼' : '▶'}</span>
				{/if}
			</div>
			{#if open[h1.id]}
				<div class="subheadings">
					{#each headings.filter(h => h.parent === h1.id) as h2}
						<div class="heading sub">{h2.text}</div>
					{/each}
				</div>
			{/if}
		</div>
	{/each}
</nav>

<style>
	.nav {
		width: 200px;
		background: #f9f9f9;
		padding: 16px;
	}
	.heading {
		cursor: pointer;
		margin-bottom: 8px;
		font-weight: bold;
	}
	.arrow {
		margin-left: 8px;
		font-size: 12.8px;
	}
	.subheadings {
		padding-left: 16px;
	}
	.sub {
		font-weight: normal;
	}
</style>
