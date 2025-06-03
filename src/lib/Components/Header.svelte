<script>
	let isOpen = $state(false);

	function toggleDropdown() {
		isOpen = !isOpen;
	}

	function closeDropdown() {
		isOpen = false;
	}
</script>

<header>
	<h1 class="site-title">Maturita</h1>
	<nav class="nav-header">
		<a href="/All_Matriculation_Subjects">Maturitní předměty</a>
		<!-- svelte-ignore a11y_no_static_element_interactions -->
		<div class="dropdown-container" onmouseenter={toggleDropdown} onmouseleave={closeDropdown}>
			<!-- svelte-ignore a11y_invalid_attribute -->
			<a href="#" class="dropdown-trigger">Předměty ▼</a>
			{#if isOpen}
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
	</nav>
</header>

<style>
	header {
		background-color: #f8f9fa;
		padding: 1rem 2rem;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
		display: flex;
		justify-content: space-between;
		align-items: center;
	}

	.site-title {
		font-size: 1.8rem;
		color: #2c3e50;
		margin: 0;
	}

	.nav-header {
		display: flex;
		gap: 2rem;
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
	}

	.dropdown {
		position: absolute;
		top: calc(100% + 0.5rem);
		left: 0;
		background: white;
		border-radius: 0.5rem;
		border: 1px solid #ddd;
		box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
		display: flex;
		flex-direction: column;
		min-width: 200px;
		z-index: 100;
		padding: 0.5rem;
	}

	.dropdown a {
		padding: 0.5rem 1rem;
		color: #333;
		text-decoration: none;
		transition: background 0.2s ease;
		border-radius: 0.3rem;
	}

	.dropdown a:hover {
		background-color: #e9f5ff;
		color: #0077cc;
	}
</style>
