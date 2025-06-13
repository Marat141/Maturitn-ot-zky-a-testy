<script lang="ts">
	import { page } from '$app/stores';
	import { get } from 'svelte/store';

	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
		path?: string;
	}

	let { headings }: { headings: Heading[] } = $props();
	let open = $state<Record<number, boolean>>({});

	// Udržíme current path jako $state
	let currentPath = $state('');

	// Reaktivně sledujeme změnu stránky
	$effect(() => {
		currentPath = get(page).url.pathname;
	});

	function toggle(id: number) {
		open[id] = !open[id];
	}

	function isActive(path?: string) {
		return path === currentPath;
	}
</script>

<main>
	<nav class="nav">
		{#each headings.filter((h) => h.level === 1) as h1}
			<div>
				<!-- svelte-ignore a11y_click_events_have_key_events -->
				<!-- svelte-ignore a11y_no_static_element_interactions -->
				<div class="heading" onclick={() => toggle(h1.id)}>
					<a href={h1.path} class:active={isActive(h1.path)}>{h1.text}</a>
					{#if headings.some((h) => h.parent === h1.id)}
						<span class="arrow">{open[h1.id] ? '▼' : '▶'}</span>
					{/if}
				</div>

				{#if open[h1.id]}
					<div class="subheadings">
						{#each headings.filter((h) => h.parent === h1.id) as h2}
							<div class="heading sub">
								<a href={h2.path} class:active={isActive(h2.path)}>{h2.text}</a>
							</div>
						{/each}
					</div>
				{/if}
			</div>
		{/each}
	</nav>
</main>

<style>
	.nav {
		width: 220px;
		background: #fff;
		padding: 16px;
		border: 1px solid #ddd;
		border-radius: 6px;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
		font-family: system-ui, sans-serif;
	}

	.heading {
		cursor: pointer;
		margin-bottom: 12px;
		font-weight: 600;
		color: #222;
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 6px 8px;
		border-radius: 4px;
		transition: background-color 0.2s ease;
		user-select: none;
	}

	.heading:hover {
		background-color: #f0f0f0;
	}

	.arrow {
		margin-left: 8px;
		font-size: 14px;
		color: #666;
		flex-shrink: 0;
		transition: transform 0.2s ease;
	}
	.heading .arrow.open {
		transform: rotate(90deg);
		color: #007acc;
	}

	.subheadings {
		padding-left: 20px;
		border-left: 2px solid #ddd;
		margin-top: 4px;
	}

	.sub {
		font-weight: 400;
		margin-bottom: 6px;
		padding: 4px 8px;
		border-radius: 3px;
		color: #444;
		transition: background-color 0.15s ease;
	}

	.sub:hover {
		background-color: #e6f0ff;
	}

	a {
		color: inherit;
		text-decoration: none;
		flex-grow: 1;
	}

	a:hover {
		text-decoration: underline;
	}

	a.active {
		background-color: #e0f2fe;
		color: #1d4ed8;
		font-weight: bold;
		text-decoration: underline;
	}
</style>
