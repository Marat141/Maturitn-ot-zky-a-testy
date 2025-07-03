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
				<h1 id="gdpr">GDPR: Souhrn</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn/Exam_GDPR_Souhrn"
					class="ButtonExam">Napsat si test</a
				>
			</div>

			<section id="principy" class="note">
				<h2>📋 Hlavní principy GDPR</h2>
				<ul>
					<li>Platí v celé EU, účinné od 25. května 2018</li>
					<li>Posiluje práva subjektů nad osobními údaji (Lidé (tzv. subjekty údajů) mají větší kontrolu a práva nad tím, jak jsou jejich osobní údaje zpracovávány.)</li>
					<li>Vyžaduje transparentnost a informovaný souhlas</li>
					<li>Stanovuje přísné sankce (až 20 mil. EUR nebo 4 % obratu)</li>
					<li><strong>Zásady zpracování údajů:</strong> zákonnost, účelnost, minimalizace, bezpečnost</li>
				</ul>
			</section>

			<section id="zasady" class="note">
				<h2>🧱 Zásady zpracování osobních údajů</h2>
				<ul>
					<li><strong>„Zásady zpracování osobních údajů“</strong> jsou pravidla, která říkají, jak se mají osobní údaje správně, bezpečně a poctivě zpracovávat.</li>
					<li><strong>Zákonnost, korektnost a transparentnost:</strong> Osobní údaje musí být zpracovávány zákonným způsobem, férově a transparentně. Subjekt údajů musí být informován, kdo a proč údaje zpracovává.</li>
					<li><strong>Účelové omezení:</strong> Údaje smí být shromažďovány jen pro konkrétní a legitimní účely. Nesmí být následně zpracovávány způsobem, který s těmito účely není slučitelný.</li>
					<li><strong>Učelové omezení lajdsky:</strong> Když někdo sbírá tvoje osobní údaje, musí přesně říct, k čemu je potřebuje – a použít je jen na to. Ne na něco úplně jiného</li>
					<li><strong>Minimalizace údajů:</strong> Sbírají se pouze údaje, které jsou nezbytné pro dosažení daného účelu.</li>
					<li><strong>Přesnost:</strong> Údaje musí být aktuální a přesné. Nepřesné údaje musí být bez prodlení opraveny nebo vymazány.</li>
					<li><strong>Omezené uložení:</strong> Údaje nesmí být uchovávány déle, než je nutné pro daný účel.</li>
					<li><strong>Integrita a důvěrnost:</strong> Musí být zajištěna bezpečnost osobních údajů, a to jak technickými, tak organizačními prostředky. Je nutné chránit je před neoprávněným přístupem, zničením nebo poškozením.</li>
					<li><strong>Odpovědnost správce:</strong> Správce odpovídá za dodržování těchto zásad a musí být schopen jejich dodržení prokázat (zásada odpovědnosti).</li>
				</ul>
			</section>

			<section id="prava" class="note">
				<h2>⚖️ Práva subjektu údajů</h2>
				<ul>
					<li><strong>Právo na informace:</strong> Subjekt musí být informován, kdo, jak a proč jeho údaje zpracovává. To zahrnuje např. dobu uchování, zdroj údajů a příjemce.</li>
					<li><strong>Právo na přístup:</strong> Jednotlivec má právo získat potvrzení, zda jsou jeho údaje zpracovávány, a získat k nim přístup, včetně kopie těchto údajů.</li>
					<li><strong>Právo na opravu:</strong> Pokud jsou údaje nepřesné nebo neúplné, subjekt má právo žádat jejich opravu nebo doplnění.</li>
					<li><strong>Právo na výmaz ("být zapomenut"):</strong> Subjekt může žádat smazání údajů, pokud např. odvolal souhlas, údaje nejsou dále potřebné nebo byly zpracovány nezákonně.</li>
					<li><strong>Právo na omezení zpracování:</strong> V určitých případech může subjekt žádat, aby správce údaje pouze uchovával, ale dále s nimi nepracoval.</li>
					<li><strong>Právo na přenositelnost:</strong> Subjekt má právo získat své údaje ve strukturovaném, běžně používaném a strojově čitelném formátu a předat je jinému správci.</li>
					<li><strong>Právo vznést námitku:</strong> Subjekt může kdykoli vznést námitku proti zpracování na základě oprávněného zájmu správce nebo při přímém marketingu.</li>
					<li><strong>Právo nebýt předmětem automatizovaného rozhodování:</strong> Subjekt má právo nebýt cílem rozhodnutí založeného pouze na automatizovaném zpracování (např. profilování), pokud má toto rozhodnutí právní účinky nebo se ho významně dotýká. Má také právo požadovat lidský zásah.</li>
				</ul>
			</section>
			<section id="zpracovani" class="note">
				<h2>⚙️ Zpracování údajů & Profilování</h2>
				<p><strong>Zpracování údajů</strong> znamená jakoukoli operaci, kterou provádíš s osobními údaji – nejen jejich ukládání, ale i získávání, organizování, úpravu, použití, přenos, omezení nebo výmaz.</p>
				<ul>
					<li>Příklady: shromažďování údajů ve formuláři, uložení do databáze, změna adresy, zpřístupnění třetí straně.</li>
					<li>Zpracování se týká jak manuálních (papírových), tak elektronických prostředků.</li>
				</ul>
				<p><strong>Profilování</strong> je specifický typ automatizovaného zpracování, který využívá osobní údaje k hodnocení určitých aspektů osoby – např. chování, preference, ekonomická situace apod.</p>
				<ul>
					<li>Probíhá pomocí algoritmů a AI.</li>
					<li>Cílem je analyzovat nebo předvídat např. pracovní výkon, zdraví nebo chování.</li>
					<li>Profilování může vést k diskriminaci nebo nespravedlivým rozhodnutím, pokud není regulováno.</li>
				</ul>
				<p><strong>GDPR vyžaduje:</strong> transparentnost a možnost lidského zásahu u profilování, pokud má zásadní dopad na subjekt údajů.</p>
			</section>


			<section id="bezpecnost" class="note">
				<h2>🔐 Informační bezpečnost</h2>
				<p>Soubor technických a organizačních opatření k ochraně <strong>důvěrnosti</strong>, <strong>integrity</strong> a <strong>dostupnosti</strong> osobních údajů.</p>
				<ul>
					<li>Zabránění neoprávněnému přístupu – např. silná hesla, šifrování, přístupová práva.</li>
					<li>Zajištění, že data nejsou upravena či zničena bez oprávnění.</li>
					<li>Zajištění dostupnosti dat pro oprávněné uživatele, kdykoli je potřebují.</li>
				</ul>
				<p>Vzhledem k rostoucí hodnotě dat a kybernetickým hrozbám (ransomware, phishing, APT) se informační bezpečnost neustále vyvíjí.</p>
			</section>


			<section id="zaklady" class="note">
				<h2>✅ Právní základy pro zpracování údajů</h2>
				<ul>
					<li><strong>Souhlas subjektu údajů:</strong> Dobrovolný, konkrétní, informovaný a jednoznačný souhlas. Musí být možné jej kdykoliv odvolat.</li>
					<li><strong>Plnění smlouvy:</strong> Zpracování je nezbytné pro splnění smlouvy, kterou subjekt uzavřel (např. doručení zboží).</li>
					<li><strong>Právní povinnost:</strong> Zpracování je vyžadováno zákonem (např. evidence pro daňové účely).</li>
					<li><strong>Životně důležité zájmy:</strong> Zpracování je nezbytné k ochraně života nebo zdraví subjektu (např. v případě nehody).</li>
					<li><strong>Veřejný zájem nebo výkon veřejné moci:</strong> Např. při zpracování policií, úřady nebo zdravotníky.</li>
					<li><strong>Oprávněný zájem správce:</strong> Zpracování je nezbytné pro oprávněný zájem organizace, pokud nepřeváží práva subjektu údajů.</li>
				</ul>
			</section>


			<section id="zvlastni-udaje" class="note">
				<h2>🛑 Zvláštní kategorie osobních údajů</h2>
				<p>Tyto údaje jsou považovány za citlivé a je zakázáno je zpracovávat, pokud neexistuje výslovný souhlas nebo výjimka podle zákona.</p>
				<ul>
					<li>Údaje o rasovém nebo etnickém původu</li>
					<li>Politické názory, náboženské nebo filozofické přesvědčení</li>
					<li>Členství v odborech</li>
					<li>Genetické a biometrické údaje</li>
					<li>Údaje o zdravotním stavu nebo sexuální orientaci</li>
					<li>Údaje o trestných činech (pouze pokud to umožňuje právo EU/členského státu)</li>
				</ul>
				<p>Zpracování je přípustné pouze za přísných podmínek, například pokud je to nezbytné z důvodu významného veřejného zájmu nebo za účelem zdravotní péče.</p>
			</section>


			<section id="uniky" class="note">
				<h2>🔄 Povinnost hlásit úniky dat</h2>
				<p>Poruší-li organizace zabezpečení osobních údajů, musí tento incident oznámit bez zbytečného odkladu, nejpozději do 72 hodin od zjištění.</p>
				<ul>
					<li><strong>Kdy hlásit:</strong> Pokud existuje riziko pro práva a svobody fyzických osob (např. riziko zneužití, finanční ztráty, diskriminace, narušení důvěrnosti).</li>
					<li><strong>Komu se hlásí:</strong> Úřadu pro ochranu osobních údajů (v ČR: ÚOOÚ), případně také přímo subjektům údajů, pokud je riziko vysoké.</li>
					<li><strong>Co musí hlášení obsahovat:</strong> Povaha incidentu, počet dotčených osob, kontakt na pověřence pro ochranu údajů, pravděpodobné dopady a přijatá nebo navrhovaná opatření.</li>
					<li><strong>Výjimka z ohlašovací povinnosti:</strong> Pokud je nepravděpodobné, že došlo k ohrožení práv a svobod jednotlivců, hlášení není nutné.</li>
				</ul>
				<p>Včasné a správné ohlášení úniku je klíčové pro minimalizaci dopadů a vyhnutí se sankcím.</p>
			</section>

			<section id="pojmy" class="note">
				<h2>🔑 Klíčové pojmy</h2>
				<ul>
					<li><strong>Osobní údaj:</strong> Jakákoli informace, která se týká identifikované nebo identifikovatelné fyzické osoby. Identifikovatelná osoba je ta, kterou lze přímo (např. jménem) nebo nepřímo (např. IP adresou) určit.</li>
					<li><strong>Příklady osobních údajů:</strong> jméno, e-mail, adresa, rodné číslo, IP adresa, lokalizační data, číslo průkazu totožnosti.</li>
					<li><strong>Citlivé údaje (zvláštní kategorie):</strong> Údaje o zdraví, biometrické údaje (např. otisky prstů), genetika, sexuální orientace, politické názory, náboženské či filozofické přesvědčení.</li>
					<li><strong>Pseudonymizace:</strong> Proces, při kterém jsou identifikátory (např. jméno) nahrazeny jinými prvky (např. kód, hash), aby nebylo možné přímo určit konkrétní osobu bez doplňujících údajů.</li>
					<li><strong>Rozdíl mezi anonymizací a pseudonymizací:</strong> Anonymizace odstraní možnost zpětné identifikace, zatímco pseudonymizace ji umožňuje pomocí odděleného klíče.</li>
				</ul>
			</section>

			<a href="/PDF/GDPR_souhrn.pdf" class="ButtonExam" download> 📄 Stáhnout PDF </a>
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
