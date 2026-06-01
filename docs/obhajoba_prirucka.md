# Příručka k obhajobě

## Co je téma

Téma je fuzzy věkové rozdělení. Vybral jsem korespondenční úkol ze skript na straně 31, kde je zadáno popsat věkové typy pomocí fuzzy množin a zobrazit je tabulkou i graficky.

## Proč je to fuzzy úloha

Věk člověka nejde dobře rozdělit ostrými hranicemi. Není rozumné říct, že člověk je přesně do 29 let mladý a od 30 let už není mladý vůbec. Lidské pojmy jako mladý, starší nebo starý jsou vágní.

Fuzzy množiny tuto vágnost popisují stupněm příslušnosti od 0 do 1.

## Co znamená stupeň příslušnosti

- `0` znamená, že věk do kategorie nepatří.
- `1` znamená, že věk do kategorie patří plně.
- Například `0,5` znamená částečnou příslušnost.

## Jaké kategorie používám

Používám šest kategorií:

- malí,
- mladí,
- střední,
- starší,
- staří,
- nejstarší.

Každá kategorie má lichoběžníkovou funkci příslušnosti.

## Co ukázat v aplikaci

1. Otevřít `index.html`.
2. Ukázat graf funkcí příslušnosti.
3. Posouvat věk posuvníkem.
4. Ukázat, že jeden věk může patřit do více kategorií současně.
5. Ukázat tabulku hodnot po 5 letech.
6. Vysvětlit, že překryvy mezi kategoriemi jsou záměrné.

## Příklad vysvětlení

Pro věk 35 let může být člověk ještě částečně mladý, ale současně už částečně střední. To je přesně situace, kde fuzzy množiny dávají větší smysl než ostré intervaly.

## Časté otázky

### Proč nejsou hranice pevné?

Protože věkové pojmy v běžném jazyce pevné hranice nemají. Fuzzy množiny umožňují plynulý přechod.

### Proč jsem zvolil lichoběžníkové funkce?

Jsou jednoduché, přehledné a dobře se vysvětlují. Mají náběh, oblast plné příslušnosti a pokles.

### Jsou intervaly jediné správné?

Ne. U fuzzy množin je návrh funkcí závislý na interpretaci a konkrétní aplikaci. Důležité je, aby byl návrh rozumný a vysvětlitelný.

### Co je hlavní výsledek projektu?

Tabulkové a grafické zobrazení věkových fuzzy množin. Projekt ukazuje, jak lze vágní lidské pojmy převést do matematického modelu.
