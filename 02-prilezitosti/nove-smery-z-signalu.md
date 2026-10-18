# Fáze B, druhý pokus: nápady odvozené ze signálů (2026-10-18)

## Proč druhý pokus
První verze Fáze B (`prehled-faze-b.md`) vznikla z mé hlavy a webového vyhledávání, Reddit jsem nepoužil a výsledkem byly varianty "AI administrativa pro malé firmy", tedy to, co Petr už znal. Tato verze vychází z dat.

## Metoda
1. **Těžba poptávky z Redditu:** 78 komunit napříč obory (profese, zdravotnictví, školství, reality, logistika, e-commerce, rodiny, Evropa), 35 503 příspěvků za 60 dní, filtr na fráze "would pay", "is there an app", "wish there was", "why is there no", "manually" atd. Výsledek: 445 zásahů, ručně jsem prošel 150 nejsilnějších (`raw-signaly/reddit-tezba-top150.txt`, celá data `raw-signaly/reddit-tezba-poptavky-60dni.jsonl`). Pozor: u části komunit sběr přerušil archiv chybou 422, pokrytí je neúplné.
2. **last30days** (vždy `--no-browser-cookies`, plán dotazů ode mě): obecné dotazy "I would pay for", "why is there no app" a cílené dotazy na témata z těžby (`raw-signaly/*-raw-v3.md`).
3. **Filtr:** doložená bolest + model funguje jinde + ve střední Evropě mezera + nejde o administrativu MSP ani o compliance.

