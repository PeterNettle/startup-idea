# Fáze B: Nové příležitosti (ai-startup-opportunity-generator)

Datum: 2026-10-18. Režim: Broad Discovery + Constraint-Based.

**Filtry podle Petra:** střední Evropa (start ČR a SR), škálovatelné, B2B, prototyp na Claude API.
**Vyloučeno:** compliance a regulace, dotace, neziskovky a už zmapovaná témata (účetní kancelář, objednávky do ERP, cizinci, autoservisy, CNC, faktury, telefonní recepční, SVJ, veřejné zakázky).
**Výhody, ke kterým jsem přihlížel:** kontakty na výrobní firmy (DEX, NETTINT), statistika a ekonomie, praxe s účetní agendou.

Bodování podle `references/scoring-rubric.md`: Bolest 25 %, Rozpočet 20 %, Vhodnost pro AI 20 %, Jednoduchost MVP 15 %, Distribuce 10 %, Odlišitelnost 10 %. **Všechna skóre jsou můj [Odhad]** na základě níže citovaných zdrojů. Nejsou ověřená u zákazníků. Rozdíly pod 0,5 bodu jsou v rámci chyby.

---

## 1. Přehled všech kandidátů

| # | Nápad | Kupující | Co dělá AI | MVP | Skóre | Přežití |
|---|---|---|---|---|---|---|
| K3 | **AI back-office nad českými ERP (B2 + N1 dohromady)** | obchodní/provozní ředitel výroby | objednávky dovnitř i urgence dodavatelů na jedné integraci | 6-8 týdnů | **6,35** | Střední |
| N6 | **AI řízení pohledávek pro B2B firmy** | majitel / finanční ředitel MSP | upomínky na míru, párování plateb, priorita dlužníků | 4-6 týdnů | **6,4** | Střední |
| N5 | **Nástupnictví: příprava a prodej malých firem** | majitel firmy 55+ | ocenění, prodejní dokumenty, párování kupců | 4-6 týdnů | **6,3** | Střední |
| B2 | Objednávky z e-mailu do ERP (původní č. 2, přeskórováno) | obchodní ředitel výroby/distribuce | vytěžení objednávky, kontrola, zápis do ERP | 6-8 týdnů | 6,3 | Střední |
| N3 | AI servisní asistent pro výrobce strojů | šéf servisu ve strojírenské firmě | odpovědi z manuálů a historie, servisní protokoly | 6-8 týdnů | 6,2 | Střední |
| N4 | AI reklamace a 8D reporty pro dodavatele automotive | vedoucí kvality | návrh 8D, dohledání dávek a příčin | 6-8 týdnů | 6,15 | Střední |
| N2 | AI asistent pro speditéry (poptávky přeprav) | majitel spedice | čtení poptávek, nacenění, nabídka | 8+ týdnů | 6,1 | Střední až nízké |
| N1 | AI hlídání potvrzení a termínů od dodavatelů | vedoucí nákupu ve výrobě | urgence dodavatelů, zápis potvrzení do ERP | 6-8 týdnů | 6,0 | Střední |
| B1 | AI účetní kancelář (původní č. 1, přeskórováno) | majitel MSP | vedení účetnictví, člověk podepisuje | 8+ týdnů | 6,0 | Střední |
| N7 | AI nabídky a rozpočty pro řemeslníky | malá stavební firma, řemeslník | nabídka z fotek a popisu | 3-4 týdny | 5,55 | Nízké |
| B3 | Cizinci ve výrobě (původní č. 3, přeskórováno) | HR / výroba / agentura | překlad postupů, školení | 6-8 týdnů | 5,6 | Nízké až střední |
| B4 | Autoservisy (původní č. 4, přeskórováno) | majitel servisu | schvalování kalkulací, follow-up | 6 týdnů | 5,6 | Nízké |
| B5 | Nacenění CNC (původní č. 5) | - | - | - | 5,8 (nepřeskórováno) | obsazeno |

**Proč jsem původní nápady přeskóroval níž než v minulé rešerši:** Fáze A ukázala víc konkurence (B2: AIVIRO v Heliosu, Comena, WizCommerce; B1: Balance, Integral; B3: doinstruct) a u B1 je MVP těžké (služba s licencovaným člověkem a účetním spoluzakladatelem).

### Podrobné body

