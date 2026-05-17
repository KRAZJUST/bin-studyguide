Kartézské genetické programování
Biologií inspirované počítače
Přednáška 3
Lukáš Sekanina
FIT VUT v Brně
2026

2

Genetické programování: Reprezentace problému

GP: synta ktický strom GE: gram atická evoluce

L ineární GP: symbolické instrukce

Cartesian GP: DAG

Source: HeuristicLab

(0, 2, 2 ) (0, 1, 0 ) (1, 3, 2 )(3, 2, 0 ) (5, 6, 3 ) (4, 6, 1 ) (5, 8)

3

Hlavní použití GP: Symbolická regrese

x y
1 0,
2 - 0,
3 0,
4 - 0,
5 - 0,
6 - 0,
7 - 0,
8 0,
9 - 0,
10 - 0,

𝑓 = ෍

𝑖= 1

𝐾= 10
|𝑦𝑖 −𝑤𝑖|

Požadovaná odezva

Odezva programu

Počet testovacích bodů

if 5 = 5 then𝑤=

2sin 𝑥
6

𝑐𝑜𝑠 𝑥−𝑥 else𝑤= 𝑥xor 2

= 5.

Eureqawww.nutonian.com
M Schmidt, H Lipson.: Distilling free-form natural laws from experimental data. Science, 2009
Since 2009 this technology is now used by more than 40,000 users including many Fortune-500 companies.
Kartézské genetické programování
Cartesian Genetic Programming (CGP)

    Vyvíjenood r. 1997, ale poprvéuceleně představeno v článku
        Miller, J., Thomson , P.: CartesianGeneticProgramming. In Proc. ofthird
        EuropeanConferenceon GeneticProgramming. LNCS 1802, Springer,
        2000, pp. 121- 132
    Podobný přístup však použit již dříve – zejména v oblasti evolučního

návrhu obvodů.

    Ve standardní formě CGP reprezentuje problém pomocí acyklického

orientovaného grafu(klasické GP používá stromy), který je zakódován
pomocí řetězce integerů o pevné délce.

    Uzly grafu jsou uspořádány ve 2D mřížce a představují jednoduché

funkce.

    Tato reprezentace je použita proto, že přibližněodpovídá struktuře

FPGA.

    CGP bude vysvětleno v úloze návrhu kombinačních obvodů.

Obdobným způsobem se ale použije např. pro symbolickou regresi atd.
Reprezentace problému v CGP

    nipočet vstupů
    nopočet výstupů
    v počet sloupců
    u počet řádků

ni

ni+

ni+u- 1

ni+u

ni+u+

ni+2u- 1

ni+(v-1)u

    napočet vstupů uzlu
     množina funkcí, gi
    L-back parametr

ni+uv- 1

u

v

0

1

ni- 1

ni no

a

b gi(a,b)

kód uzlu
Reprezentace problému v CGP: Příklad
Specifikace
(1b sčítačka)

fenotyp

genotyp

DefiniceCGP:

    početřádků,u
    početsloupců,v
    početvstupů,ni
    početvýstupů,no
    početvstupůuzlu,na
    L-backparametr,L
    množinafunkcí,
    Početfunkcív,nf

Příkladnaobrázku:

    u= 3
    v= 3
    ni= 3
    no= 2
    na= 2
    L= 3
    ={NAND ( 0 ),NOR ( 1 ),XOR( 2 ),AND( 3 ),
    OR( 4 ),NOT( 5 )}
    nf= 6

Reprezentace problému v CGP – L-back

    Vstup uzlu může být připojen k primárnímu vstupu nebo k výstupu

jiného uzlu, který se nachází v předchozích sloupcích. V rámci sloupce
je propojování zakázáno. Z pohledu číslicových obvodů tak mohou
vzniknout jen kombinační logické obvody.

    L-back parametrurčuje počet sloupců předcházejících j-tý sloupec, ze

kterých může být vybrán vstup pro uzel v j-tém sloupci (primární vstupy
jsou obvykle chápány jako výstupy „nultého“ sloupce).

    Pokud je L = 1, potom mohou být propojeny pouze sousední sloupce (to je
    výhodné pro zřetězenou HW implementaci).
    Pokud je L = max(počet sloupců), potom neexistuje omezení na propojení
    mezi sloupci.
    Pokud je L = max a počet řádků je 1, potom je povolena maximální možná
    konektivita.
    Parametr L tedy výrazně ovlivňuje množinu vytvořitelných grafů a velikost
    stavového prostoru.
    Primární vstup lze připojit na vstup libovolného uzlu.

