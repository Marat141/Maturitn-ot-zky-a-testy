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
</script>

<main>
	<div class="layout">
		<Navigation {headings} />

		<div class="content">
			<div class="Welcome-to-Operating-Systems">
				<h1>Vítejte v sekci o operačních systémech</h1>
				<p>
					Tato sekce obsahuje materiály a informace týkající se operačních systémů, které jsou
					součástí maturitních předmětů.
				</p>
				<div class="What-it-is">
					<h2>Co to je?</h2>
					<p>
						Operační systémy jsou základní software, který řídí hardware počítače a poskytuje služby
						pro programy. Umožňují uživatelům interagovat s počítačem a spouštět aplikace.
					</p>
				</div>
			</div>
			<div class="PDF-files">
				<h1>Zápisky z hodin</h1>
				<p>
					Zde buď můžete stáhnout pdf soubor nebo si to jenom procvičit na webu je jenom na vás.
				</p>
				<a href="/PDF/Aplikacni_protokoly_2.pdf" download>Aplikační protokoly</a>
				<a href="/PDF/Arduino_1-15_1_pohyb_preruseni_HC-SR501_7Seg.pdf" download
					>Arduino_1-15_1_pohyb_preruseni</a
				>
				<a href="/PDF/Arduino_10_7_segment_4_digits_s_DHT11.pdf" download
					>Arduino_10_7_segment_4_digits_s_DHT11</a
				>
				<a href="/PDF/GDPR_souhrn.pdf">GDPR souhrn</a>
				<a href="/PDF/GDPR-Technicka_opatreni.pdf">GDPR Technicka opatreni</a>
				<a href="/PDF/Operacni_systemy_All_13_Operacni_system.pdf"
					>Operační systemy All 13 Operacni system</a
				>
				<a href="/PDF/Operacni_systemy_MAC_1_1.pdf">Operační systemy MAC_1_1</a>
				<a href="/PDF/Operacni_systemy_MAC_1_2.pdf">Operační systemy MAC_1_2</a>
				<a href="/PDF/Operacni_systemy_MAC_1_4_Mail.pdf">Operační systemy MAC_1_4_Mail</a>
				<a href="/PDF/Operacni_systemy_MAC_1_7_Terminal.pdf">Operační systemy MAC_1_7_Terminal</a>
				<a href="/PDF/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz.pdf"
					>Operační systemy W_6_2_security_features_funkce_zabezpeceni_cz</a
				>
				<a href="/PDF/Operacni_systemy_W10_6_1_device_manager.pdf"
					>Operační systemy_W10_6_1_device_manager</a
				>
				<a href="/PDF/Operacni_systemy_Win_1.pdf">Operační systemy Win_1</a>
				<a href="/PDF/Operacni_systemy_Win_2.pdf">Operační systemy Win_2</a>
				<a href="/PDF/Operacni_systemy_Win_3.pdf">Operační systemy Win_3</a>
				<a href="/PDF/Operacni_systemy_Win_4_2.pdf">Operační systemy Win_4_2</a>
				<a href="/PDF/Operacni_systemy_Win_4.pdf">Operační systemy Win_4</a>
				<a href="/PDF/Operacni_systemy_Win_5_MMC.pdf">Operační systemy Win_5_MMC</a>
				<a href="/PDF/Operacni_systemy_Win_7_1_sit_1_cz.pdf">Operační systemy Win_7_1_sit_1_cz</a>
				<a href="/PDF/Operacni_systemy_Win_7_1_sit_3_cz.pdf">Operační systemy Win_7_1_sit_3_cz</a>
				<a href="/PDF/Operacni_systemy_Win_7_Windows_Server.pdf"
					>Operační systemy Win_7_Windows_Server</a
				>
				<a href="/PDF/Operacni_systemy_Win_8_Sprava_aplikaci_1.pdf"
					>Operační systemy Win_8_Sprava_aplikaci_1</a
				>
				<a href="/PDF/Operacni_systemy_Win_9_1_Firewall.pdf">Operační systemy Win_9_1_Firewall</a>
				<a href="/PDF/Souborove_systemy_1_Windows.pdf">Souborove systemy 1_Windows</a>
			</div>
		</div>
	</div>
</main>

<style>
	.layout {
		display: flex;
		gap: 32px;
	}

	.content {
		flex: 1;
		padding: 32px;
		background: rgba(255, 255, 255, 0.85);
		border-radius: 16px;
		box-shadow: 0 8px 24px rgba(0, 0, 0, 0.08);
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

	.content h1 {
		font-size: 32px;
		margin-bottom: 16px;
		color: #111827;
	}

	.content h2 {
		font-size: 24px;
		margin-top: 32px;
		margin-bottom: 12px;
		color: #1d4ed8;
		border-left: 4px solid #1d4ed8;
		padding-left: 12px;
	}

	.content p {
		line-height: 1.6;
		color: #374151;
		margin: 8px 0 20px;
		font-size: 16px;
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
</style>