| # | Bolest | Rozpočet | AI | MVP | Distribuce | Odlišení | **Skóre** |
|---|---|---|---|---|---|---|---|
| N6 Pohledávky | 7 | 5 | 8 | 7 | 6 | 4 | **6,4** |
| K3 ERP back-office (B2+N1) | 6 | 6 | 8 | 5 | 7 | 6 | **6,35** |
| N5 Nástupnictví | 7 | 7 | 5 | 7 | 5 | 6 | **6,3** |
| B2 Objednávky do ERP | 6 | 6 | 8 | 6 | 6 | 5 | **6,3** |
| N3 Servisní asistent | 6 | 7 | 6 | 6 | 6 | 6 | **6,2** |
| N4 8D reklamace | 7 | 6 | 6 | 6 | 5 | 6 | **6,15** |
| N2 Spedice | 7 | 6 | 7 | 5 | 5 | 5 | **6,1** |
| N1 Potvrzení od dodavatelů | 6 | 6 | 7 | 6 | 5 | 5 | **6,0** |
| B1 AI účetní kancelář | 6 | 7 | 7 | 4 | 5 | 6 | **6,0** |
| B3 Cizinci | 6 | 5 | 6 | 6 | 5 | 5 | **5,6** |
| B4 Autoservisy | 6 | 5 | 7 | 6 | 4 | 4 | **5,6** |
| N7 Řemeslníci | 6 | 4 | 6 | 7 | 6 | 4 | **5,55** |

---

## 2. Krátký rozbor nových kandidátů (konkurence a rizika selhání)