Vytvoření fenotypu z genotypu

    Postupujeme ze strany výstupů obvodu a potom podle indexů uzlů (sestupně).
    Př. u = 3, v = 3, ni= 3, no= 2, na= 2, L = 3, = {NAND (0), NOR (1), XOR (2),
    AND (3), OR (4), NOT (5)}
    Chromozom: (1,2, 1 ) (1,2, 2 ) (0,1, 2 ) (4,2, 5 ) (5,4, 3 ) (4,0, 2 ) (7,1, 2 ) (1,6, 5 ) (1,1, 3 ) (8,9)

3

4

5

6

7

8

9

10

11

0

1

2

4 5 7 8 9 8 9

(animace)

Aktivní uzly–jsou zahrnuty ve fenotypu.
Neaktivní uzly–nejsou zahrnuty do fenotypu

Př. Fitness funkce v CGP

    Fitness hodnota: F = počet správně určených bitů na výstupu pro všechny
    zadanévstupníkombinace(max. 16 )
    Pokud dosáhne F maxima, je možné optimalizovat např. počet hradel

(popř. zpoždění apod.):
F’= F + N – U

    kdeNje celkový počet uzlů
    kdeUje počet použitých uzlů

Cílová tabulka
Nejčastěji používané mutace v CGP

mutace

    Pravděpodobnostní mutace: Mutuj každý gen s pravděpodobností pm.
    Bodová mutace: Náhodně vyber k integerů a nahraď je náhodně

generovanými (ale legálními) hodnotami. Př. na obrázku pro k= 1.
Mutace v CGP

    Mutací se může změnit funkce uzlu (změní-li se arita funkce uzlu, změní se i

struktura obvodu), připojení vstupu uzlu obvodu nebo připojení výstupu obvodu.

    Mutací se z aktivních uzlů mohou stát neaktivní uzly a z neaktivních uzlů

se mohou stát aktivní uzly. Mutace mají v CGP velký vliv na fenotyp.

    Mutace je neutrální, pokud nemá vliv na fitness. Což nastane, pokud:
        Aplikací mutace přejdeme od jednoho fenotypu k jinému, kdy oba mají stejnou
        fitness.
        Mutace je aplikována na neaktivní uzly, tj. fenotyp se nemění.
    I neutrální mutace z generace i mohou být někdy v budoucí generaci j

užitečné.

    Další druhy mutace, např. single –mutuje se tak dlouho, dokud se

nezmění alespoň jeden aktivní uzel.

    Křížení: Zavedeno několik způsobů křížení, ale (statisticky) neprokázána

významná užitečnost. Drtivá většina uživatelů používá pouze mutaci.
Vlastnosti kódování v CGP

    Délka genotypu G(počet genů):
        G = u.v.(na+ 1) +no
    Pro danou instanci CGP má genotyp pevnou velikost, fenotypy mají

proměnnou (avšak omezenou) velikost.

    Kódování způsobuje redundanci, protože:
        některé uzly nemusí být použity
        některé uzly nemusí využívat všechny vstupy (např. pokud je na=2 a uzel
        realizuje NOT)
        funkce určité skupiny uzlů může být nahrazena menším počtem uzlů (např.
        C = not (not A)) lze nahradit C = A)
        - Pozn. Problém genetického programování je tzv. bloat, kdy roste v čase velikost
        stromu (fenotypu), ale nepřispívá to ke zvýšení fitness hodnoty. Stromy
        obsahují výše uvedené „redundantní“ konstrukce.
    Vzniká neutralita: dva různé fenotypy jsou vzájemně neutrální, pokud

mají stejnou fitness hodnotu. Tento fakt pomáhá evoluci při hledání
řešení.

    Vliv pozice uzlu na jeho aktivitu: uzly umístěné blízko k primárním

