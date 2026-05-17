Limity abstraktního a
fyzického počítání
Biologií inspirované počítače
Přednáška 4
Lukáš Sekanina
FIT VUT v Brně
2026
Motivace

    Jaké jsou fundamentální schopnosti a omezení

počítačů?

    Co to vůbec je počítání (computation)?
    Pokrývá koncept univerzálního Turingova stroje

podstatu libovolné z forem počítání?

    Anebo existují super-Turingovské výpočetní

stroje?

    Jaký je vztah mezi abstraktním počítáním a

fyzickým počítáním?

    Které fyzikální principy určující výpočetní meze

počítačů?

    Jaké jsou současné meze výkonnosti počítačů?

FIT VUT v Brně 3
Algoritmus

(viz kurz Základy programování)

    Algoritmus je přesně definovaná konečná posloupnost

příkazů (které jsou vybírány z předem definované
konečné množiny elementárních příkazů), jejichž
prováděním pro každé přípustné vstupní hodnoty
získáme po konečném počtu kroků odpovídající hodnoty
výstupní. Intuitivně algoritmem rozumíme postup, který
nás dovede k řešení úlohy.

https://www.cs.princeton.edu/~chazelle/courses/
BIB/BabbageEngine.html

    Fyzická implementace

algoritmu jako

    program pro univerzální procesor
    nebo
    speciální akcelerátor
    vytvořený jako ASIC, v FPGA, z
    Lega apod.

4

Nekonvenční počítače

a, Structure of the organism before finding the shortest path. Blue lines indicate
the shortest paths between two agar blocks containing nutrients: α1 (41 ± 1
mm); α2 (33 ±1 mm); β1 (44 ±1 mm); andβ 2 (45 ±1 mm). b, Four hours after
the setting of the agar blocks (AG), the dead ends of the plasmodium shrink and
the pseudopodia explore all possible connections. c, Four hours later, the
shortest path has been selected. Plasmodium wet weight, 90 ±10 mg. Yellow,
plasmodium; black, ‘walls’ of the maze; scale bar, 1 cm. d, Path selection.
Numbers indicate the frequency with which each pathway was selected. ‘None’,
no pseudopodia (tubes) were put out. SeeSupplementary Informationfor an
animated version of a–c.
Nakagaki, Yamada, Tóth: Maze-solving by an amoeboid organism. Nature
volume 407, page470 (2000)

Další výzkum:
HsuS. et al. A Physarum-inspired approach to the Euclidean Steiner tree
problem. ScientificReports, vol. 12, No: 14536 (2022)

    Physarumpolycephalum (PP, měňavkovitý prvok) je velká amébovitá
    buňka tvořená dendritickou sítí trubicovitých struktur (pseudopodií).
    Při plazení po hladkém agarovém gelu mění svůj tvar, a pokud je potrava
    umístěna na dvou různých místech, vysunuje pseudopodie, které spojují
    oba zdroje potravy.
    Tento jednoduchý organismus má schopnost najít cestu s minimální délkou
    mezi dvěma bodyv bludišti.
    (a) Celé bludiště na začátku experimentu pokryto kousky PP –vznikl jeden
    organismus; (b) Vytvořenímožných cest mezi body AG (zdroje potravy); (c)
    vzniká nejkratšícestamezi body AG

Počítá příroda?

    Živé organismy provádí akce, které můžeme chápat jako

počítání, např.

    amoeba najde nejkratší cestu
    tvorba 3D struktury proteinu podle genetické informace
    detekce a eliminace útočníka v imunitním systému
    vznik mnohobuněčného organismu z jedné buňky
    účelné kolektivní chování v koloniích hmyzu
    zpracování informace v mozku
    Pokud by se podařilo popsat abstraktní principy, které

určují toto „počítání“, mohlo by to vést k hlubšímu
pochopení biologie a popř. i ke konstrukci lepších
algoritmů/počítačů.
Problém nekonvenčních počítačů

    Uvažme, že „hmota“ dokáže řešit informatický problém.
        Jsme vždy schopni vysvětlit, jak to „hmota“ dělá?
        Pokud nemáme abstraktní model výpočtu „hmoty“, provádí „hmota“ vůbec
        výpočet?
    Co to je vůbec „výpočet “?
        Je nutně vázán na nějakou manipulaci se symboly?
        Provádí mozek výpočet?
    P. J. Denning: „Whatis computation?“ je jednou z otázek (podobně
    jako Co je to život? Jaké jsou základní síly ve fyzice? atd.),která nikdy
    nebude úplně zodpovězena, protože nové objevy a poznání vedou k
    stále novým otázkám.
    Tyto otázky (a případné odpovědi na ně) nespadajínutně do oblasti
    teoretické informatiky a výpočetní techniky.
    Na tytootázky se snaží odpovědět disciplíny, které zkoumají přesah
    informatiky(umělé inteligence) do filozofie.