### N1. AI hlídání potvrzení a termínů od dodavatelů (nákup ve výrobě)
- **Práce dnes:** nákupčí rozesílá objednávky, čeká na potvrzení, urguje e-mailem a telefonem a ručně přepisuje potvrzené termíny do ERP.
- **Důkaz, že model funguje jinde:** Didero (USA) získal v únoru 2026 Series A 30 mil. USD, má přes 30 zákazníků a automatizuje komunikaci s dodavateli a sledování objednávek nad e-mailem a ERP ([SiliconANGLE](https://siliconangle.com/2026/02/12/didero-raises-30m-series-expand-agentic-ai-enterprise-procurement/)). Tacto (Mnichov) získal 50 mil. EUR na nákup pro průmyslový Mittelstand ([Munich Startup](https://munich-startup.de/en/news/ai-startup-tacto-secures-50-million-euros)).
- **ČR:** českého specializovaného hráče jsem nenašel [Nenalezeno]. Našel jsem jen obecné stránky dodavatele virtualworkforce.ai v češtině ([zdroj](https://virtualworkforce.ai/cs/ai-agenti-pro-distributory-elektroniky/)).
- **Neúspěšní předchůdci:** Ravacan (procurement software, USA) skončil v červnu 2024 po získání asi 1,6 mil. USD ([CB Insights](https://www.cbinsights.com/company/ravacan)); důvody nejsou veřejně rozepsané [Nenalezeno].
- **Rizika:** integrace s českými ERP (vzor selhání 4), nákup je u menších firem často jen část úvazku, takže rozpočet je slabší.
- **Poznámka:** sdílí integrační vrstvu s B2 (objednávky do ERP). Viz karta 3.

### N2. AI asistent pro speditéry (poptávky a nabídky přeprav)
- **Práce dnes:** dispečer čte desítky poptávek z e-mailu a burz, ručně nacení a odpoví nabídkou.
- **Konkurence:** 5U AI (Mnichov, pre-seed 3,2 mil. USD, nabídky, booking, tracking) a Nexcade (Londýn, seed 6 mil. USD, agenti pro nacenění a nabídky) ([SCE](https://www.sce.de/en/news-details/5u-ai-holt-sich-32-mio-us-dollar-pre-seed-fuer-digitale-speditions-workforce.html), [The Loadstar](https://theloadstar.com/ls_press_release/nexcade-raises-6m-to-build-ai-agents-for-freight-forwarders/)).
- **Neúspěšný předchůdce:** Convoy (USA, digitální brokerage) skončil v říjnu 2023. Příčiny byly propad sazeb asi o 30 %, náklady na technologii, které tržby nikdy nepokryly, a nepovedený prodej ([Supply Chain Digest](https://www.scdigest.com/ONTARGET/23-10-31_Why_Convoy_Went_Under.php?cid=21061), [FreightWaves](https://www.freightwaves.com/news/convoy-co-founder-reflects-on-digital-brokerages-rise-and-fall)). Poučení: nebýt brokerem s vlastním rizikem, prodávat software nad prací dispečera.
- **Rizika:** Petr nemá do dopravy kontakty (vzor 10), cyklický trh s nízkými maržemi a velkou roli hrají burzy (Trans.eu, Timocom), které můžou funkci přidat samy. Počet českých speditérů [Nenalezeno].

### N3. AI servisní asistent pro výrobce strojů
- **Práce dnes:** servisní technik u zákazníka v zahraničí hledá v PDF manuálech a volá kolegům. Protokol píše večer ručně.
- **Kontext ČR:** strojírenství vyváží asi 70 % produkce, 74 % exportu jde do EU ([Businessinfo](https://www.businessinfo.cz/clanky/pilir-ceskeho-prumyslu-celi-vyzvam-strojirenstvi-zezelena-a-zautomatizuje-se/)). Podnikatel Hlavinka říká, že servis v Česku nemá takovou tradici a zákazníci v DE a USA čekají rychlou pomoc ([Newstream](https://www.newstream.cz/leaders/cesti-strojari-se-o-zivobyti-bat-nemusi-jejich-prace-se-ale-promeni-mini-podnikatel-hlavinka)).
- **Konkurence:** Aquant (USA/Izrael, celkem asi 110 mil. USD, enterprise) ([Field Service News](https://www.fieldservicenews.com/aquant-announces-70-million-series-c-funding-round-to-revolutionize-the-service-industry-using-artificial-intelligence/)). Česká alternativa [Nenalezeno].
- **Neúspěšní předchůdci:** [Nenalezeno].
- **Rizika:** dokumentace je u každého výrobce v jiném stavu a přínos se těžko měří. Kupuje střední firma, rozhodování trvá měsíce (vzor 3).

### N4. AI reklamace a 8D reporty pro dodavatele automotive
- **Práce dnes:** po reklamaci od OEM musí kvalita v termínu dodat 8D report. Většinu času zabere dohledávání dávek, záznamů a minulých případů, ne samotná analýza ([iFactory](https://ifactoryapp.com/industries/automotive-manufacturing/automotive-8d-problem-solving-corrective-action-ai), dodavatelský zdroj).
- **Konkurence:** CAQ systémy s 8D moduly ([SoftwareOne/CAQ](https://platform.softwareone.com/product/8d-report/PCP-4595-1304)). Specializovaný AI hráč pro ČR [Nenalezeno].
- **Rizika:** hraničí s "compliance" (8D je navázané na IATF 16949), což Petr vylučuje. Evropský automotive je pod tlakem. Přesnost je kritická (vzor 2).
- **Neúspěšní předchůdci:** [Nenalezeno].

### N5. Nástupnictví: příprava a prodej malých firem (karta 2)
### N6. AI řízení pohledávek pro B2B firmy (karta 1)

### N7. AI nabídky a rozpočty pro řemeslníky
- **Konkurence:** desítky malých AI nástrojů (Insta Quotes, QuoteDrop, Estimo, AirQuote, Sleepless Tradesman), zatím hlavně v anglofonních zemích ([Capterra](https://www.capterra.com/p/10046036/QuoteDrop/)). Kategorie se rychle plní a odlišit se je těžké.
- **Rizika:** nízký rozpočet řemeslníků (vzor 7) a nepřesné ceny vedou k podhodnoceným nabídkám ([The AI Career Lab](https://theaicareerlab.com/blog/best-ai-tools-for-tradespeople-2026)). **Doporučení: nepokračovat.**

---

## 3. Shrnutí podle kritérií skillu

- **Nejlepší celkově:** N6 Pohledávky (6,4). Silná bolest, AI zvládne většinu práce, rychlé MVP.
- **Nejrychlejší na stavbu:** N6 Pohledávky (bankovní API + export z účetnictví, 4-6 týdnů).
- **Nejvyšší potenciál tržeb:** N5 Nástupnictví (transakce v milionech Kč, provize z úspěchu) a karta 3 (nákup + prodej nad ERP, opakované platby od výrobních firem).
- **Nejlepší pro sólo zakladatele:** N6 Pohledávky.
- **Nejlepší start pro Petra:** karta 3 (AI back-office nad českými ERP). Má nejlepší přístup k zákazníkům přes DEX a NETTINT a víc produktů na jedné integraci.

Plné karty se všemi 28 body: `karty-top3.md`.