vstupům budou aktivní s vyšší pravděpodobností než vzdálenější uzly.
Kódování problému způsobuje neutralitu

    Obrázek ukazuje, že různé fenotypy mohou získat stejnou fitness hodnotu.
    Zde se předpokládá, že fitness hodnota je počítána pouze na základě logické
    funkce, kterou realizuje fenotyp. Pokud bychom do fitness funkce zahrnuli i
    např. požadavek na minimalizaci příkonu, potom by obrázek vypadal jinak.

Pozn.
Zjednodušené
znázorněné
genotypů

Prohledávací algoritmus v CGP

Poznámka:

equal... neutrální mutace jsou podporovány!
Prohledávací algoritmus v CGP

    V oblasti evolučních strategií se tato varianta označuje jako ES(1 + ), což
    znamená, že populaci tvoří 1 + jedinců. Nová populace se tvoří tak, že se ze
    staré populace vybere jedinec s nejlepší hodnotou fitness a vloží se do nové
    populace spolu se svými potomky (je obvykle 4).
    V CGP je jedna důležitá změna: Pokud existuje více nejlepších jedinců se
    stejnou fitness hodnotou, použije se jako rodič ten, který nebylrodičem v
    předchozí generaci (viz obrázek). Tímto se zajišťuje genetická diverzita.
    Počáteční populace se generuje buď náhodně nebo s použitím již existujících
    řešení.

Vývoj fitness hodnot populace 5 jedinců.

Fitness 13
Fitness 06
Fitness 10
Fitness 11
Fitness 10

Fitness 13
Fitness 10
Fitness 09
Fitness 13
Fitness 13

Fitness 13
Fitness 10
Fitness 08
Fitness 15
Fitness 11

Příklad: Průběh evoluce

9 bitovásudá parita

ni=9, no=1, u =6, v =6, L=1, na=2, = {and, or, xor, identity}, = 4, 10000 generací; náhodně
vygenerovaná počáteční populace

Fmax=2^9 =512. Zlepšení nejlepší fitnesv populaci
Příklad: Průběh evoluce

Generace: 9392

Max. fitness: 320

Generace: 9400
Max. fitness: 512 (nalezeno řešení)

Příklad: Redukce počtu hradel (animace)
Circuit: Cordic(LGSynth93)
23 inputs, 2 outputs
Original: 106 gates
After optimization: 39 gates
(the best circuits discovered
during a CGP run are shown)
Jak je důležité míti neutrální mutace

    Úloha: Evoluční návrh 3b násobičky (Vassilev, Miller: ICES 2000)
    Na obrázku je normalizovaná fitness hodnota pro 100 nezávislých běhů (10 mil. generací).
    ON –viz algoritmus CGP
    OFF –jako nový rodič brán jedině ten, který má vyšší fitness hodnotu než stávající rodič

Příklad: evoluční návrh násobičky 4x3bity

    Zadání: Najděte pomocí CGP zapojení násobičky 4x3 bity s minimálním

počtem hradel. K dispozici je  = {AND, OR, XOR, propojka}.

    Přípravné kroky
        Reprezentace problému v CGP (Jak zjistit parametry CGP? Zkusmo.):
            uxv= 7 x 8 nebo 7 x 10 (zkusímedvěmožnosti)
            ni= 7 ,no= 7 ,na= 2 ,nf= 4
            L= 1 nebomaximum(zkusímedvěmožnosti)
            ={AND,OR,XOR,propojka}
        Evolučníalgoritmus
            = 4
            početgenerací= 20 miliónů
            1 mutacenachromozom
            početběhů 100 prokaždénastaveníexperimentu
        Fitnessfunkce–prvnívarianta(optimalizacefunkce)
            f=B,kdeBpočetsprávněvypočtenýchbitůprovšechnykombinacenavstupu.
            Početvstupníchkombinacíje 27.
            Řešenískvalitou 100 %máfitness=Bmax= 7 * 27.
        Fitnessfunkce–druhávarianta(optimalizacefunkceapočtuhradel)
            Stejně jako v předchozím případě, ale v okamžiku, kdy má kandidátní jedinec
            fitness hodnotu Bmax, je fitness funkce změněna na f = B + (u.v - z), kde z je
            počethradelpoužitýchvkandidátnímobvodě.

