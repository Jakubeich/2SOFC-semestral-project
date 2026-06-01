# Text obhajoby na 15-20 minut

Tento text je napsaný jako mluvený scénář. Nemusí se číst úplně doslova, ale dá se podle něj obhajoba vést plynule. Časy jsou orientační.

## Slide 1: Fuzzy věkové rozdělení

Dobrý den, moje téma je fuzzy věkové rozdělení. Vybral jsem si korespondenční úkol ze skript, který se týká popisu běžných věkových kategorií pomocí fuzzy množin.

Zvolil jsem toto téma hlavně proto, že je dobře pochopitelné i bez složitého programování. Na rozdíl od evolučních algoritmů nebo neuronových sítí tady není hlavní částí projektu trénování algoritmu, ale návrh modelu, který převádí běžné lidské pojmy do matematické podoby.

V projektu řeším pojmy jako malí, mladí, střední, starší, staří a nejstarší. Tyto pojmy lidé běžně používají, ale nemají přesnou hranici. Například není úplně jasné, jestli je člověk ve 35 letech ještě mladý, nebo už patří do středního věku. Právě proto je vhodné použít fuzzy množiny, protože ty umožňují částečnou příslušnost do více kategorií současně.

Výstupem projektu je návrh fuzzy množin, tabulka hodnot a grafické zobrazení funkcí příslušnosti. Součástí je také jednoduchá webová stránka, kde si lze posuvníkem zvolit věk a vidět příslušnost do jednotlivých kategorií.

## Slide 2: Vybraný korespondenční úkol

Vybraný korespondenční úkol je ze skript na straně 31. Zadání říká, že máme popsat pomocí fuzzy množiny základní věkové rozdělení, které znají lidé. Konkrétně jde o věkové typy malí, mladí, střední, starší, staří a nejstarší. Zadání také požaduje zobrazení tabulkou i graficky.

To znamená, že cílem není pouze slovně říct, co je mladý nebo starý člověk. Je potřeba navrhnout konkrétní funkce příslušnosti. Tyto funkce musí pro každý věk říct, jak moc daný věk patří do určité kategorie.

Projekt jsem proto rozdělil na tři části. První část je teoretická, kde vysvětluji, co je fuzzy množina a proč je vhodná pro věkové kategorie. Druhá část je návrhová, kde definuji intervaly a funkce příslušnosti. Třetí část je praktická, kde je výsledek zobrazen v grafu a tabulce.

Tento úkol je podle mě vhodný pro zápočet, protože jasně ukazuje princip fuzzy logiky. Navíc je jednodušší na obhajobu, protože se dá vysvětlit na běžném příkladu z každodenního života.

## Slide 3: Proč se hodí fuzzy množiny

Hlavní důvod, proč jsem použil fuzzy množiny, je neostrost věkových kategorií. V klasické logice prvek do množiny buď patří, nebo nepatří. Tedy hodnota je jen 0 nebo 1.

U věku by ale takový přístup působil nepřirozeně. Kdybychom například řekli, že člověk je mladý do 30 let a od 31 let už mladý není, vznikla by ostrá hranice, která neodpovídá realitě. Člověk se přece ze dne na den nezmění z mladého člověka na člověka středního věku.

Fuzzy množiny tento problém řeší tak, že umožňují postupný přechod. Věk může do kategorie patřit částečně. Například člověk ve 35 letech může být ještě částečně mladý, ale zároveň už částečně střední. To odpovídá tomu, jak lidé o věku běžně přemýšlejí.

Na slidu je vidět rozdíl mezi ostrým a fuzzy rozdělením. Ostré rozdělení vytváří pevnou hranici. Fuzzy rozdělení pracuje s plynulým přechodem. Právě tento plynulý přechod je hlavní myšlenkou projektu.

## Slide 4: Stupeň příslušnosti μ(x)

Základním pojmem v projektu je stupeň příslušnosti. Označuje se řeckým písmenem mí, tedy μ(x). Hodnota μ(x) je vždy v intervalu od 0 do 1.

Když je μ(x) rovno 0, znamená to, že daný věk do určité kategorie vůbec nepatří. Když je μ(x) rovno 1, znamená to plnou příslušnost. Hodnoty mezi 0 a 1 znamenají částečnou příslušnost.

Například pokud by člověk ve věku 35 let měl příslušnost k množině mladí 0,42, znamená to, že podle zvoleného modelu do této kategorie patří jen částečně. Nejde o pravděpodobnost, ale o míru vhodnosti nebo míru příslušnosti k vágnímu pojmu.

