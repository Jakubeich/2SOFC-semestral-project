# Fuzzy věkové rozdělení

Semestrální projekt k zápočtu z předmětu **Základy softcomputingu 1**.

Autor: **Jakub Mitrega**

## Zadání

Projekt vychází z korespondenčního úkolu ze skript, strana 31:

> Popište pomocí fuzzy množiny základní věkové rozdělení, které znají lidé. Jedná se o věkové typy: malí, mladí, střední, starší, staří, nejstarší. Zobrazte tabulkou i graficky.

## Cíl projektu

Cílem projektu je převést běžné slovní věkové kategorie do podoby fuzzy množin. Věkové pojmy jako `mladí`, `střední`, `staří` nebo `nejstarší` nemají v běžném jazyce přesnou hranici. Fuzzy množiny umožňují popsat tyto přechody plynule pomocí stupně příslušnosti v intervalu od `0` do `1`.

Výsledkem je:

- návrh fuzzy množin pro šest věkových kategorií,
- tabulka parametrů použitých množin,
- graf funkcí příslušnosti,
- interaktivní webová aplikace pro výpočet příslušnosti zvoleného věku.

## Spuštění aplikace

Aplikace je vytvořená jako statická webová stránka. Není potřeba instalovat žádné závislosti.

Lokální spuštění:

1. Otevřít soubor `index.html` v prohlížeči.
2. Posuvníkem `Zvolený věk` měnit vstupní věk.
3. Sledovat změny v grafu a tabulce příslušnosti.

Volitelně lze spustit lokální server:

```bash
python3 -m http.server 8765
```

Potom je aplikace dostupná na adrese:

```text
http://127.0.0.1:8765/index.html
```

## Struktura projektu

```text
.
├── index.html
├── vercel.json
├── data/
│   └── fuzzy_mnoziny.csv
├── docs/
│   ├── semestralni_projekt.md
│   ├── obhajoba_prirucka.md
│   ├── scenar_obhajoby_krok_za_krokem.md
│   ├── text_obhajoby_15_20_min.md
│   └── pruvodce_ukazkou_aplikace_a_pojmy.md
└── prezentace_fuzzy_vekove_rozlozeni.pptx
```

## Použité věkové kategorie

Projekt pracuje s těmito fuzzy množinami:

- `malí`,
- `mladí`,
- `střední`,
- `starší`,
- `staří`,
- `nejstarší`.

Každá množina je popsána lichoběžníkovou funkcí příslušnosti. Funkce vrací hodnotu `μ(x)` pro zvolený věk `x`.

## Interpretace hodnot

- `μ(x) = 0` znamená, že věk do dané kategorie nepatří.
- `μ(x) = 1` znamená plnou příslušnost.
- Hodnoty mezi `0` a `1` znamenají částečnou příslušnost.

Příklad: věk `35 let` může mít nenulovou příslušnost ke kategoriím `mladí` i `střední`. To vyjadřuje plynulý přechod mezi dvěma věkovými pojmy.

## Použitá funkce příslušnosti

Pro všechny věkové kategorie je použita lichoběžníková funkce příslušnosti se čtyřmi parametry `a`, `b`, `c`, `d`:

- od `a` do `b` příslušnost roste z `0` na `1`,
- od `b` do `c` je příslušnost rovna `1`,
- od `c` do `d` příslušnost klesá z `1` na `0`,
- mimo interval `<a, d>` je příslušnost rovna `0`.

Tento tvar byl zvolen kvůli jednoduchému výpočtu, přehlednému grafickému zobrazení a srozumitelné interpretaci.

## Nasazení

Projekt je možné nasadit jako statickou stránku například na Vercel.

Při importu repozitáře do Vercelu je vhodné nastavit:

```text
Framework Preset: Other
Root Directory: .
Build Command: prázdné
Output Directory: .
Install Command: prázdné
```

Pokud je tento projekt uložený v nadřazeném repozitáři jako podsložka, nastaví se ve Vercelu `Root Directory` na:

```text
fuzzy-vekove-rozlozeni
```

## Dokumentace k obhajobě

Ve složce `docs/` jsou připravené podpůrné materiály:

- `semestralni_projekt.md` - písemné vypracování projektu,
- `obhajoba_prirucka.md` - stručná příručka k obhajobě,
- `scenar_obhajoby_krok_za_krokem.md` - scénář obhajoby,
- `text_obhajoby_15_20_min.md` - delší text k prezentaci,
- `pruvodce_ukazkou_aplikace_a_pojmy.md` - průvodce ukázkou aplikace a slovníček pojmů.
