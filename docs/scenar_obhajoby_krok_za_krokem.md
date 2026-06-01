# Scénář obhajoby krok za krokem

## 1. Úvod

Vybral jsem si korespondenční úkol ze skript na straně 31. Zadání je popsat pomocí fuzzy množin základní věkové rozdělení: malí, mladí, střední, starší, staří a nejstarší. Výsledek má být zobrazen tabulkou i graficky.

## 2. Proč jsem zvolil fuzzy množiny

Věkové kategorie nejsou ostré. Člověk se nestane ze dne na den z mladého člověka člověkem středního věku. Proto je vhodné použít fuzzy množiny, kde má věk stupeň příslušnosti v intervalu od 0 do 1.

## 3. Vysvětlení stupně příslušnosti

Stupeň příslušnosti `μ(x)` říká, jak moc daný věk patří do určité kategorie.

```text
0 = nepatří
1 = patří plně
0,5 = patří částečně
```

## 4. Vysvětlení kategorií

Použil jsem šest fuzzy množin: malí, mladí, střední, starší, staří a nejstarší. Každá množina má lichoběžníkovou funkci příslušnosti. To znamená, že nejprve roste, potom má oblast plné příslušnosti a nakonec klesá.

## 5. Ukázka grafu

Otevřu soubor `index.html`. V grafu jsou vidět všechny funkce příslušnosti. Na ose x je věk od 0 do 100 let. Na ose y je stupeň příslušnosti od 0 do 1.

## 6. Ukázka posuvníku

Posunu věk například na 35 let. Ukážu, že věk může mít nenulovou příslušnost k více kategoriím současně. Tím demonstruji hlavní výhodu fuzzy množin.

## 7. Ukázka tabulky

Dole je tabulka hodnot po 5 letech. Tím je splněna část zadání, která požaduje tabulkové zobrazení.

## 8. Shrnutí

Projekt splňuje zadání, protože obsahuje popis fuzzy množin, tabulku hodnot a grafické zobrazení. Výsledkem je jednoduchý model, který lépe odpovídá běžnému vnímání věku než ostré intervaly.