Jaké jsou fundamentální schopnosti a limity
počítačů?

    Tradičně se odpovědí na tuto otázku zabývají disciplíny:
        Teorie automatů – zabývá se modely výpočtů.
        Teorie vyčíslitelnosti – zabývá se tím, které problémy mohou být
        principielně řešeny na počítačích.
        Teorie složitosti–zabývá se složitostí algoritmů.
    Jak vzniklo toto tradiční pojetí, které se standardně učí v

teoretické informatice již přes 50 let?

    Kladen důraz na algoritmy, jiné formy počítání nebyly důležité.
    Von Neumannův počítač a jeho realizace pomocí elektroniky.
    S rozvojem překladačů byla velmi důležitá teorie formálních jazyků.
    Tyto disciplíny ale nekladou otázky typu:
    Provádí příroda „výpočet“? V jakém smyslu?
    Jak souvisí abstraktní a fyzické počítání?
    Tyto otázky začínají být důležité až v poslední době.

Turingův stroj (TS)
opakování z kurzu TIN
Zopakujte si:
Jak provádí
TS výpočet?
Univerzální Turingův stroj a procesor

    Univerzální Turingův stroj může simulovat libovolný jiný

Turingův stroj.

    Prostřednictvím Turingova stroje je možné definovat pojem

algoritmus.

    Procesor s pamětí je v principu implementací univerzálního

Turingova stroje.
Nerozhodnutelné problémy

    Neexistuje TS (algoritmus), který problém rozhoduje.
    Příklady:
        Problém zastavení TS
        Určení algoritmické entropie
        Určení, zda se nelineární dynamický systém ustálí při dané
        počáteční podmínce
        atd.
    Existence nerozhodnutelných problémů ukazuje na meze

algoritmizace a meze formálních metod.
Další výpočetní modely výpočetně ekvivalentní TS

    registrový stroj (Random Access Machine)
    celulární automat (ne všechny!)
    Random Boolean Networks (RBN)
    parciálně rekurzivní funkce
    lambda kalkul
    nelineární diskrétní dynamický systém
    ...

Church-Turingova teze

    Church-Turingova teze: Turingovy stroje (a jim

ekvivalentní systémy) definují svou výpočetní silou
to, co intuitivně považujeme za efektivně
vyčíslitelné.

    Church-Turingova teze není dokazatelná (tj. nemůže být

vyvrácena), ale má se za to, že žádný fyzicky
realizovatelný výpočetní systém není výpočetně silnější
než Turingův stroj.

    termín „efektivně“ je problematický!!!
    Fyzická Church-Turingova teze: Libovolná funkce,

kterou je možné fyzicky vypočítat, může být
vypočtena pomocí Turingova stroje.
Super-turingovské výpočty (hypercomputing)

    Existuje zařízení, které má vyšší výpočetní sílu než

Turingův stroj?

    Abstraktní stroj: Není problém vytvořit výpočetní model, který má
    vyšší výpočetní sílu než TS (další slide).
    Fyzický stroj: zdá se nemožné, pokud bychom chtěli zachovat
    výpočetní scénář TS.

Super-turingovské výpočetní modely

    Akcelerující TS: Uvažme standardní TS, jehož krok výpočtu trvá polovinu času
    než ten předchozí. Potom je doba výpočtu:
    - T = 1 + ½+1/4 + 1/8 + ... = 2
    Nekonečně dlouho trvající výpočet je proveden v konečném čase.
    Akcelerující TS rozhodujeproblém zastavení standardního TS!
    Protože se v tomto případě však nejedná o „efektivní vyčíslitelnost“, akcelerující
    TS není relevantní pro Church-Turingovu tezi a nemůže ji porušit.
    První model „super-turingovského“ výpočtu navrhl již Turing ve své dizertační
    práci (1939). TS je vybaven schopností v jednom kroku odpovědět na dotaz
    (ano/ne), zda řetězec na pásce náleží do množiny, která může být obecně
    rekurzivně vyčíslitelná. Tento model se dnes nazývá TS s orákulem. Turing
    uvedl, že takový stroj není možné fyzicky sestrojit.
    Existují další modely super-turingovského výpočtu, např. neuronové sítě,
    jejichž váhy jsou reálná čísla (nevyčíslitelná).
    Obecně se super-turingovské výpočetní síly dosahuje trikem: redukcí doby
    trvání operace (nebo prostoru nutného k uchování dat) z nekonečné kvantity na
    konečnou kvantitu.
    I tyto super-turingovské systémy mají svoje výpočetní omezení (existuje pro ně
    „problém zastavení“).

