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
				<h1 id="gdpr-opatreni">GDPR: Technická a organizační opatření</h1>
				<a href="/PDF/GDPR-Technicka_opatreni.pdf" class="ButtonExam" download>📄 Stáhnout PDF</a>
			</div>

			<section id="uvod" class="note">
				<h2>📘 Úvod</h2>
				<p>
					GDPR klade důraz na ochranu osobních údajů pomocí <strong>technických</strong> a
					<strong>organizačních</strong>
					opatření. Klíčová je schopnost doložit, že bezpečnostní kroky byly učiněny (<em
						>accountability</em
					>).
				</p>
			</section>

			<section id="ntfs" class="note">
				<h2>🗂️ Nastavení práv NTFS</h2>
				<ul>
					<li>Detailní řízení přístupu k souborům a složkám ve Windows.</li>
					<li>Pomáhá naplnit zásadu omezení přístupu (<strong>need-to-know</strong>).</li>
					<li>Chrání důvěrnost dat (např. pomocí oprávnění <code>read/write/modify</code>).</li>
				</ul>

				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>
									NTFS (New Technology File System) v systémech Windows umožňuje detailní
									konfiguraci přístupu k souborům a složkám. Je tak možné přesně nastavit, kdo může
									data číst, upravovat, mazat či spouštět
								</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li>
									<strong>Zásada omezení přístupu (need-to-know):</strong> Podle čl. 32 GDPR je jednou
									ze základních povinností správce omezit přístup k osobním údajům pouze na osoby, které
									je k výkonu své práce skutečně potřebují
								</li>
								<li>
									<strong>Ochrana důvěrnosti:</strong> Přesné nastavení oprávnění (read, write, modify
									apod.) brání neoprávněným osobám v přístupu k citlivým datům
								</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="kvoty" class="note">
				<h2>📏 Diskové kvóty</h2>
				<ul>
					<li>Omezují objem dat, které může uživatel uložit.</li>
					<li>Napomáhá minimalizaci údajů – zásada GDPR.</li>
				</ul>

				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Diskové kvóty určují maximální kapacitu disku, kterou může konkrétní uživatel či skupina využívat</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Organizační opatření:</strong> Ačkoliv nepředstavují přímý požadavek GDPR, mohou pomoci v rámci správy dat, na říklad zamezením nekontrolovaného shromažďování velkého množství osobních údajů</li>
								<li><strong>Minimalizace údajů (data minimization):</strong> GDPR vyžaduje zpracovávat jen nezbytné množství dat. Nastavení kvót může motivovat k tomu, aby se zbytečně nehromadila nepotřebná data</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="mazani" class="note">
				<h2>🗑️ Výmaz a práce se soubory</h2>
				<ul>
					<li>GDPR vyžaduje výmaz údajů, které již nejsou potřebné.</li>
					<li>
						Musí být možné prokázat, že data byla bezpečně odstraněna (např. elektronická skartace).
					</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Základní operace s daty v souborovém systému (například prostřednictvím průzkumníka ve Windows nebo příkazové řádky)</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Zásada omezení uložení a výmaz:</strong> GDPR ukládá povinnost vymazat či anonymizovat osobní data, jakmile nejsou dále potřebná (např. na žádost subjektu údajů nebo po uplynutí zákonné lhůty)</li>
								<li><strong>Dokumentace procesů výmazu:</strong> Organizace musí být schopna prokázat, že data byla skutečně odstraněna (např. skartací či bezpečným elektronickým smazáním)</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="komprese" class="note">
				<h2>📦 Komprimace dat</h2>
				<ul>
					<li>Kompresní algoritmy snižují objem dat (ZIP, RAR).</li>
					<li>Užitečné při bezpečném přenosu dat – často kombinováno se šifrováním.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Snížení objemu dat pomocí kompresních algoritmů (např. ZIP, RAR)</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Technické opatření:</strong> Komprimace sama o sobě není zabezpečovací metodou, avšak často se kombinuje se šifrováním (např. zaheslované ZIP archivy)</li>
								<li><strong>Přenos dat:</strong> Při přenášení velkých objemů citlivých dat komprimace urychluje a usnadňuje bezpečný přenos, pokud je zároveň použito šifrování</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="sifrovani" class="note">
				<h2>🔐 Šifrování dat</h2>
				<ul>
					<li>Klíčové opatření dle čl. 32 GDPR.</li>
					<li>Zabezpečuje data při úniku – bez klíče nečitelná.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Převod čitelné podoby dat na nečitelnou, k jehož zpětnému převodu je potřeba příslušný klíč či certifikát</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Jedno z hlavních bezpečnostních opatření (čl. 32 GDPR):</strong> GDPR přímo uvádí šifrování jako příklad vhodného technického opatření pro ochranu dat</li>
								<li><strong>Minimalizace rizika úniku:</strong> V případě, že dojde k úniku (např. odcizení) databáze, zašifrovaná data zůstávají nečitelná bez příslušného klíče</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="periferie" class="note">
				<h2>💻 Periferní zařízení</h2>
				<ul>
					<li>Omezení tisku, USB portů a dalších zařízení.</li>
					<li>Minimalizuje riziko zneužití osobních údajů.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Konfigurace tiskáren, USB portů, skenerů, přenosných disků a dalších zařízení, která mohou ukládat či jinak zpracovávat data</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Prevence neoprávněného kopírování či tisku:</strong> Např. omezení možnosti tisknout citlivé dokumenty, kontrola přístupu k USB portům</li>
								<li><strong>Bezpečnostní politika:</strong> Minimalizace rizika zneužití dat (např. zcizení na flash disku)</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="zalohy" class="note">
				<h2>💾 Zálohování dat</h2>
				<ul>
					<li>Zajišťuje dostupnost údajů i po nehodě nebo útoku.</li>
					<li>Zálohy musí být zabezpečené a uchovávány jen po nezbytnou dobu.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Vytváření kopie dat pro případ ztráty, havárie nebo kybernetického útoku</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Dostupnost osobních údajů (čl. 32 GDPR):</strong> Jedním z cílů GDPR je zajištění dostupnosti, aby data mohla být obnovena i po technické nehodě či útoku</li>
								<li><strong>Retenční politika:</strong> Je nutné dbát na to, aby zálohy neobsahovaly osobní údaje déle, než je nutné, a aby byly rovněž řádně zabezpečeny (ideálně šifrované)</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="zalohy-os" class="note">
				<h2>🖥️ Záloha OS</h2>
				<ul>
					<li>Kompletní obraz disku – důležitý pro obnovu po havárii.</li>
					<li>Stejné zásady jako u záloh dat: šifrování, omezená doba uchování.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Kompletní záloha (image) disku obsahující celý operační systém, včetně nainstalovaných aplikací a nastavení</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Zajištění funkčnosti a rychlé obnovy:</strong> U systému zpracovávajícího osobní údaje je obnova po havárii či ransomwarovém útoku zásadní pro zachování chodu organizace</li>
								<li><strong>Stejná pravidla jako u klasické zálohy:</strong> Musí být dostatečně zabezpečená (nejlépe šifrovaná) a uchovávaná pouze po nezbytně dlouhou dobu</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="os-bezpecnost" class="note">
				<h2>🛡️ Zabezpečení operačního systému</h2>
				<ul>
					<li>Hesla, aktualizace, firewall, antivir – základní ochrana.</li>
					<li>Naplnění zásad <strong>privacy by design</strong> a <strong>by default</strong>.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Soubor opatření a konfigurací (uživatelské účty, firewall, antivir, správa aktualizací, řízení služeb atd.) zajišťujících ochranu systému</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Čl. 32 GDPR – Bezpečnost zpracování:</strong> Organizace by měly přijmout vhodná technická opatření proti neoprávněnému či nezákonnému zpracování</li>
								<li><strong>Privacy by Design a by Default (čl. 25 GDPR):</strong> Bezpečný základní stav systému (např. nastavení silných hesel, pravidelných aktualizací) je předpokladem pro bezpečné zpracování osobních údajů</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="aktualizace" class="note">
				<h2>♻️ Aktualizace systému</h2>
				<ul>
					<li>Pravidelné záplaty zamezují zneužití zranitelností.</li>
					<li>Důležité opatření pro kybernetickou bezpečnost dle čl. 32 GDPR.</li>
				</ul>
				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li><strong>Co to je:</strong></li>
							<ul>
								<li>Pravidelná instalace oprav a záplat (Windows Update, Linux patch management atd.)</li>
							</ul>
							<li><strong>Vztah k GDPR:</strong></li>
							<ul>
								<li><strong>Základní prvek ochrany:</strong> Neaktuální systém s neopravenými chybami je zranitelnější vůči útočníkům a zvyšuje riziko úniku či narušení integrity dat</li>
								<li><strong>Článek 32 GDPR – Bezpečnost:</strong> Aktualizace OS patří mezi nejzásadnější kroky při zajištění kybernetické bezpečnosti</li>
							</ul>
						</ul>
					</div>
				</details>
			</section>

			<section id="shrnutí" class="note">
				<h2>📌 Shrnutí & Doporučení</h2>
				<ul>
					<li>Všechna opatření podporují bezpečnost, důvěrnost, integritu a dostupnost údajů.</li>
					<li>
						Organizace musí prokázat přijatá opatření a jejich účinnost (zásada <em>accountability</em>).
					</li>
					<li>Dokumentace je klíčová pro důvěru dozorových orgánů i subjektů údajů.</li>
				</ul>

				<details class="details-block">
					<summary>Podrobnější zápisky</summary>
					<div class="details-content">
						<ul>
							<li>Veškeré výše uvedené postupy a opatření se přímo nebo nepřímo vážou k několika klíčovým požadavkům GDPR, a to zejména k:</li>
							<ol>
								<li><strong>Bezpečnosti zpracování (čl. 32 GDPR)</strong></li>
								<li><strong>Principu odpovědnosti (accountability)</strong>, tedy schopnosti doložit, že bylo učiněno vše pro ochranu dat</li>
								<li><strong>Zásadám důvěrnosti, integrity a dostupnosti osobních údajů</strong></li>
							</ol>
							<li>Tato opatření zabraňují neoprávněnému přístupu (důvěrnost), ztrátě a poškození dat (integrita) a pomáhají zajistit, aby byla v případě potřeby dostupná (dostupnost)</li>
						</ul>
					</div>
				</details>
			</section>
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
