# Bezpečnostní kontrola skills (2026-10-18)

Zdroje (verze = commit při klonování):
- mvanhorn/last30days-skill @ 0341304 (skills/last30days, v3.28.0)
- ferdinandobons/startup-skill @ a5f97c3 (startup-design, startup-competitors, startup-positioning, startup-pitch)
- nmsavaliya/claude-startup-validator @ 8f558c9 (ai-startup-opportunity-generator)
- emotixco/claude-skills-founder @ 474edd7 (13 skills, shared/conventions.md)

## Co jsem kontroloval
- skryté znaky (zero-width, bidi), HTML komentáře, fráze typu "ignore previous", "do not tell", odkazy na klíče, cookies, ~/.ssh, curl/wget, base64
- u Python/JS kódu: všechny síťové adresy, čtení souborů v domovském adresáři, eval/exec, telemetrie

## Výsledek
- **18 markdown skills (startup-*, ai-startup-opportunity-generator, founder-*)**: jen textové instrukce, žádný spustitelný kód, žádné skryté instrukce ani odkazy na externí servery. Founder skills mají omezené nástroje (Read, Edit jen do founder/, WebSearch, WebFetch). Složka evals/ (testovací shell skripty) se neinstaluje.
- **last30days**: rozsáhlý Python engine (~120 souborů). Nenašel jsem skryté instrukce, eval/exec, base64 ani telemetrii. Všechny síťové adresy odpovídají deklarovaným zdrojům (Reddit, HN Algolia, Polymarket, GitHub, YouTube, ScrapeCreators a volitelní placení poskytovatelé).
  - Rizika, která je potřeba hlídat:
    1. Umí číst cookies z prohlížečů (Chrome, Firefox, Safari) kvůli X/Twitteru. Jen s výslovným souhlasem; `--no-browser-cookies` to vypíná natvrdo (ověřeno v last30days.py, browser_mode = "off").
    2. Detekuje přihlášení jiných nástrojů: čte ~/.grok/auth.json, ~/.xurl/auth.yml, konfiguraci Bright Data a agentcookie (jen kontrola existence tokenů, ne odesílání jinam). V tomto kontejneru nic z toho není.
    3. Používá `gh` token pro GitHub vyhledávání (v kontejneru přítomen).
    4. S klíčem ScrapeCreators utrácí kredity (Reddit backfill, když bezplatná cesta vrátí < 5 výsledků).
    5. Umí publikovat výstupy na ht-ml.app (veřejně), jen po výslovné žádosti. Nepoužívat.
    6. Přibalený X klient (vendor/bird-search) obsahuje konstanty pro odeslání tweetu, ale kód je nevolá; bez cookies X stejně neběží.
    7. Ukládá výstupy do ~/Documents/Last30Days (lokálně v kontejneru).
