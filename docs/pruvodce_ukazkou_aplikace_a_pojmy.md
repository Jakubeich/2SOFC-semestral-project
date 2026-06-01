# Průvodce ukázkou aplikace a vysvětlivky pojmů

Tento dokument je praktická opora k obhajobě. Je napsaný tak, aby se podle něj dala vést živá ukázka webové aplikace a zároveň aby bylo po ruce stručné vysvětlení základních pojmů.

## Rychlá struktura ukázky

Ukázku aplikace bych vedl přibližně takto:

1. Otevřít aplikaci a říct, co zobrazuje.
2. Ukázat posuvník `Zvolený věk`.
3. Ukázat graf funkcí příslušnosti.
4. Ukázat tabulku `Příslušnost pro zvolený věk`.
5. Posunout věk na několik příkladů.
6. Vysvětlit, proč se některé kategorie překrývají.
7. Ukázat použitou funkci příslušnosti a tabulku hodnot.

Stačí mluvit klidně a ukazovat hlavně to, co je na obrazovce vidět. Není potřeba vysvětlovat úplně celou teorii znovu, protože ta už je v prezentaci.

## Co říct při otevření aplikace

Můžeš říct:

> Tady je praktická část projektu. Aplikace ukazuje navržené fuzzy věkové množiny. Nahoře si zvolím konkrétní věk a aplikace mi hned vypočítá, jak moc tento věk patří do kategorií malí, mladí, střední, starší, staří a nejstarší.

Potom ukaž na dvě hlavní části:

- vlevo je graf funkcí příslušnosti,
- vpravo je tabulka příslušností pro právě zvolený věk.

Můžeš pokračovat:

> Graf ukazuje průběh všech věkových kategorií od 0 do 100 let. Tabulka vpravo ukazuje přesné číselné hodnoty pro aktuálně vybraný věk.

## Co ukázat na posuvníku

Posuvník je hlavní interaktivní prvek aplikace. Říkej mu klidně:

- posuvník věku,
- vstupní hodnota,
- zvolený věk.

Věta k obhajobě:

> Posuvníkem měním vstupní hodnotu, tedy věk. Po každé změně se přepočítají všechny stupně příslušnosti a zároveň se aktualizuje graf i tabulka.

Dobré je nechat výchozí věk `35`, protože na něm je dobře vidět překryv kategorií `mladí` a `střední`.

## Ukázkový scénář s konkrétními věky

### Věk 10 let

Nastav věk na `10`.

Řekni:

> U věku 10 let je nejvyšší příslušnost do kategorie malí. To odpovídá tomu, že tento věk ještě spadá do dětského věku. Ostatní kategorie mají nulovou nebo velmi nízkou hodnotu.

Smysl ukázky:

- ukázat kategorii, která je jasná,
- vysvětlit hodnotu blízko `1`.

### Věk 15 let

Nastav věk na `15`.

Řekni:

> U věku 15 let už je vidět přechod. Člověk už nemusí být plně v kategorii malí, ale zároveň začíná částečně patřit do kategorie mladí. Tady je právě vidět výhoda fuzzy přístupu, protože výsledek není jen ano nebo ne.

Smysl ukázky:

- ukázat první plynulý přechod,
- zdůraznit částečnou příslušnost.

### Věk 25 let

Nastav věk na `25`.

Řekni:

> U 25 let je kategorie mladí v oblasti plné příslušnosti. To znamená, že podle navrženého modelu tento věk odpovídá pojmu mladý velmi dobře, tedy hodnota je rovna jedné.

Smysl ukázky:

- ukázat plnou příslušnost,
- vysvětlit rovnou horní část lichoběžníku.

### Věk 35 let

Nastav věk na `35`.

Řekni:

> Tohle je nejdůležitější příklad. Věk 35 let neleží čistě v jedné kategorii. Podle modelu je ještě částečně mladý a současně už částečně střední. Proto mají dvě sousední fuzzy množiny nenulovou hodnotu.

Pokračuj:

> To neznamená pravděpodobnost. Neříkám, že člověk má 42 procent šanci být mladý. Říkám, že věk 35 let odpovídá pojmu mladý se stupněm příslušnosti přibližně 0,42.

Smysl ukázky:

- nejlépe vysvětlit princip fuzzy množin,
- ukázat překryv dvou kategorií,
- odlišit fuzzy hodnotu od pravděpodobnosti.

### Věk 60 let

Nastav věk na `60`.

Řekni:

> U věku 60 let už model přechází ze středního věku do kategorie starší. Podle nastavených hranic může být tento věk ještě na konci střední kategorie, ale zároveň už silně patří do kategorie starší.

Smysl ukázky:

- ukázat další překryv ve vyšším věku,
- ukázat, že stejný princip funguje pro všechny kategorie.

