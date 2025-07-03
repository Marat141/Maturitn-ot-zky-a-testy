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
            level: 2,
            text: 'Linux DHCP',
            parent: 2,
            path: '/All_Matriculation_Subjects/Operating_system/LinuxOp_20_1_DHCP'
        },
        {
            id: 26,
            level: 2,
            text: 'Windows Server DHCP',
            parent: 2,
            path:  '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_Server_14_DHCP',       
        },
		{
			id: 27,
			level: 1,
			text: 'Opravné zkoušky',
			path: '/All_Matriculation_Subjects/Operating_system/Opravne-Zkousky-OS'
		},

        ]);
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Windows – část 7: Windows Server – role a vlastnosti</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_7_Windows_Server/Exam-Operacni_systemy_Win_7_Windows_Server"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📌 Klíčové pojmy a technologie</h2>
				<ul>
					<li><strong>Významné rysy systému:</strong> Virtualizace, vysoká dostupnost, bezpečnost, centralizovaná správa, cloud-ready řešení.</li>
					<li><strong>Active Directory (AD):</strong> Centrální správa uživatelů, skupin, počítačů a zásad v doménovém prostředí.</li>					
					<li><strong>Hyper-V:</strong> Virtualizační technologie pro běh více operačních systémů (VM) na jednom fyzickém serveru.</li>					
					<li><strong>Failover Clustering:</strong> Vysoká dostupnost služeb – automatické přesunutí služby na jiný uzel při výpadku.</li>					
					<li><strong>Storage Spaces Direct (S2D):</strong> Softwarově definované úložiště – spojuje disky z více serverů do jednoho svazku.</li>					
					<li><strong>Windows Admin Center:</strong> Webové rozhraní pro správu serverů, clusterů a dalších komponent bez nutnosti RDP.</li>					
					<li><strong>Šifrování zařízení (BitLocker):</strong> Ochrana dat na discích šifrováním – chrání proti krádeži nebo zneužití.</li>					
					<li><strong>Shielded Virtual Machines:</strong> Zabezpečené VM, které chrání před přístupem administrátorů hostitele, využívá TPM a BitLocker.</li>					
					<li><strong>Microsoft Defender for Endpoint:</strong> Podniková ochrana proti hrozbám, EDR, správa zranitelností, automatizované reakce.</li>					
					<li><strong>Active Directory Domain Services (AD DS):</strong> Role zajišťující autentizaci uživatelů a správu identit v síti.</li>					
					<li><strong>Active Directory Certificate Services (AD CS):</strong> Správa digitálních certifikátů pro autentizaci a šifrování.</li>					
					<li><strong>DHCP Server:</strong> Automatické přidělování IP adres a síťových konfigurací klientům v síti.</li>					
					<li><strong>DNS Server:</strong> Překlad názvů domén na IP adresy (např. seznam.cz → 77.75.x.x).</li>					
					<li><strong>File and Storage Services:</strong> Sdílení souborů, správa disků, kvót, deduplikace a pokročilé možnosti ukládání.</li>					
					<li><strong>Web Server (IIS):</strong> Hostování webových aplikací a služeb – běží na Internet Information Services (IIS).</li>					
					<li><strong>Remote Desktop Services (RDS):</strong> Vzdálený přístup k desktopům a aplikacím – řešení pro terminálové prostředí.</li>				
					<li><strong>Print and Document Services:</strong> Správa tiskáren, tiskových úloh a dokumentů v síti – centrální tiskový server.</li>					
					<li><strong>Windows Deployment Services (WDS):</strong> Nasazení OS po síti – automatická instalace Windows na nové počítače.</li>					
					<li><strong>Network Policy and Access Services (NPAS):</strong> Autentizace a autorizace přístupu do sítě – využívá RADIUS (NPS).</li>					
					<li><strong>Windows Server Update Services (WSUS):</strong> Centrální distribuce a správa aktualizací systému Windows a dalšího softwaru.</li>
				</ul>
			</section>

			<section class="note">
				<h2>🪟 Windows Server</h2>
				<ul>
					<li>Windows Server je řada serverových operačních systémů vyvinutých společností Microsoft</li>
					<li>Je navržena pro podporu podnikových potřeb, jako je správa sítí, hostování webových serverů, databázových služeb, virtualizace a další kritické úlohy</li>
					<li>Windows Server poskytuje spolehlivou a škálovatelnou platformu pro podniky všech velikostí</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧰 Významné vlastnosti Windows Serveru</h2>
				<ul>
					<li><strong>Active Directory:</strong> Centrální služba pro správu uživatelských účtů, skupin, počítačů a dalších síťových zdrojů</li>
					<li><strong>Virtualizace (Hyper-V):</strong> umožňuje efektivní využití hardwaru</li>
					<li><strong>PowerShell:</strong> pokročilé skriptování a automatizace správy</li>
					<li><strong>Failover Clustering:</strong></li>
					<ul>
						<li> Funkce pro zajištění vysoké dostupnosti aplikací a služeb prostřednictvím klastrů</li>
						<li>Umožňuje seskupit dva nebo více serverů (tzv. uzly) do jednoho clusteru pro zajištění vysoké dostupnosti služeb a aplikací</li>
					</ul>
					<li><strong>Bezpečnost:</strong> Shielded VM, Defender, BitLocker, JEA</li>
					<li><strong>Storage Spaces Direct:</strong> Řešení pro softwarově definované ukládání dat, umožňující vytváření vysoce dostupných a škálovatelných úložných řešení</li>
					<li><strong>Windows Admin Center: </strong>Webové uživatelské rozhraní pro správu serverů, clusterů, hyperkonvergované infrastruktury a Windows klientských počítačů</li>
					<li><strong>Vylepšená Bezpečnost:</strong> Funkce jako Shielded Virtual Machines, Microsoft Defender for Endpoint a Just Enough Administration pro zvýšení bezpečnosti systému</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Role vs Funkce</h2>
				<ul>
					<li><strong>Role:</strong> hlavní funkční oblast / hlavní služby – např. DNS, AD DS, Web Server</li>
					<li><strong>Funkce:</strong> dodatečné komponenty / podpůrné – .NET, PowerShell, Management nástroje</li>
					<li><strong>Instalace:</strong> pomocí Server Manager nebo PowerShell (např. <code>Install-WindowsFeature</code>)</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧱 Postup instalace rolí</h2>
				<ul>
					<li>Analýza potřeb: zjistit závislosti a požadavky prostředí</li>
					<li>Instalace přes Server Manager:
						<ul>
							<li>Add Roles and Features → výběr cílového serveru</li>
							<li>Výběr role a nezbytných funkcí</li>
							<li>Potvrzení a instalace</li>
						</ul>
					</li>
					<li>Instalace přes PowerShell:
						<code>Install-WindowsFeature -Name Web-Server -IncludeManagementTools</code>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔐 Detailní bezpečnostní funkce</h2>
				<ul>
					<li><strong>Shielded VM:</strong> šifrované VM, hostitel je nevidí, vyžaduje TPM a Host Guardian Service</li>
					<li><strong>Defender for Endpoint:</strong> EDR s EDR/XDR ochranou, správou zranitelností a integrací s dalšími Microsoft nástroji</li>
					<li><strong>Just Enough Administration:</strong> definování přesných oprávnění pomocí Role Capability File a Session Configuration</li>
				</ul>
			</section>

			<section class="note">
				<h2>📋 Přehled klíčových rolí</h2>
				<ul>
					<li><strong>Active Directory Domain Services (AD DS):</strong> centrální správa domény, účtů, politik a replikace</li>
					<li><strong>Active Directory Certificate Services (AD CS):</strong> správa certifikátů (SSL, šifrování, autentizace)</li>					
					<li><strong>DHCP Server:</strong> automatické přidělování IP adres a síťových parametrů klientům</li>					
					<li><strong>DHCP Failover:</strong> zálohování DHCP, zajišťuje vysokou dostupnost přidělování adres</li>					
					<li><strong>DNS Server:</strong> překlad názvů domén na IP adresy</li>					
					<li><strong>File and Storage Services:</strong> správa sdílení souborů, diskových kvót, deduplikace atd.</li>					
					<li><strong>Distributed File System (DFS):</strong> jednotný přístup k datům na více serverech, replikace souborů</li>					
					<li><strong>Web Server (IIS):</strong> hostování webových aplikací a služeb (.NET, PHP, HTTP/S)</li>					
					<li><strong>Remote Desktop Services (RDS):</strong> poskytuje vzdálený přístup ke vzdálené ploše nebo aplikacím</li>					
					<li><strong>Windows Deployment Services (WDS):</strong> nasazení OS přes síť (PXE boot, bez fyzického média)</li>					
					<li><strong>Network Policy and Access Services (NPAS):</strong> RADIUS server, politiky připojení, ověřování VPN</li>					
					<li><strong>Failover Clustering:</strong> zajištění dostupnosti – automatický přesun služeb mezi servery</li>					
					<li><strong>Windows Server Update Services (WSUS):</strong> centrální správa a schvalování aktualizací</li>					
					<li><strong>Print and Document Services:</strong> centrální správa tiskáren a tiskových front</li>					
					<li><strong>Remote Access Services (RAS):</strong> umožňuje vzdálený přístup pomocí VPN nebo DirectAccess</li>					
					<li><strong>Storage Spaces Direct (S2D):</strong> softwarově definované úložiště pro vysokou dostupnost a škálování</li>
				</ul>
			</section>


			<section class="note">
				<h2>🧠 Technologie a závislosti</h2>
				<ul>
					<li><strong>Failover Clustering:</strong> závislý na specifické síťové infrastruktuře</li>
					<li><strong>S2D:</strong> vyžaduje Failover Cluster; určen pro úložiště a Hyper-V</li>
					<li><strong>RDS:</strong> obsahuje více komponent, např. Gateway, Broker, Session Host</li>
					<li><strong>Web Server (IIS):</strong> může vyžadovat .NET, ASP.NET, WebSockets</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_7_Windows_Server.pdf" class="ButtonExam" download>
				📄 Stáhnout PDF
			</a>
		</div>
	</div>
</main>

<style>
	/* stejné styly jako v předchozím kódu */
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
	.content h1,
	.content h2 {
		color: #2563eb;
		margin-top: 0;
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
