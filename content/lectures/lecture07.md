Evoluční návrh a adaptace
analogových obvodů a antén
Biologií inspirované počítače
Přednáška 7

Lukáš Sekanina
FIT VUT v Brně
2026

Přehled (EA a analogové obvody)

    Při návrhu pomocí simulátoru je kandidátní obvod zakódován buď
        přímo –pro každou komponentu existuje určitý počet genů, které určují její
        typ, hodnotu, parametry, připojení do obvoduatd. (podobně jako CGP)
        nepřímo –Kozova metoda, viz dále
    Největších úspěchů dosáhl J. Koza, který pro evoluční návrh
    analogových obvodů používá GPve spolupráci se simulátorem Spice.
    - Několik desítek human-competitivevýsledků (patentovatelnýchvýsledků)
    - Obvody na úrovni pasivních prvků, tranzistorů, OZ.
    - Nejčastěji filtry, stabilizátory,regulátory
    Evoluční návrh s rekonfigurovatelnýmiobvody
        FPTA, FPAA(aplikace: adaptivní regulátory, filtry, ...)
        Specializované rekonfigurovatelnéASIC
    Cíle
        nalézt požadovanou funkci (a optimalizovat další parametry, např. příkon)
        opravit nefunkční obvod v případě poruchy nebo v extrémním prostředí.

Návrh analogových obvodů pomocí GP

    Chromozom obsahuje program, který, když je spuštěn, postupně konstruuje kandidátní
    analogový obvod ze zadaného triviálního obvodu (tzv. embrya).
    Program obsahujeinstrukce, např.: sem vlož kapacitor(100pF), vytvoř uzel, vlož kapacitor
    10pF atd. (viz animace). Na obrázku je příklad jednoho kroku konstrukce.
    Vytvořený obvod je následně zkonvertován do formátu netlist(viz obr. dole).
    Tentonetlist společně se zvoleným typem simulace (stejnosměrná, přechodová,
    frekvenční, šumová...) a nastavením vstupních signálů představuje vstup pro simulátor.
    Spustí se simulátor, provede se požadovaná simulace a výstup simulace se uloží do
    souboru (např. frekvenční charakteristika).
    Na základě analýzy tohoto souboru zjistíme fitness hodnotu (viz dále).

* netlist
R1 1 2 1k ; rezistor R1 mezi uzly 1 a 2
R2 2 0 2k
V1 1 0 DC 1 ;zdroj o napětí 1Vss
* definice analýz
.OP
.END

Program a jeho reprezentace v chromozomu

(LIST (C (– 0.963 (– (– -0.875 -0.113)
0.880)) (series (flip end) (series
(flip end) (L -0.277 end) end) (L (– -
0.640 0.749) (L -0.123 end)))) (flip
(nop (L -0.657 end)))))

Animace: http://www.genetic-programming.com/gpdevelopment.html

Animace: vytvoření obvodu

podle kandidátního programu

Na obrázku je počáteční obvod
(embryo), který obsahuje zdroj s
vnitřním odporem, zátěž a dva
modifikovatelné vodiče Z0 a Z1.

Program (zobrazený jako strom)
obsahuje instrukce pro vkládání
komponent, změnu topologie
obvodu apod. Pro každý
modifikovatelný vodičexistuje
jeden podstrom.

C –vytvoř kapacitor(podstrom
definuje kapacitu)
L –vytvoř cívku(podstrom
definuje indukčnost)
S –vytvoř sériové propojení–
např. rozděl úsek mezi uzly na tři
části, pro každou vytvoř podstrom
(existuje více variant pro S)
F –otoč polaritu
E –empty(konec)
a další

Popis animace:

vytvoření obvodu podle kandidátního programu