### Věk 85 let

Nastav věk na `85`.

Řekni:

> U věku 85 let je vidět přechod mezi kategoriemi staří a nejstarší. Opět to není ostrá hranice. Model vyjadřuje, že takový věk může být ještě částečně ve skupině staří, ale zároveň už patří i do skupiny nejstarší.

Smysl ukázky:

- ukázat konec škály,
- připomenout, že model pokrývá věk od 0 do 100 let.

## Co říct u grafu

U grafu používej tyto pojmy:

- vodorovná osa = věk,
- svislá osa = stupeň příslušnosti `μ`,
- barevná křivka = jedna fuzzy množina,
- čárkovaná svislá linka = aktuálně zvolený věk,
- bod na křivce = hodnota příslušnosti pro zvolený věk.

Věty k obhajobě:

> Na vodorovné ose je věk od 0 do 100 let. Na svislé ose je stupeň příslušnosti od 0 do 1.

> Každá barevná křivka představuje jednu věkovou kategorii. Červená je malí, oranžová mladí, zelená střední, modrozelená starší, fialová staří a vínová nejstarší.

> Čárkovaná linka ukazuje aktuálně zvolený věk. Body na křivkách ukazují, jakou hodnotu příslušnosti má tento věk v jednotlivých kategoriích.

> Překryvy mezi křivkami jsou záměrné. Díky nim může jeden věk patřit částečně do více kategorií současně.

## Co říct u tabulky vpravo

Tabulka `Příslušnost pro zvolený věk` je přesné číselné vyjádření toho, co je v grafu vidět.

Věty k obhajobě:

> V tabulce vpravo jsou přesné hodnoty pro aktuální věk. Graf je názorný, tabulka je přesná.

> Když má nějaká kategorie hodnotu 0, znamená to, že do ní daný věk podle modelu nepatří. Když má hodnotu 1, znamená to plnou příslušnost. Hodnoty mezi tím znamenají částečnou příslušnost.

> U věku 35 let je dobře vidět, že hodnota není jen u jedné kategorie. To je hlavní rozdíl proti klasickému ostrému rozdělení.

## Co říct u použité funkce příslušnosti

Sekce `Použitá funkce příslušnosti` vysvětluje lichoběžníkovou funkci.

Věty k obhajobě:

> Pro všechny věkové kategorie používám lichoběžníkovou funkci příslušnosti. Ta má náběh, oblast plné příslušnosti a pokles.

> Mimo interval je hodnota 0. V náběhu roste z 0 na 1. Uprostřed je rovna 1. A na konci zase klesá z 1 na 0.

> Tento tvar jsem zvolil proto, že je jednoduchý, přehledný a dobře se vysvětluje.

## Co říct u tabulky hodnot po 5 letech

Tabulka po 5 letech slouží jako splnění tabulkové části zadání.

Věty k obhajobě:

> Dole je tabulka hodnot po pěti letech. Ta ukazuje stejné informace jako graf, ale v číselné podobě.

> Tím je splněna i tabulková část zadání. Pro každý vybraný věk je vidět příslušnost ke všem šesti kategoriím.

> Tabulka je vhodná pro kontrolu konkrétních hodnot, zatímco graf je vhodnější pro celkový přehled.

## Krátká verze ukázky na 2 minuty

Když nebude moc času, řekni jen toto:

> Tohle je moje webová aplikace k projektu. Posuvníkem nastavím věk a aplikace vypočítá, jak moc tento věk patří do jednotlivých věkových kategorií.

> Vlevo je graf funkcí příslušnosti. Vodorovná osa je věk, svislá osa je hodnota μ od 0 do 1. Každá barva je jedna věková fuzzy množina.

> Vpravo je tabulka přesných hodnot pro zvolený věk. Například u 35 let je vidět, že věk patří částečně do kategorie mladí a částečně do kategorie střední.

> To je hlavní princip fuzzy logiky: místo ostré hranice ano nebo ne používám plynulou míru příslušnosti.

> Dole je ještě vzorec použité lichoběžníkové funkce a tabulka hodnot po pěti letech, takže výsledek je zobrazen graficky i tabulkově.

## Delší verze ukázky na 5 minut

Když bude čas na delší demo, drž se tohoto pořadí:

1. Ukaž výchozí věk 35.
2. Vysvětli graf a tabulku.
3. Posuň věk na 10 a ukaž plnou příslušnost do `malí`.
4. Posuň věk na 15 a ukaž přechod mezi `malí` a `mladí`.
5. Posuň věk na 25 a ukaž plnou příslušnost do `mladí`.
6. Posuň věk zpět na 35 a vysvětli překryv `mladí` a `střední`.
7. Posuň věk na 60 a ukaž přechod do `starší`.
8. Posuň věk na 85 a ukaž přechod do `nejstarší`.
9. Ukaž vzorec lichoběžníkové funkce.
10. Ukaž tabulku hodnot po 5 letech.

