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
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_4_Mail/Exam_Operacni_systemy_MAC_1_4_Mail"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>📨 Funkce aplikace Mail</h2>
				<ul>
					<li>
						<strong>Více typů účtů:</strong> Podpora IMAP, POP3, Exchange, iCloud, Gmail, Outlook a dalších
						poskytovatelů
					</li>
					<li>
						<strong>Správa více účtů:</strong> Přepínání mezi účty v jedné aplikaci, neomezený počet
						účtů
					</li>
					<li>
						<strong>Pořádek v poště:</strong> Možnost vytvářet složky, inteligentní schránky (Smart Mailboxy),
						pravidla pro třídění
					</li>
					<li><strong>Přílohy:</strong> Náhledy, úprava přes Markup (např. PDF, obrázky)</li>
					<li><strong>Kontinuita:</strong> Handoff – psaní mailu na iPhonu, dokončení na Macu</li>
					<li>
						<strong>Vyhledávání:</strong> Výkonné a rychlé hledání podle odesílatele, obsahu, příloh
						aj.
					</li>
					<li><strong>Podpisy:</strong> Vytváření různých podpisů pro jednotlivé účty</li>
					<li><strong>Ochrana:</strong> Spam filtr, blokace odesílatelů, nastavitelná pravidla</li>
					<li><strong>Notifikace:</strong> Přizpůsobitelné upozornění, různé zvuky a styly</li>
					<li>
						<strong>Integrace:</strong> Automatické rozpoznání událostí v e-mailech, přidání do Kalendáře/Připomínek
					</li>
					<li>
						<strong>Zabezpečení:</strong> Šifrování přes SSL/TLS, podpora Kerberos/NTLM, integrace s
						Gatekeeperem
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚙️ Nastavení účtů</h2>
				<ul>
					<li>
						<strong>iCloud:</strong> Stačí Apple ID a heslo, často se vše nastaví automaticky. Podporuje
						dvoufaktorové ověření
					</li>
					<li>
						<strong>IMAP:</strong> Potřebuje adresy serverů (IMAP a SMTP), porty (993, 465/587), SSL
						a autentizaci
					</li>
					<li>
						<strong>POP:</strong> Stahuje poštu na zařízení, nastavení podobné jako IMAP. Možnost zachování
						kopie na serveru
					</li>
					<li>
						<strong>Exchange:</strong> EWS podpora, doména, server (Autodiscover nebo ručně), často Kerberos/NTLM
						autentizace
					</li>
				</ul>

				<details class="details-block">
					<summary>📖 Zobrazit podrobný popis</summary>
					<div class="details-content">
						<h3>📬 iCloud</h3>
						<ul>
							<li><strong>Co je třeba zadat</strong></li>
							<ul>
								<li>Používá <strong>Apple ID</strong> jako přihlašovací údaj</li>
								<li>
									<strong>Heslo (pro Apple ID)</strong> nebo tzv. heslo pro aplikaci (při 2FA)
								</li>
							</ul>
						</ul>
						<ul>
							<li><strong>Poznámky k iCloud</strong></li>
							<ul>
								<li>macOS nastavení zjistí automaticky</li>
								<li>Pošta se synchronizuje mezi všemi zařízeními s tímto Apple ID</li>
							</ul>
						</ul>

						<h3>📬 IMAP</h3>
						<ul>
							<li><strong>Co je třeba zadat</strong></li>
							<ul>
								<li>
									<strong>E-mailová adresa a uživatelské jméno</strong> (někdy se shodují, jindy se liší
									– např. u firemní schránky může být „jméno@firma.cz“ a uživatelské jméno jen „jméno“).
								</li>
								<li><strong>Heslo</strong> k účtu</li>
								<li><strong>Adresy k účtu:</strong></li>
								<ul>
									<li>
										<strong>Server příchozí pošty (IMAP)</strong> – např. imap.seznam.cz, imap.gmail.com
										apod.
									</li>
									<li>
										<strong>Server odchozí pošty (SMTP)</strong> – např. smtp.seznam.cz, smtp.gmail.com
									</li>
								</ul>
								<li><strong>Porty:</strong></li>
								<ul>
									<li>IMAP běžně používá port 143 (nešifrovaně) nebo 993 (šifrovaně/SSL)</li>
									<li>SMTP běžně používá port 25, 465 (SSL) nebo 587 (TLS)</li>
								</ul>
								<li>
									<strong>Typ zabezpečení</strong> (SSL/TLS) – obvykle vyberete v aplikaci Mail šifrované
									připojení, aby byla komunikace chráněná
								</li>
								<li>
									Případně <strong>metoda ověření</strong>(heslo/SPA/Kerberos) – nejčastěji heslo
									(Password)
								</li>
							</ul>
						</ul>
						<ul>
							<li><strong>Poznámky k IMAP</strong></li>
							<ul>
								<li>
									E-maily zůstávají uloženy na serveru, dokud je neodstraníte (buď v Mailu, nebo
									přes webové rozhraní)
								</li>
								<li>
									Změny ve složkách (přesuny, mazání, označování) se synchronizují se serverem a
									dalšími zařízeními
								</li>
							</ul>
						</ul>

						<h3>📬 POP</h3>
						<ul>
							<li><strong>Co je třeba zadat</strong></li>
							<ul>
								<li><strong>E-mailová adresa a uživatelské jméno</strong></li>
								<li><strong>Heslo</strong> k účtu</li>
								<li>
									<strong>Server příchozí pošty (POP)</strong> – např. pop.seznam.cz, pop.gmail.com.
								</li>
								<li>
									<strong>Server odchozí pošty (SMTP)</strong> – stejně jako u IMAP, např. smtp.seznam.cz,
									smtp.gmail.com
								</li>
								<li><strong>Porty:</strong></li>
								<ul>
									<li>POP běžně používá port 110 (nešifrovaně) nebo 995 (šifrovaně/SSL)</li>
									<li>SMTP porty jsou stejné jako u IMAP (25, 465, 587)</li>
								</ul>
								<li><strong>Typ zabezpečení</strong> (SSL/TLS)</li>
								<li>
									<strong>Zachování kopií na serveru</strong> – v nastavení POP účtu v Mailu obvykle
									volíte, zda se po stažení mají zprávy na serveru ponechat či smazat
								</li>
							</ul>
							<li><strong>Poznámky k POP</strong></li>
							<ul>
								<li>
									POP účty standardně stahují zprávy na lokální počítač a ne vždy je synchronizují
									na serveru (pokud si nastavení nepřizpůsobíte)
								</li>
								<li>
									Pokud ponecháváte zprávy na serveru, můžete je stahovat i z jiných zařízení, ale
									při mazání v jedné aplikaci nemusí dojít k synchronizaci s ostatními klienty
								</li>
							</ul>
						</ul>

						<h3>📬 Exchange</h3>
						<ul>
							<li><strong>Co je třeba zadat</strong></li>
							<ul>
								<li>
									<strong>E-mailová adresa</strong> – často se zadává zároveň ve formě uživatel@domena.cz
								</li>
								<li>
									<strong>Uživatelské jméno</strong> (v některých firmách to může být i formát jako domena\uzivatel)
								</li>
								<li><strong>Heslo</strong> k účtu</li>
								<li>
									<strong>Doména</strong> – pokud ji server vyžaduje (v podnikových prostředích)
								</li>
								<li>
									<strong>Server (URL Exchange)</strong> – někdy se zjistí automaticky přes Autodiscover,
									jindy je nutné ho zadat ručně (např. mail.firma.cz)
								</li>
								<li>
									<strong>Typ zabezpečení a ověření</strong> – často integrovaná ověřování (NTLM, Kerberos)
									nebo prosté zadání hesla
								</li>
							</ul>
							<li><strong>Poznámky k Exchange</strong></li>
							<ul>
								<li>
									Server musí podporovat EWS (Exchange Web Services), aby jej bylo možné
									konfigurovat v Mailu
								</li>
								<li>Stejně jako u IMAP zůstávají zprávy fyzicky na serveru</li>
								<li>
									Exchange nabízí další funkce, jako je například sdílení kalendářů či kontaktů
								</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🧪 Příklad – Nastavení IMAP účtu na macOS</h2>
				<ol>
					<li>
						<strong>Spuštění aplikace Mail:</strong>
						<ul>
							<li>Otevři aplikaci Mail z Docku nebo ze složky Aplikace</li>
							<li>Pokud máš už nějaké účty přidané, otevře se rovnou hlavní okno</li>
						</ul>
					</li>
					<li>
						<strong>Přidání nového účtu:</strong>
						<ul>
							<li>V horním menu klikni na <em>Mail → Nastavení</em> (nebo <em>Předvolby</em>)</li>
							<li>Přejdi na záložku <strong>Účty</strong>, klikni na <strong>+</strong></li>
							<li>
								Vyber <strong>Jiný poštovní účet…</strong> a klikni na <strong>Pokračovat</strong>
							</li>
						</ul>
					</li>
					<li>
						<strong>Základní údaje:</strong>
						<ul>
							<li>Jméno (např. Jan Novák – jak se zobrazí příjemcům)</li>
							<li>E-mailová adresa (např. [email protected])</li>
							<li>Heslo k e-mailu → klikni na <strong>Přihlásit se</strong></li>
							<li>Pokud se nepodaří automatické připojení, zobrazí se rozšířená konfigurace</li>
						</ul>
					</li>
					<li>
						<strong>Ruční nastavení (pokud autodetekce selže):</strong>
						<ul>
							<li><strong>Typ účtu:</strong> IMAP</li>
							<li><strong>IMAP server:</strong> např. <code>imap.gmail.com</code></li>
							<li><strong>SMTP server:</strong> např. <code>smtp.gmail.com</code></li>
							<li>
								<strong>Uživatelské jméno:</strong> často celé e-mailové jméno nebo jen část (liší se
								podle poskytovatele)
							</li>
							<li><strong>Heslo:</strong> může se požadovat znovu</li>
						</ul>
					</li>
					<li>
						<strong>Rozšířená konfigurace:</strong>
						<ul>
							<li><strong>Porty:</strong> 993 pro IMAP-SSL, 465 nebo 587 pro SMTP-SSL/TLS</li>
							<li><strong>Zabezpečení:</strong> zapni <strong>SSL/TLS</strong> pro oba servery</li>
							<li><strong>Ověřování:</strong> zpravidla metoda „heslo“</li>
						</ul>
					</li>
					<li>
						<strong>Test funkčnosti:</strong>
						<ul>
							<li>Zavři okno nastavení</li>
							<li>Zkontroluj složku „Přijatá pošta“</li>
							<li>Odešli testovací e-mail s předmětem „Test“</li>
						</ul>
					</li>
				</ol>

				<h3>💡 Tipy na závěr:</h3>
				<ul>
					<li>Uživatelské jméno a heslo musí přesně odpovídat údajům poskytovatele</li>
					<li>Doporučeno: zapnout SSL/TLS pro bezpečný přenos</li>
					<li>Pokud se přihlášení nedaří, zkontroluj porty a nastavení zabezpečení</li>
					<li>
						U některých poskytovatelů (např. Gmail) může být nutné povolit přístup pro „méně
						zabezpečené aplikace“ nebo vytvořit tzv. „app-specific password“
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📂 Smart Mailbox (chytrá schránka)</h2>
				<ul>
					<li>
						<strong>Smart mailbox</strong> je virtuální složka, která dynamicky zobrazuje e-maily podle
						zadaných filtrů
					</li>
					<li>Zprávy nejsou fyzicky přesunuty – zobrazí se pouze pokud splňují pravidla</li>
					<li>
						Např. e-maily s příznakem, od konkrétní osoby, obsahující klíčová slova, nebo nepřečtené
						zprávy
					</li>
					<li>Pravidla můžeš nastavit dle vlastních potřeb (kombinace podmínek)</li>
				</ul>
				<ol>
					<li>Otevři Mail</li>
					<li>
						Menu → <strong>Schránka (Mailbox)</strong> → <strong>Nová chytrá schránka</strong>
					</li>
					<li>Zadej název (např. „Zprávy od šéfa“)</li>
					<li>Definuj podmínky (např. „odesílatel je [email protected]“)</li>
					<li>Ulož → zobrazí se v postranním panelu</li>
				</ol>
				<p>📌 Vhodné pro přehled nad prioritními zprávami napříč všemi účty.</p>
			</section>

			<section class="note">
				<h2>🔐 Zabezpečení a doporučení</h2>
				<ul>
					<li>
						<strong>Dvoufaktorové ověření:</strong> Doporučeno u všech poskytovatelů (např. Gmail)
					</li>
					<li><strong>SSL/TLS:</strong> Zabezpečení přenosu zpráv a hesel</li>
					<li>
						<strong>Pozor na autentizaci:</strong> Někteří poskytovatelé vyžadují „app-specific“ hesla
						nebo povolení méně zabezpečených aplikací
					</li>
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

	.details-block summary {
		cursor: pointer;
		font-weight: 600;
		color: #2563eb;
		margin-top: 12px;
		margin-bottom: 8px;
		user-select: none;
		transition: color 0.2s ease;
	}

	.details-block[open] summary {
		color: #1d4ed8;
	}

	.details-content {
		margin-left: 20px;
		padding: 10px 0 0 8px;
		border-left: 2px solid #cbd5e1;
		font-size: 15px;
	}

	.details-content h3 {
		margin-top: 12px;
		margin-bottom: 6px;
		color: #111827;
		font-size: 15px;
	}

	.details-content ul {
		list-style: disc;
		padding-left: 24px;
		margin-bottom: 8px;
	}

	.details-content li {
		margin-bottom: 6px;
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