To je důležité rozlišit. Fuzzy hodnota 0,42 neříká, že člověk má 42% šanci být mladý. Říká, že pojem mladý odpovídá věku 35 let se stupněm 0,42.

Tento princip se dá použít u mnoha běžných pojmů. Například vysoká teplota, malá rychlost, drahé zboží nebo velká vzdálenost. Všude tam, kde přirozený jazyk nepoužívá ostré hranice, může fuzzy přístup dávat smysl.

## Slide 5: Navržené věkové kategorie

Na tomto slidu je tabulka navržených věkových kategorií. Pro každou fuzzy množinu používám čtyři parametry: a, b, c a d.

Tyto parametry popisují lichoběžníkovou funkci příslušnosti. Parametr a označuje začátek náběhu. Od hodnoty a do hodnoty b příslušnost roste z 0 na 1. Mezi b a c je příslušnost rovna 1, tedy plná příslušnost. Od c do d potom příslušnost klesá zpět na 0.

Pro kategorii malí jsem zvolil interval 0, 0, 10, 16. To znamená, že dítě do 10 let plně patří do kategorie malí a potom příslušnost postupně klesá do 16 let.

Pro kategorii mladí jsem zvolil interval 12, 20, 28, 40. To znamená, že mladý věk začíná plynule kolem 12 let, plná příslušnost je přibližně mezi 20 a 28 lety a potom postupně klesá do 40 let.

Kategorie střední má interval 30, 42, 50, 60. To vytváří překryv s mladým věkem a zároveň i s kategorií starší. Kategorie starší má interval 50, 60, 67, 75. Kategorie staří má interval 65, 75, 82, 90. A kategorie nejstarší má interval 80, 90, 100, 100.

Tyto hranice nejsou jediným možným řešením. U fuzzy množin je návrh často závislý na interpretaci. Důležité je, aby byl návrh rozumný, vysvětlitelný a aby mezi kategoriemi byly plynulé přechody.

## Slide 6: Funkce příslušnosti

Pro všechny kategorie jsem použil lichoběžníkovou funkci příslušnosti. Zvolil jsem ji proto, že je jednoduchá, dobře se kreslí, dobře se vysvětluje a pro tento typ úkolu je dostačující.

Lichoběžníková funkce má tři hlavní části. První část je náběh, kde příslušnost roste z 0 na 1. Druhá část je plošina, kde je příslušnost rovna 1. Třetí část je pokles, kde se příslušnost snižuje z 1 zpět na 0.

Tento tvar je vhodný například pro kategorii mladí. Není rozumné říct, že člověk je plně mladý od přesného dne narozenin. Proto je tam náběh. Potom je období, kdy do kategorie mladí patří plně. A nakonec je pokles, kdy se postupně přesouvá směrem ke střednímu věku.

Parametry a, b, c a d tedy určují celý průběh funkce. Před hodnotou a je příslušnost nulová. Mezi a a b roste. Mezi b a c je plná. Mezi c a d klesá. Za hodnotou d je zase nulová.

Výhodou tohoto tvaru je jednoduchý výpočet. V rostoucí části lze stupeň příslušnosti spočítat lineárně jako poměr vzdáleností. Podobně v klesající části.

## Slide 7: Grafické zobrazení

Na tomto slidu je graf všech šesti funkcí příslušnosti. Na vodorovné ose je věk od 0 do 100 let. Na svislé ose je stupeň příslušnosti od 0 do 1.

Každá barva odpovídá jedné věkové kategorii. Červená je kategorie malí, oranžová mladí, zelená střední, modrozelená starší, fialová staří a vínová nejstarší.

Na grafu je dobře vidět, že jednotlivé kategorie se překrývají. To je záměr. Překryv znamená, že jeden věk může částečně patřit do dvou sousedních kategorií. Například kolem 35 let se překrývá mladý a střední věk. Kolem 70 let se zase překrývá starší a starý věk.

Svislá čárkovaná linka ukazuje konkrétní zvolený věk, v prezentaci je to 35 let. Body na křivkách ukazují, jakou příslušnost má tento věk do jednotlivých kategorií.

Tento graf splňuje část zadání, která požaduje grafické zobrazení. Současně slouží jako dobrá pomůcka při obhajobě, protože na něm lze názorně ukázat hlavní rozdíl mezi ostrým a fuzzy popisem.

## Slide 8: Příklad, věk 35 let

Teď ukážu konkrétní výpočet na věku 35 let. Pro kategorii střední jsem zvolil parametry a rovno 30, b rovno 42, c rovno 50 a d rovno 60.

Věk 35 leží mezi hodnotami a a b. To znamená, že se nachází v rostoucí části funkce. V této části se příslušnost počítá jako rozdíl věku a začátku intervalu dělený délkou náběhu.

