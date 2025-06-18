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
			<h1>Anglický jazyk</h1>
			<p>
				Anglický jazyk — zde najdete různé věci od <em>past continuous</em> až po základy, slovíčka a
				další. Přidávám také odkazy na další weby s angličtinou — pro jistotu, kdybych to tu úplně nedotáhl.
				😄
			</p>

			<div class="note">
				<p>Užitečné odkazy:</p>
				<ul>
					<li><a href="https://www.umimeanglicky.cz/" target="_blank">Umíme anglicky</a></li>
					<li>
						<a
							href="https://anglina.unas.cz/easy-english/anglictina-procvicovani-vasich-znalosti/"
							target="_blank">Angličtina - procvičování</a
						>
					</li>
					<li>
						<a href="https://www.jazyky-online.info/anglictina/procvicovani.php" target="_blank"
							>Jazyky online</a
						>
					</li>
				</ul>
			</div>
		</div>
	</div>
</main>

<style>
	.layout {
		display: flex;
		gap: 32px;
		background-color: #f9fafb;
		min-height: 100vh;
	}

	.content {
		flex: 1;
		padding: 32px;
		background: #ffffff;
		border-radius: 16px;
		box-shadow: 0 12px 32px rgba(0, 0, 0, 0.08);
		font-family: 'Inter', system-ui, sans-serif;
		color: #1f2937;
		transition: all 0.3s ease;
	}

	.content h1 {
		color: #2563eb;
		margin-top: 0;
	}

	.content p {
		line-height: 1.6;
		margin-bottom: 24px;
	}

	.content ul {
		padding-left: 24px;
		list-style-type: disc;
		margin-bottom: 24px;
	}

	.content li {
		margin-bottom: 10px;
	}

	.content a {
		display: inline-block;
		color: #2563eb;
		background-color: #f0f9ff;
		padding: 8px 12px;
		margin: 4px 0;
		border-radius: 6px;
		text-decoration: none;
		transition:
			background-color 0.25s,
			color 0.25s;
		font-size: 15px;
	}

	.content a:hover {
		background-color: #dbeafe;
		color: #1d4ed8;
	}

	.note {
		background-color: #f3f4f6;
		border-left: 4px solid #9ca3af;
		padding: 16px 24px;
		border-radius: 8px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
		transition: background-color 0.3s ease;
	}

	.note:hover {
		background-color: #e5e7eb;
	}

	@media (max-width: 768px) {
		.layout {
			flex-direction: column;
			gap: 24px;
		}
		.content {
			padding: 24px;
		}
	}
</style>
