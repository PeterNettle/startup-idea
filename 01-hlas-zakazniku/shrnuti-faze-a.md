# Fáze A: Hlas zákazníků (last30days)

Datum: 2026-10-18, okno 2026-09-18 až 2026-10-18.
Nástroj: last30days v3.28.0, plán dotazů jsem napsal já (`--plan`), vždy `--no-browser-cookies`.

## Jak výzkum reálně proběhl (důležité pro váhu závěrů)

- **Fungovalo:** Reddit (bezplatná cesta, 23 až 34 položek na téma), Hacker News, Polymarket (0 relevantních trhů), GitHub.
- **Nefungovalo:** YouTube (YouTube z cloudové IP požaduje přihlášení, "Sign in to confirm you're not a bot"), X/Twitter (bez cookies záměrně vypnuto), TikTok a Instagram (vyžadují ScrapeCreators, nezaloženo).
- **Komentáře z Redditu** engine nestáhl, protože www.reddit.com blokuje cloudové IP (403). U 13 nejrelevantnějších vláken jsem je doplnil přímo z veřejného archivu arctic-shift (soubor `raw/komentare-arctic-shift.md`). Počty bodů u komentářů jsou z okamžiku archivace, proto jsou nízké.
- **Šum:** Reddit a HN jsou anglické a převážně americké. U B2B témat (ERP, výroba) byla většina nalezených položek mimo téma. Pokud téma "nemá výsledky", neznamená to, že bolest neexistuje: lidé z provozu výrobních firem na Redditu o tom prostě nepíšou.
- Webové doplňky (krok 2 skillu) jsou v raw souborech v sekci `WebSearch Supplemental Results` a níže jsou vždy označené jako "web".

Surová data: `raw/*-raw-v3.md`, komentáře `raw/komentare-arctic-shift.md`.

---

## 1. AI účetní firmy pro malé firmy

**Síla bolesti: střední.** Komunita je aktivní (6 relevantních vláken, přes 300 komentářů), ale převážně v USA. Majitelé hledají účetní, protože nestíhají, ne kvůli AI.

