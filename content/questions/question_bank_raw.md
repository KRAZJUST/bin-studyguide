Prvý termín 2023/

1. Moorovo okoli, co to znamena. Bylova smycka - kolika stavu muze nabyvat. Pokud ma nejaka
**bunka vsude v okoli 0, jaky bude jeji dalsi stav.

    Konvolucni a FF site, pocitani parametru a nasobeni + nakreslit MAC prvek.
    Priklad SAT DNA pocitani + pseudokod
    Definice x dominuje y (mas dve fitness f_1 a f_2). Dva zpusoby jak delat multikriterialni**
    **optimalizaci.
    Pseudokod evoluce CNN + proc pouzivat prediktor fitness a jake jsou jeho vstupy
    Pojmy z entropie + vypocitat pravdepodobnost nejakeho makrostavu.
    RNG otazky**
    a. Kde probiha pri synteticke biologii vypocet? Čím se zde udava logicka 1 nebo 0.
    Prvý termín 2021/
    1)a) MAC - rozkresliť implementáciu MAC pomocou násobičky, sčítačky a registrov. Odkiaľ (z ktorej časti
    neurónovej siete) získava MAC vstupné hodnoty?
    b) Za ako dlho sa vybije batéria o kapacite 2 Wh použitá v HW akcelerátore inference CNN, ktorý pracuje ako
    klasifikátor obrázkov z video streamu (20 frames/s), vykoná 200*10^9 operácií na jednu inferenciu a energia
    potrebná na jednu operáciu je 0,2 pJ?
    c) Ktorá časť výpočtu CNN na ASIC akcelerátore spotrebováva najviac energie?

    Pareto fronta , obe fitness P a A maximalizujeme - a) uviesť, ktoré riešenia dominuje daný bod, b) vypísať
    paretovu frontu, c) Čo by pribudlo do paretovej fronty, ak by sme nebrali kritérium C1, d) zapísať x#y
    (kandidátne riešenie x dominuje riešenie y)
    SAT solver
    a) Dokresliť (dopredu aj dozadu)
    b) Obvod z a) je prevedený pomocou Tseitinovy transformace, ak vráti YES, čo to znamená pre vzťah
    medzi A a B
    A a B nie sú ekvivalentné
    c) Fitness F pre evolučnú minimalizáciu počtu hradiel už plne funkčného obvodu c , v ktorom sa vykonáva
    vyššie uvedený test na funkčnú ekvivalenciu
    F(a) =? pocet hradiel v “a” ak su ekv., Inak FITNESS_MAX
    Podle mě by to mělo být F = F + N - U, kde F je původní fitness, N je počet hradel a U je počet
    využitých hradel

    CGP - implementácia mediánu pre 7 vstupov. Vstupy aj výstupy sú 8 bitové. Množina G dvojvstupových 8
    bitových elementárnych funkcií, každá vracia jednu 8 bitovú hodnotu.
    a) Aký je počet vstupov a výstupov CGP 7 vstupov 1 vystup
    b) G = { AND, OR }
    c) Dĺžka chromozónu pre 15 riadkov a 4 stĺpcov 60 * (1 + 2) + 1 = 181
    d) Navrhnúť fitness F, napísať či maximalizujeme alebo minimalizujeme maximalizujeme pocet spravne
    urcenych bitov medzi vystupom a ocakavnym vystupom
    CA - Bylova smyčka
    a) Prečo sa študujú takéto smyčky?
    b) Je uvedený CA 1D, 2D alebo 3D?
    c) V koľkých stavoch môže byť bunka pre 1D CA 2 nie? 0 a 1
    d) Čo je to 5-susedstvo, nakresliť nova hodota bunky i sa rata podla jej 5tich susedov po vsetkych
    stranach -> i-5, i-4, i-3, i-2, i-1, i, i+1, i+2, i+3, i+4, i+
    Nemalo by to susedstvo byť len i-2, i-1, i, i + 1, i+2 podľa tohto?
    Podle tohohle mi to nepřijde, ale možná tam má chybu, idk
    e) Bunka je v “0”, všetci jej susedia sú “0”, aký bude nový stav? Ak je F = XOR tak 0
    f) Koľko riadkov bude mať lokálna prechodová funkcia v najhoršom prípade
    6)a) Boltzmanova entropia sa v štatistickej fyzike vypočíta ako S = kB ln W. Čo je to kB a W?
    kB - boltzmanova konstanta
    W - pocet mikrostavov na makrostav