http://www.genetic-programming.com/gpdevelopment.html

    The process starts with a very simple embryonic circuit. In this example, the embryo consists of
    two modifiable wires, Z0 and Z1. The embryo is embedded in a test fixture whose input is the
    electrical signal VSOURCE and whose output is the voltage VOUT. The text fixture also contains a
    source resistor and a load resistor. The output produced by these two embryonic wires sitting in
    their test fixture is always zero, and uninteresting. Execution of the circuit-constructing program
    tree begins with the capacitor-creating C function associated with modifiable wire Z0 inserting
    capacitor C3 in lieu of modifiable wire Z0. The seven-point arithmetic-performing subtree of the C
    function establishes the numerical value of 403 nano-Farads as the sizing of capacitor C3. The
    next function in the tree —an S function —now becomes associated with C3. The polarity-
    reversing flip function F now reverses the polarity of modifiable wire Z1. The topology-modifying
    series, or S, function now creates a series composition consisting of two copies of the capacitor
    and new modifiable wire Z4. These three new components become associated with an F, S, and L
    function. The inductor-creating L function inserts inductor L8 into the growing circuit. Its arithmetic
    subtree establishes .22 micro-Henries as the value of inductor L8. This flip function F reverses the
    polarity of capacitor C3. The just-flipped capacitor C3 then becomes associated with the E function.
    The second series function then trifurcates modifiable wire Z4 into three modifiable wires. Another
    inductor-creating L function converts capacitor C5 into inductor L7 The three-point arithmetic-
    performing subtree assigns a value of 0.41 micro-Henries to new inductor L7. The end function E at
    the far right of the screen then ends development of its particular path, as does this end function
    and other similar end functions later. Modifiable wire Z4 is flipped. Inductor L9 is inserted in lieu of
    modifiable wire Z6 ... and inductor L7 is changed in value to .753 micro-Henries. Continuing in the
    same fashion, we get a fully developed electrical circuit

Vytvořen kapacitor a přechod na 2. podstrom
(LIST (C (– 0.963 (– (– -0.

- 0.113) 0.880)) (series (flip
end) (series (flip end) (L –

0.277 end) end) (L (– -0.

0.749) (L -0.123 end)))) (flip
(nop (L -0.657 end)))))

Podle nejlevějšího podstromu byl vytvořen
kapacitor C3.
Modrá šipka ukazuje, kam se bude
generovat obvod podle podstromu s
kořenem S.
Žlutá šipka ukazuje, kam se bude
generovat obvod podle podstromu F, který
říká: otoč polaritu (zatím je tam vodič, nic
se tedy s obvodem nestane) a vlož cívku.

Vytvoření sériového propojení (z animace)
(LIST (C (– 0.963 (– (– -0.

    0.113) 0.880)) (series (flip
    end) (series (flip end) (L –

0.277 end) end) (L (– -0.

0.749) (L -0.123 end)))) (flip
(nop (L -0.657 end)))))

Vytvořený obvod

Př. fitness funkce při návrhu filtrů

    fije vzorkovací frekvence, d(x) je absolutní odchylka mezi výstupem filtru a požadovanou
    hodnotou pro frekvenci x. W(x,y) je váhová funkce. Vzorkovací body jsou od rozmístěny
    logaritmicky od 1Hz to 100KHz. Pokud je odchylka menší než 0.03V, váha je 1. Pokud je
    odchylka větší než 0.03V, potom je váha 10.

Příklad specifikace Frekvenční charakteristiky kandidátních filtrů

Kozova metoda: Shrnutí

    Pomocí této metody založené na GP vytvořeny: analogové obvody,
    regulátory, optické systémy, antény apod.
    - Metoda je vždy stejná, podle aplikační domény se mění fitness funkce a
    základní množina komponent, ze kterých se konstruují řešení.
    V řadě případů se jedná o znovuobjevení patentovaných invencí (20. i
        století) i vytvoření patentovatelnýchvynálezů.
    Nevýhody: nutnost vysokého výpočetního výkonu (použit cluster s
    1000 procesory Pentium – rok cca 1996)
    - EA typicky používá populace velikosti tisíců jedinců, ale pouze řádově
    tisíce generací.
    - Simulace v Spicejsou výrazně nejpomalejší složkou systému (pokud se
    obvody ohodnocují, např. v FPTA, dochází k významnému urychlení
    návrhu).
    Kozova metoda bývá někdy kritizována, protože generuje obvody,
    které nerespektují určitá technologická omezení, a tudíž nejsou vhodné
    pro stávající postup výroby. Tyto nedostatky lze eliminovat zavedením
    určitých omezení do procesu generování kandidátních řešení (např.
    metoda ISCLEs).

