# Fáze B: Plné karty pro 3 nejlepší kandidáty (28 bodů)

Ceny, časy a skóre jsou můj [Odhad], pokud u nich není zdroj. Nic z toho není ověřené u zákazníků.

---

## Karta 1: AI řízení pohledávek pro B2B firmy (N6)

1. **Název:** AI správce pohledávek (pracovně "Inkaso agent").
2. **Obor:** finance malých a středních B2B firem (výroba, velkoobchod, služby, stavebnictví).
3. **Kupující:** majitel nebo finanční ředitel firmy s 10 až 250 zaměstnanci.
4. **Uživatel:** účetní nebo asistentka, která dnes hlídá splatnosti.
5. **Dnešní ruční práce:** jednou týdně projde v účetním programu faktury po splatnosti, ručně napíše nebo zavolá, s klientem domlouvá splátky, ručně páruje příchozí platby a ve sporných případech předá věc advokátovi nebo inkasní agentuře.
6. **Problém:** B2B odběratelé platí pozdě a firmy nemají kapacitu je soustavně a slušně urgovat.
7. **Proč na tom záleží:** česká firma dostává pozdní platbu od každého pátého zákazníka, 4 % faktur jsou nedobytné a 57 % českých firem kvůli pozdním platbám přišlo o zisk (EOS European Payment Practices 2025, [Businessinfo](https://www.businessinfo.cz/clanky/evropskym-spolecnostem-hradi-pozde-nebo-vubec-ctvrtina-firem-se-spatnou-platebni-moralkou-se-potykaji-i-ceske-firmy/)). 61 % evropských firem uvádí, že jejich odběratelé neplatí, protože sami nedostali zaplaceno (tamtéž).
8. **Co dělá AI:** podle historie odběratele určí prioritu a tón, napíše upomínku v češtině nebo slovenštině, odpovědi zákazníků roztřídí ("zaplatím v pátek", "spor o kvalitu", "chci splátky"), navrhne splátkový kalendář, spáruje platby z banky a eskaluje. Člověk schvaluje vše, co odchází s novým tónem nebo slibem.
9. **Funkce:**
   - napojení na banku (Fio, KB, ČSOB přes API) a export z účetnictví (Pohoda, Money),
   - skóre rizika odběratele z historie plateb,
   - upomínkové sekvence psané AI, schvalované jedním klikem,
   - třídění odpovědí a zápis domluvených termínů,
   - hlídání slibů "zaplatím do..." a automatický follow-up,
   - týdenní přehled cash flow pro majitele,
   - předání do inkasa nebo advokátovi s připravenými podklady.
10. **MVP:** jedna banka (Fio, má veřejné API [Odhad]) + import faktur z Pohody přes XML, jen e-mailové upomínky se schválením. Cíl: o X dní kratší průměrná doba inkasa u 5 pilotních firem.
11. **Vstupní data:** seznam vydaných faktur, bankovní pohyby, e-mailová schránka pro odpovědi, kontakty odběratelů.
12. **Integrace:** banka (1), účetní program (1), e-mail (SMTP/IMAP nebo Gmail/M365).
13. **Proč AI:** psaní a třídění textu, extrakce slibů a dat z odpovědí a klasifikace sporů jsou silné stránky LLM. Párování plateb je pravidlová úloha s výjimkami, které vyřeší AI.
14. **Model:** předplatné podle počtu aktivních odběratelů, volitelně provize z vymožených částek po splatnosti nad 60 dní.
15. **Cena:** 1 490 až 4 990 Kč měsíčně [Odhad]. Pro srovnání: Fakturoid nabízí automatické upomínky v dražších tarifech ([Fakturoid](https://www.fakturoid.cz/podpora/automatizace/upominky)).
16. **Složitost:** nízká až střední.
17. **Čas do MVP:** 4 až 6 týdnů [Odhad].
18. **Obrana:** data o platební morálce odběratelů napříč klienty (kdo komu platí pozdě) vytvoří síťový efekt. Pozor: práce s takovými daty má právní limity (GDPR, obchodní tajemství) [Odhad, ověřit].
19. **Rizika:**
    - malá odlišitelnost: Fakturoid má automatické upomínky, účetní programy je můžou přidat,
    - nesoulad ceny (vzor 7): malé firmy mají nízký rozpočet,
    - citlivost vztahu: firma nechce zkazit vztah se zákazníkem, proto je nutné schvalování,
    - pokud se rozšíří do vymáhání, hrozí regulace inkasní činnosti [Odhad, ověřit].
20. **Vstup na trh:** přes účetní kanceláře, které mají desítky klientů a samy urgují (partnerský program), a přes Petrovy výrobní kontakty. Obsah: "Kolik vás stojí 20 % pozdních plateb" s kalkulačkou.
21. **Existující alternativy:** Fakturoid (upomínky), Inkaso24 (vymáhání drobných pohledávek do 50 000 Kč, [E15](https://www.e15.cz/byznys/obchod-a-sluzby/vymahani-nezaplacenych-miliard-z-drobnych-faktur-se-usnadni-1322633)), inkasní agentury (EOS, Intrum), Upflow (FR, celkem asi 23 mil. USD, [Caplight](https://www.caplight.com/company/upflow)), Kolleno (UK, seed 4 mil. GBP v roce 2022, [UK Tech News](https://www.uktech.news/fintech/kolleno-collects-4m-funding-20220309)), SAP Joule pro velké firmy.
22. **Proč může vyhrát:** Upflow a Kolleno nemají české banky, účetní programy ani jazyk [Odhad, ověřit ve Fázi C]. Fakturoid cílí na živnostníky a umí jen pevné šablony, ne vyjednávání. Mezera je ve středních B2B firmách s Pohodou nebo Money.
23. **Skóre:** Bolest 7, Rozpočet 5, AI 8, MVP 7, Distribuce 6, Odlišení 4. **Celkem 6,4.**
24. **Verdikt:** Nejrychlejší cesta k platícímu zákazníkovi a dobrá na prototyp pro Claude for Startups. Slabá obrana. Bez dat napříč klienty nebo hluboké integrace z toho bude funkce, kterou okopíruje účetní software.
25. **Mapa konkurence:**
    - přímí: Upflow, Kolleno (zahraniční, bez CZ integrací [Odhad]),
    - nepřímí: Fakturoid upomínky (pevné šablony), inkasní agentury (berou procenta, kazí vztah),
    - sousední: Pohoda, Money, ABRA by mohly přidat AI upomínky,
    - DIY: Excel + ChatGPT, asistentka,
    - nasycení: v ČR spíš neobsazeno, v Evropě validováno.
26. **Neúspěšní předchůdci:** konkrétní zaniklý AI nástroj na pohledávky jsem nenašel [Nenalezeno].
27. **Poučení:** neprodávat "AI", prodávat "méně peněz u odběratelů bez zkažených vztahů". Začít úzce: jedna banka, jeden účetní program, schvalování člověkem.
28. **Proč teď:** platební morálka je špatná a firmy ztrácejí zisk (EOS 2025). LLM umí psát česky přirozeně a české banky mají otevřená API (PSD2) [Odhad]. 40 % nejmenších českých firem zatím AI nepoužívá ([Businessinfo, EY](https://www.businessinfo.cz/clanky/nejvetsi-prekazky-podnikani-v-roce-2026-nefunkcni-pracovni-trh-a-prilisna-byrokracie/)).

**Rozbor selhání:** zranitelné vzory 7 (cena) a 6 (horizontální past, protože "pohledávky pro všechny"). Proti tomu: začít jedním segmentem (výroba a velkoobchod s fakturami nad 50 000 Kč). Předběžná kontrola (pre-mortem): 7/10. **Šance na přežití: střední.**

---

## Karta 2: Nástupnictví, příprava a prodej malých firem (N5)

1. **Název:** Platforma pro předání firmy (pracovně "Nástupce").
2. **Obor:** malé M&A, rodinné firmy (výroba, služby, řemesla), ČR a SR.
3. **Kupující:** majitel firmy 55+ bez nástupce. Druhou stranou jsou kupci: manažeři, kteří chtějí koupit firmu, menší investoři a konkurenti.
4. **Uživatel:** majitel a jeho účetní, na druhé straně kupec.
5. **Dnešní ruční práce:** majitel to odkládá a pak volá známým nebo M&A poradci, který bere vysokou odměnu a malé firmy často odmítne. Ocenění, prodejní dokumenty a prověrka se dělají ručně a trvají měsíce.
6. **Problém:** tisíce zdravých malých firem nemají nástupce a jejich majitelé nemají dostupnou cestu k prodeji.
7. **Proč na tom záleží:** Dun & Bradstreet odhaduje, že asi 30 % českých podniků v příštích letech změní majitele nebo zanikne ([Businessinfo](https://www.businessinfo.cz/clanky/generacni-zlom-tretinu-firem-ceka-zasadni-zmena-jak-to-ovlivni-ekonomiku/)). Formální nástupnický plán má jen 36 % firem a externího poradce využívají 2 % (EY Barometr 2026, [EY](https://www.ey.com/cs_cz/podnikatel-roku/poznatky-ey-entrepreneurship-barometer-2026-pro-cesko)). Víc než polovina rodinných firem generační výměnu nepřežije ([ČT24](https://ct24.ceskatelevize.cz/clanek/ekonomika/vybudovali-uspesne-rodinne-firmy-pokud-je-ale-nepripravi-na-svuj-odchod-mohou-je-znicit-95954)). Komerční banka uvádí generační důvody u více než 60 % prodejů firem ([E15](https://www.e15.cz/byznys/finance-a-bankovnictvi/prodej-ceskych-firem-je-letos-rekordni-1364452), článek bez data).
8. **Co dělá AI:** z účetních výkazů a rozhovoru s majitelem připraví orientační ocenění, anonymní teaser a informační memorandum, upozorní na rizika (závislost na majiteli, koncentrace zákazníků), spáruje firmu s kupci a připraví datovou místnost. Člověk (Petr nebo partner) vede jednání.
9. **Funkce:**
   - "test připravenosti k prodeji" zdarma (vstupní brána),
   - orientační ocenění podle oborových násobků,
   - AI generátor teaseru a memoranda,
   - databáze ověřených kupců a párování,
   - datová místnost s AI kontrolou úplnosti,
   - plán předání (vazba na zákazníky a klíčové lidi),
   - síť partnerů: advokát, daňový poradce, banka na akviziční úvěr.
10. **MVP:** služba s AI v pozadí, ne platforma. Pro 5 majitelů z Petrovy sítě připravit prodejní balíček (ocenění + teaser + memorandum) a najít kupce. Měřítko: podepsaná exkluzivita a 1 transakce do 6 až 9 měsíců.
11. **Vstupní data:** účetní závěrky (veřejné ve Sbírce listin), interní výkazy, rozhovor s majitelem, profil kupců.
12. **Integrace:** v MVP žádné. Později obchodní rejstřík a Sbírka listin, banky.
13. **Proč AI:** extrakce a shrnutí dokumentů, psaní memorand a strukturovaná analýza rizik zkrátí práci poradce z týdnů na dny. Díky tomu se vyplatí i firmy za 5 až 50 mil. Kč, které poradci dnes odmítají [Odhad].
14. **Model:** poplatek za přípravu + provize z úspěšné transakce, předplatné pro kupce za přístup k nabídkám.
15. **Cena:** příprava 20 000 až 60 000 Kč, provize 2 až 5 % [Odhad]. InBase uvádí minimální hodnotu prodávané firmy 1 mil. Kč ([CzechCrunch](https://cc.cz/inbase-ceska-platforma-na-ktere-lze-koupit-ci-prodat-fungujici-firmu-jiz-za-jeden-milion-korun/)).
16. **Složitost:** nízká technicky, vysoká obchodně.
17. **Čas do MVP:** 4 až 6 týdnů na nástroje, ale první tržba až s transakcí za 6 a víc měsíců [Odhad].
18. **Obrana:** likvidita a důvěra. Kdo má nejvíc ověřených kupců a prodávajících, vyhrává. Data o skutečných cenách transakcí.
19. **Rizika:**
    - dlouhý cyklus a nepravidelné tržby (jedna transakce za majitele za život),
    - problém slepice a vejce u marketplace,
    - důvěra: majitelé nechtějí, aby se vědělo, že prodávají,
    - Petr nemá M&A praxi (vzor 10), potřeba partnera z oboru,
    - regulace finančního zprostředkování a úvěrů [Odhad, ověřit].
20. **Vstup na trh:** přes účetní a daňové poradce, kteří o plánech majitelů vědí první, přes banky (KB a další mají firemní klientelu) a přes DEX a NETTINT. Obsah: test připravenosti k prodeji.
21. **Existující alternativy:** InBase (Brno, od 2015, inzertní platforma + služby), M&A boutiques a banky, v DE DUB.de (koupily ho DEALCIRCLE a AMBER), selvendo, nexxt-change od KfW ([Startbase](https://www.startbase.com/news/dealcircle-und-amber-uebernehmen-dub-de/), [Viaductus přehled](https://www.viaductus.de/en-US/posts/business-succession-marketplaces-in-germany-a-comprehensive-comparison-of-all-key-platforms)).
22. **Proč může vyhrát:** v ČR je jedna menší inzertní platforma a drahé poradenství. Chybí levná a rychlá příprava prodeje díky AI pro firmy, které poradce nezajímají. Model funguje v DE, kde KfW čeká asi 532 000 MSP s nástupnictvím do konce roku 2028 (podle [Viaductus](https://www.viaductus.de/en-US/posts/business-succession-marketplaces-in-germany-a-comprehensive-comparison-of-all-key-platforms), originál KfW neověřen).
23. **Skóre:** Bolest 7, Rozpočet 7, AI 5, MVP 7, Distribuce 5, Odlišení 6. **Celkem 6,3.**
24. **Verdikt:** Velký a rostoucí problém s jasným časováním. Ve střední Evropě je to málo obsazené. AI je ale jen urychlovač, jádro je obchod a důvěra. Hodí se, pokud Petr chce dělat byznys s lidmi, ne čistý software. Pro Claude for Startups je slabší (AI není jádro).
25. **Mapa konkurence:**
    - přímí: InBase (CZ),
    - nepřímí: M&A poradci, banky, advokátní kanceláře,
    - sousední: DE platformy (DUB/dealcircle, selvendo) by mohly expandovat do CZ,
    - DIY: prodej známým, likvidace firmy,
    - nasycení: v ČR neobsazeno, v DE validováno a konsoliduje se.
26. **Neúspěšní předchůdci:** konkrétní zaniklou platformu jsem nenašel [Nenalezeno]. Obecné riziko marketplace s nízkou likviditou je [Odhad].
27. **Poučení:** nezačínat jako prázdný marketplace. Začít jako služba s AI nástroji, nasbírat první nabídky a kupce a teprve pak otevřít platformu.
28. **Proč teď:** odchází první generace polistopadových podnikatelů ([E15](https://www.e15.cz/byznys/cesko-stoji-pred-tichou-krizi-odchod-prvni-generace-polistopadovych-podnikatelu-zmeni-ekonomiku-1435379)), J&T Banka mluví o "etapě generační obměny a velkých transakcí" ([Businessinfo](https://www.businessinfo.cz/clanky/jt-banka-business-report-firmy-vstupuji-do-etapy-generacni-obmeny-a-velkych-transakci/)) a LLM zlevnily přípravu dokumentů.

**Rozbor selhání:** zranitelné vzory 10 (tým), 8 (pomalý cyklus) a 1 (latentní bolest, majitelé to odkládají). Pre-mortem 6/10. **Šance na přežití: střední.**

---

## Karta 3: AI back-office nad českými ERP: přijaté objednávky a potvrzení od dodavatelů (B2 + N1)

1. **Název:** AI obchodní a nákupní referent pro výrobní firmy (pracovně "ERP agent").
2. **Obor:** výroba a velkoobchod v ČR a SR (Helios, K2, ABRA, Money, Pohoda).
3. **Kupující:** obchodní nebo provozní ředitel, v menších firmách majitel.
4. **Uživatel:** referentka prodeje (zakázky) a nákupčí.
5. **Dnešní ruční práce:**
   - Prodej: objednávka přijde e-mailem jako PDF, Excel nebo text, referentka ji přepíše do ERP, ověří ceny a dostupnost a pošle potvrzení.
   - Nákup: nákupčí pošle objednávku dodavateli, čeká na potvrzení, urguje a ručně přepíše potvrzený termín do ERP.
6. **Problém:** obě strany obchodu tráví hodiny přepisováním e-mailů do ERP a chyby se projeví ve výrobě.
7. **Proč na tom záleží:** 39 % z 200 velkoobchodů a výrobců uvádí ruční zadávání nabídek a objednávek mezi největšími brzdami prodeje (ECC KÖLN, červenec 2026, podle [Xictron](https://www.xictron.com/en/blog/ai-order-entry-email-pdf-orders-erp/), originál neověřen). Dodavatel WizCommerce udává 20 minut a 10 až 12 USD na ručně zpracovanou objednávku ([Distribution Strategy](https://distributionstrategy.com/2026/06/wizcommerce-launches-ai-order-entry-tool-for-distributors/), údaj dodavatele).
8. **Co dělá AI:** přečte příchozí objednávku nebo potvrzení dodavatele, spáruje zákazníka, položky a ceny s kmenovými daty v ERP, upozorní na rozdíly a připraví záznam ke schválení. U nákupu sama urguje dodavatele, kteří nepotvrdili.
9. **Funkce:**
   - čtení objednávek z e-mailu (PDF, Excel, text) a párování s kmenovými daty,
   - kontrola cen, MOQ a dostupnosti proti ERP,
   - koncept objednávky v ERP ke schválení jedním klikem,
   - automatické urgence dodavatelů a zápis potvrzených termínů,
   - upozornění na posunuté termíny, které ohrozí výrobu,
   - učení z oprav referentky (mapování kódů položek zákazníka),
   - přehled: kolik objednávek prošlo bez zásahu.
10. **MVP:** jedno ERP (to, které mají Petrovy první 3 pilotní firmy), jen přijaté objednávky, schvalování člověkem. Nákupní modul až jako druhý krok na stejné integraci.
11. **Vstupní data:** sdílená schránka objednávek, kmenová data (zákazníci, položky, ceníky), historie objednávek.
12. **Integrace:** e-mail (1) + jedno ERP (1).
13. **Proč AI:** extrakce z nestrukturovaných dokumentů a párování na kmenová data jsou dnes pro LLM s vizí dobře zvládnuté. Klasifikace výjimek zbude na člověka.
14. **Model:** předplatné podle objemu dokladů + jednorázová implementace.
15. **Cena:** 5 000 až 25 000 Kč měsíčně podle objemu + implementace 30 000 až 100 000 Kč [Odhad].
16. **Složitost:** střední (integrace na ERP).
17. **Čas do MVP:** 6 až 8 týdnů pro jedno ERP [Odhad].
18. **Obrana:** hotové konektory na česká ERP a naučené mapování položek u každého zákazníka. Odchod pak bolí. Dva moduly na jedné integraci zvyšují hodnotu.
19. **Rizika:**
    - integrační peklo (vzor 4): každé ERP a každá instalace jsou jiné,
    - konkurence: AIVIRO už dělá roboty pro Helios ([případová studie Helios](https://www.helios.eu/files/agendovy-list-aiviro.pdf)), Apertia uvádí Helios a Pohodu ([Apertia](https://apertia.ai/en/b2b-objednavky)),
    - dodavatelé ERP můžou funkci přidat sami,
    - prodej trvá u středních firem měsíce (vzor 3).
20. **Vstup na trh:** NETTINT (už digitalizuje výrobní firmy) jako první kanál, DEX síť, partnerství s implementátory ERP (dostanou provizi), případová studie z prvního pilota.
21. **Existující alternativy:** v ČR AIVIRO (Helios), Apertia, ERP integrátoři na míru. V zahraničí Comena (YC), WizCommerce, Lleverage (NL), Workist (DE), Conexiom, Y Meadows, na nákup Didero (30 mil. USD, [SiliconANGLE](https://siliconangle.com/2026/02/12/didero-raises-30m-series-expand-agentic-ai-enterprise-procurement/)) a Tacto (50 mil. EUR, [Munich Startup](https://munich-startup.de/en/news/ai-startup-tacto-secures-50-million-euros)).
22. **Proč může vyhrát:** zahraniční hráči česká ERP nepodporují (původní rešerše, ověřit ve Fázi C). Čeští hráči dělají zakázková řešení, ne opakovatelný produkt [Odhad]. Petr má přímý přístup ke kupujícím. Dva moduly (prodej + nákup) nad jednou integrací dávají lepší ekonomiku implementace.
23. **Skóre:** Bolest 6, Rozpočet 6, AI 8, MVP 5, Distribuce 7, Odlišení 6. **Celkem 6,35.**
24. **Verdikt:** Nejlépe sedí na Petrovu síť a NETTINT a je to čisté AI jádro, vhodné pro Claude for Startups. Hlavní riziko jsou integrace a skutečný stav české konkurence, který musí prověřit Fáze C.
25. **Mapa konkurence:**
    - přímí: AIVIRO, Apertia (CZ), Comena, WizCommerce, Workist, Lleverage (zahraničí),
    - nepřímí: ERP integrátoři, EDI pro velké odběratele,
    - sousední: dodavatelé ERP (Asseco/Helios, K2, ABRA, Stormware),
    - DIY: referentky, Excel, makra,
    - nasycení: v zahraničí se plní, v ČR validováno, ale málo produktů [Odhad].
26. **Neúspěšní předchůdci:** Ravacan (procurement software, USA) skončil v červnu 2024 ([CB Insights](https://www.cbinsights.com/company/ravacan)), důvody [Nenalezeno]. Starší generace OCR a "RPA" vytěžování dokumentů byla drahá na údržbu, protože se rozbíjela při každé změně formátu [Odhad, obecná zkušenost oboru].
27. **Poučení:** neslibovat 100% automatizaci, prodávat "koncept ke schválení". Začít jedním ERP a jedním typem dokladu, měřit podíl objednávek bez zásahu.
28. **Proč teď:** LLM s vizí čtou libovolné formáty bez šablon (to RPA neumělo). Investoři to validují (Didero, Comena, 5U AI). V ČR je 40 % nejmenších firem bez AI ([Businessinfo, EY](https://www.businessinfo.cz/clanky/nejvetsi-prekazky-podnikani-v-roce-2026-nefunkcni-pracovni-trh-a-prilisna-byrokracie/)) a chybí lidi.

**Rozbor selhání:** zranitelné vzory 4 (integrace), 3 (prodejní cyklus) a 2 (přesnost u cen). Mitigace: schvalování člověkem, jedno ERP, piloty přes NETTINT. Pre-mortem 7/10. **Šance na přežití: střední.**
