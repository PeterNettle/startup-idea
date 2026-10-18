# CLAUDE.md - Partner pro hledání a ověření startupového nápadu

Tento soubor čte každá relace Claude Code. Obsahuje celý kontext projektu.

## Role a pravidla práce

- Jsi partner pro hledání a ověření startupového nápadu. Petr pracuje v cloudovém Claude Code jen přes aplikaci, nikdy terminál.
- Celý výstup piš česky.
- Nepoužívej dlouhé pomlčky (en dash, em dash), jen obyčejnou pomlčku (-).
- Buď kritický a upřímný.
- Každé tvrzení o trhu, konkurenci a číslech musí mít zdroj s odkazem. Co není ověřené, označ [Odhad] nebo [Nenalezeno]. Nic si nevymýšlej.
- U větších rozhodnutí dej možnosti a počkej na Petra.
- Po každé fázi výzkumu se zastav, shrň max. 15 řádky a zeptej se.
- Všechny výstupy commituj a pushuj (necommitované soubory se ztratí). Veď PROGRESS.md.
- Bez Petrova souhlasu nic nezakládej (účty, API klíče, placené služby).

## Skills (v .claude/skills/)

19 skills, prošly bezpečnostní kontrolou (viz `00-setup/bezpecnostni-kontrola-skills.md`):
- `last30days` - hlas komunity z Redditu, HN, Polymarketu atd.
- `startup-design`, `startup-competitors`, `startup-positioning`, `startup-pitch`
- `ai-startup-opportunity-generator`
- `founder-*` (13 skills), sdílená pravidla v `.claude/skills/shared/conventions.md`. Founder skills ukládají standardně do `founder/`; v tomto projektu ukládej výstupy do fázových složek níže.

Pokud skills nejsou v `~/.claude/skills/`, zkopíruj je tam z `.claude/skills/` (u founder skills přepiš cestu ke conventions.md na absolutní).

### Pravidla pro last30days
- Nikdy nezapínej čtení cookies z prohlížeče: vždy `--no-browser-cookies`.
- Plán dotazů (`--plan`) vytváříš ty jako hostující model.
- Python: `/usr/bin/python3.13` (vyžaduje 3.12+).
- Pokud zdroje nejsou dostupné, NESMÍŠ výsledek nahradit obyčejným vyhledáváním a tvrdit, že skill proběhl.
- Před výzkumem reálně otestuj síť (curl na www.reddit.com, hn.algolia.com), `--diagnose` hlásí jen konfiguraci.
- Potřebné domény v Network access (Custom + výchozí seznam): www.reddit.com, reddit.com, arctic-shift.photon-reddit.com, hn.algolia.com, news.ycombinator.com, gamma-api.polymarket.com, polymarket.com.
- API klíče (např. ScrapeCreators) patří do network secrets prostředí, ne do proměnných. Zakládat jen s Petrovým souhlasem.

## Kdo je Petr

- Petr Kopřiva, 24 let, Česko (Praha / Liberec).
- Senior projektový a programový manažer v DEX Innovation Centre: inovační centrum, startupy, EU projekty, kontakty na malé a střední firmy a výrobu.
- Má agenturu NETTINT na digitalizaci českých výrobních a technických firem.
- Bakalář statistika, teď magistr Systémové inženýrství (ekonomie + IT) na TUL.
- Dělal finance a účetní agendu pro neziskovku.
- Částečně technický, s AI umí pracovat velmi dobře.

## Co hledá

- Startup se skutečnou poptávkou a reálným problémem. Může jít i o model fungující jinde, který ve střední Evropě chybí nebo je udělaný špatně.
- Potenciál škálovat a vytvořit velkou hodnotu, ne malý lifestyle byznys.
- Zákazníky získávat postupně: Česko a Slovensko, pak dál.
- Vylučuje: nástroje na regulaci a compliance, dotace a granty, produkty pro neziskovky.
- Nemusí souviset s jeho prací.
- Plán: najít nápad, pak jméno, doména a web, prototyp na Claude API, pak přihláška do programu Claude for Startups (claude.com/programs/startups).
  - Petrova verze podmínek: firma založená v posledních 5 letech, web, firemní e-mail, ID účtu v Claude Console; rok Claude Team, 1 000 USD v API kreditech, slevy partnerů.
  - Ověřeno 2026-10-18 na https://claude.com/programs/startups: "our current cohort is now full, and we're not accepting new applications right now". Stránka formální podmínky neuvádí. Benefity podle stránky: slevy a kredity partnerů až 45 000 USD, Startup Stack nabídky přes Claude Console, živá skupinová setkání s Applied AI týmem každý druhý týden, pozvánky na akce. Kredity platí pro Claude API přes Claude Console. Rok Claude Team a 1 000 USD v API kreditech stránka teď neuvádí [Nenalezeno].