Evoluční optimalizace antén (NASA AMES)

    EA optimalizuje parametrymodelu (velikost a
    polohu prvku), např. Yagiho antény.
    Fitness hodnota se vypočítá pomocí simulátoru
    antén, např. NEC.
    Cílem optimalizace je např. minimalizovat rozdíl
    mezi ideálním vyzařovacím diagramema
    změřeným vyzařovacím diagramem. Zisk (v dB) je
    počítán přes všechny sférické souřadnicové úhly 
    a .

Příklad vstupu pro simulátor NEC2.
NEC vypočítá vyzařovací diagram a
celou řadu dalších hodnot.

chromozom

    EA navrhuje celou konstrukci antény(např. mise
    ST5 z NASA)
    - GP vytváří jednu větev antény, která je
    použita symetricky ve výsledné anténě 4x.
    - Proces konstrukce začíná položením
    vodiče z počátku souřadnic (x = 0; y = 0; z
    = 0) do bodu (x = 0; y = 0; z = 0; 4) [cm]. Je
    to „embryonální anténa“.
    - Do koncového bodu vodiče je umístěna
    „konstrukční hlava“, která je řízena
    programem v chromozomu
    - Instrukce:
    - forward(L, R) -z pozice konstrukční
    hlavy veď nový vodič o délce L a pod
    úhlem R.
    - Posuň konstrukční hlavu na konec
    vytvořeného vodiče.
    - Rotate-x(R) -změň orientaci hlavy o R
    radiánů v ose x.
    - Rotate-y(R) -změň orientaci hlavy o R
    radiánů v ose y.
    - Rotate-z(R) -změň orientaci hlavy o R
    radiánů v ose z.
    Nalezené řešení je lepší než konvenční řešení
    (nižší příkon, uniformní tvar charakteristiky,
    doba návrhu kratší než u konvenční antény -
    snížení z 5 na 3 člověko/měsíce).

Specifikace: Zisk ≥0 dBi pro úhly 40°  80 °a
0 ° 360 °.Činitel stojatých vln SWR pro
vysílací frekvenci (8470 MHz) musí být menší než
1,2 a pro přijímací frekvenci (7209,125 MHz)
menší než 1,5. Vstupní impedance je 50Ω.
Hmotnost antény musí být nižší než 165 g, průměr
a výška menší než 15,24 cmatd.

Evoluční návrh antén

Evoluční návrh v FPTA-2 (NASA JPL)

    Rekonfigurovatelný obvod: Field Programmable Transistor Array
    (FPTA)
    EA běží v DSP (tj. v signálovém procesoru), DSP konfiguruje FPTA.
    Chromozom přímo reprezentuje konfigurační řetězec FPTA.
    Jedna buňka je konfigurována pomocí 77 bitů, které jsou zaslány do
    FPTA v pěti 16b slovech (16b/ 5 MHz).
    Ohodnocení obvodu probíhá tak, že
        DSP generuje stimuly pro FPTA (např. při evoluci NANDugeneruje každou
        ze 4 vstupních kombinací po dobu 1us na vstupech FPTA)
        DSP čte výstup FPTA a převede ho do digitální podoby
        DSP vypočítá fitness
            EA se snaží minimalizovat rozdíl mezi hodnotou změřenou na FPTA P(i) a
            požadovanou hodnotou T(i) pro Kvzorků získaných během evaluace (v našem
            příkladu je to např. 200 vzorků získaných během 4 us).
    Evoluce je asi 100-10000x rychlejší než s využitím simulátoru (závisí
    na velikosti obvodu).


=

= −

K

i

fitness P i T i
1

| ( ) ( )|

Experimentální platforma
JPL’s Stand Alone Board-Level Evolvable System (SABLES)

DSP (TI 320C6701)
Rychlost konfigurace: 16b/7,5MHz
max. frekvencepro převodník je 100kHz.

    FPTA-
    Stoica, A: Evolvable Hardware for Autonomous Systems, Tutorial CEC

Evoluční návrh usměrňovače

Vstupní signál 2kHz, 1.8V

Vlevo: evaluace celé populace (113 ms). Šipka GA ukazuje časový úsek (6ms) kdy dochází
k vytvoření nové populace a kdy se negeneruje vstup pro FPTA.
Vpravo: evaluace dvou kandidátních jedinců. Je zřetelná doba rekonfigurace FPTA.

Evoluce probíhá pouze v jedné buňce FPTA.

konfigurace FPTA