Závěrečná věta:

> Tím aplikace ukazuje obě požadované části zadání: grafické zobrazení i tabulku hodnot. Zároveň na konkrétních věcích ukazuje, proč je fuzzy přístup vhodný pro vágní pojmy.

## Wiki pojmů a vysvětlivky

### Fuzzy logika

Fuzzy logika je přístup, který nepracuje jen s hodnotami `pravda` a `nepravda`, ale umožňuje i něco mezi tím.

Jak to říct:

> Fuzzy logika se hodí tam, kde pracujeme s neostrými pojmy. Například mladý, starý, vysoký, nízký, rychlý nebo pomalý.

### Fuzzy množina

Fuzzy množina je množina, do které prvek nemusí patřit jen úplně, nebo vůbec. Může do ní patřit částečně.

Jak to říct:

> Fuzzy množina neurčuje jen ano nebo ne, ale říká, jak moc prvek do množiny patří.

Příklad:

- věk 25 let patří do množiny `mladí` skoro nebo úplně,
- věk 35 let patří do množiny `mladí` už jen částečně,
- věk 70 let do množiny `mladí` nepatří.

### Stupeň příslušnosti

Stupeň příslušnosti je číslo od `0` do `1`.

- `0` = vůbec nepatří,
- `1` = patří plně,
- `0,5` = patří částečně.

Jak to říct:

> Stupeň příslušnosti vyjadřuje, jak moc daný věk odpovídá dané kategorii.

### Značka μ

Značka `μ` je řecké písmeno mí. Čte se jako `mí`.

Jak to říct:

> Na svislé ose je μ, čte se mí, a znamená stupeň příslušnosti.

Není potřeba říkat "mikro". V tomto kontextu je to řecké písmeno pro funkci příslušnosti.

### μ(x)

Zápis `μ(x)` znamená funkci příslušnosti pro konkrétní hodnotu `x`.

V tomto projektu:

- `x` je věk,
- `μ(x)` je příslušnost tohoto věku do konkrétní věkové kategorie.

Jak to říct:

> Když dosadím věk do funkce příslušnosti, dostanu hodnotu μ(x), tedy jak moc tento věk patří do dané fuzzy množiny.

### Univerzum

Univerzum je rozsah všech hodnot, se kterými pracujeme. V tomto projektu je univerzum věk od `0` do `100` let.

Jak to říct:

> Univerzum je celý rozsah hodnot, které model řeší. Tady je to věk od 0 do 100 let.

### Lingvistická proměnná

Lingvistická proměnná je proměnná popsaná slovy. Tady je lingvistická proměnná `věk`.

Její jazykové hodnoty jsou:

- malí,
- mladí,
- střední,
- starší,
- staří,
- nejstarší.

Jak to říct:

> Věk beru jako lingvistickou proměnnou, protože ho nepopisuji jen číslem, ale i slovními kategoriemi.

### Jazyková hodnota

Jazyková hodnota je konkrétní slovní kategorie lingvistické proměnné.

Příklad:

- `mladí` je jazyková hodnota proměnné věk,
- `staří` je další jazyková hodnota proměnné věk.

Jak to říct:

> Jednotlivé věkové typy jsou jazykové hodnoty, tedy slovní označení pro různé části věku.

### Funkce příslušnosti

Funkce příslušnosti je funkce, která pro každou hodnotu věku vrátí číslo od `0` do `1`.

Jak to říct:

> Funkce příslušnosti určuje, jak se mění příslušnost s věkem.

Příklad:

- u kategorie `mladí` hodnota nejdřív roste,
- potom je rovna `1`,
- potom zase klesá.

### Lichoběžníková funkce

Lichoběžníková funkce má tvar lichoběžníku:

- nejdřív roste,
- potom je nahoře rovná,
- potom klesá.

Jak to říct:

> Lichoběžníková funkce je jednoduchý tvar funkce příslušnosti. Má náběh, plnou oblast a pokles.

### Parametry a, b, c, d

Parametry `a`, `b`, `c`, `d` určují tvar lichoběžníkové funkce.

- `a` = začátek náběhu,
- `b` = začátek plné příslušnosti,
- `c` = konec plné příslušnosti,
- `d` = konec poklesu.

Jak to říct:

> Parametry a, b, c a d určují, odkud kategorie začíná, kde je plná a kde končí.

### Náběh

Náběh je část funkce, kde hodnota roste z `0` na `1`.

Jak to říct:

> Náběh znamená, že věk do kategorie začíná postupně patřit.

### Plná příslušnost

Plná příslušnost znamená hodnotu `1`.

