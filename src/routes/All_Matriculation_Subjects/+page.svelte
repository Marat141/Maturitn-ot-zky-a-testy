<script>
</script>

<main class="wrapper">
	<section class="content">
		<h1>Maturitní předměty</h1>
		<div class="ListOfSubject">
			<ul>
				<li><a href="/All_Matriculation_Subjects/Applied_software_in_practice">Aplikovaný software v praxi</a></li>
				<li><a href="/All_Matriculation_Subjects/Computer_Network(PSI)">Počítačové sítě</a></li>
				<li><a href="/All_Matriculation_Subjects/Czech_Language">Český jazyk</a></li>
				<li><a href="/All_Matriculation_Subjects/English_Language">Anglický jazyk</a></li>
				<li><a href="/All_Matriculation_Subjects/Hardware">Hardware</a></li>
				<li><a href="/All_Matriculation_Subjects/Operating_system">Operační systémy</a></li>
				<li><a href="/All_Matriculation_Subjects/Web_Creating">Tvorba webových stránek</a></li>
			</ul>
		</div>
	</section>
</main>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

	.wrapper {
		height: 88vh;
		display: flex;
		justify-content: center;
		align-items: center;
		background: linear-gradient(135deg, #eef2f3, #dff1ff);
		padding: 20px;
		box-sizing: border-box;
	}

	.content {
		background-color: #ffffff;
		padding: 40px 30px;
		border-radius: 16px;
		box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
		width: 100%;
		max-width: 400px;
		font-family: 'Inter', sans-serif;
		text-align: center;
		animation: fadeIn 0.5s ease-out;
	}

	h1 {
		margin-bottom: 24px;
		font-size: 26px;
		color: #222;
		font-weight: 600;
	}

	.ListOfSubject ul {
		list-style-type: none;
		padding: 0;
		margin: 0;
	}

	.ListOfSubject li {
		margin: 10px 0;
	}

	.ListOfSubject a {
		display: block;
		padding: 10px 15px;
		border-radius: 8px;
		background-color: #f0f8ff;
		color: #007acc;
		font-size: 16px;
		text-decoration: none;
		transition: all 0.3s ease;
		font-weight: 500;
		box-shadow: inset 0 0 0 0 #007acc;
	}

	.ListOfSubject a:hover {
		background-color: #007acc;
		color: #fff;
		box-shadow: inset 300px 0 0 0 #007acc;
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
			transform: translateY(10px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@media (max-width: 480px) {
		.content {
			padding: 30px 20px;
		}

		h1 {
			font-size: 22px;
		}

		.ListOfSubject a {
			font-size: 15px;
		}
	}
</style>
