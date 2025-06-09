<script lang="ts">
	import Navigation from '$lib/Components/Navigation.svelte';

	interface Heading {
		id: number;
		text: string;
		level: number;
		parent?: number;
		path?: string;
	}

	let headings: Heading[] = [
		{ id: 1, level: 1, text: 'Úvod do OS', path: './Operating_system' },
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
		}
	];

	const protocols = [
		{
			name: 'HTTP/HTTPS',
			description: 'Protokoly pro přenos webových stránek. HTTPS je zabezpečená verze HTTP.',
			port: '80/443'
		},
		{
			name: 'FTP',
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
			name: 'SMB',
			description: 'Protokol pro sdílení souborů a tiskáren v síti, běžně používaný ve Windows.',
			port: '445'
		},
		{
			name: 'NFS',
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
			name: 'iSCSI',
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
			name: 'SSH',
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
			name: 'SNMP',
			description: 'Protokol pro správu a monitorování síťových zařízení.',
			port: '161'
		},
		{
			name: 'NTP',
			description: 'Protokol pro synchronizaci času mezi počítači v síti.',
			port: '123'
		},
		{
			name: 'RDP',
			description: 'Protokol pro vzdálený přístup k desktopům, běžně používaný ve Windows.',
			port: '3389'
		},
		{
			name: 'LDAP',
			description: 'Protokol pro přístup a správu adresářových služeb.',
			port: '389'
		},
		{
			name: 'MQTT',
			description:
				'Protokol pro lehkou komunikaci mezi zařízeními, často používaný v IoT aplikacích.',
			port: '1883'
		},
		{
			name: 'CoAP',
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
</style>
