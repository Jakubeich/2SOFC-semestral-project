# Fuzzy věkové rozdělení

Jednodušší semestrální projekt do předmětu **Základy softcomputingu 1**. Projekt vychází z korespondenčního úkolu ve skriptech na straně 31:

> Popište pomocí fuzzy množiny základní věkové rozdělení, které znají lidé. Jedná se o věkové typy: malí, mladí, střední, starší, staří, nejstarší. Zobrazte tabulkou i graficky.

Tento projekt je jednodušší než evoluční algoritmus i perceptron. Neřeší se zde programování složitého algoritmu, ale návrh fuzzy množin a jejich přehledné zobrazení.

## Co projekt obsahuje

- `index.html` - interaktivní tabulka a graf fuzzy věkových množin,
- `data/fuzzy_mnoziny.csv` - definice použitých fuzzy množin,
- `docs/semestralni_projekt.md` - hotové vypracování,
- `docs/obhajoba_prirucka.md` - stručné vysvětlení k obhajobě,
- `docs/pruvodce_ukazkou_aplikace_a_pojmy.md` - průvodce ukázkou webové aplikace a slovníček pojmů,
- `docs/scenar_obhajoby_krok_za_krokem.md` - scénář, podle kterého lze projekt odprezentovat.

## Spuštění

Stačí otevřít soubor:

```text
index.html
```

Není potřeba Maven, Java ani žádný server. Projekt funguje jako obyčejná webová stránka v prohlížeči.

## Princip

Klasické množiny by člověka zařadily do jedné pevné kategorie. Fuzzy množiny umožňují, aby člověk patřil do více kategorií současně s různým stupněm příslušnosti.

Příklad: člověk ve věku 60 let může být částečně **střední** a zároveň hodně **starší**. To odpovídá běžnému lidskému vnímání věku lépe než ostrá hranice.

## Použité věkové typy

Projekt používá šest fuzzy množin:

- malí,
- mladí,
- střední,
- starší,
- staří,
- nejstarší.

Každá množina má lichoběžníkovou funkci příslušnosti. Hodnota `0` znamená, že věk do kategorie nepatří. Hodnota `1` znamená plnou příslušnost. Hodnoty mezi `0` a `1` znamenají částečnou příslušnost.
# 2SOFC-semestral-project