Pozn.: Bitově paralelní simulace

    Jak rychle ohodnotit kandidátní obvod? Uvažme příklad kandidátního obvodu, který má n
    = 4 vstupy, obsahuje tři hradla a realizuje funkci y = h(x1, x2, x3, x4). Dále uvažme, že
    cílem evoluce je najít chování popsané vektorem r, který vyjadřuje výstupní hodnotu pro
    všechny vstupní kombinace.
    Při běžné (naivní) simulaci bychom aplikovali 2ntestovacích vektorů, tj. procházeli
    obvodem 16krát. Doba simulace roste exponenciálně s rostoucím počtem vstupů.
    Při bitověparalelní simulaci využijeme toho, že např. v jazyce C existují bitové logické
    operátory. Pokud můžeme do proměnné typu integeruložit 16b vektor, potom můžeme
    všechny vstupní kombinace zakódovat pomocí vhodně zvoleného vstupu (viz x1, x2, x3,
    x4). V jednom průchodu obvodem získáme výsledek simulace y. Porovnáním y a r
    získáme fitness hodnotu. Urychlení je 16 oproti naivní simulaci.
    Protože běžně dostupné procesory pracují s 64b aritmetikou, můžeme v jednom
    průchodu vypočítat výsledek pro až 64 kombinací na vstupech.

Pro porovnání ještě dva příklady

    Kromě násobičky 4x3b budeme pomocí CGP hledat zapojení pro

obvod

    7 - vstupová řadicí síť–obvod, který seřadí 7bitový vstupní vektor
    7 - vstupová majorita (medián)
    Použijeme stejné nastavení experimentů jako v předchozím případě,

ale = {AND, OR}. Z literatury víme, že tyto obvody vystačí s těmito
funkcemi.

(a) Třívstupová řadicí síť a (b) její alternativní zakreslení.

Výsledky experimentů (násobička)

Jedno z nalezených zapojení násobičky 4x3 bity, které má zpoždění 7T a obsahuje 46 hradel
Použité funkce: AND (1), OR (2), XOR (3). Jedná se o nejlepší známé řešení.
Výsledky experimentů (řadicí síť)

Jedno z nejlepších nalezených zapojení 7b řadicí sítě
Použité funkce: AND (1), OR (2). Jedná se o nejlepší známé řešení.

Příklad rozložení elementů v matici

Alternativní schéma pomocí komparátorů. Řešení je obecné. Pokud nahradíme AND za MIN a OR za
MAX, bude tato řadicí síť řadit libovolné vstupy, ne pouze binární vektory.
Výsledky experimentů (medián)

Jedno z nejlepších nalezených zapojení 7b mediánu
Použité funkce: AND (1), OR (2)
Jedná se o nejlepší známé řešení.

Výsledky experimentů (násobička, 100 běhů)

Četnost výskytu násobičky s určitým počtem hradel pro 7x8 a 7x10 uzlů v CGP:
Zvýšení počtu uzlů obvykle vede na zajímavější řešení a zkrácení doby evolučního návrhu.

Výsledky experimentů (řadicí síť, 100 běhů)

Počet hradel nalezených řešení a četnost výskytu těchto řešení na struktuře 7 x 8 (vlevo) a 7x10
(vpravo). Modře L= 1, červeně L=max.
Výsledky experimentů (medián, 100 běhů)

Počet hradel nalezených řešení a četnost výskytu těchto řešení na struktuře 7 x 8 (vlevo) a 7x 10
(vpravo). Modře L= 1, červeně L=max.
Srovnání experimentů

Násobičku na struktuře 7x8při minimálním L-backparametru se nepodařilo do stanoveného
limitu dvaceti milionů generací vůbec nalézt.