## Co data ukázala (upřímně)
- **Obecné "would pay" dotazy jsou šum:** vrací hlavně zakladatele, kteří si ověřují vlastní nápady (r/SaaS, r/SideProject).
- **Reddit je americký a anglický.** Pro střední Evropu ukazuje témata bolesti, ne místní poptávku. Němečtí, čeští ani slovenští zákazníci tu skoro nejsou.
- **Opakující se silná témata mimo admin MSP:** péče o stárnoucí rodiče, lidé proti pojišťovnám a fakturám, nedostatek služeb a řemeslníků v Německu.
- **Varování:** aplikace na koordinaci péče o rodiče je přeplněná. Na r/eldercare zakladatele banují: "everyone and their cousin is building EXACTLY what you are" ([r/eldercare](https://www.reddit.com/r/eldercare/comments/1x762wo/im_building_a_startup_to_make_caring_for_aging/)). Tento směr proto vyřazuji.

---

## Směr 1: Platforma pro 24hodinovou domácí péči v koridoru CZ/SK/PL -> Německo a Rakousko

**Signál:** péče o stárnoucí rodiče je jedno z nejsilnějších emočních témat na Redditu (např. [r/digitalnomad, 133 bodů, 117 komentářů](https://www.reddit.com/r/digitalnomad/comments/1ws6pir/how_do_you_deal_with_living_far_away_from_aging/)). Přímé hlasy německých rodin na Redditu ale nejsou [Nenalezeno], musí se ověřit jinde.

**Trh (doložený):**
- Rakousko: asi 57 000 pečovatelek "24h", 98 % dojíždí z Rumunska, Slovenska, Chorvatska a Maďarska, 912 zprostředkovatelských agentur ([Wojczewski, MedUni Wien 2025](https://verwaltung.steiermark.at/cms/dokumente/12943442_181857756/a723c872/Equal%20care%20day_SWojczewski.pdf)). Slovenky pracují jako OSVČ a agentury se chovají jako zaměstnavatelé, což vytváří nerovnováhu sil ([CELSI 2025](https://www.celsi.sk/media/datasource/CARE4CARE_SK_Policy_paper_final_EN_QA8Qlex.pdf)).
- Německo: odhady 100 000 až 400 000 pečovatelek z východní Evropy (ZDF), rodiny platí agenturám 1 470 až 3 400 EUR měsíčně, Stiftung Warentest prověřil 13 celostátních agentur ([test.de](https://www.test.de/Pflege-Betreuungskraft-aus-Osteuropa-die-besten-Vermittler-5170957-0/)). Verbraucherzentrale NRW odhaduje, že asi 85 % pracuje načerno (tamtéž, odhad, ne statistika).
- Hrubý řád trhu v DE: 300 000 pečovatelek x 2 000 EUR měsíčně = asi 7 mld. EUR ročně [Odhad z čísel výše].

**Nápad:** moderní, legální a transparentní platforma, která páruje pečovatelky z CZ, SK a PL s rodinami v DE a AT. AI tu pomáhá s jazykem (překlad mezi pečovatelkou, rodinou a lékařem), předáváním směn a péčí, dokumentací a plánováním rotací. Pečovatelky dostanou férovější podmínky než u starých agentur, rodiny důvěru a přehled.

**Proč by to mohlo škálovat:** obrovský roztříštěný trh starých agentur, rostoucí poptávka (stárnutí DACH) a nabídka ze střední Evropy. Kdo ovládne nabídku pečovatelek, vyhrává.

**Neúspěšný předchůdce:** Careship (Berlín, přes 13 mil. EUR, platforma pomocníků pro seniory) šel v prosinci 2021 do insolvence po ztrátě 3,8 mil. EUR za rok 2019 a nepovedeném prodeji ([deutsche-startups.de](https://www.deutsche-startups.de/2021/12/08/careship-exit-insolvenz/)). Pozor, šlo o jiný segment (hodinová výpomoc, ne 24h péče).

**Rizika:** právní šedá zóna (vysílání pracovníků, OSVČ vs zaměstnanec) [Odhad, ověřit], provozně náročné (lidi, ne software), reputační riziko při incidentu, nízká marže agentur [Nenalezeno].

**Proč Petr:** Liberec u hranic se Saskem, česká a slovenská nabídková strana, zkušenost s EU projekty.

---

## Směr 2: AI zastání spotřebitele proti pojišťovnám (model Votum, ale s AI a pro menší nároky)

**Signál:** "Long Term Care Insurance is a Scam", 391 bodů, 165 komentářů. Rodiny popisují, jak pojišťovna zdržuje a tvrdí, že chybí dokumenty ([r/CaregiverSupport](https://www.reddit.com/r/CaregiverSupport/comments/1x52m95/long_term_care_insurance_is_a_scam/)). Ve Fázi A zmatek kolem výplaty pojistky za opravu auta ([r/Insurance](https://www.reddit.com/r/Insurance/comments/1wmo9le/insurance_cheque_is_2800_but_body_shop_says_the/)). V těžbě: spor o nadsazenou lékařskou fakturu v Německu ([r/germany](https://www.reddit.com/r/germany/comments/1x1pajb/)).

**Důkaz, že model funguje ve střední Evropě:** polská Votum S.A. (Wrocław, burza ve Varšavě) vymáhá odškodnění od pojišťoven a bank. Tržby za rok 2025 asi 462 mil. PLN podle čtvrtletních dat, 407 mil. PLN za rok 2024 ([ROIC](https://www.roic.ai/quote/VOT.WA/classic), [PitchBook](https://pitchbook.com/profiles/company/159870-07), údaje se mezi zdroji liší).

**Nápad:** AI připraví a vede reklamaci pojistného plnění pro spotřebitele (krácené plnění z povinného ručení, havarijní a cestovní pojištění), advokát podepisuje. Platí se provizí z navýšení. AI zlevní práci natolik, že se vyplatí i malé nároky, které Votum a advokáti dnes neberou [Odhad].

**Neúspěšný předchůdce:** DoNotPay ("robot lawyer") dostal v roce 2024 od FTC pokutu 193 000 USD, protože netestoval kvalitu a nespolupracoval s advokáty ([ABA Journal](https://www.abajournal.com/news/article/robot-lawyer-website-donotpay-settles-ftc-claims-it-couldnt-deliver-on-promises)). Poučení: advokát v procesu, žádné přehnané sliby.

**Rizika:** regulace právních služeb (advokacie) [Odhad, ověřit], pojišťovny se brání, CZ trh je menší než PL (v PL je tradice "odszkodowania"), české konkurenty jsem zatím nedohledal [Nenalezeno].

---

## Co nedoporučuji
- Aplikace na koordinaci péče o rodiče (přeplněno, viz výše).
- "Najdi řemeslníka v Německu": Němci podle Redditu spoléhají na svépomoc ([r/AskAGerman, 243 bodů](https://www.reddit.com/r/AskAGerman/comments/1wzaoze/how_much_value_do_people_in_germany_place_on/)), signál je slabý.
