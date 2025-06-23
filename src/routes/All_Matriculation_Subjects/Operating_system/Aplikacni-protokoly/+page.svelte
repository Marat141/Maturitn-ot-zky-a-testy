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
			text: 'GDPR souhrn',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn'
		},
		{
			id: 5,
			level: 2,
			text: 'GDPR Technická opatření',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/GDPR-Technicka_opatreni'
		},
		{
			id: 6,
			level: 2,
			text: 'Operační systémy základní součásti operačního systému',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_All_13_Operacni_system'
		},
		{
			id: 7,
			level: 2,
			text: 'Mac OS část 1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_1'
		},
		{
			id: 8,
			level: 2,
			text: 'Mac OS část 1.2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_2'
		},
		{
			id: 9,
			level: 2,
			text: 'Mac OS část 1.4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail'
		},
		{
			id: 10,
			level: 2,
			text: 'Mac OS část 1.7',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal'
		},
		{
			id: 11,
			level: 2,
			text: 'Operační systémy Windows 6.2 Funkce zabezpečení ve Windows – přehled',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz'
		},
		{
			id: 12,
			level: 2,
			text: 'Operační systémy Windows Ovladače zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
		},
		{
			id: 13,
			level: 2,
			text: 'Operační systémy Win_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_1'
		},
		{
			id: 14,
			level: 2,
			text: 'Operační systémy Win_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_2'
		},
		{
			id: 15,
			level: 2,
			text: 'Operační systémy Win_3',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_3'
		},
		{
			id: 16,
			level: 2,
			text: 'Operační systémy Win_4_2',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4_2'
		},
		{
			id: 17,
			level: 2,
			text: 'Operační systémy Win_4',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_4'
		},
		{
			id: 18,
			level: 2,
			text: 'Operační systémy Win_5_MMC',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC'
		},
		{
			id: 19,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_1_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_1_cz'
		},
		{
			id: 20,
			level: 2,
			text: 'Operační systémy Win_7_1_sit_3_cz',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_1_sit_3_cz'
		},
		{
			id: 21,
			level: 2,
			text: 'Operační systémy Win_7_Windows_Server',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server'
		},
		{
			id: 22,
			level: 2,
			text: 'Operační systémy Win_8_Sprava_aplikaci_1',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_8_Sprava_aplikaci_1'
		},
		{
			id: 23,
			level: 2,
			text: 'Operační systémy Win_9_1_Firewall',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_9_1_Firewall'
		},
		{
			id: 24,
			level: 2,
			text: 'Souborove systemy 1_Windows',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Souborove_systemy_1_Windows'
		},
		{
			id: 25,
			level: 1,
			text: 'Opravné zkoušky',
			path: '/All_Matriculation_Subjects/Operating_system/Opravne-Zkousky-OS'
		}
	]);

	const protocols = [
		{
			name: 'HTTP/HTTPS',
			description: 'Protokoly pro přenos webových stránek. HTTPS je zabezpečená verze HTTP.',
			port: '80/443'
		},
		{
			name: 'FTP (File Transfer Protocol)',
			description: 'Protokol pro přenos souborů mezi počítači.',
			port: '20(data), 21(řízení)'
		},
		{ name: 'SFTP', description: 'Zabezpečená verze FTP, používá SSH pro šifrování.', port: '22' },
		{
			name: 'FTPS',
			description: 'Zabezpečená verze FTP, používá SSL/TLS pro šifrování.',
			port: '990'
		},
		{
			name: 'SMB (Server Message Block)',
			description: 'Protokol pro sdílení souborů a tiskáren v síti, běžně používaný ve Windows.',
			port: '445'
		},
		{
			name: 'NFS (Network File System)',
			description: 'Protokol pro sdílení souborů v Unix/Linux systémech.',
			port: '2049'
		},
		{
			name: 'WebDav',
			description: 'Sdílení a správa souborů přes HTTP',
			port: '80(HTTP)/HTTPS(443)'
		},
		{
			name: 'rsync',
			description: 'Protokol pro synchronizaci souborů a adresářů mezi počítači.',
			port: '873'
		},
		{
			name: 'iSCSI (Internet Small Computer Systems Interface)',
			description:
				'Připojení vzdalených disku. iSCSI umožňuje připojit vzdálené úložiště jako lokální disk.',
			port: '3260'
		},
		{ name: 'SMTP', description: 'Protokol pro odesílání e-mailů.', port: '25' },
		{
			name: 'IMAP',
			description: 'Protokol pro příjem e-mailů, umožňuje správu pošty na serveru.',
			port: '143'
		},
		{
			name: 'POP3',
			description: 'Protokol pro příjem e-mailů, stahuje poštu na klienta a maže ji ze serveru.',
			port: '110'
		},
		{ name: 'DNS', description: 'Protokol pro překlad doménových jmen na IP adresy.', port: '53' },
		{
			name: 'Telnet',
			description: 'Nezabezpečený protokol pro vzdálený přístup, dnes již zastaralý.',
			port: '23'
		},
		{
			name: 'SSH (Secure Shell)',
			description: 'Zabezpečený protokol pro vzdálený přístup a správu serverů.',
			port: '22'
		},
		{
			name: 'DHCP',
			description:
				'Protokol pro automatické přidělování IP adres a dalších síťových nastavení klientům v síti. ',
			port: '67(klient), 68(server)'
		},
		{
			name: 'SNMP (Simple Network Management Protocol)',
			description: 'Protokol pro správu a monitorování síťových zařízení.',
			port: '161'
		},
		{
			name: 'NTP (Network Time Protocol)',
			description: 'Protokol pro synchronizaci času mezi počítači v síti.',
			port: '123'
		},
		{
			name: 'RDP (Remote Desktop Protocol)',
			description: 'Protokol pro vzdálený přístup k desktopům, běžně používaný ve Windows.',
			port: '3389'
		},
		{
			name: 'LDAP (Lightweight Directory Access Protocol)',
			description: 'Protokol pro přístup a správu adresářových služeb.',
			port: '389'
		},
		{
			name: 'MQTT (MQ Telemetry Transport)',
			description:
				'Protokol pro lehkou komunikaci mezi zařízeními, často používaný v IoT aplikacích.',
			port: '1883'
		},
		{
			name: 'CoAP (Constrained Application Protocol)',
			description:
				'Protokol pro komunikaci mezi zařízeními v IoT, optimalizovaný pro nízkou spotřebu energie.',
			port: '5683'
		},
		{
			name: 'VNC',
			description: 'Protokol pro vzdálený přístup k desktopům, nezávislý na operačním systému.',
			port: '5900'
		}
	];
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="Aplikacni-protokoly">
				<div class="header-with-button">
					<h1>Aplikační protokoly</h1>
					<a
						href="/All_Matriculation_Subjects/Operating_system/Aplikacni-protokoly/Exam_Aplikacni-protokoly"
						class="ButtonExam">Napsat si test</a
					>
				</div>
				<p>
					Aplikační protokoly jsou pravidla, podle kterých spolu komunikují programy (aplikace) přes
					síť. Umožňují například prohlížeči načíst webovou stránku (pomocí HTTP) nebo e-mailové
					aplikaci odesílat zprávy (pomocí SMTP nebo IMAP).
				</p>
				<table class="protocol-table">
					<thead>
						<tr>
							<th>Název protokolu</th>
							<th>Popis</th>
							<th>Port</th>
						</tr>
					</thead>
					<tbody>
						{#each protocols as protocol}
							<tr>
								<td>{protocol.name}</td>
								<td>{protocol.description}</td>
								<td>{protocol.port}</td>
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
			<a href="/PDF/Aplikacni_protokoly_2.pdf" class="ButtonExam" download> 📄 Stáhnout PDF </a>
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

	.content p {
		line-height: 1.6;
		color: #374151;
		margin: 8px 0 20px;
		font-size: 16px;
	}

	.protocol-table {
		width: 100%;
		border-collapse: collapse;
		margin-top: 24px;
		background-color: #ffffff;
		color: #1f2937;
		font-size: 15px;
		border-radius: 8px;
		overflow: hidden;
	}

	.protocol-table th,
	.protocol-table td {
		border: 1px solid #e5e7eb;
		padding: 14px 18px;
		text-align: left;
	}

	.protocol-table th {
		background-color: #f3f4f6;
		font-weight: 600;
		color: #111827;
	}

	.protocol-table tr:nth-child(even) {
		background-color: #f9fafb;
	}

	.protocol-table tr:hover {
		background-color: #eef2ff;
	}

	.header-with-button {
		display: flex;
		justify-content: space-between;
		align-items: center;
		margin-bottom: 16px;
	}

	.header-with-button h1 {
		margin: 0;
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

	.ButtonExam:hover {
		background-color: #1d4ed8;
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