Jelikož požadavek na malé zpoždění kombinačního obvodu a požadavek na malý počet hradel
jsou většinou vzájemně protichůdné, musí se v praxi zvolit jeden z požadavků jako prioritnější.
Komentář k předchozí tabulce

    Ve všech experimentech se podařilo získat buď lepší, nebo alespoň stejně dobré řešení
    jako dosud známé. V případě násobičky 4x3 bity se i přesto, že počet logických funkcí
    byl limitován pouze na tři, podařilo nalézt lepší řešení, než potřebuje konvenční návrh (tj.
    47 dvouvstupových hradel). Ostatní evolucí navržené obvody byly stejně složité jako
    nejlepší známé. V případě 7b řadicí sítě již nemůže být nalezeno lepší řešení, neboť bylo
    dokázáno, že se jedná o nejlepší řešení.
    Experimenty proběhly na dvou různých rozměrech matice a sice 7x8a 7x10. Dalším
    nastavovaným parametrem byl L-back, který nabýval minimální a maximální hodnoty.
    V tabulce 1 jsou shrnuty výsledky evolučního návrhu jednotlivých kombinačních obvodů
    pro matici rozměru 7x8. Tabulka 2 obsahuje stejné informace -avšak pro matici 7x10. Je
    možné si všimnout, že změnou L-backparametru na maximum, se zvýší úspěšnost
    nalezení řešení, sníží průměrný potřebný počet generací k nalezení řešení, zmenší
    minimální zpoždění a zmenší minimální počet elementů. Nyní by se mohlo zdát, že je
    ideální nastavit L-backna maximum, je však nutné podotknout, že vnitřní struktura
    řešení se pak často stává velmi komplikovanou a nelze ji již využít v zřetězeném
    provozu.

Problémy CGP

    Pokud pracujeme na úrovni hradel a ohodnocujeme ve fitness funkci

všechny vstupní kombinace, potom CGP je schopno vygenerovat
kvalitní řešení pro obvody do cca 15 vstupů –za předpokladu, že je
počáteční populace náhodně inicializována.

    V případě násobiček ale CGP běžně funguje jen pro max. 4b operandy

(tj. 8 vstupů a 8 výstupů)

    Pokud neohodnocujeme ve fitness funkci všechny vstupní kombinace,

často se nepodaří najít správně fungující obvod.

    S rostoucí složitostí cílového obvodu klesá počet běhů, které skončí

úspěšně.

    Další přednášky BIN: jak pomocí CGP navrhovat a optimalizovat

mnohem složitější obvody
Co dále najdeme o CGP v literatuře

    Analýza vlastností CGP
        vliv redundance, neutrality a četnosti mutací na rychlost evoluce a kvalitu
        řešení
        způsoby mutace
        CGP a křížení
        vysvětlení, proč nevzniká „bloat“
    Varianty CGP
        CGP s operacemi nad různými datovými typy
        CGP, ve kterém mohou vznikat moduly a kde je možné znovupoužití těchto
        modulů
        CGP s více chromozomy
        CGP s možností zpětné vazby
        CGP, které používá pro reprezentaci obvodu reálná čísla
        samomodifikujícíse CGP
        vícekriteriální CGP
    Aplikace
    SW a HWimplementaceCGP

Aplikace CGP

    návrh programů – symbolická

regrese, klasifikace ...

    návrh číslicových obvodů

(aproximativní obvody)

    návrh obrazových operátorů
    návrh kontrolérů pro roboty
    návrh NN a CNN
    development
    alife
    návrh kryptograficky důležitých

funkcí

    evoluční umění
    CGP v FPGA aj.

Literatura

    Miller, J., Thomson , P.: CartesianGeneticProgramming. In Proc. ofthirdEuropeanConferenceon
    GeneticProgramming. LNCS 1802, Springer, 2000, pp. 121- 132
    Miller, J., Job, D., Vassilev, V.: Principlesin theEvolutionaryDesign ofDigital Circuits-Part I. Genetic
    Programmingand EvolvableMachines. Vol. 1 No. 1, 2000
    VassilevV. K., Job D., Miller J.F.: TowardstheAutomaticDesign ofMore EfficientDigital Circuits. In
    Proc. ofthe2nd NASA/DOD Workshop on EvolvableHardware, IEEE Press, 2000, str. 151- 160
    Knuth, D.: TheArt ofComputerProgramming(2nd ed.), AddisonWesley, 1998
    Vašíček, Z., Sekanina, L.: Evoluční návrh kombinačních obvodů, In: Elektrorevue-
    http://www.elektrorevue.cz, roč. 2004, č. 43, Brno, CZ, s. 1-6, ISSN 1213- 1539
    Miller J. F.: Cartesian Genetic Programming, Springer Verlag, 2011
    Miller J.F.: Cartesian genetic programming: its status and future. Genetic programming and evolvable
    machines, Vol. 21, No. 1-2, pp. 129–168, 2020