b)n = ť? 0.
c) V nevratnýhch (nereverzibilných) výpočetných systémoch dochádza pri výpočte k strate informácie,
zvýšeniu entropia a rozptýleniu energie. Uveďte vzťah pre túto energiu pre 1 bit (pri teplote T)
ESNL = kB T ln 2
d) Pokiaľ má byť výpočetný systém fyzicky reverzibilný, čo musí platiť o spôsobe jeho výpočtu (tzv.
Laudaurevov princíp)? Musi byt logicky reverzibilny

    a) Nakreslite graf, na ktorý sa prevedie riešenie SAT problému pomocou DNA počítania pre formulu y = (x 1
    V x 2 V x 3 ). Vyznačiť a popísať vrcholy + ukázať cestu pre x 1 = 1, x 2 = 0, x 3 = 0.
    b) Vrcholy R = AAATTTCC, S = GGAACCCC sú takto zakódované. Aký bude kód cesty z vrcholu S do R?
    GGGGTTTA
    c) Čo bude v počiatočnej skúmavke? Môžte zapísať binárne
    Všechny kombinace x 1 , x 2 a x 3 :000, 001, 010, 011, 100, 101, 110, 111
    d) Čo bude v skúmavke na konci výpočtu? Môžte zapísať binárne
    Pouze ohodnocení při kterých je výstup celé formule log 1: 001, 010, 011, 100, 101, 110, 111
    QCA - doplniť bodky pre Y = majority(A,B,C). Dva obrázky, jeden pre A=0, B=0, C=1 a druhý pre A=1, B=0,
    C=1.
    Napísať aspoň 2 vlastnosti, v ktorých superturingové výpočetné systémy porušujú výpočetný scenár
    Turingovho stroja.
    **1) reakcie na vonkajsie interakcie
    meni svoju funkciu pocas vypoctu
    nie vzdy sa ocakava dokoncenie vypoctu**
    V čom spočíva hlavná odlišnosť L-systémov oproti klasickej gramatike z pohľadu vykonania výpočtu?
    L-systemy vykonavaju vypocet paralelne
    11)a) Kde prebieha výpočet v prípade, že je systém implementovaný podľa princípov syntetickej biológie?
    Vo vnutri buniek
    b) Akú (fyzikálnu) podstatu majú signály v biochemických digitálnych obvodoch?
    Možná fluorescence?
    Vzťah pre výpočet výstupného signálu n -vstupového neurónu so vstupmi x , váhami w, biasom b a
    aktivačnou funkciou A
    A(x^T * w + b)
    y = A(∑(x_i * w_i) + b)
    Prvy termin 2020/
    MAC (ako na poslednej prednaske)
    Algoritmicka entropia - vzorec na vypocet
    Neuronova siet - vypocet trenovatelnych parametrov - 20x20 ciernobiely obrazok na vstupe, 4 skryte vrstvy po
    20 neuronov, vystupna vrstva s 10 neuronmi(Vsetky tieto Dense)
    O kolko sa zredukuje pocet vah pri nahradeni jednej skrytej vrstvy za konvolucnu vrstvu (6 filtrov, 3x
    kernel size)
    Nemá reálný smysl dávat conv mezi dvě dense vrstvy ne?
    A taky očekává se jako součást conv. Vrstvy i nějaký pooling?
    Taky záleží jaký vezmeme stride a dilatation v conv. vrstvě. Toto je z prdele zadání.
    souhlasím, že to zadaní je na nic.
    Ale i tak je ten výpočet níž špatně, ne?