Konkrétně:

μ(35) = (35 - 30) / (42 - 30)

To je 5 / 12, což je přibližně 0,42.

Výsledek tedy říká, že člověk ve věku 35 let patří do kategorie střední se stupněm příslušnosti přibližně 0,42.

Současně podle navržené množiny mladí vychází pro věk 35 také přibližně 0,42. To znamená, že model tento věk vyhodnocuje jako přechod mezi mladým a středním věkem.

Právě to je podle mě dobrý příklad smyslu fuzzy logiky. Nemusíme člověka zařadit do jediné kategorie. Můžeme říct, že patří do více kategorií současně, ale s různou mírou.

## Slide 9: Jak výsledek interpretovat

Výsledek projektu se neinterpretuje jako jedna pevná kategorie. Neříkáme tedy automaticky: tento člověk je mladý a nic jiného. Místo toho získáme několik hodnot příslušnosti.

Například pro 15 let může mít člověk příslušnost k množině malí 0,17 a k množině mladí 0,38. To odpovídá tomu, že 15 let je přechod mezi dítětem a mladým člověkem.

Pro 35 let vychází příslušnost k mladým i středním přibližně 0,42. Tím model ukazuje přechod mezi těmito dvěma pojmy.

Pro 85 let může být příslušnost k množině staří 0,63 a k množině nejstarší 0,50. Opět jde o přechod, tentokrát mezi starým a nejstarším věkem.

Důležité je, že fuzzy model není absolutní pravda. Je to zjednodušený matematický popis vágních pojmů. Někdo by mohl navrhnout hranice trochu jinak. To ale nevadí, protože cílem projektu je ukázat princip, ne vytvořit jedinou správnou definici věku.

Výhodou je, že model je přehledný a snadno upravitelný. Pokud bychom chtěli použít jiné kulturní, zdravotní nebo sociální hledisko, stačilo by změnit intervaly jednotlivých množin.

## Slide 10: Závěr obhajoby

Na závěr shrnu, co projekt obsahuje a proč splňuje zadání. Zadání požadovalo popsat věkové typy pomocí fuzzy množin a zobrazit výsledek tabulkou i graficky.

V projektu jsem navrhl šest fuzzy množin: malí, mladí, střední, starší, staří a nejstarší. Pro každou množinu jsem určil parametry lichoběžníkové funkce příslušnosti. Tyto parametry jsou uvedeny v tabulce.

Dále jsem vytvořil graf, který ukazuje průběh všech funkcí příslušnosti. Graf názorně ukazuje překryvy mezi kategoriemi a plynulé přechody.

Součástí projektu je také jednoduchá webová stránka, kde lze posuvníkem měnit věk a sledovat hodnoty příslušnosti v tabulce. To pomáhá prakticky ukázat, jak se fuzzy množiny chovají.

Hlavní myšlenka projektu je, že fuzzy logika umožňuje matematicky popsat pojmy, které jsou v běžném jazyce neostré. Věk je pro to vhodný příklad, protože hranice mezi kategoriemi jako mladý, střední nebo starý nejsou přesné.

Projekt tedy ukazuje rozdíl mezi ostrým a fuzzy popisem. Ostrý popis používá pevné hranice. Fuzzy popis používá stupně příslušnosti a plynulé přechody. Díky tomu lépe odpovídá běžnému lidskému uvažování.

Tím bych obhajobu uzavřel. Pokud by bylo potřeba projekt rozšířit, šlo by například přidat porovnání s trojúhelníkovými funkcemi, umožnit uživateli měnit hranice kategorií nebo použít fuzzy pravidla pro nějaké konkrétní doporučení, například v oblasti zdravotní prevence nebo sportovní aktivity podle věku.

## Krátká rezerva pro otázky

Kdyby se vyučující zeptal, jestli jsou zvolené hranice jediné správné, odpověď je, že nejsou. U fuzzy množin často záleží na kontextu a subjektivní interpretaci. Důležité je, že zvolené hranice dávají smysl a vytvářejí plynulé přechody.

Kdyby se zeptal, proč jsem použil lichoběžníkové funkce, odpověď je, že jsou jednoduché, přehledné a pro tento příklad dobře vysvětlitelné. Mají náběh, oblast plné příslušnosti a pokles.

Kdyby se zeptal, jaký je rozdíl mezi fuzzy hodnotou a pravděpodobností, odpověď je, že fuzzy hodnota není pravděpodobnost. Neříká, s jakou šancí je člověk mladý. Říká, jak moc daný věk odpovídá pojmu mladý.