Ještě jiný přístup k super-turingovským výpočtům

(Van Leeuwen & Wiedermann, 2000)

    Je možné simulovat reálně existující systémy jako je Internet, interaktivní řídicí
    systémy, biologické systémy atd. na standardním TS?
    Má se za to, že nelze, protože provádějí koncepčně jiný druh výpočtu.
    Připomeňme, jak počítá TS (tj. co rozumíme pojmem algoritmus):
        TS dostane celý vstup na pásku před započetím výpočtu (pak se vstup nesmí měnit),
        potom se TS spustí (za běhu se nesmí měnit přechodová funkce) a
        výsledek najdeme opět na pásce (pokud TS zastaví).
    Systémy uvedené v první odrážce však vykazují tyto vlastnosti:
        interagují během výpočtu s okolím,
        mění svoji funkci během výpočtu a
        neočekává se v některých případech, že výpočet skončí.
        Z prostředí tedy získávají obecně nevyčíslitelnou informaci
    Tyto vlastnosti jsou evidentně v rozporu s koncepcí výpočtu TS.
    Nejedná se však o porušení Church-Turingovy teze, protože koncept výpočtu je
    jiný než představuje TS –nejedná se o aplikaci konečně popsatelného algoritmu,
    který je „mechanicky“ aplikován na vstupní data.

Ještě jiný přístup k super-turingovským výpočtům

(Van Leeuwen & Wiedermann, 2000)

    Byl zformulovánnový výpočetní model tzv. „interaktivní Turingůvstroj s rádcem“
    (ITSR), který tyto výpočetní procesy postihuje (Van Leeuwen & Wiedermann, 2000).
    - Jedná se o standardní Turingůvstroj vybavený schopností v průběhu výpočtu číst a
    zapisovat data na speciální porty a možností získávat během výpočtu specializovanou
    obecně nevypočitatelnou informaci zvenčí. ITSR může běžet nekonečně dlouho.
    Může ITSR, když má větší výpočetní sílu než Turingův stroj, rozhodovat

nerozhodnutelné problémy?

    J. Wiedermannuvádí, že ano, ale pouze za určitých předpokladů, které v
    praxi nelze splnit. Nevypočitatelná informace, která je nutná pro řešení
    nerozhodnutelných problémů, by se musela z okolí do super-turingovského
    výpočetního systému nějak (prostřednictvím interakce nebo změny
    konfigurace) dostat. A to nejsme schopni zařídit pro ty nerozhodnutelné úlohy,
    které nás zajímají (viz Mařík et al.: Umělá inteligence V, Academia, 2007).

Abstraktní vs. fyzické stroje

    Fyzický svět, ve kterém žijeme, se zdá být (je?) konečný.
        Doba existence libovolného stroje je konečná.
        Zdrojů (tj. atomů...) je konečné množství.
        Rychlost světla je konečná.
        Energie je omezená.
    Což vymezuje třídu strojů, které je možné fyzicky vytvořit.
    Abychom mohli simulovat libovolný TS, univerzální TS

vyžaduje neomezeně velkou paměť.

    Skutečný univerzální TS nelze fyzicky realizovat.
        Výpočty s reálnými čísly jsou nutně jen aproximací.

Poznámky z fyziky

    Heisenbergův princip neurčitostiříká, že přesnost měření je v mikrosvětě omezena.
    Je nemožné přesně změřit polohu částice a její hybnost současně. Čím přesněji
    určíme jednu z veličin, tím méně toho víme o druhé. Součin neurčitosti v poloze (x) a
    neurčitosti v hybnosti (p) je tedy větší nebo roven určité konstantě. Stejně tak součin
    neurčitosti v energii a času opět nemůže být menší než daná konstanta. Po velmi
    krátkou dobu tak může nastat obrovská neurčitost ve velikosti energie.
    xp≥ ħ /2 a Et≥ ħ /
    Pozn: E, p, x označují standardní odchylku,t je časový interval měření.
    Vztah mezi energií a hmotou

