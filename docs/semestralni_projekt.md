# Semestrální projekt: Fuzzy věkové rozdělení

## Zadání

Projekt vychází z korespondenčního úkolu ve skriptech **Základy softcomputingu 1**, strana 31:

> Popište pomocí fuzzy množiny základní věkové rozdělení, které znají lidé. Jedná se o věkové typy: malí, mladí, střední, starší, staří, nejstarší. Zobrazte tabulkou i graficky.

Tento projekt je záměrně jednodušší. Nejde o implementaci evolučního algoritmu ani neuronové sítě, ale o praktické použití fuzzy množin na běžně pochopitelném příkladu.

## Cíl projektu

Cílem je popsat lidské věkové kategorie pomocí fuzzy množin. V běžném životě totiž věk nevnímáme ostře. Člověk se nestane přesně v den narozenin najednou z mladého člověka člověkem středního věku. Přechod je plynulý.

Fuzzy množiny umožňují vyjádřit, že jeden věk může částečně patřit do více kategorií současně. Například věk 60 let může mít vysokou příslušnost ke kategorii **starší**, ale zároveň malou příslušnost ke kategorii **střední**.

## Teoretický základ

Klasická množina pracuje jen s hodnotami 0 a 1. Prvek do množiny buď patří, nebo nepatří.

Fuzzy množina pracuje se stupněm příslušnosti:

```text
μ(x) ∈ <0, 1>
```

Význam hodnot:

- `0` znamená, že prvek do množiny nepatří,
- `1` znamená, že prvek do množiny patří plně,
- hodnota mezi `0` a `1` znamená částečnou příslušnost.

Pro věkové rozdělení je to vhodné, protože hranice mezi kategoriemi nejsou ostré.

## Návrh fuzzy množin

V projektu je věk omezen na interval 0 až 100 let. Použito je šest fuzzy množin:

- **malí**,
- **mladí**,
- **střední**,
- **starší**,
- **staří**,
- **nejstarší**.

Každá množina je popsána lichoběžníkovou funkcí příslušnosti. Lichoběžníkový tvar je vhodný, protože má plynulý nástup, oblast plné příslušnosti a plynulý pokles.

## Použité intervaly

| Fuzzy množina | a | b | c | d | Význam |
|---|---:|---:|---:|---:|---|
| malí | 0 | 0 | 10 | 16 | Plná příslušnost v dětském věku, potom plynulý pokles |
| mladí | 12 | 20 | 28 | 40 | Mladý věk s překryvem s dětským a středním věkem |
| střední | 30 | 42 | 50 | 60 | Střední věk s plynulým nástupem i ústupem |
| starší | 50 | 60 | 67 | 75 | Přechod mezi středním a starým věkem |
| staří | 65 | 75 | 82 | 90 | Starý věk s překryvem se starším a nejstarším věkem |
| nejstarší | 80 | 90 | 100 | 100 | Nejvyšší věková kategorie |

Parametry `a`, `b`, `c`, `d` určují tvar funkce:

- od `a` do `b` hodnota roste z 0 na 1,
- od `b` do `c` je hodnota 1,
- od `c` do `d` hodnota klesá z 1 na 0,
- mimo interval `<a, d>` je hodnota 0.

## Příklad výpočtu

Pro množinu **střední** jsou parametry:

```text
a = 30, b = 42, c = 50, d = 60
```

Pro věk 35 let leží hodnota v rostoucí části funkce:

```text
μ(35) = (35 - 30) / (42 - 30)
μ(35) = 5 / 12
μ(35) = 0,42
```

Člověk ve věku 35 let tedy patří do fuzzy množiny **střední** se stupněm příslušnosti přibližně 0,42.

## Tabulkové a grafické zobrazení

Soubor `index.html` obsahuje:

- graf všech šesti funkcí příslušnosti,
- posuvník pro zvolený věk,
- tabulku příslušnosti pro aktuální věk,
- tabulku hodnot po 5 letech pro celý interval 0 až 100 let.

Tím je splněna část zadání, která požaduje zobrazení tabulkou i graficky.

## Interpretace výsledku

Hlavní smysl fuzzy věkového rozdělení je v plynulých přechodech. Například:

- dítě kolem 14 let už není plně **malé**, ale ještě může mít částečnou příslušnost k této kategorii,
- člověk kolem 35 let může být částečně **mladý** a částečně **střední**,
- člověk kolem 70 let může být současně **starší** i **starý**,
- člověk kolem 85 let může být **starý** a zároveň částečně **nejstarší**.

Takové vyjádření odpovídá reálnému jazyku lépe než pevné hranice typu „do 30 let mladý, od 31 let střední“.

## Možné rozšíření

Projekt by šlo rozšířit například o:

- jinak nastavené věkové hranice,
- porovnání trojúhelníkových a lichoběžníkových funkcí,
- slovní vyhodnocení nejvhodnější kategorie pro zadaný věk,
- export tabulky do CSV,
- použití fuzzy pravidel například pro doporučení životního pojištění, sportovní aktivity nebo typu zdravotní prevence.

## Závěr

Projekt ukazuje jednoduché a srozumitelné použití fuzzy množin. Věkové kategorie nejsou popsány ostrými hranicemi, ale plynulými funkcemi příslušnosti. Výsledek je zpracován tabulkou i graficky, takže odpovídá zadání korespondenčního úkolu ze skript.