**Co lidé říkají:**
- Majitel firmy se 200 transakcemi měsíčně dělá účetnictví sám v QuickBooks a nestíhá: "currently doing it myself in QuickBooks and falling behind" ([u/Zestyclose_Tie_8189, r/AskAccounting](https://www.reddit.com/r/AskAccounting/comments/1wo82fh/best_outsourced_bookkeeping_services_for_a_small/)).
- **Ceny, které lidé platí (USA):** 100 USD/měsíc za IT konzultanta, 400 USD za služby a mzdy pro 2 lidi, 700 USD za maloobchod včetně DPH přiznání ([vlákno r/smallbusiness](https://www.reddit.com/r/smallbusiness/comments/1wmaefs/business_owners_how_much_are_you_paying_for/)). Účetní sama uvádí 300 až 1 200 USD měsíčně ([u/Bookkeeper_Here](https://www.reddit.com/r/smallbusiness/comments/1wmaefs/comment/pbsqhf0/)). Rada z oboru: "don't pay less than $400/month" ([u/mag100](https://www.reddit.com/r/AskAccounting/comments/1wo82fh/comment/pbpknd0/)).
- **Nedůvěra k levným a AI řešením:** "the majority of my work comes from messy and inaccurate books done by off shore bookkeepers, the business owner, or AI mistakes" ([u/Bookkeeper_Here](https://www.reddit.com/r/smallbusiness/comments/1wmaefs/comment/pbsqhf0/)). Účetní firma: bookkeeping se stal "technology led race to the bottom" a živí se úklidem po levných službách ([u/RidgelineCPA](https://www.reddit.com/r/AskAccounting/comments/1wo82fh/comment/pc08qf4/)).
- **Hrozba "udělej si sám s AI":** majitel s 10 zaměstnanci řeší, jestli připojit Claude ke QuickBooks; nejlépe hodnocená odpověď: "I use the quickbooks MCP, total gamechanger. Either you can use it, or you can pay a bookkeeper and they will use it." ([u/HarambeTooSoon](https://www.reddit.com/r/ClaudeAI/comments/1x1dhdw/comment/pesnn0j/)).
- **Pohled účetních:** "your job is safe, but instead of taking care of 30 clients, with AI you're assigned 300" ([u/IroIroBike, r/Accounting](https://www.reddit.com/r/Accounting/comments/1x1z38n/comment/pf1oi6s/)). To je přesně ekonomika AI účetní firmy.
- **Jak si klienti vybírají:** reference od jiných podnikatelů nebo od bankéře, "remote is not an option for most people; you need to meet them" ([u/TangibleValues](https://www.reddit.com/r/smallbusiness/comments/1wy7px0/comment/pe0iaai/)).

**Co zkoušeli:** sami v QuickBooks + Square, lokální účetní, offshore služby, nově AI přes MCP.

**Web:** Integral (Berlín) má Series A 18 mil. EUR, celkem přes 30 mil. EUR, agenti vedou účetnictví u více než poloviny klientů ([tech.eu](https://tech.eu/2026/09/16/integral-lands-eur18m-series-a-for-ai-native-accounting-and-tax-services/)). **Oprava k dosavadní rešerši:** Limetax 36 mil. EUR je jen 6 mil. EUR kapitál a 30 mil. EUR úvěrová linka na skupování kanceláří ([Startbase](https://www.startbase.com/news/limetax-erhaelt-36-millionen-euro-fuer-ki-getriebene-steuerkanzleigruppe/)). Nový hráč: Balance (YC W26), 150+ klientů v Kodani a Londýně ([The Hub](https://thehub.io/startups/balance-yc-w26)). Údaj "58 % samostatných účetních odmítá klienty (B-Inside 2024)" se mi v této fázi dohledat nepodařilo [Nenalezeno, ověřit]; česká data jen nepřímo potvrzují nedostatek lidí ([Businessinfo](https://www.businessinfo.cz/clanky/pruzkum-kvalitu-ucetnich-sluzeb-zhorsuje-chybejici-legislativa-i-nedostatek-lidi/)).

**Kritický závěr:** Poptávka po "někdo to za mě udělá" je reálná a platí se za ni. Klíčové je důvěra a osobní vztah, ne technologie. Riziko ze dvou stran: levná DIY cesta (Claude + MCP) a velcí dobře financovaní hráči v DE.

---

## 2. Ruční zadávání objednávek do ERP

**Síla bolesti: z komunity [Nenalezeno].** Za 30 dní jsem na Redditu ani HN nenašel jediné vlákno o ručním přepisování objednávek. Nalezené položky byly o kariéře v sales. Jediné relevantní vlákno ("Next generation of ERP", r/ERP, 46 komentářů) mluví o "headless ERP" a AI agentech nad ERP jako novém trendu: "The ERP will own the tax calculation, contracts, pricing, and master records, but all operation users will connect to custom front ends" ([u/Bizdatastack](https://www.reddit.com/r/ERP/comments/1x7e4d2/comment/ph3ezs9/)). Skeptický hlas: "I think AI-native ERP is overhyped right now" ([u/Gujimiao](https://www.reddit.com/r/ERP/comments/1x7e4d2/comment/ph7x2gf/)).

**Web (nejsilnější důkaz):** průzkum ECC KÖLN (200 velkoobchodů a výrobců, červenec 2026): 39 % uvádí ruční zadávání nabídek a objednávek mezi největšími brzdami prodeje (jen sekundární shrnutí u [Xictron](https://www.xictron.com/en/blog/ai-order-entry-email-pdf-orders-erp/), originál neověřen).

**Konkurence je hustší, než uvádí dosavadní rešerše:** WizCommerce ([Distribution Strategy](https://distributionstrategy.com/2026/06/wizcommerce-launches-ai-order-entry-tool-for-distributors/)), Comena (YC, [ycombinator.com](https://www.ycombinator.com/companies/comena)), Lleverage (NL), Workist (DE), Xictron (DE). **V Česku navíc:** robot AIVIRO zpracovává objednávky přímo v Heliosu ([případová studie Helios](https://www.helios.eu/files/agendovy-list-aiviro.pdf)) a Apertia uvádí podporu Heliosu i Pohody ([apertia.ai](https://apertia.ai/en/b2b-objednavky)). Teze "česká ERP nikdo nepodporuje" tedy neplatí úplně.

**Kritický závěr:** Bolest potvrzuje průzkum, ne lidé. Ověřit se dá jen rozhovory (Petrovy kontakty z výroby jsou tu výhoda). Mezera v ERP integracích je menší, než jsme mysleli.

---

## 3. Jazyková bariéra cizinců ve výrobě a stavebnictví

**Síla bolesti: z komunity [Nenalezeno].** Nalezená vlákna řeší kulturu a integraci (např. "foreigners should learn the language", 756 bodů), ne provoz ve fabrice. Mistři a HR z výroby o tom na Redditu nepíšou.

**Nepřímý signál z Německa:** firmy odmítají nové zákazníky, protože nemají lidi: "Fachkräftemangel. There is a massiv shortage of workforce in Germany" ([u/Kitchen-Badger8435, r/germany](https://www.reddit.com/r/germany/comments/1x5lyl3/comment/pgnho6d/)), "In trades especially, there's a massive shortage of workers" ([u/Glad_Resolution230](https://www.reddit.com/r/germany/comments/1x5lyl3/comment/pgnhtqt/)).

**Web:** doinstruct (DE) má školení frontline pracovníků v 16+ jazycích a 170+ zákazníků, 7,6 mil. EUR v roce 2024 ([HTGF](https://htgf.de/en/htgf-financing-doinstruct)). FlashAcademy Workplace (UK) s Make UK cílí na výrobu a stavebnictví ([FlashAcademy](https://flashacademy.com/news/new-digital-workplace-english-app-launched-in-partnership-with-make-uk/)). V Česku řeší VÚBP výzkum BOZP u cizinců. Jeden podnik to vyřešil školením v češtině a angličtině a považuje to za dostatečné ([Práce a mzda](https://www.praceamzda.cz/clanky/vybrane-poznatky-z-oblasti-zamestnavani-cizincu)). Bezpečnostní riziko je doložené: ve Velké Británii zemřela čtvrtina zahraničních obětí ve stavebnictví první den ([Building](https://www.building.co.uk/news/mind-your-language/1015921.article)).

**Kritický závěr:** Problém je doložený, ale kupující (výroba, agentury) není online vidět. doinstruct je přímý konkurent a se 170 zákazníky už je v DACH dál.

---

## 4. Administrativa autoservisů a pojistné události

**Síla bolesti: střední až silná, ale jinde, než jsme čekali.** Nejživější bolest není pojišťovna, ale **nedodělaná komunikace se zákazníky**: neodpovězená schválení kalkulací a nikdo neobvolá odmítnuté opravy.
- "morning was 6 'your car is ready' texts, two estimate approvals that never answered, plus the guy who ghosted a $900 brake job tuesday. 45 cars a week, me and one advisor" ([u/ActiveStrict6633, r/serviceadvisors](https://www.reddit.com/r/serviceadvisors/comments/1wpsffc/is_a_crm_actually_worth_it_for_a_small_auto/)).
- "Our reminder system is a sticky note behind the desk" / "Whiteboard at my shop has names from 2024 on it" (tamtéž).
- Ochota platit existuje, výsledky taky: "Ours goes out on its own now and about a third of it books. we run Autoleap" ([u/Turbo_Axis47](https://www.reddit.com/r/serviceadvisors/comments/1wpsffc/comment/pbytycj/)).
- Ale pozor na opuštěný software: "six months later its a 400 a month rolodex because the advisor stopped entering stuff in february" ([u/falxn_](https://www.reddit.com/r/serviceadvisors/comments/1wpsffc/comment/pbygzli/)). Shopmonkey a Tekmetric si za SMS účtují příplatek ([u/Otherwise-Soft9026](https://www.reddit.com/r/serviceadvisors/comments/1wpsffc/comment/pbyg6v7/)).
- Pojistky z pohledu zákazníka: zmatek, kdo dostane šek a proč servis neukáže fakturu ([r/Insurance](https://www.reddit.com/r/Insurance/comments/1wmo9le/insurance_cheque_is_2800_but_body_shop_says_the/)).
- Německo: servisy jsou plně vytížené a nové zákazníky nepotřebují ([u/FastNumberCruncher](https://www.reddit.com/r/germany/comments/1x5lyl3/comment/pgnj612/)). Prodávat "více zákazníků" tam nejde, "méně administrativy na stejný počet aut" možná ano.

**Web:** nový konkurent Rote (YC), AI pojistné oddělení pro karosárny, které vymáhá doplatky od pojišťoven ([YC adresář](https://amanydv2112-suggest-orgs.hf.space/company/yc/rote), údaj o batchi nekonzistentní). Česká data o procesu likvidace jsou jen v diplomových pracích ([theses.cz](https://theses.cz/id/mcxowz?lang=en)) [Nenalezeno aktuální].

**Kritický závěr:** Bolest je hmatatelná a konkrétní (peníze z odmítnutých oprav). Petr ale obor nezná a v USA je trh plný (AutoLeap, Tekmetric, Shopmonkey). Pro ČR chybí data, jak funguje vztah servis-pojišťovna.

---

## 5. Discovery: co trápí malé firmy v Evropě a za co by zaplatily

**Nejdůležitější vhled napříč tématy:** majitelé nekupují automatizaci, kupují klid.
- "Small business owners don't buy automations. They buy not having to think about something." ([r/AI_Agents](https://www.reddit.com/r/AI_Agents/comments/1wqz2bv/small_business_owners_dont_buy_automations_they/)). Jediná otázka, která rozhodla o podpisu: "What happens when it gets something wrong."
- "owners don't need it perfect, they need to know how they'd find out" ([u/optima-pacifist](https://www.reddit.com/r/AI_Agents/comments/1wqz2bv/comment/pcatjnt/)).
- U všeho, co jde ke klientovi, chtějí člověka: "If a canned email goes out with someone's name spelled wrong or a dollar figure that's off by a digit, that's a mess I don't want to clean up" ([u/Limp-Mirror3228, r/smallbusiness](https://www.reddit.com/r/smallbusiness/comments/1x5jsuh/whats_one_task_in_your_small_business_you_would/)).
- Pozor: r/smallbusiness výslovně zakazuje průzkum trhu ("We are not your focus group"), takže zákazníky přes Reddit hledat nejde ([AutoModerator](https://www.reddit.com/r/smallbusiness/comments/1wmaefs/comment/pb57vta/)).

**Web, Česko a Evropa:** administrativa je významnou překážkou pro 84 % českých podnikatelů, 40 % nejmenších firem nepoužívá AI (EY), přes 240 hodin ročně na administrativu (Hospodářská komora) ([Businessinfo](https://www.businessinfo.cz/clanky/nejvetsi-prekazky-podnikani-v-roce-2026-nefunkcni-pracovni-trh-a-prilisna-byrokracie/)). Malí podnikatelé v ČR tráví administrativou téměř 70 mil. hodin ročně ([ČT24](https://ct24.ceskatelevize.cz/clanek/ekonomika/male-podnikatele-zahlcuje-byrokracie-366219)). Německé MSP průměrně 32 hodin měsíčně ([KfW](https://www.kfw.de/About-KfW/Newsroom/Latest-News/Pressemitteilungen-Details_847424.html)). Data o ochotě platit za automatizaci jsem nenašel [Nenalezeno].

---

## Souhrnné hodnocení

| Téma | Síla bolesti (komunita) | Ochota platit (doložená) | Nová konkurence z Fáze A |
|---|---|---|---|
| 1. AI účetní firma | střední, hodně hlasů | ano, 100-1 200 USD/měs. (USA) | Balance (YC), Integral potvrzen, DIY přes MCP |
| 2. Objednávky do ERP | [Nenalezeno] online, průzkum 39 % | [Nenalezeno] | WizCommerce, Comena, Lleverage, Workist, AIVIRO v Heliosu |
| 3. Cizinci ve výrobě | [Nenalezeno] online | [Nenalezeno] | doinstruct (170+ zákazníků), FlashAcademy |
| 4. Autoservisy | střední až silná (follow-up, schválení) | ano (AutoLeap, CRM) | Rote (YC), AutoLeap, Tekmetric, Shopmonkey |
| 5. Discovery | silná obecně, "klid, ne automatizace" | [Nenalezeno] | - |

**Co z toho plyne pro další fáze:**
1. Témata 2 a 3 nejde ověřit z internetu, jen rozhovory. Pro Petra jsou ale nejdostupnější (kontakty z výroby).
2. Produkt musí odpovědět na otázku "co se stane, když se AI splete" (záznam, upozornění, člověk na konci). To nahrává modelu "AI + člověk podepisuje" (téma 1).
3. Dosavadní rešerše podcenila konkurenci u tématu 2 a nadhodnotila Limetax.