Nemělo by to být tak, že v plně propojené vrstvě je na každý vstup jedná trénovatelná váha. Tedy
((počet_vstupů + bias) * počet_neuronů).
Tedy původní síť: ((400 + 1) * 20) + 3((20 + 1) * 20) + ((20 + 1) * 10) = 8020 + 3420 + 210 = 9490.
S tou conv je to pak spekulace no xd ale třeba nahrazení první vrstvy za conv by podle mě bylo:
6((33)+1)*1, s tím, že bez nějákého paddingu a poolingu by z toho lezl obrázek
(origošířka-šířka_jádra+1,origo_výška-výška_jádra+1,počet_filtrů)=(18,18,6) a teda celé dohromady by to
imho bylo:
S tím odečítáním jádra + 1 je to sporné. To by se dělo, když by sis nechával nějaký odstup od kraje. Jinak
standartně přiložíš střed konvolučního jádra na nějaký pixel, klidně i rohový a vypočítáš konvoluci. Takže z
toho leze ouput, co má stejný shape jako input. Ona konvoluce v NN bez poolingu nemá smysl podle mě.
Protože akorát si nějak upravíš vstupní obrázek a to je všechno, co ta conv. vrstva udělá.
(6((33)+1)1) + ((18186)+1)20 + 2((20 + 1)20) + ((20 + 1) * 10) = 60 + 38 900 + 2420 + 210 = 40010
Původní síť: 400 20+20 + 2020 +20 + 2020+20 + 2020+20 + 2020+20 + 2010 + 10
Nová síť bez poolingu: 6(33)1 + 6 + 400 620 + 20 + 2(2020+20) + 20*10 + 10
Nová síť s poolingem:
Rozdíl:_
QCA - Nakreslit vodic, 2 obrazky pre Majority(A,B,C) - vyplnit farby uzlov podla vstupu a tym vypocitat
vysledok
CGP - obrazok s hradlami a vstupmi - vypocitat maximalnu hodnotu fitness na vystupe. Urobit mutaciu, ktora
vzhladom na tuto fitness bude neutralna. Zmena parametru lookback na max - pocet, kam sa moze pripojit
jedno z poslednych hradiel(vratane vstupov). Vypocitat pocet integerov
L-gramatika - napisat abecedu, axiom, mnozinu pravidiel podla zadanych prechodov
První termín 2019/

    NN (6b)

    nakreslit schema neuronu se 4 vstupama, popsat
    pocet trenovacich parametru
    proc se v praxi nepouziva jenom 1 neuron?

Jeden neuron dokáže rozlišit (iba) lineárně separovatelné třídy.

    CA (6b)

    dana velikost sousedstvi, kolik existuje ruznych CA
    popsat wolframovy tridy

    entropie (6b)

    zadana pravdepodobnost stavu systemu, spocitat informacni entropii
    nakreslit graf

    co to je algoritmicka entropie?
    Algoritmická entropie, též Kolmogorovská složitost K(J, Z) zprávy (posloupnosti) Z, je délka nejkratšího
    programu (v jazyce J), který generuje Z.

    CGP (7b)

    nakresleny obvod, vymyslet k obvodu 2 fitness funkce a nakreslit mutaci, ktera bude skodliva pro jednu z
    fitness a neskodliva pro druhou
    plati u obvodu L-back 1?
    spocitat delku chromozomu

    nakreslit reverzibilni obvod a xor b xor c xor d (6b)
    DNA (6b)

    graf pro SAT problem, popsat uzly co znamenaji
    uvest pro kolik promennych uvedeny graf je
    dalsi veci ohledne postupu jak resit SAT na DNA

    CGP - beh (6b)

    zadany doba vytvareni generace, doba vyhodnoceni obvodu, delka vstupu, vystupu (s pouzitim n-bitove
    paralelni simulace)
    spocitat celkovou dobu behu
    jaky vliv bude mit zmena delky vstupu na vypocet

    nakreslit a popsat hw akcelerator pro NN (6b)

    moc si nepamatuju co presne

    boxplot (6b)

    nakreslit a popsat
    vymyslet si boxploty pro realny priklad a slovne zhodnotit

    neco s emergenci (2b)
    rozdil mezi L-systemem a normalni gramatikou (2b)
    jak se zmeni pocet DNA fragmentu po 1 kroku PCR (2b)
    neco se syntetickou biologii (2b)
    co je to ramec v FPGA (2b)
    Nejmenší adresovatelná jendotka konfigurační paměti.
    uvest 1 priklad metody pro fylogenezi a 1 pro ontogenezi (2b)

