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

	let presentations = $state([
		{
			id: 'Australia&New_Zealand',
			title: 'Australia and New Zealand',
			url: 'https://docs.google.com/presentation/d/1QAfHC-E-OVbIwU7Gg2vksQX3tobZZn-N/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Czech_Republic',
			title: 'Czech Republic',
			url: 'https://docs.google.com/presentation/d/1g-YJryHCNgUnZRtXAXXUgWBbSGZwrwmJ/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Canada',
			title: 'Canada',
			url: 'https://docs.google.com/presentation/d/1QAnnoDzzWqi7tUyLXdMka03lcL50s_sP/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'London',
			title: 'London',
			url: 'https://docs.google.com/presentation/d/1Ee8FaJAZBQYWUB6ifgVE_OiRXHKr9SOT/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Pilsen',
			title: 'Pilsen',
			url: 'https://docs.google.com/presentation/d/1yuryaAPh0i1q4fqMCZ1AgS9LRrrQhR4R/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Prague',
			title: 'Prague',
			url: 'https://docs.google.com/presentation/d/1NG3cJZXVkXXyzUUbhHJnTtXGN0B06btm/edit?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'USA',
			title: 'USA',
			url: 'https://docs.google.com/presentation/d/1iurzjrt5oR0eSgSam4fIycTvfO-bhUI3/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
		},
		{
			id: 'Britania',
			title: 'Great Britain',
			url: 'https://docs.google.com/presentation/d/1ki-nbKcpAb9OUVo4A-w9UEyPU9CbKt9B/preview?usp=sharing&ouid=113494242568922904409&rtpof=true&sd=true'
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
			<div class="presentations">
				<h1>Maturita – Anglický jazyk</h1>
				<p class="intro">Prezentace k maturitním tématům z angličtiny.</p>

				{#each presentations as presentation}
					<button class="presentation-button" onclick={() => toggle(presentation.id)}>
						📖 {presentation.title}
					</button>

					{#if openId === presentation.id}
						<div class="iframe-container">
							<!-- svelte-ignore a11y_missing_attribute -->
							<iframe src={presentation.url} frameborder="0" allowfullscreen></iframe>
						</div>
					{/if}
				{/each}
			</div>
		</div>
	</div>
</main>

<style>
	main {
		background: linear-gradient(to bottom right, #e7eff6, #f9fcff);
		min-height: 100vh;
		padding: 2rem 0;
	}

	.layout {
		display: flex;
		gap: 2rem;
		max-width: 1400px;
		margin: 0 auto;
		background: white;
		padding: 2rem;
		border-radius: 16px;
		box-shadow: 0 10px 30px rgba(0, 0, 0, 0.05);
	}

	.content {
		flex: 1;
	}

	.presentations {
		max-width: 900px;
		margin: 0 auto;
		display: flex;
		flex-direction: column;
		gap: 1.5rem;
	}

	h1 {
		font-size: 2rem;
		margin-bottom: 0.25rem;
		color: #1f2d3d;
	}

	.intro {
		font-size: 1rem;
		color: #546e7a;
		margin-bottom: 1.5rem;
	}

	.presentation-button {
		background: #f0f4f8;
		border: none;
		padding: 1rem 1.5rem;
		border-radius: 8px;
		font-size: 1.05rem;
		color: #2c3e50;
		text-align: left;
		cursor: pointer;
		box-shadow: 0 2px 6px rgba(0, 0, 0, 0.04);
		transition:
			background 0.2s,
			transform 0.15s;
	}

	.presentation-button:hover {
		background: #dce8f2;
		transform: translateY(-2px);
	}

	.iframe-container {
		margin-top: 1rem;
		border-radius: 10px;
		overflow: hidden;
		box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
	}

	iframe {
		width: 100%;
		height: 600px;
		border: none;
	}
</style>
