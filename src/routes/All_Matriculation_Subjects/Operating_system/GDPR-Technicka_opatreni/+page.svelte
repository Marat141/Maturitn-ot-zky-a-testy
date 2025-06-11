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
		{ id: 1, level: 1, text: 'Úvod do OS', path: '/All_Matriculation_Subjects/Operating_system' },
		{ id: 2, level: 1, text: 'IT3B PDF soubory' },
		{
			id: 3,
			level: 2,
			text: 'Aplikační protokoly',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Aplikacni-protokoly'
		},
		{
			id: 4,
			level: 2,
			text: 'Arduino 1-15-1 pohyb přerušení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-1_15'
		},
		{
			id: 5,
			level: 2,
			text: 'Arduino 10 7 segment 4 digits s DHT11',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Arduino-10-7'
		},
		{
			id: 6,
			level: 2,
			text: 'GDPR souhrn',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'
		},
		{
			id: 7,
			level: 2,
			text: 'GDPR Technická opatření',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni'
		},
		{
			id: 8,
			level: 2,
			text: 'Operační systémy základní součásti operačního systému',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system'
		},
		{
			id: 9,
			level: 2,
			text: 'Mac OS část 1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1'
		},
		{
			id: 10,
			level: 2,
			text: 'Mac OS část 1.2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2'
		},
		{
			id: 11,
			level: 2,
			text: 'Mac OS část 1.4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail'
		},
		{
			id: 12,
			level: 2,
			text: 'Mac OS část 1.7',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal'
		},
		{
			id: 13,
			level: 2,
			text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz'
		},
		{
			id: 14,
			level: 2,
			text: 'Operační systémy Windows Ovladače zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
		},
		{
			id: 15,
			level: 2,
			text: 'Operační systémy Win_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1'
		},
		{
			id: 16,
			level: 2,
			text: 'Operační systémy Win_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2'
		},
		{
			id: 17,
			level: 2,
			text: 'Operační systémy Win_3',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3'
		},
		{
			id: 18,
			level: 2,
			text: 'Operační systémy Win_4_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2'
		},
		{
			id: 19,
			level: 2,
			text: 'Operační systémy Win_4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4'
		},
		{
			id: 20,
			level: 2,
			text: 'Operační systémy Win_5_MMC',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC'
		},
		{
			id: 21,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_1_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz'
		},
		{
			id: 22,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_3_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz'
		},
		{
			id: 23,
			level: 2,
			text: 'Operační systémy Win_7_Windows_Server',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server'
		},
		{
			id: 24,
			level: 2,
			text: 'Operační systémy Win_8_Sprava_aplikaci_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1'
		},
		{
			id: 25,
			level: 2,
			text: 'Operační systémy Win_9_1_Firewall',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall'
		},
		{
			id: 26,
			level: 2,
			text: 'Souborove systemy 1_Windows',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows'
		}
	]);
	// Experiment
	let opatreni = $state([
		{
			id: 'ntfs',
			ikona: '🗂️',
			nadpis: 'Nastavení práv NTFS',
			body: [
				'Omezení přístupu na základě potřeby (need-to-know)',
				'Přesné oprávnění chrání důvěrnost osobních údajů',
				'Zajišťuje ochranu dat podle čl. 32 GDPR'
			]
		},
		{
			id: 'kvoty',
			ikona: '📏',
			nadpis: 'Diskové kvóty',
			body: [
				'Pomáhá minimalizovat objem zpracovávaných údajů',
				'Podporuje princip data minimization podle GDPR'
			]
		},
		{
			id: 'soubory',
			ikona: '🧹',
			nadpis: 'Práce se soubory',
			body: [
				'GDPR vyžaduje výmaz dat po skončení účelu zpracování',
				'Nutnost doložit, že data byla bezpečně odstraněna'
			]
		},
		{
			id: 'komprese',
			ikona: '🗜️',
			nadpis: 'Komprimace dat',
			body: [
				'Zrychluje přenos dat, často kombinována se šifrováním',
				'Není sama o sobě zabezpečovací metodou'
			]
		},
		{
			id: 'sifrovani',
			ikona: '🔒',
			nadpis: 'Šifrování dat',
			body: ['Zajišťuje důvěrnost i při úniku dat', 'Jedno z hlavních opatření dle čl. 32 GDPR']
		},
		{
			id: 'periferie',
			ikona: '🔌',
			nadpis: 'Periferní zařízení',
			body: [
				'Omezení přístupu k USB, tiskárnám apod.',
				'Zabraňuje neoprávněnému kopírování citlivých dat'
			]
		},
		{
			id: 'zalohy',
			ikona: '💾',
			nadpis: 'Záloha dat',
			body: [
				'Musí být zabezpečené a uchovávané jen po nutnou dobu',
				'Důležitá pro zajištění dostupnosti dle GDPR'
			]
		},
		{
			id: 'obnova',
			ikona: '♻️',
			nadpis: 'Záloha OS',
			body: [
				'Zajištění rychlé obnovy systému po havárii',
				'Platí stejné zásady jako pro běžné zálohy'
			]
		},
		{
			id: 'zabezpeceni',
			ikona: '🛡️',
			nadpis: 'Zabezpečení OS',
			body: [
				'Silná hesla, firewall, antivir, řízení služeb',
				'Naplnění zásady „privacy by design/by default“'
			]
		},
		{
			id: 'aktualizace',
			ikona: '🔁',
			nadpis: 'Aktualizace systému',
			body: [
				'Nutné kvůli opravě zranitelností',
				'Zásadní součást kybernetické bezpečnosti (čl. 32 GDPR)'
			]
		}
	]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />

		<div class="content">
			<div class="header-with-button">
				<h1 id="gdpr-tech">GDPR: Technická a organizační opatření</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni/Exam_GDPR-Technicka-opatreni"
					class="ButtonExam">Napsat si test</a
				>
			</div>

			{#each opatreni as o (o.id)}
				<section id={o.id} class="note">
					<h2>{o.ikona} {o.nadpis}</h2>
					<ul>
						{#each o.body as radek}
							<li>{radek}</li>
						{/each}
					</ul>
				</section>
			{/each}
			<a href="/PDF/GDPR-Technicka_opatreni.pdf" class="ButtonExam" download> 📄 Stáhnout PDF </a>
		</div>
	</div>
</main>

<style>
	.layout {
		display: flex;
		gap: 32px;
		background-color: #f9fafb;
		min-height: 700px;
	}

	.content {
		flex: 1;
		padding: 32px;
		background: #ffffff;
		border-radius: 16px;
		box-shadow: 0 12px 32px rgba(0, 0, 0, 0.08);
		font-family:
			'Inter',
			system-ui,
			-apple-system,
			'Segoe UI',
			Roboto,
			sans-serif;
		color: #1f2937;
		transition: all 0.3s ease;
	}
	.content h1,
	.content h2 {
		color: #2563eb;
		margin-top: 0;
	}

	.content h2 {
		margin-top: 32px;
		margin-bottom: 16px;
		font-size: 1.4rem;
	}
	.content ul {
		padding-left: 24px;
		list-style-type: disc;
		margin-bottom: 24px;
	}

	.content li {
		margin-bottom: 10px;
		line-height: 1.6;
	}

	.note:hover {
		background-color: #e5e7eb;
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
	.ButtonExam {
		display: inline-block;
		color: #ffffff;
		background-color: #2563eb;
		padding: 8px 16px;
		border-radius: 6px;
		text-decoration: none;
		font-weight: 500;
		transition: background-color 0.3s ease;
		font-size: 15px;
	}

	.header-with-button {
		display: flex;
		align-items: center;
		justify-content: space-between;
		margin-bottom: 24px;
	}
	.note {
		background-color: #f3f4f6;
		border-left: 4px solid #9ca3af;
		padding: 16px 24px;
		border-radius: 8px;
		margin-bottom: 24px;
		box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
		transition: background-color 0.3s ease;
	}
	.note h2 {
		margin-bottom: 0.5em;
	}
	.note ul {
		padding-left: 1.2em;
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