Evoluční návrh usměrňovače (2)

Vlevo:odezva nejlepšího jedince v generaci a) 1, b) 5, c) 50, d) 82
Vpravo: nalezené řešení v 82. generaci. Celkem ohodnoceno 8200 jedinců za cca 8 vteřin.

Evoluční návrh usměrňovače (3)

Nejlepší konfigurace na konci evoluce (a) nemusí být vždy vhodným řešením.
Nemusí se jednat o stabilní obvod –obrázek ukazuje, že cca po 1 vteřině (d) řešení
přestane fungovat. Proč?
a) Obvod závisí na předchozí konfiguraci FPTA(při evoluci nedošlo k vybití parazitních
kapacit během rekonfigurace obvodu)
b) Obvod je nestabilní –ale po dobu evaluace stabilní byl, proto dostal vysokou fitness
Řešení: delší doba evaluace jedince (vyzkoušet různou zátěž, časové domény), „mixtrinsic“
evoluce

Evoluční návrh usměrňovače (4)

Nejlepší konfigurace na konci evoluce nemusí být vždy vhodným řešením.
Obvod pracuje korektně pro frekvence 500 Hz –5 kHz (obr. vlevo), pro 50 kHz již
nepracuje (obr. vpravo).

Evolučně navržené obvody často pracují jen v těch podmínkách, které existovaly v
průběhu evoluce a pro ty vstupy, na které byly trénovány.

Problémy v FPTA: NAND

Sloupec 1: odezva vyevolvovaného NAND (trénovací signály se mění v mikrosekundách)
Sloupec 2: chybná odezva stejného obvodu, kdy jsou na vstupu signály měnící se v
sekundách
Sloupec 3 a 4: Znovuspuštěná evoluce opravila obvod, použity trénovací signály z obou
časových domén

Motivace výzkumu: Obnova funkce při poruše pro

vesmírné aplikace

FPTA-2 v extrémních podmínkách

    Extrémní teploty (mimo rozsah - 65 ºC až
    125 ºC)
    - Při nízkýchteplotách je nedostatek nosičů
    v polovodičích (protože dopanty nejsou
    dostatečně ionizovány).
    - Při vysokýchteplotách přestává pracovat
    PN přechod, nekontrolovaně přes něho
    protéká proud.
    Radioaktivní záření
        Radiační dávkapředstavuje podíl množství energie ionizujícího záření
        pohlcené v látce a hmotnosti této látky. Jedná se o základní veličinu
        charakterizující působení ionizujícího záření na látku. Jednotkou dávky
        je jeden Gray[Gy], což je jeden Joul pohlcený v jednom kg látky (1 Gy =
        1 J / 1 kg). Mimosoustavová jednotka je 1 rad, přičemž 100 rad = 1 Gy.
        Efekt na polovodiče:
            U CMOS tranzistoru se mění závislost Id na Ug -permanentní vliv na obvod,
            pokud je vystaven určité dávce.
            SEU (Single Event Upset) –dočasné překlopení bitu paměti SRAM.

FPTA při teplotách kolem 300 º C

Kandidátní obvody jsou ohodnocovány v FPTA, které je umístěno v prostředí s vysokou
teplotou.

FPTA při teplotách kolem 300 º C

Hradlo NORvyevolvované pro 27ºC nepracuje pro 326ºC. EA nalezl konfiguraci, která
realizuje NOR i při 326ºC. Vhodnou rekonfigurací dochází k rozšíření pracovních podmínek,
pro které je obvod schopen pracovat. Je to nová technika pro zajištění funkčnosti
(konvenčně se zajištění funkce provede pomocí realizace obvodu ze zvláštního materiálu
nebo pomocí různých kompenzačních technik).

FPTA v radioaktivním prostředí

(gamma záření - Cobalt 60 – tvrdý, křehký, šedý kov)

Testované obvody(28,5 cm od radioaktivního zdroje):
Spínaný prvek (přenosové hradlo): Obnova funkce Identita při 250Krad
Analogový obvod: Obnova usměrňovače při 100, 175 a 250Krad
Logický obvod: Obnova hradla NAND při 175 a 250 Krad
Smíšené signály: Obnova funkce 4b DAC při 175 a 250 Krad(viz následující obrázek)

Kumulativní ozáření [Krad]