E = mc^2

    Shannon-von Neumann-Landauerovaenergie nutná pro zpracování bitu informace

ESNL kBT ln 2

    Zpoždění tvodiče o délce L, po kterém je přenášena informace rychlostí světla c. r
    je permitivita dielektrika, které obklopuje vodič. Odpor a kapacita vodiče jsou zde
    zanedbány

Fyzikální konstanty:

    Rychlost světla c= 2.9979× 108 [m/s]
    Planckova redukovanákonst. ħ = 1.0545 × 10 −34[Js]
        ħ = h/ 2(kde hje Planckova konstanta)
    Boltzmannovakonstanta kB= 1.3805 × 10 −23[JK-^1 ]
    Hmotnost elektronu me= 9 , 1093826 × 10 -^31 [kg]

t = 𝜀𝑟𝐿/𝑐
Př. tenisák vselektron (Heisenbergův princip):
Zvolená Δv a dopočítaná neurčitost Δ x

Meze zvyšování hustoty integrace na čipu (1)

    Hranice pro zvyšování hustoty integrace je určena minimální energií,
    která je potřeba k přepnutí mezi logickou 0 a logickou 1. Budeme
    uvažovat tzv. nereverzibilní systémy(kam patří všechny současné
    technologie), u kterých je každý elementární výpočetní krok spojen s
    vyzářením energie. Odvození vychází z článku (Zhirnov et. al, 2003)
    V oblasti elektroniky je kladen důraz
        snižování času tnutného pro změnu stavu(tj. na maximalizaci pracovní
        frekvence)
        na hustotu integracen, tj. na počet elementárních přepínačů na jednotku
        plochy.
    Informační propustnost B je definována jako B = n/t. (maximální počet
    výpočetních elementů, které je možné přepnout za jednotku času).
    - Bdoposud roste exponenciálně v důsledku platnosti Moorova zákona.
    K přepnutí přepínače je třeba minimální energie Ebit
    Ebit ESNL, kde ESNL= kBT ln 2
    Ebit 0.017eV (pro T = 300 K)

Meze zvyšování hustoty integrace na čipu (2)

    Podle Heisenbergova princip neurčitosti platí:
    Minimální velikost přepínače, xmin, kterému k přepnutí stačí energie ESNL

je:

    kde meje hmotnost elektronu (pro odvození použito E = ½ mv^2 a p = mv).
    Toto minimum odpovídá maximální hustotě integrace
    Minimální doba přepnutí:
    Ztrátový výkon na jednotku plochy:

Pozn: výkonová hustota vlákna žárovky je 100 W/cm^2 a povrchu Slunce 6 kW/cm^2.

Meze zvyšování hustoty integrace na čipu (3)

    Snižováním velikosti přepínače roste potřeba odvádět teplo z čipu.
    Dennardscaling: Po desetiletí bylo možné zvyšovathustotu integrace

(zmenšovat tranzistory) a zvyšovatfrekvenci. Sníženímnapájecího
napětí byl zajištěn vesměs konstantní příkon(Pdyn= CfU^2 )

    Současnost:
        frekvenci nelze zvyšovat, nelze adekvátně snížit napájecí napětí,
        vícejádrovéprocesory
        běžící na nižším kmitočtu
        inteligentní řízení příkonu
    Fenomén: Darksilicon
        na čipu je mnoho
        tranzistorů, ale jen část
        může být současně
        využita, jinak čip shoří
    Komunikace je drahá
        FP ~ 20 pj, FX ~1pJ, read
        local mem~ 26 pJ, read
        DRAM~ 26 nJ(nVIDIA 28
        nm)

22

