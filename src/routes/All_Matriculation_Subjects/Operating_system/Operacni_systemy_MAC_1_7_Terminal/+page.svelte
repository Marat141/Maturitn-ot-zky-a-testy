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
				<h1>Mac OS – část 1.7: Terminál</h1>
				<a
					href="/All_Matriculation_Subjects/Operating_system/Operacni_systemy_MAC_1_7_Terminal/Exam_Operacni_systemy_MAC_1_7_Terminal"
					class="ButtonExam"
				>
					Napsat si test
				</a>
			</div>

			<section class="note">
				<h2>🖥️ Úvod do Terminálu</h2>
				<ul>
					<li>Terminál je příkazová řádka pro komunikaci se systémem v macOS.</li>
					<li>Vychází z UNIXového prostředí, je kompatibilní s Linuxovým shellem.</li>
					<li>
						Od macOS Catalina je výchozí shell <strong>Zsh</strong>, dříve <strong>Bash</strong>.
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📜 Historie Terminálu v macOS</h2>
				<ul>
					<li><strong>Před Mac OS X:</strong> chyběla příkazová řádka, pouze GUI.</li>
					<li>
						<strong>Mac OS X (2001):</strong> přechod na UNIX (Darwin), první verze Terminálu.
					</li>
					<li><strong>Catalina (2019):</strong> změna výchozího shellu z Bash na Zsh.</li>
					<li><strong>Dnes:</strong> podpora více shellů: Zsh, Bash, Fish.</li>
				</ul>
			</section>

			<section class="note">
				<h2>🚀 Jak spustit Terminál</h2>
				<ul>
					<li><kbd>Cmd</kbd> + <kbd>Mezerník</kbd> → „Terminal“ (Spotlight)</li>
					<li>Launchpad → Other → Terminal</li>
					<li>Finder: <code>/Applications/Utilities/Terminal</code></li>
					<li>Volitelně: vlastní klávesová zkratka přes Automator</li>
				</ul>
			</section>

			<section class="note">
				<h2>🔠 Základní příkazy</h2>
				<ul>
					<li><code>cd</code> – změna adresáře</li>
					<li><code>ls</code> – výpis obsahu složky</li>
					<li><code>pwd</code> – zobrazí aktuální složku</li>
					<li><code>whoami</code> – aktuální uživatel</li>
					<li><code>mv</code>, <code>cp</code>, <code>ditto</code> – přesun, kopie</li>
					<li>
						<code>nano</code>, <code>open</code>, <code>man</code> – editace, otevření souboru, nápověda
					</li>
				</ul>
				<details class="details-block">
					<summary>📌 Příklady použití</summary>
					<div class="details-content">
						<ul style="margin-left: 2em;">
							<li><code>cd ~/Documents</code> – přechod do složky Dokumenty</li>
							<li><code>ls -la</code> – výpis všech souborů včetně skrytých</li>
							<li><code>nano poznamky.txt</code> – otevře soubor v textovém editoru</li>
							<li><code>open -a Safari www.apple.com</code> – otevře web v Safari</li>
						</ul>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🌐 Síťové a diagnostické příkazy</h2>
				<ul>
					<li><code>ping</code>, <code>traceroute</code>, <code>dig</code> – test sítě a DNS</li>
					<li><code>ifconfig</code> – informace o síťových rozhraních</li>
					<li>
						<code>ps</code>, <code>top</code>, <code>kill</code> – sledování a ukončení procesů
					</li>
				</ul>
				<details class="details-block">
					<summary>📌 Příklad: zabití aplikace Safari</summary>
					<div class="details-content">
						<ul style="margin-left: 2em;">
							<li><code>kill $(pgrep Safari)</code> – zavře všechny procesy aplikace Safari</li>
						</ul>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>💻 Skriptování v Terminálu</h2>
				<ul>
					<li>Skript = soubor s příkazy, které se spustí naráz (např. <code>zaloha.sh</code>)</li>
					<li>Začíná direktivou <code>#!/bin/bash</code> nebo <code>#!/bin/zsh</code></li>
					<li>Obsahuje proměnné, podmínky, smyčky, funkce</li>
				</ul>
				<details class="details-block">
					<summary>📌 Příklad: jednoduchý skript</summary>
					<div class="details-content">
						<pre style="margin-left: 2em;"><code
								>#!/bin/bash
echo "Ahoj"
ls -l</code
							></pre>
						<p style="margin-left: 2em;">
							Nastavení jako spustitelného souboru: <code>chmod +x skript.sh</code>
						</p>
					</div>
				</details>
			</section>

			<section class="note">
				<h2>🧠 Uživatelské tipy a rozdíly Bash vs Zsh</h2>
				<ul>
					<li><strong>Bash:</strong> standardní, kompatibilní</li>
					<li><strong>Zsh:</strong> modernější, podporuje pluginy (např. Oh My Zsh)</li>
					<li>
						<strong>Doporučení:</strong> běžné skripty piš v Bash, pokud nepotřebuješ pokročilé funkce
					</li>
				</ul>
			</section>

			<section class="note">
				<h2>📌 Užitočné skripty (příklady)</h2>
				<details class="details-block">
					<summary>🗂️ 1. Záloha složky</summary>
					<pre style="margin-left: 2em;"><code
							>#!/bin/bash
src="$1"
dest="$2"

if [ -d "$src" ]; then
	cp -r "$src" "$dest"
	echo "Záloha hotova."
else
	echo "Zdroj nenalezen."
fi</code
						></pre>
				</details>

				<details class="details-block">
					<summary>🌐 2. Test připojení k internetu</summary>
					<pre style="margin-left: 2em;"><code
							>#!/bin/bash
ping -c 1 google.com > /dev/null && echo "Internet OK" || echo "Internet nefunguje"</code
						></pre>
				</details>

				<details class="details-block">
					<summary>🔍 3. Vyhledání textu ve všech souborech</summary>
					<pre style="margin-left: 2em;"><code
							>#!/bin/bash
if [ -z "$1" ]; then
	echo "Zadej hledaný text"
	exit 1
fi

grep -rnw . -e "$1"</code
						></pre>
				</details>
			</section>

			<a href="/PDF/Operacni_systemy_MAC_1_7_Terminal.pdf" class="ButtonExam" download>
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
