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
				<h1>Windows – část 5: Microsoft Management Console (MMC)</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_Win_5_MMC/Exam-Operacni_systemy_Win_5_MMC"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🧩 Co je MMC</h2>
				<ul>
					<li><strong>Microsoft Management Console (MMC)</strong> je rámec (framework) pro správu systému Windows</li>
					<li>Slouží k otevírání a vytváření tzv. <strong>konzol</strong> – přehledných nástrojů pro správu systému</li>
					<li>Není to samotný nástroj, ale prostředí, do kterého se přidávají <strong>moduly (snap-ins)</strong></li>
					<li>Snap-in = specializovaný nástroj pro konkrétní oblast systému (např. uživatelé, disky, služby)</li>
					<li>Pomocí MMC lze <strong>spravovat hardware, software i síťové komponenty</strong> systému Windows</li>
				</ul>
			</section>

			<section class="note">
				<h2>📦 Klíčové vlastnosti MMC</h2>
				<ul>
					<li><strong>Modularita:</strong> Umožňuje přidávání a odebírání snap-ins podle potřeby</li>
					<li><strong>Flexibilita:</strong> Uživatelé si mohou vytvářet vlastní konzoly pro specifické úkoly</li>
					<li><strong>Centralizace:</strong> Přístup k různým správním nástrojům z jednoho místa</li>
				</ul>
			</section>

			<section class="note">
				<h2>🧰 Příklady běžných snap-ins</h2>
				<ul>
					<li><strong>Device Manager</strong> – Správa zařízení</li>
					<li><strong>Disk Management</strong> – Správa disků a oddílů</li>
					<li><strong>Event Viewer</strong> – Prohlížení systémových událostí a chyb</li>
					<li><strong>Local Users and Groups</strong> – Správa místních uživatelů a skupin</li>
				</ul>
			</section>

			<section class="note">
				<h2>🛡️ Výhody použití MMC konzole</h2>
				<ul>
					<li><strong>Flexibilita a přizpůsobitelnost:</strong>
						<ul>
							<li>Možnost vytvořit si vlastní konzoly s vybranými snap-ins</li>
							<li>Export a přenos konzol mezi počítači</li>
						</ul>
					</li>
					<li><strong>Centralizace správy:</strong>
						<ul>
							<li>Jednotné rozhraní pro všechny správní nástroje</li>
							<li>Usnadňuje dohled nad systémem</li>
						</ul>
					</li>
					<li><strong>Rozšířenost snap-ins:</strong>
						<ul>
							<li>Široká podpora integrovaných i externích nástrojů</li>
							<li>Snadná integrace do prostředí MMC</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚠️ Nevýhody MMC konzole</h2>
				<ul>
					<li><strong>Složitost pro začátečníky:</strong>
						<ul>
							<li>Vyšší křivka učení</li>
							<li>Méně přívětivé rozhraní než moderní GUI nástroje</li>
						</ul>
					</li>
					<li><strong>Omezená funkcionalita:</strong>
						<ul>
							<li>Některé moderní nástroje nejsou dostupné v MMC</li>
							<li>Některé snap-ins mohou být zastaralé nebo nefunkční v nových Windows</li>
						</ul>
					</li>
					<li><strong>Bezpečnostní rizika:</strong>
						<ul>
							<li>Přístup ke správě systému může být nebezpečný bez správného zabezpečení</li>
							<li>Nesprávná oprávnění u snap-ins mohou otevřít rizika</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔁 Alternativy k MMC</h2>
				<ul>
					<li><strong>Control Panel (Ovládací panely):</strong>
						<ul>
							<li><strong>Popis:</strong> Tradiční rozhraní pro správu různých nastavení systému, jako je hardware, uživatelské účty, síťové připojení a další</li>
							<li><strong>Výhody:</strong> Intuitivní a přístupné pro běžné uživateleu</li>
							<li><strong>Nevýhody:</strong> Postupně nahrazován modernějšími nastaveními a některé funkce jsou omezené</li>
						</ul>
					</li>
					<li><strong>Settings App (Nastavení):</strong>
						<ul>
							<li><strong>Popis:</strong> Moderní GUI nástroj pro správu nastavení systému, který nahrazuje některé funkce Ovládacích Panelů</li>
							<li><strong>Výhody:</strong> Přehledné a uživatelsky přívětivé rozhraní, optimalizované pro dotykové ovládání</li>
							<li><strong>Nevýhody:</strong> Omezená funkcionalita ve srovnání s MMC, některé pokročilé nastavení nejsou dostupné</li>
						</ul>
					</li>
					<li><strong>Administrative Tools (Administrativní nástroje):</strong>
						<ul>
							<li><strong>Popis:</strong> Sada nástrojů dostupných v Ovládacích panelech pro správce systému, včetně Event Viewer, Task Scheduler, Disk Management a dalších</li>
							<li><strong>Výhody:</strong> Přístup k pokročilým správním nástrojům</li>
							<li><strong>Nevýhody:</strong> Méně centralizované než MMC, každý nástroj je samostatný</li>
						</ul>
					</li>
					<li><strong>Windows Admin Center:</strong>
						<ul>
							<li><strong>Popis:</strong> Moderní webová správcovská platforma od Microsoftu, která umožňuje správu serverů, clusterů a zařízení z jednoho rozhraní</li>
							<li><strong>Výhody:</strong> Pokročilé funkce, podpora cloudových služeb, snadná integrace s Azure</li>
							<li><strong>Nevýhody:</strong> Vyžaduje instalaci a konfiguraci, závisí na síťové infrastruktuře</li>
						</ul>
					</li>
					<li><strong>PowerShell ISE / Visual Studio Code:</strong>
						<ul>
							<li><strong>Popis:</strong> Výkonné nástroje pro skriptování a automatizaci úloh pomocí PowerShellu</li>
							<li><strong>Výhody:</strong> Pokročilé skriptovací schopnosti, podpora rozšíření a ladění skriptů</li>
							<li><strong>Nevýhody:</strong> Vyšší křivka učení, méně intuitivní pro běžné uživatele</li>
						</ul>
					</li>
					<li><strong>Třetí strany (např. SolarWinds, ManageEngine):</strong>
						<ul>
							<li><strong>Popis:</strong> Různé správcovské nástroje od třetích stran, jako je SolarWinds, ManageEngine, a další</li>
							<li><strong>Výhody:</strong> Specifické funkce a pokročilé možnosti správy, často s lepšími uživatelskými rozhraními</li>
							<li><strong>Nevýhody:</strong> Náklady na licenci, potenciální bezpečnostní rizika, závislost na poskytovateli</li>
						</ul>
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>🚀 Jak spustit MMC</h2>
				<ul>
					<li><strong>Win + R</strong> → <code>mmc</code></li>
					<li>Přes CMD: <code>mmc</code></li>
					<li>Přes PowerShell: <code>mmc</code></li>
				</ul>
			</section>

			<section class="note">
				<h2>🛠️ Přidávání/Odebírání modulů snap-in</h2>
				<ul>
					<li>Soubor → Přidat/odebrat modul snap-in nebo <code>CTRL + M</code></li>
					<li>Výběr, přidání a konfigurace modulu</li>
					<li>Možnost správy místního nebo vzdáleného počítače</li>
				</ul>
			</section>

			<section class="note">
				<h2>⚠️ Výhody a nevýhody MMC</h2>
				<ul>
					<li><strong>Výhody:</strong> přizpůsobitelnost, centralizace, možnost sdílení konzol</li>
					<li>
						<strong>Nevýhody:</strong> méně intuitivní rozhraní, zastaralé snap-ins, složitá oprávnění
					</li>
				</ul>
			</section>

			<a href="/PDF/Operacni_systemy_Win_5_MMC.pdf" class="ButtonExam" download>
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
