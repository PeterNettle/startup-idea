# Fáze B, třetí pokus: škálovatelné B2B příležitosti ze signálů (2026-10-18)

Zadání od Petra: škálovatelné, B2B, ne administrativa malých firem, ne nic z už řešených nápadů.

## Metoda
1. **Těžba Redditu (arctic-shift):** 34 B2B komunit (IT, devops, data, bezpečnost, produkt, prodej, RevOps, marketing, PPC, SEO, e-commerce, nákup, supply chain, výroba, kvalita, legaltech, účetnictví, FP&A, HR, CS, AI vývojáři, Salesforce, SAP, NetSuite), posledních 60 dní, u 30 z nich posledních 300 příspěvků. 4 900+ příspěvků, 467 zásahů. Data: `raw-signaly-b2b/` (soubory jsou v repozitáři).
2. **last30days** (vždy `--no-browser-cookies`, plán dotazů ode mě) na 4 B2B témata: výdaje na AI, AI agenti v produkci, viditelnost v AI vyhledávání a zavádění AI v průmyslu. Výsledky: 40 až 76 položek na téma, `raw-signaly-b2b/*-raw-v3.md`.
3. **Ověření konkurence a peněz** u každé kategorie (web).

## Hlavní zjištění
Bolesti B2B uživatelů za poslední kvartál se nejvíc točí kolem **zavádění AI ve firmách**: náklady, bezpečnost agentů, kvalita dat a měření přínosu. Je to globální trh, ne český.

## Zamítnuté kategorie (silná bolest, ale přeplněno nebo bez šance)