Fylo = EA, Onto = CA
První termín 2018/
L - gramatika, odvodit (definovat) gramatiku z ukazky derivacnych krokov. Dalej bolo potrebne podla pravidiel
nakreslit ciaru.
Navrhnut fitness funkciu pre obrazkovy filter, uviest priklad CGP genotypu a fenotypu.
Ako zvolit parametre CGP aby sme docielili maximalny vyhladavaci priestor.
DNA - popisat experiment.
Aka technika sa pouziva pri navrhu s pouzitim nano castic. (Zdola nahor)
Pocet pravidiel pre CA s trojokolim. - 128
Tranzistor z nanotrubiciek. (cca takto http://www.impactlab.net/wp-content/upllicon.jpeg))
A mnohe dalsie, ktore si uz nepamatam.
Co říkal že by se mohl ptát v přednáškách:
Emergence - Vznik globálního chování (tvarů nebo uspořádání) na základě lokální interakce velkého množství
komponent systému (bez centrálního řízení).
Samoorganizace
entropie
atraktor
fázový diagram-graf poloha rychlost
chaos
bifurkace
logistická rovnice
algoritmická entropie
CA - lokální interakce
fylogeneze
ontogeneze
epigeneze
church-turingova teze
super-turingův
energie nutná pro zpracování bitu informace
reverzibilní počítaní- bijetivní zobrazení
rozhodněte zda dané hradlo je reverzibilní
parotova křivka
symbolická regrese
delka genotypu v cgp
zvyšování funkční hustoty
dynamická a parciální rekonfigurace
Co je rámec
obvod pro sat solver
ustřední dogma
inference
sekvence nukleotidů
jak funguje zakodování v dna počítání při

řádný termín 2019
L - gramatika, odvodit (definovat) gramatiku z ukazky derivacnych krokov. Dalej bolo potrebne podla pravidiel
nakreslit ciaru.
Navrhnut fitness funkciu pre obrazkovy filter, uviest priklad CPG genotypu a fenotypu.
Evolučně navržený filtr (kernel 3x3)

Ako zvolit parametre CPG aby sme docielili maximalny vyhladavaci priestor.
Lback = max
Mřížka nejlépe v rozměrech x * 1 (pro zachování počtu hradel v tomto případě 1*32)
DNA - popisat experiment.
Aka technika sa pouziva pri navrhu s pouzitim nano castic.
Zdola nahoru
Pocet pravidiel pre CA s trojokolim.
2^(2^7) --- 2^8 - trojokoli tedy mam 3 bity, tedy 8 cisel 0-7 a 2^8 pravidel
Tranzistor z nanotrubiciek oznacit casti na obrazku. (cca takto http://www.impactlab.net/wp-content/upl ...
licon.jpeg)
Půlsemestrálka 2018

    CGP siet - (blok ma 2 vstupy, 2 vystupy, nie vsetky su vzdy pouzite) - ocislovanie vystupov, max fitness,
    vymena bloku co sposobi apod.
    Odvodit vzorec pre vypocet minimalnej velkosti prepinaca pri danej energii (wine Dalej ako sa zmeni
    entropia pri strate 1 bitu informacie.
    logisticka rovnica - popis parametre, nakrelsli bifurk. diagram, da sa komprimovat chaoticky signal z
    logist. rovnice? ako?

    teoria - alela, neutralna mutacia, atraktor
    Alela - varianta genu
    Neutralni mutace - mutace, neovlivni fitness
    Atraktor - mnozina stavu, do kterych system smeruje
    Zkouška 2017
    Neuronove siete
    a. Nakreslit a popisat 4 vstupovy perceptron
    b. preco sa nepouzivaju jedno perceptronove siete
    c. rozidel medzi NN a Deep neuron network
    kvantovy celularny automat

a. popis na obrazku, bunka, bodka, elektron
b. doplnit aby to vykonavalo logicky OR, bol zadany podobny obrazok ako v slidoch, ale rozsireny napravo
nebola jedna bunka, ale 2 za sebou
c. pomocou QCA urobit vodic

    Informacna entropia - mira informace, kterou je potreba dodat na zjisteni stavu
    a. vztah pre informacnu entropiu
    b. vztah medzi H a P

c. definovat algoritmicku entropiu

    CGP obrazok
    a. zmutovat nieco v CGP a vymyslet na to fitness, ktorej tato mutacia uskodi
    b. fitness ktorej tato mutacia neuskodi
    c. kolko hradiel je vo fenotype
    d. velkost chromozomu
    Napr. pro ten detektor iran dole: 32*3+
    Dektektor hran nepamatam si moc otazku, nevedel som vobec
    a. -
    b. -
    c. ako sa overi Evolucne navrhnuty detektor hran, alebo take nieco
    SAT DNA pocitanie 3 premenne, zadany graf
    a. dokreslit do obrazka nazvy uzlov
    b. vyznacit cestu pre dany vyraz
    c. -
    d. -
    e. skumakva na zaciaktu
    f. skumavka po vyrieseni prvej formule
    logicky obvod FPGA

a. nakreslit
b. ake typy pamate sa pouzivaju
SRAM?
c. -

    pravidlo 255 do akej wolframovej tiredy patri
        třída - homogenní
    kodon co to je a preco vznika redundancia, alebo ako?
    64 kombinaci, ale jen 20 aminokyselin (nektere kodovany vice kodony)
    nieco s hodnotou Emin, v slidoch to je, presne neviem nevedel som otazku
    11. zadany 3 jedinci s fitness 40,50,60 a vypocitat s akou pravdepodobnostou bude vybrany jedinec s
    hodnotou 60 ak sa vybera na zaklade turnaju
    100%? (kdyby ruleta, tak 60/(40+50+60) = 6/15 = 2/5)
    nevyhody VRC
        drahé
        Půlsemestrálka 2017
    Zadána CGP síť 2x8, 5 vstupů, 4 výstupy, už propojená jedním kandidátním řešením:
    a) určete velikost fenotypu
    b) určete velikost chromozomu (v integerech)
    c) navrhněte neutrální mutaci a zakreslete ji do obrázku
    d) kolikrát se urychlí simulace, pokud použijeme bitově paralelní simulaci na počítači s 16-bitovým procesorem
    (napište ve tvaru zlomku)
    e) určete maximální hodnotu fitness funkce
    f) formálně napište, jak se vypočítá fitness. Jeden vzorec, pokud chceme pouze správnou funkčnost obvodu a
    druhý vzorec, pokud chceme i minimalizovat počet použitých hradel.
    Popište evoluční návrh filtrů poprvé použitý J. Kozou. Popište to tak, že vysvětlíte následující pojmy:
    a) embryo - počáteční obvod
    b) kandidátní program - předpis, jak vytvořit z genotypu fenotyp