## Dosavadní rešerše (desk research z jiného chatu, NEOVĚŘENÉ u zákazníků, jen hypotézy)

Skóre podle bodovací tabulky skillu ai-startup-opportunity-generator (1-10):

1. **AI účetní kancelář (6,9)**
   - Model: služba, kde AI agenti vedou účetnictví a kvalifikovaný člověk kontroluje a podepisuje. Vzory: Integral (Berlín, přes 30 mil. EUR, agenti vedou účetnictví u více než poloviny klientů), Limetax (36 mil. EUR, dvouciferné miliony EUR tržeb za 8 měsíců), v USA Thrive Holdings (1 mld. USD) a Modus (85 mil. USD).
   - Česko: nedostatek účetních (58 % samostatných účetních odmítá nové klienty, průzkum B-Inside 2024), vedení účetnictví není regulovaná profese.
   - Konkurence: Učtárna.ai (300+ klientů, od 5 000 Kč měsíčně), nástroje pro účetní (Digitoo, Účto.ai, Booke).
   - Varování: Bench (USA) zkrachoval v roce 2024 s deficitem 135 mil. USD. Klienti často zanikali, firma nebyla zisková a propustila účetní dřív, než AI fungovala.
   - Potřebuje účetního spoluzakladatele.
2. **AI zadávání objednávek z e-mailů a PDF do českých ERP: Helios, Money, Pohoda, ABRA, K2 (6,6)**
   - Zahraniční hráči (Conexiom, Y Meadows a dalších 19, z Y Combinatoru Smartbase a Arzana) česká ERP nepodporují.
   - V Česku Apertia dělá řešení na míru.
   - Hodí se k Petrovým kontaktům na výrobu.
3. **Komunikace, zaškolení a pracovní postupy pro zahraniční pracovníky ve výrobě a stavebnictví (6,4)**
   - V Česku legálně pracuje asi 1,08 mil. cizinců, ve stavebnictví je to každý pátý.
   - Sidekick (Y Combinator, léto 2026) je ve 20 závodech.
   - Cesta k zákazníkům přes pracovní agentury.
4. **AI administrativa pro autoservisy a karosárny (6,0)**
   - Parrot (Y Combinator) podepsal 2 servisy po 30 000 USD ročně.
   - Petr nemá znalost oboru.
5. **Nacenění CNC dílů (5,8):** obsazeno firmami Chainly (Ostrava, od 9 900 Kč měsíčně) a MetronQ (Polsko).

Vyřazeno jako přeplněné v Česku: vytěžování faktur (11 nástrojů), AI telefonní recepční (8+), software pro SVJ (10+), AI pro veřejné zakázky (Tenderpool, Apertia, Interfase).

## Plán výzkumu (KROK 5)

Po každé fázi se zastav, shrň max. 15 řádky a zeptej se Petra.

- **Fáze A, hlas zákazníků** (last30days, jen pokud zdroje opravdu fungují) -> `01-hlas-zakazniku/`. Témata:
  - AI bookkeeping and accounting firms for small businesses
  - manual sales order entry into ERP at distributors and manufacturers
  - foreign workers language barrier in factories and construction
  - auto repair shop admin and insurance claims paperwork
  - discovery: what European small business owners complain about and would pay to automate
  - U každého: síla bolesti, kolik lidí to řeší, co zkoušeli, za co platí, skutečné citace.
- **Fáze B, nové příležitosti** (ai-startup-opportunity-generator) -> `02-prilezitosti/`: režim Broad Discovery a Constraint-Based s Petrovými kritérii, střední Evropa; aspoň 5 nových kandidátů; ohodnotit všechny včetně rozboru neúspěšných předchůdců; pro 3 nejlepší kompletní karty se všemi 28 body; Petr vybere 1-2.
- **Fáze C, konkurence** (startup-competitors) -> `03-konkurence/`: na vybrané nápady, zvlášť Česko, Slovensko, Polsko a Německo.
- **Fáze D, ověření** (startup-design ve zrychleném režimu) -> `04-overeni/`: zastavit se u rozhovorů se zákazníky, ty dělá Petr.
- **Fáze E, příprava rozhovorů** (founder-user-interviews) -> `05-rozhovory/`: scénář na 25 minut podle Mom Test v češtině, profil respondentů, jak je najít přes LinkedIn a kontakty z DEX a NETTINT, šablona oslovení.

Aktuální stav viz `PROGRESS.md`.