| Kategorie | Signál | Proč ne |
|---|---|---|
| Bezpečnost a oprávnění AI agentů | HN 948 bodů / 620 komentářů ([CSO Online](https://www.csoonline.com/article/4234854/ai-agents-arent-going-rogue-frontier-labs-are-skipping-security-basics.html)), r/devops "How are you giving AI agents access to AWS in production?" | 435 mil. USD ve 12 kolech za duben až září 2026 ([Forkast](https://forkast.news/enterprise-ai-agent-funding-surges-to-435m-in-five-months-security-and-governance-lead/)), HiddenLayer 100 mil. USD, AIR 50 mil. USD seed. Potřeba špičkového bezpečnostního týmu. |
| Viditelnost v AI vyhledávání (GEO) | r/SEO, r/growthmarketing: zastaralé odpovědi ChatGPT o cenách firmy | Profound 1,8 mld. USD valuace, Peec AI (Berlín) 21 mil. USD, 7 startupů vybralo 472 mil. USD ([Dealroom](https://dealroom.co/charts/generative-engine-optimization-startups)). Marketéři sami píšou, že trackery jsou "scams". |
| Správa SSL certifikátů (platnost 200 -> 47 dní) | r/sysadmin 95 a 106 komentářů | Harmonogram je reálný ([AppViewX](https://www.appviewx.com/blogs/certificate-validity-period-47-days/)), ale certifikační autority samy vstupují do segmentu MSP (GlobalSign TLS Connect, [Help Net Security](https://www.helpnetsecurity.com/2026/04/27/gmo-globalsign-tls-connect/)). |
| Kontrola výdajů a adopce AI ve středních firmách | "Massive AI bills, for what?" 175 bodů / 271 komentářů ([r/ExperiencedDevs](https://www.reddit.com/r/ExperiencedDevs/comments/1x65khe/massive_ai_bills_for_what/)), r/ITManagers "shadow AI" ve firmách s 10 až 100 lidmi | Bolest ano, ale Larridin (17 mil. USD, a16z), Harmonic (76 mil. USD), Nudge (22,5 mil. USD) a dodavatelé (Microsoft, OpenAI, Anthropic) přidávají vlastní přehledy. AI tu dělá málo, je to hlavně sběr dat. Moje skóre 5,35. |

---

## Doporučený kandidát: AI příprava firemních dat pro AI (kmenová data ve výrobě)

**Jednou větou:** AI agent, který vyčistí, sjednotí a průběžně hlídá kmenová data výrobních firem (položky, kusovníky, dodavatelé, náhradní díly), aby na nich mohly fungovat AI projekty a migrace ERP.

**Signály z komunit (B2B uživatelé):**
- "Leadership wants an Agentforce pilot on data we all know is messy" ([r/salesforce](https://www.reddit.com/r/salesforce/comments/1x4pl6u/))
- "AI won't fix your Customer Success if your data looks like mine" ([r/CustomerSuccess](https://www.reddit.com/r/CustomerSuccess/comments/1wnhxbl/))
- "How common is it to have unclean database?" ([r/FPandA, 51 komentářů](https://www.reddit.com/r/FPandA/comments/1wuosz5/))
- Strach pouštět AI na databázi kvůli halucinacím a účtům ([r/analytics](https://www.reddit.com/r/analytics/comments/1wu5bmx/))
- Továrna s 200+ lidmi, kde "each department had its own spreadsheets, dozens of them, in some places hundreds" ([r/manufacturing](https://www.reddit.com/r/manufacturing/comments/1x5822x/))

**Tvrdá data:**
- Gartner: do konce roku 2026 firmy opustí 60 % AI projektů, které nemají "AI-ready" data. 63 % organizací nemá správné postupy správy dat pro AI, nebo si tím není jisté ([Gartner, únor 2025](https://www.gartner.com/en/newsroom/press-releases/2025-02-26-lack-of-ai-ready-data-puts-ai-projects-at-risk)).
- SAP ECC končí běžnou podporu 31. 12. 2027. Ke konci roku 2024 nemigrovalo 39 % z 35 000 zákazníků ECC ([The Register](https://www.theregister.com/2026/02/05/sap_migrations_research/)). Migrace přenáší špinavá data ([Pomerol Partners](https://marketplace.microsoft.com/it-it/product/pomerolpartnersllc1723838376119.pomerolpartners_accelerating_erp_ai_mdm?country=CA)).
- SPARETECH uvádí 15 % duplicit a 17 % zastaralých položek v náhradních dílech továren ([SPARETECH](https://en.sparetech.io/blog/series-a-funding-led-by-us-investor-insight-partners), údaj dodavatele).

**Konkurence:**
- SPARETECH (Stuttgart, Series A 10 mil. EUR v roce 2023, 120+ výrobců, jen náhradní díly MRO, hlavně SAP) ([Silicon Canals](https://siliconcanals.com/sparetech-raises-10m/))
- SAP poradci s AI doplňky: Pikon, apsolut + Creactives ([Pikon](https://www.pikon.com/en/blog/mastering-data-accuracy-innovations-in-duplication-detection/))
- Velké MDM (Informatica, Stibo, Profisee) jsou drahé enterprise řešení [Odhad, bez zdroje ceny]
- U CRM: Traction Complete Data Agents, Tofu, Insycle, Cloudingo ([Tofu přehled](https://www.tofuhq.com/post/best-tools-make-crm-data-agent-ready))
- **Mezera [Odhad, ověřit ve Fázi C]:** střední výrobní firmy mimo SAP (Business Central, Odoo, Infor, Epicor, Helios, K2, ABRA) a jiné typy dat než MRO (výrobní položky, kusovníky, dodavatelé).

**Proč škálovatelné:** každá výrobní firma má špinavá kmenová data. Trh je celoevropský i globální a nezávisí na češtině. Na ERP navazuje jen přes export a import, takže v MVP nejsou potřeba integrace. Opakovaný příjem je z průběžného hlídání kvality (nové položky, duplicity), ne jen z jednorázového úklidu.

**MVP (4 až 6 týdnů) [Odhad]:** firma nahraje export položek (CSV/Excel). AI najde duplicity, doplní a sjednotí atributy (rozměr, materiál, norma), navrhne klasifikaci a vrátí soubor ke schválení a nahrání zpět do ERP. Bez integrace.

**Obchodní model [Odhad]:** jednorázový úklid (podle počtu položek) + předplatné na průběžné hlídání (nové položky, duplicity, "AI readiness skóre"). Prodej přes ERP partnery a implementátory (dostanou podíl) a přes NETTINT.

**Skóre (rubrika skillu) [Odhad]:** Bolest 7, Rozpočet 7, AI 7, MVP 6, Distribuce 6, Odlišení 6 = **6,65**.

**Rizika:**
- **Projektový charakter:** po úklidu zákazník odejde. Nutné dokázat průběžnou hodnotu (vzor selhání: cena).
- **Přesnost:** chybné sloučení položek způsobí škody ve výrobě, proto vždy schvaluje člověk (vzor 2).
- **Je to nesexy kategorie:** prodej přes "AI readiness" a migrace, ne přes "čištění dat".
- **Konkurence z SAP světa** se může posunout do středního trhu.
- **Překryv s dřívějšími nápady:** dotýká se ERP. Rozdíl je, že nejde o automatizaci jednoho procesu pro českou firmu, ale o datovou vrstvu prodávanou celoevropsky.

**Proč Petr:** NETTINT digitalizuje výrobní firmy a sám vidí stav jejich dat. Má kontakty na výrobu (DEX) a statistiku (párování a deduplikace jsou statistické úlohy). Pilotní zákazníky má na dosah.

**Neúspěšní předchůdci:** konkrétní zaniklý startup v této kategorii jsem nenašel [Nenalezeno]. Obecně: data quality nástroje často skončily jako služby na míru, protože každá firma má jiná data [Odhad].