Jak to říct:

> Plná příslušnost znamená, že daný věk dané kategorii odpovídá úplně podle navrženého modelu.

### Pokles

Pokles je část funkce, kde hodnota klesá z `1` na `0`.

Jak to říct:

> Pokles znamená, že věk z dané kategorie postupně odchází.

### Překryv fuzzy množin

Překryv znamená, že dvě sousední kategorie mají pro stejný věk nenulovou hodnotu.

Jak to říct:

> Překryv je záměrný, protože věkové pojmy se v běžném jazyce také překrývají.

Příklad:

> Věk 35 let může být částečně mladý a částečně střední.

### Ostrá množina

Ostrá množina je klasická množina, kde prvek buď patří, nebo nepatří.

Jak to říct:

> Ostrá množina pracuje jen s hodnotami 0 a 1. Fuzzy množina umožňuje i mezihodnoty.

### Ostrá hranice

Ostrá hranice je pevně daný předěl.

Příklad:

> Do 30 let mladý, od 31 let už ne.

Jak to říct:

> Ostrá hranice je u věku nepřirozená, protože člověk se ze dne na den nezmění do jiné kategorie.

### Vágní pojem

Vágní pojem je slovo, které nemá přesnou hranici.

Příklady:

- mladý,
- starý,
- vysoký,
- nízký,
- teplý,
- drahý.

Jak to říct:

> Vágní pojem je pojem, který lidé běžně používají, ale nejde ho přesně ohraničit jedním číslem.

### Pravděpodobnost vs. příslušnost

Tohle je důležité nezaměnit.

Fuzzy příslušnost není pravděpodobnost.

Špatně:

> Člověk má 42 procent šanci být mladý.

Správně:

> Věk 35 let odpovídá pojmu mladý se stupněm příslušnosti 0,42.

Jak to říct:

> Fuzzy hodnota neříká šanci, ale míru vhodnosti daného označení.

### Defuzzifikace

Defuzzifikace znamená převod fuzzy výsledku zpět na jednu ostrou hodnotu.

V tomto projektu se defuzzifikace nepoužívá.

Jak to říct, pokud se někdo zeptá:

> Defuzzifikaci tady nepotřebuji, protože cílem není vybrat jednu výslednou kategorii. Cílem je zobrazit příslušnosti ke všem věkovým kategoriím.

## Časté otázky při ukázce aplikace

### Proč se hodnoty nesčítají na 1?

Protože to nejsou pravděpodobnosti. Každá fuzzy množina má vlastní funkci příslušnosti.

Odpověď:

> Hodnoty se nemusí sčítat na 1, protože nejde o pravděpodobnostní rozdělení. Každá hodnota samostatně říká, jak moc věk odpovídá jedné kategorii.

### Proč jsou hranice právě takové?

Odpověď:

> Hranice jsem zvolil jako rozumný model běžného vnímání věku. Nejsou jediné možné, ale jsou vysvětlitelné a vytvářejí plynulé přechody.

### Proč používám věk do 100 let?

Odpověď:

> Je to prakticky zvolený rozsah pro ukázku. Pokrývá běžný lidský věk a dobře se zobrazuje v grafu.

### Proč lichoběžník, a ne jiná funkce?

Odpověď:

> Lichoběžníková funkce je jednoduchá, přehledná a pro tento korespondenční úkol dostačující. Dobře ukazuje náběh, plnou příslušnost i pokles.

### Co je hlavní výsledek aplikace?

Odpověď:

> Hlavní výsledek je interaktivní tabulka a graf, které ukazují příslušnost zvoleného věku ke všem šesti fuzzy věkovým kategoriím.

## Věty, kterým se raději vyhnout

Neříkej:

> Je to pravděpodobnost, že člověk je mladý.

Raději řekni:

> Je to stupeň příslušnosti k pojmu mladý.

Neříkej:

> Kategorie jsou přesně dané pro všechny lidi.

Raději řekni:

> Kategorie jsou model běžného vnímání věku a daly by se podle kontextu upravit.

Neříkej:

> Věk patří jen do jedné kategorie.

Raději řekni:

> Jeden věk může mít nenulovou příslušnost do více kategorií současně.

## Krátký tahák před obhajobou

- `μ` se čte `mí`.
- `μ(x)` znamená stupeň příslušnosti.
- Hodnota `0` znamená vůbec ne.
- Hodnota `1` znamená plně.
- Hodnota mezi `0` a `1` znamená částečně.
- Fuzzy hodnota není pravděpodobnost.
- Překryvy kategorií jsou záměrné.
- Lichoběžník má náběh, plnou oblast a pokles.
- Aplikace splňuje grafické i tabulkové zobrazení zadání.
- Nejlepší příklad k vysvětlení je věk `35 let`.