c) fenotyp
d) netlist - vnitřní popis HW (program je zkonvertován do tohoto formátu)
e) fitness funkce - porovnání frekvenčních charakteristik

    Entropie ve fyzice
    Míra neurčitosti.
    a) co představují proměnné ve vzorci Boltzmannovy entropie.
    W - počet mikrostavů na makrostav
    a) Předpokládejte 6 molekul plynu v uzavřené nádobě. Který z makrostavů má největší pravděpodobnost?
    Tuto pravděpodobnost vypočtěte.
    celkem kombinací: 2^6 = 64
    Nejpravdepodobnejsi stavy:
    ABC|DEF
    ABD|CEF
    ABE|DCF
    ABF|CDE
    ADC|BEF
    AEC|BDF
    AFC|BDE
    DBC|AEF
    EBC|ADF
    FBC|AEF
    a pak to stejné obráceně: 10+10=20 nebo jednoduseji pres vzorec
    W = n!/(nl!nr!) = 6!/(3!3!) = 20
    Pravdepodobnost = 20/64 = 0,3125 +
    c) ????? {Už si nepamatuju. Možná napsat nějaký vzorec pro algoritmickou/informační entropii, nebo pro
    energii nutnou ke zpracování bitu informace} ?????
    8
    a) Mějme 2 fitness f1 a f2, a výsledky experimentů x a y. Napište formálně co musí platit, abychom mohli říct,
    že x dominuje nad y.
    existuje i, f_i(x) < f_i(y)

b) Nakreslete graf, osa x je fitness f1, osa y je fitness f2. Do grafu nakreslete alespoň 5 dominujících řešení
(křížkem) a alespoň 5 nedominujících řešení (kolečkem).
c) Napište tvar fitness funkce, při metodě popisu jednou fitness funkcí vícekriteriální optimalizace.
F = suma(fi * wi)

    Počítání fitness pomocí SAT solveru. Byl zadán obvod (přibližně jako na obrázku G, přednáška 6, slajd 15,
    pouze ta část uvnitř obdélníků).
    a) Do obvodu dokreslete hradla tak, aby byl použitelný pro formální verifikaci SAT solverem.
    b) Kolik bude ve formuli pro SAT solver potřeba proměnných? Jednotlivé proměnné očíslujte na příslušná
    místa v obvodu.

c) Co to znamená z hlediska evolučního návrhu, když SAT solver nalezne řešení pro zadanou formuli?
Nalezneme řešení, takže obvody c1 a c2 nejsou ekvivalentní