krátkodobé ozáření [Krad]

FPTA v radioaktivním prostředí (2)

4b DAC Odezva poškozeného obvodu Obnova EA

Shrnutí: Evoluce v FPTA- 2

    Je obtížné vyevolvovat složité obvody, i když je evaluace kandidátních
    obvodů v FPTA výrazně rychlejší než pomocí simulátoru.
    Často je obtížné dosáhnout toho, aby vyevolvované řešení bylo
    robustní, stabilní a pracovalo i v podmínkách, které neexistovaly v
    průběhu evoluce.
    Obtížnost spočívá ve vytvoření vhodné fitness funkce. Implicitní
    předpoklady EA nebere v úvahu.
    Experimentálně prokázáno, že je evoluční návrh schopen generovat
    řešení pro extrémní prostředí. Oproti běžným technikách (použití
    speciálních materiálů nebo kompenzačních obvodů), je obnovení
    funkce zajištěno vhodnou rekonfigurací.

The challenge of conventional design is replaced with that of designing an
evolutionary process that automatically performs the design in our place. This
may be harder than doing the design directly, but makes autonomy possible.
(A. Stoica)

Speciální ASIC: Kalibrace IO po výrobě

    Výrobní proces integrovaného obvodu není úplně dokonalý – hodnoty
    parametrů se liší tranzistor od tranzistoru, čip od čipu, a lišíse od
    specifikace (zvláště patrné v nejnovějších technologiích).
    Např. IF filtr (IntermediateFrequencyFilter) –1% odchylkaod
    požadované frekvencejeneakceptovatelná.
    - střední frekvence: 455kHz, šířka pásma: 21kHz
    Obvykle se tento problém (tzv. variabilita procesu) řeší zavedením
    různých kompenzací – obvod se ale zvětšuje a zvyšuje svůj příkon.
    Jiný přístup –použije se jednoduchý konfigurovatelný IF filtr (malý
    nárůst plochy), u kterého je možné vyladitněkolik parametrů pomocí
    konfiguračního řetězce o délce kolem 100 bitů.
    PomocíGA se hledá vhodná hodnota těchto parametrů. Např. u IF filtrů
    se jedná o nastavení konfiguračních proudů transkonduktančních
    operačních zesilovačů (OTA).
    - snížení plochy o 63%
    - snížení příkonu o 26%
    - efektivitaprodukce 97%
    V Japonsku na trhu od roku 2001 – masová produkce v mobilních
    telefonech.

Transkonduktanční operační zesilovač (OTA)

    OTA = OZ, jehož výstup není napěťový, ale proudový a vstupy sledují napětí.
    Hlavní parametr: přenosová vodivost gm(ne napěťové nebo proudové
    zesílení).
    Vstupní i výstupní odpor transkonduktančního zesilovače je ideálně
    nekonečný.
    Vztah mezi výstupním proudem Ioa vstupními napětími na inverujícím (U-) a
    neinvertujícím (U+) vstupu je tedy:
    Parametr gmje možné měnit pomocí proudu Iset, tj. OTA je rekonfigurovatelný.
    Použití: laditelné filtry pracující na stovkách MHz.

Princip činnosti obvodu

Zlepšení frekvenční charakteristiky

Před
kalibrací

Po kalibraci

Literatura

    Koza, J. R. et al.: Genetic Programming III: Darwinian Invention and Problem
    Solving (Morgan Kaufmann Publishers, San Francisco CA 1999)
    Stoica, A.: Evolvable Hardware for Autonomous Systems. Tutorial CEC,
    GECCO (2004)
    Zebulum, R., Pacheco, M., Vellasco, M.: Evolutionary Electronics -Automatic
    Design of Electronic Circuits and Systems by Genetic Algorithms (CRC Press,
    Boca Raton 2002)
    Greenwood, G., Tyrrell, A.: Introductionto EvolvableHardware. A Practical
    GuideforDesigningSelf-AdaptiveSystems. IEEE PressSerieson
    ComputationalIntelligence, 200 7
    Higuchi, T., Liu, Y., Yao, X.: EvolvableHardware. SpringerVerlag, 2006
    Linden, D.: AutomatedDesign and OptimizationofAntennasusingGenetic
    Algorithms. Dizertační práce, MIT Cambridge, 1997.
