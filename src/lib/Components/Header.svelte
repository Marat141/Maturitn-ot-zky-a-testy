<script>
	let isMenuOpen = $state(false);
	let isSubjectsOpen = $state(false);
	let isDocsOpen = $state(false);

	let closeSubjectsTimeout = $state();
	let closeDocsTimeout = $state();

	function toggleMenu() {
		isMenuOpen = !isMenuOpen;
	}

	function openSubjects() {
		clearTimeout(closeSubjectsTimeout);
		isSubjectsOpen = true;
	}

	function closeSubjects() {
		closeSubjectsTimeout = setTimeout(() => {
			isSubjectsOpen = false;
		}, 200);
	}

	function openDocs() {
		clearTimeout(closeDocsTimeout);
		isDocsOpen = true;
	}

	function closeDocs() {
		closeDocsTimeout = setTimeout(() => {
			isDocsOpen = false;
		}, 200);
	}
</script>

<header>
	<a href="/" class="site-title">Maturita</a>
	<button class="hamburger" onclick={toggleMenu} aria-label="Menu">☰</button>

	<nav class="nav-header {isMenuOpen ? 'open' : ''}">
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="dropdown-container" onmouseenter={openSubjects} onmouseleave={closeSubjects}>
			<a href="/All_Matriculation_Subjects" class="dropdown-trigger">Maturitní předměty ▼</a>
			{#if isSubjectsOpen}
				<div class="dropdown">
					<a href="/All_Matriculation_Subjects/Applied_software_in_practice">Aplikovaný software v praxi</a>
					<a href="/All_Matriculation_Subjects/Computer_Network(PSI)">Počítačové sítě</a>
					<a href="/All_Matriculation_Subjects/Czech_Language">Český jazyk</a>
					<a href="/All_Matriculation_Subjects/English_Language">Anglický jazyk</a>
					<a href="/All_Matriculation_Subjects/Hardware">Hardware</a>
					<a href="/All_Matriculation_Subjects/Operating_system">Operační systémy</a>
					<a href="/All_Matriculation_Subjects/Web_Creating">Tvorba webových stránek</a>
				</div>
			{/if}
		</div>

		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="dropdown-container" onmouseenter={openDocs} onmouseleave={closeDocs}>
			<a href="/Documents_For_Download" class="dropdown-trigger">Dokumenty ▼</a>
			{#if isDocsOpen}
				<div class="dropdown">
					<a href="/Documents_For_Download/Czech_Documents">Český jazyk</a>
					<a href="/Documents_For_Download/English_Documents">Anglický jazyk</a>
					<a href="/Documents_For_Download/Hardware_Docuemnts">Hardware</a>
				</div>
			{/if}
		</div>
	</nav>
</header>

<style>
	header {
		background-color: #00000036;
		padding: 16px 32px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
		display: flex;
		justify-content: space-between;
		align-items: center;
		flex-wrap: wrap;
	}

	.site-title {
		font-size: 29px;
		color: #2c3e50;
		text-decoration: none;
	}

	.hamburger {
		display: none;
		background: none;
		border: none;
		font-size: 28px;
		cursor: pointer;
		color: #2c3e50;
	}

	.nav-header {
		display: flex;
		gap: 32px;
		align-items: center;
	}

	.nav-header a {
		text-decoration: none;
		color: #34495e;
		font-weight: 500;
		position: relative;
		transition: color 0.3s ease;
	}

	.nav-header a:hover {
		color: #0077cc;
	}

	.dropdown-container {
		position: relative;
	}

	.dropdown-trigger {
		cursor: pointer;
		user-select: none;
		display: inline-block;
	}

	.dropdown {
		position: absolute;
		top: calc(100% + 8px);
		right: 0;
		background: white;
		border-radius: 8px;
		border: 1px solid #ddd;
		box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: column;
		min-width: 200px;
		z-index: 100;
		padding: 8px;
	}

	.dropdown a {
		padding: 8px 16px;
		color: #333;
		text-decoration: none;
		transition: background 0.2s ease;
		border-radius: 4px;
	}

	.dropdown a:hover {
		background-color: #e9f5ff;
		color: #0077cc;
	}

	/* RESPONSIVE */
	@media (max-width: 768px) {
		.hamburger {
			display: block;
		}

		.nav-header {
			flex-direction: column;
			gap: 16px;
			width: 100%;
			display: none;
		}

		.nav-header.open {
			display: flex;
		}

		.dropdown {
			position: static;
			border: none;
			box-shadow: none;
			padding: 0;
			background: transparent;
		}

		.dropdown a {
			padding: 8px 0;
		}
	}
</style>
