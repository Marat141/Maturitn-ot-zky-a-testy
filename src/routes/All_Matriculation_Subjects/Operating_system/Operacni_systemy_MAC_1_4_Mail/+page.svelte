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
</script>

<main>
	<div class="layout">
		<Navigation {headings} />
		<div class="content">
			<div class="header-with-button">
				<h1>Mac OS – část 1.4: Aplikace Mail</h1>
				<a href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail/Exam_Operacni_systemy_MAC_1_4_Mail" class="ButtonExam">
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📨 Funkce aplikace Mail</h2>
				<ul>
					<li><strong>Více typů účtů:</strong> Podpora IMAP, POP3, Exchange, iCloud, Gmail, Outlook a dalších poskytovatelů</li>
					<li><strong>Správa více účtů:</strong> Přepínání mezi účty v jedné aplikaci, neomezený počet účtů</li>
					<li><strong>Pořádek v poště:</strong> Možnost vytvářet složky, inteligentní schránky (Smart Mailboxy), pravidla pro třídění</li>
					<li><strong>Přílohy:</strong> Náhledy, úprava přes Markup (např. PDF, obrázky)</li>
					<li><strong>Kontinuita:</strong> Handoff – psaní mailu na iPhonu, dokončení na Macu</li>
					<li><strong>Vyhledávání:</strong> Výkonné a rychlé hledání podle odesílatele, obsahu, příloh aj.</li>
					<li><strong>Podpisy:</strong> Vytváření různých podpisů pro jednotlivé účty</li>
					<li><strong>Ochrana:</strong> Spam filtr, blokace odesílatelů, nastavitelná pravidla</li>
					<li><strong>Notifikace:</strong> Přizpůsobitelné upozornění, různé zvuky a styly</li>
					<li><strong>Integrace:</strong> Automatické rozpoznání událostí v e-mailech, přidání do Kalendáře/Připomínek</li>
					<li><strong>Zabezpečení:</strong> Šifrování přes SSL/TLS, podpora Kerberos/NTLM, integrace s Gatekeeperem</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Nastavení účtů</h2>
				<ul>
					<li><strong>iCloud:</strong> Stačí Apple ID a heslo, často se vše nastaví automaticky. Podporuje dvoufaktorové ověření</li>
					<li><strong>IMAP:</strong> Potřebuje adresy serverů (IMAP a SMTP), porty (993, 465/587), SSL a autentizaci</li>
					<li><strong>POP:</strong> Stahuje poštu na zařízení, nastavení podobné jako IMAP. Možnost zachování kopie na serveru</li>
					<li><strong>Exchange:</strong> EWS podpora, doména, server (Autodiscover nebo ručně), často Kerberos/NTLM autentizace</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧪 Příklad – Nastavení IMAP účtu</h2>
				<ul>
					<li>Mail → Předvolby → Účty → „+“ → Jiný poštovní účet</li>
					<li>Zadat jméno, e-mailovou adresu a heslo</li>
					<li>Při chybě → ruční zadání serverů (IMAP/SMTP), porty, SSL a typ ověřování</li>
					<li>IMAP server: např. <code>imap.gmail.com</code>, SMTP: <code>smtp.gmail.com</code></li>
					<li>Porty: 993 (IMAP-SSL), 465/587 (SMTP-SSL/TLS)</li>
					<li>Ověřit → stáhnout zprávy → odeslat testovací e-mail</li>
				</ul>
			</section>

			<section class="note">
				<h2>📂 Smart Mailbox (chytrá schránka)</h2>
				<ul>
					<li>Virtuální složka zobrazující e-maily na základě zadaných kritérií (např. odesílatel, příznak, slovo v předmětu)</li>
					<li>Nejde o fyzické přesunutí zpráv – jen dynamický výběr</li>
					<li>Vytvoření: Mailbox → Nová chytrá schránka → nastavení pravidel</li>
					<li>Příklady: Nepřečtené e-maily, zprávy s příznakem, zprávy od určité osoby</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔐 Zabezpečení a doporučení</h2>
				<ul>
					<li><strong>Dvoufaktorové ověření:</strong> Doporučeno u všech poskytovatelů (např. Gmail)</li>
					<li><strong>SSL/TLS:</strong> Zabezpečení přenosu zpráv a hesel</li>
					<li><strong>Pozor na autentizaci:</strong> Někteří poskytovatelé vyžadují „app-specific“ hesla nebo povolení méně zabezpečených aplikací</li>
				</ul>
			</section>

			<section class="note">
				<h2>📌 Tipy</h2>
				<ul>
					<li>Pokud selže připojení, ověřte porty, server a zabezpečení</li>
					<li>Pravidelně zálohujte pomocí Time Machine</li>
					<li>Pro test použijte jednoduchý e-mail s předmětem „Test“</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_MAC_1_4_Mail.pdf" class="ButtonExam" download>
				📄 Stáhnout PDF
			</a>
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