Reverzibilní počítání

    Běžná logická hradla nejsou reverzibilní obvody, tj.
    z výsledku není možné zrekonstruovat vstupní
    hodnoty (výjimka –hradlo NOT).
    Při výpočtu dochází ke ztrátě informace, zvýšení
    entropie a rozptýlení energie W = T S= kBT ln 2
    (ztráta energie na bit).
    - PostulovalLandauerv r. 1961
    - Experimentálněprokázáno v BerutA. et al., 2012
    Tato energie je zanedbatelná pro současné počítače
        Hradlo tvořené tranzistory rozptyluje cca 10^6 TkB[J].
        Mechanismus kopie DNA v lidské buňce rozptyluje cca
        100 TkB[J] nazkopírovanýbit (chemické vazby musí
        být porušeny a opět vytvořeny).
    Reverzibilita
        Logická–z výstupu je vždy možné zrekonstruovat
        vstupní hodnoty, tj. výpočetní systém realizuje
        bijektivní zobrazení.
        Fyzická–systém nerozptyluje žádnou energii, entropie
        se nemění. Výpočet s nulovou rozptýlenou energií
        nedovoluje Heisenbergův princip neurčitosti Et≥ ħ
    Landauerůvprincip (1961)–pro fyzicky reverzibilní
    výpočetní proces musí platit, že je logicky
    reverzibilní.
    Reverzibilní hradlomusí realizovat bijektivní
    zobrazení.
    Reverzibilní počítání umožňuje, aby minimální nutná
    disipace energie byla teoreticky nulová, ale skutečný
    fyzikální výpočet nikdy nemůže probíhat s přesně
    nulovou energií (kvůli neideálním vlastnostem
    součástek, šumu ...).

ztráta 1 bitu informace

Logicky reverzibilní hradlo:
a

b

Y1 = a

Y2 = a xor b

    Reverzibilní obvody
        Stejný počet vstupů a výstupů,
        bijektivní funkce
        „vysoké nároky“ na uchování
        informace
        „garbage“ vodiče
        čímpomalejšía bližší
        rovnovázevýpočet, tímmenší
        disipaceenergie.
        kvantovéobvody jsou
        reverzibilní
        praktickýzajímavé z pohledu:
        kryptografie a kvantového
        počítání

Příklady reverzibilních hradel a obvodů

Které z uvedených reverzibilních
hradel je univerzální?

Reverzibilní úplná 1b sčítačka( 4 vstupy, 4 výstupy)

součet

výstupní přenos

“ garbage ” vodi č

“ garbage ”vodič

“ garbage ”vodič
Shrnutí limitů pro výpočetní systémy

(zabývali jsme se jen některými)

MarkovI.L.: Limits on fundamental limitsto computation(NatureVol. 512, 2014)

Shrnutí

    „What is computation?“ – v odpovědi na tuto otázku není

mezi experty shoda!!!

    Meze abstraktního počítání určuje teoretická informatika.
    Meze praktického počítání určují fyzikální zákony.
        Z tohoto pohledu je největším problémem odvádění tepelné energie
        z výpočetního zařízení.
    Výpočetní systémy, které nesdílí výpočetní scénář

Turingova stroje, nejsou relevantní pro Church-Turingovu
tezi a tudíž ji neporušují.

    Pro některé systémy, jejichž chování je možné chápat jako

výpočetní proces, je klíčová fyzická realizace. Není zřejmé,
zda existuje abstraktní model vysvětlující jejich „výpočet“.
Literatura

    Mařík el al.: Umělá inteligence V, Academia, 2007
    Češka, M. et al. Teoretická informatika. Studijní materiál FIT VUT v Brně, 2006
    Lloyd, S.:Ultimate Physical Limits to Computation. Nature 406,2000, s. 1047 - 1054
    van Leeuwen, J., Wiedermann, J.: TheTuringMachineParadigmin Contemporary
    Computing. In: MathematicsUnlimited--2001 and Beyond. Springer, BerlinHeidelberg
    New York 2001, s. 1139- 1155
    Zhirnovet al.: Limitsto Binary LogicSwitchScaling–A GedankenModel. Proceedingof
    theIEEE, Vol. 91, No. 11, 2003, s. 1934- 1939
    BerutA.et al.: Experimental verification of Landauer’sprinciple linking information and
    thermodynamics. Nature Vol. 483, 2012, p. 187- 190
    Markov I.L.: Limits on fundamental limits to computation. Nature Vol. 512, 2014, p. 147-
    154
    Ubiquity Symposium: What is Computation?http://ubiquity.acm.org/symposia.cfm
    LigmajerF.: Myšlenky rychlé jako světlo: Fotony v neuromorfníma kvantovém počítání,
    Science & Technology Club, 2025
        doporučenáliteratura dleseznamu, který byl uveden na první přednášce.
