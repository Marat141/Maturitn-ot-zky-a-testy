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
			id: 28,
			level: 2,
			text: 'Operační systémy Windows 6.1 Správce zařízení',
			parent: 2,
			path: '/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W10_6_1_device_manager'
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
				<h1>Windows – část 6.2: Funkce zabezpečení</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz/Exam_Operacni_systemy_W_6_2_security_features"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🛡️ Windows Defender Antivirus</h2>
				<ul>
					<li>Integrovaná antivirová ochrana ve Windows 10/11</li>
					<li>Poskytuje ochranu v reálném čase proti virům, malwaru a dalším škodlivým softwarům</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Ochrana v reálném čase: Neustálé monitorování systému pro detekci hrozeb</li>
						<li>Cloudová ochrana: Využívá cloudové služby pro rychlejší detekci nových hrozeb</li>
						<li>Automatické aktualizace: Pravidelně aktualizuje definice virů a malwaru.</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Uživatelé mohou naplánovat pravidelné skenování, vyloučit určité soubory nebo složky a konfigurovat úroveň ochrany</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🔥 Windows Firewall</h2>
				<ul>
					<li>Integrovaný firewall, který pomáhá zabránit neoprávněnému přístupu k systému přes síť nebo internet.</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Filtrace příchozího a odchozího provozu: Kontroluje data vstupující a opouštějící systém na základě předefinovaných pravidel</li>
						<li>Profily:  Umožňuje nastavit různé úrovně zabezpečení pro soukromé, veřejné a doménové sítě</li>
						<li>Pokročilá konfigurace přes rozhraní nebo GPO (Group Policy Object) </li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong> Přístupné přes Windows Security nebo Windows Defender Firewall s pokročilým zabezpečením pro detailní konfiguraci</li>
				</ul>
			</section>

			<section class="note">
				<h2>👤 User Account Control (UAC)</h2>
				<ul>
					<li>Ochrana před neautorizovanými změnami systému</li>
					<li>Vyžaduje potvrzení pro akce s vyššími oprávněními</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Prevence nežádoucích změn: Upozorňuje uživatele, když aplikace nebo procesy chtějí provést změny vyžadující vyšší oprávnění</li>
						<li>Ochrana proti malware: Snižuje riziko, že malware získá administrátorská práva bez vědomí uživatele</li>	
					</ul>
					<li><strong>Možnosti Nastavení:</strong> Účty > Možnosti přihlášení nebo Ovládací panely</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔒 BitLocker</h2>
				<ul>
					<li>Šifrování celých disků i externích jednotek  před neoprávněným přístupem v případě ztráty nebo krádeže zařízení</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Šifrování disků: Umožňuje šifrovat systémové i datové disky</li>
						<li>TPM integrace: Využívá Trusted Platform Module (TPM) pro bezpečné ukládání šifrovacích klíčů</li>
						<ul>
							<li style="font-size: 15px; text-decoration:underline">Trusted Platform Module (TPM) je bezpečnostní čip v počítači, který slouží k uchovávání kryptografických klíčů a ověřování integrity systému. Chrání data tím, že umožňuje šifrování disku, bezpečné přihlašování a ověřování, že systém nebyl změněn škodlivým softwarem</li>
						</ul>
						<li>BitLocker to go: Šifrování externích disků a USB flash disků</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Přístupné přes Ovládací panely > Šifrování jednotky BitLocker</li>
						<li>Umožňuje zálohovat obnovovací klíče a nastavit metody ověřování (PIN, heslo)</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>👁️ Windows Hello</h2>
				<ul>
					<li>Biometrické přihlašování (obličej, otisk, duhovka)</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Biometrická autentizace: Nahrazuje tradiční hesla bezpečnějšími metodami</li>
						<li>Komfort a rychlost: Umožňuje rychlé přihlášení bez potřeby pamatovat si hesla</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Účty > Možnosti přihlášení</li>
						<li>Vyžaduje kompatibilní hardware</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🔐 Secure Boot</h2>
				<ul>
					<li>Bezpečnostní standard UEFI, který pomáhá zajistit, že počítač spustí pouze důvěryhodný software při startu systému</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Ochrana před malware při startu: Zabraňuje načtení škodlivého kódu při bootování</li>
						<li>Digitální podepisování: Vyžaduje, aby firmware a ovladače byly digitálně podepsány</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong> Konfigurace v BIOS/UEFI</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧪 Windows Defender Application Guard</h2>
				<ul>
					<li>Izoluje nedůvěryhodné webové stránky a aplikace v bezpečném kontejneru</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Izolace: Spouští Edge nebo aplikace v izolovaném prostředí pomocí virtualizace</li>
						<li>Ochrana před útoky: Zabraňuje škodlivému kódu z izolovaného prostředí ovlivnit hostitelský systém</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Konfigurace přes Windows Security > Virus & threat protection > Manage settings</li>
						<li>Pokročilá nastavení pomocí Group Policy nebo System Center Configuration Manager</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🔐 Windows Defender Credential Guard</h2>
				<ul>
					<li>Chrání přihlašovací údaje ukládáním ve virtualizovaném prostředí</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Ochrana pověřovacích údajů: Izolace LSA procesů, prevence útoků jako Pass-the-Hash</li>
						<li>Virtualizace: Využívá Hyper-V pro vytvoření bezpečného prostředí</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Vyžaduje Windows 10/11 Enterprise a podporu virtualizace v hardware</li>
						<li>Konfigurace přes Group Policy nebo Registry Editor</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🛡️ Windows Defender Exploit Guard</h2>
				<ul>
					<li>Funkce pro prevenci exploitů, kontrolu přístupu a chování aplikací</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Attack surface reduction: Omezuje oblasti napadnutelnosti</li>
						<li>Network protection: Blokuje nebezpečné odchozí připojení</li>
						<li>Controlled folder access: Chrání soubory a složky před neoprávněnými změnami</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Konfigurace přes Windows Security > Virus & threat protection > Manage settings</li>
						<li>Pokročilá nastavení pomocí Group Policy nebo System Center Configuration Manager</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🧠 Windows Defender SmartScreen</h2>
				<ul>
					<li>Filtrace škodlivých webových stránek a souborů ke stažení</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Webová ochrana: Varuje před nebezpečnými weby v Microsoft Edge</li>
						<li>Ochrana při stahování: Blokuje škodlivé soubory</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Nastavení v Windows Security > App & browser control</li>
						<li>Uživatelé mohou povolit, zakázat nebo upravit úroveň varování</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🔄 Windows Update</h2>
				<ul>
					<li>Zajišťuje aktuálnost systému pomocí bezpečnostních aktualizací a oprav</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Automatické aktualizace: Pravidelné stahování a instalace</li>
						<li>Možnosti odložení: Kontrola nad nasazením aktualizací</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Nastavení v Nastavení > Aktualizace a zabezpečení > Windows Update</li>
						<li>Pokročilá správa pomocí Windows Server Update Services (WSUS) nebo Microsoft Endpoint Configuration Manager</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>📦 Windows Sandbox</h2>
				<ul>
					<li>Bezpečné spouštění nedůvěryhodných aplikací v izolovaném prostředí</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Izolované prostředí: Každé spuštění je čistá instalace Windows</li>
						<li>Automatické odstranění: Po zavření se obsah trvale odstraní</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Dostupné v edicích Windows 10/11 Pro a Enterprise</li>
						<li>Lze povolit přes Windows Features</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🏢 Skupinové Politiky a Active Directory</h2>
				<ul>
					<li>Centrální správa a konfigurace nastavení v síti</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Centrální správa: Politiky pro OU (Organizational Unit (česky organizační jednotka)) v Active Directory</li>
						<li>Bezpečnostní nastavení: Hesla, přístupová práva, firewall atd.</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Správa přes Group Policy Management Console (GPMC)</li>
						<li>Umožňuje detailní kontrolu nad téměř všemi aspekty systému</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🧳 Windows Information Protection</h2>
				<ul>
					<li>Ochrana firemních dat před únikem na osobní zařízení nebo aplikace</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Oddělení dat: Firemní vs. osobní data na jednom zařízení</li>
						<li>Kontrola přístupu: Které aplikace mají přístup k firemním datům</li>
						<li>Šifrování: Automatické šifrování firemních dat</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Konfigurace pomocí Intune, System Center Configuration Manager nebo Group Policy</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🛡️ Microsoft Defender for Endpoint</h2>
				<ul>
					<li>Podnikové řešení pro pokročilou ochranu koncových zařízení</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Endpoint Detection and Response (EDR): Detekce a reakce na hrozby</li>
						<li>Threat & Vulnerability Management: Identifikace a oprava zranitelností</li>
						<li>Automatizovaná Reakce: Automatizace reakcí na incidenty</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Spravováno přes Microsoft 365 Defender portál</li>
						<li>Vyžaduje předplatné Microsoft 365 E5 nebo samostatné licence</li>
					</ul>
				</ul>
			</section>

			<section class="note">
				<h2>🖥️ Device Guard</h2>
				<ul>
					<li>Ochrana před spuštěním nedůvěryhodného kódu</li>
					<li><strong>Klíčové Funkce:</strong></li>
					<ul>
						<li>Code Integrity Policies: Pouze důvěryhodný kód</li>
						<li>Virtualization-Based Security: Ochrana kritických procesů pomocí virtualizace</li>
					</ul>
					<li><strong>Možnosti Nastavení:</strong></li>
					<ul>
						<li>Konfigurace přes Group Policy a PowerShell</li>
						<li>Konfigurace přes Group Policy a PowerShell Konfigurace přes Group Policy a PowerShell</li>
					</ul>
				</ul>
			</section>
			<section class="note">
				<h2>🧠 Další Bezpečnostní Funkce</h2>
				<ul>
					<li><strong>AppLocker:</strong> Umožňuje kontrolovat, které aplikace a soubory mohou být spuštěny</li>
					<li><strong>Controlled Folder Access:</strong> Chrání důležité složky před neoprávněnými změnami, zejména před ransomwarem</li>
					<li><strong>Windows Defender Firewall s pokročilým zabezpečením:</strong> Poskytuje detailní nastavení pravidel firewallu a IPSec</li>
					<li><strong>Encrypting File System (EFS):</strong> Umožňuje šifrovat jednotlivé soubory a složky</li>
					<li><strong>Credential Manager:</strong> Bezpečně ukládá přihlašovací údaje a hesla</li>
					<li><strong>Dynamic Lock:</strong> Automaticky uzamkne počítač, když se uživatel vzdálí (např. pomocí Bluetooth spárovaného zařízení)</li>
				</ul>
			</section>

			<a
				href="/PDF/Operacni_systemy_W_6_2_security_features_funkce_zabezpeceni_cz.pdf"
				class="ButtonExam"
				download
			>
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
