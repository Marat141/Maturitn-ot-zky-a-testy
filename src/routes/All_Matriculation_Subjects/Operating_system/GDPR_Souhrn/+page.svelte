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
				<a href="/All_Matriculation_Subjects/Operating_system/GDPR_Souhrn/Exam_GDPR_Souhrn" class="ButtonExam">Napsat si test</a>
			</div>

			<section id="bezpecnost" class="note">
				<h2>🔐 Informační bezpečnost</h2>
				<p><strong>Informační bezpečnost</strong> je soubor procesů, opatření, technologií a organizačních postupů, jejichž cílem je chránit důvěrnost, integritu a dostupnost informací a systémů.</p>
				<ul>
					<li>Zabránění neoprávněnému přístupu – silná hesla, šifrování, řízení přístupu.</li>
					<li>Zajištění, že data nejsou nechtěně změněna nebo zničena – zálohování, kontrolní mechanismy.</li>
					<li>Zajištění dostupnosti dat oprávněným uživatelům – např. vysoká dostupnost, obnova po havárii.</li>
				</ul>
				<p>Vzhledem k rostoucí hodnotě dat (např. osobní údaje, duševní vlastnictví, finanční informace) a rostoucí hrozbě (ransomware, phishing, APT) se informační bezpečnost neustále vyvíjí.</p>
				<p><strong>Informační bezpečnost je důležitá i z hlediska GDPR</strong>, protože zabezpečení zpracování osobních údajů je jednou ze základních zásad tohoto nařízení.</p>
			</section>

			<section id="gdpr" class="note">
				<h2>📚 GDPR – Obecné nařízení o ochraně osobních údajů</h2>
				
				<p><strong>GDPR</strong> je právní předpis Evropské unie (Nařízení (EU) 2016/679), který sjednocuje pravidla ochrany osobních údajů v celé EU a zvyšuje práva občanů na ochranu jejich dat.</p>
				
				<h3>🎯 Hlavní cíle GDPR</h3>
				<ul>
					<li>Rozšířená definice osobních údajů – vše, co může vést k identifikaci osoby (např. IP adresa, GPS, biometrie).</li>
					<li>Transparentnost a informovaný souhlas – subjekt musí vědět, proč a jak jsou jeho údaje zpracovávány.</li>
					<li>Silnější práva subjektů údajů – přístup, oprava, výmaz, přenositelnost, námitka.</li>
					<li>Zásady zpracování údajů – zákonnost, minimalizace, přesnost, omezená doba uchování, bezpečnost, odpovědnost.</li>
					<li>Povinnost hlásit úniky dat – do 72 hodin u incidentu s rizikem pro práva subjektů.</li>
					<li>Významné sankce – až 20 mil. EUR nebo 4 % celosvětového obratu.</li>
					<li>Zásada „privacy by design and by default“ – ochrana dat má být integrována od začátku návrhu systému a procesů.</li>
				</ul>

				<h3>⚙️ Základní podmínky pro zpracování údajů</h3>
				<p>Zpracování osobních údajů je možné jen pokud je splněna alespoň jedna z těchto podmínek:</p>
				<ul>
					<li>Souhlas subjektu údajů</li>
					<li>Plnění smlouvy</li>
					<li>Právní povinnost</li>
					<li>Ochrana životně důležitých zájmů</li>
					<li>Veřejný zájem / výkon veřejné moci</li>
					<li>Oprávněný zájem správce (pokud nepřevažují práva subjektu)</li>
				</ul>

				<h3>🧾 Souhlas se zpracováním údajů</h3>
				<ul>
					<li>Musí být svobodný, konkrétní, informovaný a jednoznačný.</li>
					<li>Nesmí být podmínkou pro poskytnutí služby, pokud není nutný.</li>
					<li>Musí být možné jej kdykoli odvolat.</li>
				</ul>

				<h3>👤 Subjekt údajů – práva podle GDPR</h3>
				<ul>
					<li><strong>Právo na informace:</strong> kdo, proč a jak zpracovává jeho data.</li>
					<li><strong>Právo na přístup:</strong> zjištění, jaké údaje o něm organizace uchovává.</li>
					<li><strong>Právo na opravu:</strong> opravení nepřesných údajů.</li>
					<li><strong>Právo na výmaz („být zapomenut“):</strong> pokud už nejsou údaje potřeba nebo byl odvolán souhlas.</li>
					<li><strong>Právo na omezení zpracování:</strong> např. pokud subjekt napadne správnost údajů.</li>
					<li><strong>Právo na přenositelnost údajů:</strong> převod údajů k jinému správci.</li>
					<li><strong>Právo vznést námitku:</strong> proti zpracování na základě oprávněného zájmu nebo pro marketing.</li>
					<li><strong>Právo nebýt předmětem automatizovaného rozhodování:</strong> včetně profilování, pokud má významný dopad.</li>
				</ul>

				<h3>🌍 Kde se GDPR uplatní?</h3>
				<ul>
					<li>Pro všechny organizace v EU, které zpracovávají osobní údaje.</li>
					<li>Také pro organizace mimo EU, pokud zpracovávají údaje osob v EU (např. online služby, e-shopy).</li>
				</ul>
			</section>

			<section id="zasady" class="note">
				<h2>🧱 Zásady zpracování osobních údajů</h2>
				<ul>
					<li><strong>„Zásady zpracování osobních údajů“</strong> jsou pravidla, která říkají, jak se mají osobní údaje správně, bezpečně a poctivě zpracovávat.</li>
					<li><strong>Zákonnost, korektnost a transparentnost:</strong> Osobní údaje musí být zpracovávány zákonným způsobem, férově a transparentně. Subjekt údajů musí být informován, kdo a proč údaje zpracovává.</li>
					<li><strong>Účelové omezení:</strong> Údaje smí být shromažďovány jen pro konkrétní a legitimní účely. Nesmí být následně zpracovávány způsobem, který s těmito účely není slučitelný.</li>
					<li><strong>Učelové omezení lajdsky:</strong> Když někdo sbírá moje osobní údaje, musí přesně říct, k čemu je potřebuje – a použít je jen na to. Ne na něco úplně jiného</li>
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
				
				<p><strong>Zpracování údajů</strong> <i>znamená jakoukoli operaci nebo soubor operací, kterou provádíš s osobními údaji – nejen jejich ukládání, ale také získávání, zaznamenávání, organizování, strukturování, úpravu, použití, předání, zpřístupnění, omezení nebo výmaz.</i> Týká se to manuálních (např. papírových) i elektronických prostředků. Zpracování může být prováděno automatizovaně nebo manuálně.</p>
				
				<p>Příklady činností, které se považují za zpracování:</p>
				<ul>
					<li>Shromažďování údajů (např. získávání kontaktních informací ve formuláři)</li>
					<li>Zaznamenání a ukládání údajů (např. do databáze nebo archivu)</li>
					<li>Uspořádání, strukturování a třídění údajů</li>
					<li>Úprava nebo změna údajů (např. aktualizace adresy)</li>
					<li>Vyhledávání nebo nahlížení do údajů</li>
					<li>Použití údajů (např. při poskytování služeb)</li>
					<li>Předání nebo zpřístupnění údajů třetím osobám</li>
					<li>Kombinování nebo sdružování údajů</li>
					<li>Omezení zpracování (např. omezení přístupu k údajům)</li>
					<li>Výmaz nebo zničení údajů</li>
				</ul>

				<p><strong>Profilování</strong> je specifický typ automatizovaného zpracování osobních údajů, jehož cílem je vyhodnocování určitých osobních aspektů fyzické osoby. Může se jednat o analýzu nebo předvídání chování, ekonomické situace, zdraví, osobních preferencí, zájmů, spolehlivosti, polohy nebo pohybu.</p>
				
				<ul>
					<li>Probíhá automaticky, pomocí algoritmů nebo umělé inteligence</li>
					<li>Slouží k analýze nebo predikci pracovního výkonu, chování, zdraví apod.</li>
					<li>Může vést k nespravedlivému zacházení nebo diskriminaci, pokud není správně regulováno</li>
				</ul>
				<p><strong>Charakteristické rysy profilování:</strong></p>
				<ul>
					<li>Automatizované zpracování: Profilování probíhá převážně pomocí softwarových nástrojů, algoritmůa umělé inteligence.</li>
					<li>Hodnotící a předpovídací prvek: Profilování není jen prosté zpracování dat, ale snaha odvodit z nich určité vlastnosti, kategorie, rizikové faktory či pravděpodobné chování jednotlivce.</li>
					<li>Rizika: Profilování může vést k nepřiměřeným zásahům do soukromí, diskriminaci nebo nespravedlivým rozhodnutím, pokud není prováděno transparentně a za dodržení pravidel na ochranu osobních údajů.</li>
				</ul>

				<p><strong>GDPR vyžaduje:</strong> transparentnost, právo být informován a možnost lidského zásahu v případě, že profilování má zásadní dopad na subjekt údajů (např. automatické zamítnutí žádosti o úvěr).</p>
			</section>

			<section id="role-a-povinnosti" class="note">
				<h2>📘 Role a povinnosti v ochraně osobních údajů</h2>

				<h3>🔑 Pseudonymizace</h3>
				<p><strong>Pseudonymizace</strong> je proces, při kterém jsou identifikátory osobních údajů (např. jméno, rodné číslo) nahrazeny jinými prvky (např. kódem), které bez dodatečných informací nelze spojit s konkrétní osobou.</p>
				<ul>
					<li><strong>Oddělení identifikátorů:</strong> Dodatečné informace (např. klíče) jsou uchovány zvlášť a chráněny.</li>
					<li><strong>Zvýšení bezpečnosti:</strong> Snížení rizika zneužití údajů při neoprávněném přístupu.</li>
					<li><strong>Rozdíl oproti anonymizaci:</strong> U pseudonymizace zůstává možnost zpětné identifikace, u anonymizace nikoliv.</li>
					<li>Jde stále o <strong>zpracování osobních údajů</strong> dle GDPR.</li>
				</ul>

				<h3>📋 Záznam o činnostech zpracování (Records of Processing Activities, ROPA)</h3>
				<p>Záznam o činnostech zpracování dle čl. 30 GDPR je dokument, který obsahuje přehled o tom, jaké osobní údaje organizace zpracovává, proč a jakým způsobem.</p>
				<ul>
					<li>Jméno a kontakt na správce, zpracovatele a DPO (pokud je jmenován)</li>
					<li>Účely zpracování (např. účetnictví, marketing, smlouvy)</li>
					<li>Kategorie subjektů údajů a údajů samotných</li>
					<li>Kategorie příjemců</li>
					<li>Předávání do třetích zemí a záruky</li>
					<li>Lhůty pro výmaz údajů</li>
					<li>Technická a organizační bezpečnostní opatření (např. šifrování, pseudonymizace)</li>
				</ul>

				<h3>👤 Správce (Controller)</h3>
				<p><strong>Správce</strong> je subjekt, který určuje účely („proč“) a prostředky („jak“) zpracování osobních údajů.</p>
				<ul>
					<li>Odpovídá za soulad se GDPR</li>
					<li>Může využívat zpracovatele, ale nese hlavní odpovědnost</li>
					<li>Příklady: e-shop, škola, zaměstnavatel</li>
				</ul>

				<h3>🛠️ Zpracovatel (Processor)</h3>
				<p><strong>Zpracovatel</strong> zpracovává údaje jménem správce a podle jeho pokynů.</p>
				<ul>
					<li>Nemůže rozhodovat o účelu a prostředcích zpracování</li>
					<li>Musí mít uzavřenou zpracovatelskou smlouvu se správcem</li>
					<li>Musí zajistit bezpečnost zpracování</li>
					<li>Příklady: účetní firma, IT dodavatel, cloudový hosting</li>
				</ul>

				<h3>📨 Příjemce a třetí strana</h3>
				<p><strong>Příjemce</strong> je subjekt, kterému jsou osobní údaje zpřístupněny. Může být i <strong>zpracovatel</strong> nebo <strong>správce</strong>, ale může jít i o <strong>třetí stranu</strong>.</p>
				<ul>
					<li><strong>Třetí strana</strong> není subjekt údajů, správce ani zpracovatel</li>
					<li>Příklady třetí strany: policie, obchodní partner, který používá údaje pro vlastní účely</li>
				</ul>

				<h3>🧑‍⚖️ Pověřenec pro ochranu osobních údajů (DPO)</h3>
				<p><strong>DPO</strong> je osoba, která dohlíží na dodržování GDPR v organizaci, poskytuje poradenství a je kontaktním bodem pro úřady i občany.</p>
				<ul>
					<li>Povinný u veřejných subjektů, rozsáhlého monitorování nebo zpracování citlivých údajů</li>
					<li>Musí být nezávislý a mít odborné znalosti</li>
					<li>Může být jmenován i dobrovolně</li>
				</ul>

				<h3>🚨 Ohlašovací povinnost</h3>
				<p>Porušení zabezpečení osobních údajů (např. únik, ztráta, neoprávněný přístup) musí být oznámeno do 72 hodin Úřadu pro ochranu osobních údajů, pokud hrozí riziko pro fyzické osoby.</p>
				<ul>
					<li>Vysoké riziko → nutné informovat i dotčené osoby</li>
					<li>Výjimky: např. pokud byly údaje šifrované</li>
					<li>Hlášení musí obsahovat popis incidentu, počet dotčených osob, přijatá opatření apod.</li>
				</ul>
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
