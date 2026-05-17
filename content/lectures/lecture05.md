Evoluční návrh číslicových
obvodů
Biologií inspirované počítače
Přednáška 5

Lukáš Sekanina
FIT VUT v Brně
2026

Obsah

    Princip evolučního návrhu obvodů
    Thompsonův experiment
    Evoluce na úrovni hradel
        Dekompozice problému
        Snížení výpočetní náročnosti pomocí formální verifikace
    Evoluce na úrovni funkčních bloků
        Evoluce obrazových operátorů
    Další příklady

EHW = EA + RZ

    Na počátku 90. let provedeny první experimenty, kdy byl

evoluční algoritmus (EA) použit přímo pro návrh obvodu v
rekonfigurovatelném zařízení (RZ).

    T. Higuchipoužil GA pro návrh 6-vstupového multiplexoru v PLA
    (Programmable Logic Array).
    Poprvé byl použit termín „evolvable hardware“ (EHW),

který do češtiny překládáme jako vyvíjející se obvody nebo
evoluční hardware.

    Pozor, EA se používaly v oblasti návrhu obvodů již dávno

před tím – jako optimalizační technika pro „řešení určitého
podproblému“ (optimalizace hodnot součástek obvodu,
rozmístění součástek na čipu od r. 1987, apod.). Nebyl jim
ale svěřen celý proces návrhu.

Příklad evoluční optimalizace v návrhu obvodu:
Optimalizace propojení v rámci „standardní buňky“

    Technologická knihovna obsahuje tisíce vysoce optimalizovaných
    „standard cells“ (SC), např. AND3, XOR2, 1b-adder atd.
    Velké obvody sestávají ze stovek miliónů SC.
    Cílem je minimalizovat šířku SC, výška je pevná v dané knihovně.
    NVCell – optimalizace návrhu SC firmy NVidia:
        Rozmístění tranzistorů a pinů –pomocí simulovaného žíhání a RL
        Predikce kvality propojení pro rozmístění pomocí RL
        Propojení vývodů tranzistorů a pinů pomocí genetického algoritmu s cílem
        minimalizovat propojení a porušení návrhových pravidel (DCR –Design CheckRule)

Stickdiagram ofa Standard Cell:
LISD (local interconnect source-
drain), LIG (local
interconnect gate), M1, M2 and M
(metal) layers.

H. Ren and M. Fojtik, "Invited-NVCell: Standard Cell Layout in Advanced Technology Nodes with Reinforcement Learning," DAC2021,
10.1109/DAC18074.2021.9586188.

Rekonfigurovatelná zařízení

FIT VUT v Brně

LUT

Číslicové obvody: přepínače, multiplexory a LUTy

Netradiční rekonfigurovatelné materiály (např. kapalné krystaly)

    přiložením vhodných napětí na vhodná místa

Polarising filter

NanoCell-rekonfigurovatelnámolekula. “On” a “off” I(V)
charakteristikynitroanilinu.Napěťový puls 1.75Vmění konfiguraci.

Analogové obvody:

    analogové multiplexory
    spínané kapacitory
    transkonduktanční
    operační zesilovače

Rekonfigurovatelnézrcadlo

Rekonfigurovatelná
anténa

FIT VUT v Brně

Bity konfiguračnípamětidefinují zapojení hardware.

5

6

Vyvíjející se obvody

    EA pracuje jako generátor nových řešení. Chromozom je transformován na
    konfigurační řetězec, podle kterého je nakonfigurováno RZ.
    Požadavky na cílové řešení jsou formulovány ve fitness funkci. V rámci
    evaluace kandidátního obvodu jsou generovány stimuly pro RZ, měřeny odezvy
    RZ a vypočtena fitness hodnota.

Reprezentace obvodu

    Obvod může být v chromozomu reprezentován

přímo a to na různých úrovních:

    úroveň materiálu, nanostruktury
    tranzistory
    hradla
    funkční bloky
    matematický model (rozhodovací diagram, AIG, ...)
    Obvod může být reprezentován v chromozomu

nepřímo

    Chromozom obsahuje program (předpis) pro konstrukci
    obvodu – viz development v dalších přednáškách.

Ohodnocení kandidátních obvodů
(česká terminologie zavedena pro BIN)

    nepravá evoluce ( extrinsic evolution)–kandidátní obvody jsou
    vyhodnocovány pomocí simulátoru. Jen pro výsledek evoluce je
    uvažována fyzická realizace.
    - Nevýhody: obvykle pomalé, není možné do modelu zahrnout „celý svět“
    pravá evoluce ( intrinsicevolution)- kandidátní obvody jsou
    vyhodnocovány ve skutečném HW.
    smíšená evoluce ( mixtrinsicevolution)– část populace je
    ohodnocena pomocí simulátoru, část v reálném HW.

Dvě základní použití vyvíjejících se obvodů

    Evoluční návrh obvodů
        EA je použit ve fázi návrhu. EA není součástí výsledného produktu.
        Zajímá nás výsledek evoluce. Cílem je najít inovativní řešení schopné
        „porazit“ konvenční řešení nebo zautomatizovat návrh.
        Doba běhu EA může být dlouhá, pokud to přinese očekávaný výsledek.
    Evolvable hardware(vyvíjející se HW)
        EA je použit pro adaptaci HW během činnosti HW v případě, že:
            je změněna specifikace (nová specifikace nebyla uvažována v době návrhu)
            dojde ke změně v charakteru vstupních dat
            dojde k poruše HW a je třeba najít „lepší“ konfiguraci, která v ideálnímpřípadě
            obnoví původní činnost obvodu
        EA je typicky součástí systému. Kromě kvality vyevolvovaného řešení nás
        zajímá i doba evoluce.
        Často se jedná se o evoluci s otevřeným koncem, tj. není znám cílový
        stav, po jehož dosažení by evoluce mohla skončit.
        Vyevolvovanéřešení je optimalizováno pro dané místo, čas a okolní
        podmínky.
        Termín „evolvablehardware“ je správné používat pouzev tomto kontextu,
        i když je často používán ipro evoluční návrh obvodů.

Klíčový experiment A. Thompsona (1996)

    Problém: Najdi zapojení obvodu, který pracuje jako tónový diskriminátor. Obvod má
    generovat log. 1, když jefinput= 10kHz,a log. 0,když je finput= 1kHz.
    Použito pole 10x10 CLB obvodu XC6261. Evoluceprováděna přímo na úrovni
    konfiguračního řetězce FPGA. Pozn.: U tohoto čipu bylznám formát konfiguračního
    řetězce a byla podporována parciální rekonfigurace.
    Mohou tak vzniknout netradiční asynchronní obvody a dokonce obvody, které je
    vhodnější označit raději za analogové než digitální. Pozn: CLB mají zpoždění v
    jednotkách ns, požadované chování je na úrovni ms!
    Parametry GA: délka chromozomu 1800 bitů, velikost populace 50, pravděpodobnost
    křížení 70%, průměrně 2,7 bitů znegováno pomocí mutace.
    Fitness funkce maximalizuje rozdíl mezi průměrným napětím na výstupu pro sérii vstupů
    s frekvencí 1kHz (S 1 ) a sérii vstupů s frekvencí 10kHz (S 10 ).
    Uspořádání experimentu:

Problematický výsledek evoluce

Odezva obvodu v průběhu
evoluce.V generaci 3500
nalezeno řešení.

Nalezené řešení je asynchronní, používá jen
několik buněk, vykazuje netypické zpětné vazby
a využívá vlastnosti konkrétního materiálu.
Řešení nefunguje když:

    se vyevolvovaná konfigurace nahraje na jiné
    FPGA stejného typu,
    se změní pracovní podmínky (teplota...)
    se podle konfiguračního souboru vytvoří model
    a simuluje se na PC.
    Doposud nebylo uspokojivě vysvětleno, jak a
    proč obvod funguje.

Důsledky Thompsonova experimentu

    EA je schopen využít pro řešení problému i ty fyzikální vlastnosti
    platformy (vlastnosti křemíku) a prostředí (teplotu, elekromagnetismus,
    ...), které člověk neuvažuje.
    - Problém portability, přenositelnosti: řešení pracuje jen na platformě, kde bylo
    vyevolvovánoa jen při okolních podmínkách, které byly během evoluce.
    Pokud umožníme neomezenou evoluci u těch aplikací, kde je EA
    součástí systému a řešení se nepřenáší jinam, potom není problém s
    portabilitou.
    Pokud bychom však měli výsledek neomezené evoluce použít jinde (u
    dalších uživatelů), nemusí vždy fungovat.
    - Smíšená (mixtrinsic)evoluce je způsob, který vylepší portabilitu.
    - Thompson ukázal, že EA je schopen v několika málo generacích „doladit“
    řešení, které bylo nalezeno pro platformu A, i pro platformu B.
    - Robustní řešení je také možné získat tak, že kandidátní obvody budeme
    trénovat v různých prostředích na různých platformách během evoluce.
    Bylo prokázáno, že evoluční design umí něco, co člověk jako designér
    nedokáže –Thompsonůvexperiment byl motivací pro další výzkumníky
    - Je zde potenciál, že takto navržená řešení budou efektivnější než řešení
    navržená konvenčními postupy.

Evoluční návrh obvodů: Současné problémy

    Škálovatelnost reprezentace
        Složité obvody jsou obvykle reprezentovány dlouhým chromozomem 
        velký (a členitý) prostor kandidátních řešení EA je neefektivní
        EA pracující na úrovni hradel umožňuje najít řešení pro obvody do cca 1 5
        vstupů a 10 výstupů a cca 100 hradel –jedná se o evoluční návrh s
        prakticky nulovou znalostí od návrháře.
        Řešení: dodat znalost o problému do metody řešení
            evoluce na úrovni funkčních bloků
            dekompozice a inkrementální evoluce
            development
            EA s podporoumodulů, koevoluce apod.
    Škálovatelnost evaluace kandidátních řešení
        Doba ohodnocení roste exponenciálně s počtem vstupů (komb. obvody).
        Řešení:
            volba vhodné trénovacímnožiny
            odhad fitness hodnoty
            formální verifikace kandidátních řešení (pokud existuje plně funkční řešení)
    EA negarantuje nalezení řešení s požadovanými vlastnostmi.
    Jak navrhnoutEA? -Experimentálně.

Evoluční návrh malých klasifikátorů pro ASIC

IordanouKL et al. Low-cost and efficient predictionhardwarefor tabular data using tiny classifier circuits.
Nature Electronics | Volume 7 | May 2024 | 405– 413

Snížení výpočetní náročnosti fitness funkce

pomocí formální verifikace

    Předpoklad: Obvod C1 je plně funkční (a dobře zoptimalizovaný
    konvenčními metodami), cílem je minimalizovat počet hradel.
    Výpočet fitness:
        SAT solver je použit k rozhodnutí, zda kandidátní obvodCiareferenční
        obvodC1 jsou funkčně ekvivalentní.
        - Pokud ano, potom fitness(Ci) = počet hradel v Ci;
        - jinak: fitness(Ci) = WORST_FITNESS.
        Ověření ekvivalence je možné provádět pro řadu i velkých obvodů
        velmi rychle!

Konvenční syntéza
(ABC, SIS...)

CGP

obvodC1 opt.C
(= referenční
obvod)

Specifikace
(obvod C)

SAT problém

    Problém splnitelnosti (SAT problém) je rozhodovací

problém, jehož vstupem je booleovský výraz zapsaný v
konjunktivní normální formě (CNF), tj. jako konjunkce
klauzulí, např.

    Otázka je, zda existuje takové přiřazení (0, 1) proměnným,

že je výraz splněn.

    Tento problém je NP úplný.
    Př. SAT solveru: MiniSAT, http://minisat.se/

SAT solver ve fitness funkci (1)

?



Sestavíme obvod G, který porovná C1 s kandidátním obvodem C2.
PokudC1 a C2 nejsoufunkčně ekvivalentní, potom existuje alespoň jedno přiřazení
vstupům, pro které je výstupG roven1.

G:

C1: C2:

SAT solver ve fitness funkci (2)

    Obvod G je transformován na CNF (kterou potřebujeme

pro SAT solver) pomocí Tseitinovy transformace.

    CNF reprezentace musí zachycovat platné vztahy mezi

vstupy a výstupy každého hradla obvodu G.

    Uvažme hradloy = OP(x 1 , x 2 ).
    Jeho chování zachycuje formule , která je splněna
    ((y, x 1 , x 2 ) = 1),pokud predikáty = OP(x 1 , x 2 ) je pravdivý.
    x 1 y = x 1 x 2
    x 2
    (y => x 1 x 2 )(x 1 x 2 => y)
    (y + x 1 x 2 )(x 1 x 2 + y)
    (y + x 1 )(y + x 2 )(x 1 + x 2 + y)

PříkladPř: y = not (x) :

x y g
0 0 0
0 1 1
1 0 1
1 1 0
g = (~x  ~y)(x  y)

CNF formuleg(x, y) = 1,pokud predikát
y = not(x) je pravdivý.

SAT solver ve fitness funkci (3)

SAT solver

variables: 13, clauses: 30, time elapsed: 0.03ms

              -
        -

    -

        -
              -
                       -
                    -
                          -
                    - SAT solver ve fitness funkci (3)
              -

        -

            -
                  -
                           -
                        -
                              -

    model / counter example: result: SATISFIABLE => C1 and C2 are NONEQUIVALENT

Výsledky (LGSynth93 benchmarks)

CGP
ES(1+1), 1 mut/chrom, seed: SIS, Gate set: {AND, OR, NOT, NAND, NOR, XOR}, 100
běhů

ABC, SIS –akademické nástroje pro syntézu a optimalizaci

C1, C2, C3 –komerční nástroje pro syntézu a optimalizaci

[Vašíček, Sekanina: DATE 2011]

Příklad konvergence

    Shrnutí
        Metoda (CGP+SAT solver) dosahuje častolepší výsledky při
        minimalizaci počtu hradel než běžné metody,
        je velmi časově náročná (čas lze snížit, pokud se formální verifikace
        kombinuje se simulací),
        vyžaduje na počátku inicializaci plně funkčním obvodem.

Evoluční návrh na úrovni funkčních bloků

    Oproti úrovni hradel (viz CGP) evoluce pracuje na úrovni sčítaček,
    komparátorů a složitějších komponent, které nejsou propojeny jediným
    vodičem, ale skupinou vodičů – do metody řešení je dodána znalost.
    Tato reprezentace vede nazkráceníchromozomu oproti reprezentaci
    stejného obvodu na úrovni hradel.
    Protože jsou takto navrhovány složitější obvody, není obvykle možné
    otestovat ve fitness funkci všechny možné kombinace na vstupech. Při
    evoluci se proto používá trénovací množina. Výsledek evoluce je
    testován pomocí testovací množiny.
    Hlavním problémem je vhodně zvolit sadu funkčních bloků, ze kterých
    evoluce sestavuje řešení, a trénovací data.
    Příklad: Evoluční návrh obrazových operátorů.

Př. Evoluční návrh obrazových operátorů:

Definice problému

    Cílem je navrhnout obrazový operátor pro obrázky v 256

úrovních šedé.

    Operátor má devět 8b vstupů (jádro 3x3) a jeden 8b

výstup.

(^012)
(^345)
(^678)
4
kombinační
obvod
72 vstupů/8 výstupů
I4
I3
I5
I6
I2
I7
I1
I0
I8
I4’
poškozený obrázek výstupní obrázek

Různé typy šumu

a) originál

b) výstřelový šum – poškozené pixely mají náhodnou hodnotu

c) šum sůl a pepř – poškozené pixely mají hodnotu 0 nebo 255

d) 10 % gaussovský šum – hodnota každého pixelu je

modifikována podle Gaussova rozložení

Konvenční řešení: výstřelový šum

    Pro odstranění tohoto typu šumu se používá nelineární filtr –medián (c).
    Lineární filtr nefunguje (b).

a b c

CS –compare&swap
D –registr

CGP na funkcionální úrovni

xxx|2, 4, 3|4, 6, 1|7, 8, 6|xxx|xxx|10, 11, 1|xxx|.......|23

vstupy: 9 x 8bit , výstupy: 1 x 8bit
velikost pole: 10 x 4
EA: viz CGP

Chromozom (konfigurace)

I4’
I4

I3

I5
I6

I2

I7

I1

I0

I8

3

1

6

1 7

11

10

9

12

13 45

(^1523)

Programovatelný element

8
8

8

konfigurace

A
B

C

Programovatelný element

Příklady používaných funkcí v PE

Fitness funkce

referenční

poškozený obrázek - w
obrázek

Filtr

chromozom

Komparátor

fitness


= =

= −

N

i

M

j

fitness v i j w i j
1 1

| ( , ) ( , )|

N x Mpixelů,

výstupní
obrázek - v

𝑀𝐴𝐸=

𝑓𝑖𝑡𝑛𝑒𝑠𝑠
𝑁𝑀

Příklad filtru navrženého pomocí CGP

a) Obrázek s 5% šumem sůl a pepř
PSNR: 18.43dB (peak signal to noise ratio)

b) Původní obrázek

c) Mediánovýfiltr (kernel 3x3)
PSNR: 27.92dB
268 FPGA slices; 30 5 MHz

d) Evolučně navržený filtr (kernel 3x3)
PSNR: 37.50dB
200 FPGA slices; 30 8 MHz a)

d) c) b)

Porovnání různých filtrů (FPGA)

PSNR –theaveragefor25 test images
MF –Median Filter; AMF –Adaptive Median Filter
The single filter and 3-bank are evolved filters (Czech patent #304181).
Best SW -Y. Dong, S. Xu: A new directional weighted median filter for removal of random-valued impulse
noise. Signal Processing Letters. vol. 14, no. 3, p. 193–196, 2007

Porovnání různých filtrů (ASIC)

Evoluční návrh filtrů v SW: Shrnutí

    Navrženy filtry, které pro určité typy šumu vykazují lepší kvalitu
    filtrovaných obrazů i nižší implementační cenu.
    Jaké jsou „optimální“ parametry systému?
        Je nutné udělat analýzu –viz ladění EA.
    Evoluční návrh je pomalý
        EA je třeba spustit několikrát, aby byl nalezen kvalitní filtr.
        Bylo změřeno, že na procesoru Celeron2,4GHz je třeba cca 22 vteřin k
        ohodnocení 3000 kandidátních filtrů (pro obraz 128x128 pixelů).
        Pro nalezení kvalitního filtru je potřeba cca 150 tis. evaluací, tj. cca 18
        minut. 10 experimentů bude trvat 3 hodiny.

Jeden z prvních EHW ASIC (Kajitaniet al., 1998)

2 x Programmable LogicArray (PLA), 28 vstupů, 8 výstupů, max.
128 součinových vodičů, max. velikost chromozomu 2048 bitů
Aplikace: řízení umělé končetiny, řízení robota

Příklad adaptivního systému: kontrolér pro umělou končetinu

    EMG –myoelektrické(nebo
    také elektromyografické)
    signály
    měří se aktivita svalůve
    zbývajícíčásti ruky
    kontrolér má za úkol na
    základě těchto signálů
    pohybovat s umělou
    končetinou
    běžné řešení: člověk se musí
    naučit svými signály „ovládat“
    kontrolér, který není
    konfigurovatelný
    EA hledá co nejvhodnější
    klasifikátor pro konkrétního
    člověka
    Znovunatrénováníkontroléru
    je občas nutností –
    myoelektrickésignály se u
    každého člověka mohou v čase
    měnit
    Oproti NN mnohem
    kompaktnější řešení

Trénovací fáze:
Pro každý ze 6 pohybů si pacient představí, že ho chce
provést. V okamžiku, kdy tak činí, jsou na zbytku paže měřeny
myoelektrické signály a je uchován typ pohybu (1 -6). Pro
každý pohyb je změřeno n vzorků. Signály je nutné před
přivedením na vstup PLA předzpracovat a kvantizovat. Obvykle
jsou použity čtyři datové kanály (ze čtyř elektrod) a čtyři bity na
vzorek. Na vstup PLA je přiváděn 16b vektor, výstup je 6-bitový.
Pro zkušeného uživatelelze dosáhnout až 98% přesnosti
klasifikace.

Evoluční algoritmus
je schopen najít
vhodný kontrolér
během 5 minut.
Adaptace člověka
na fixní kontrolér
trvá 1 měsíc.

Čip pro bezeztrátovou kompresi obrazu

Kvalitní barevné electrofotografické tiskárny (JBIG standard):

    dokumenty mají vysoké rozlišenía velkou velikost
    doba přenosu dat z disku do tiskárny určuje rychlost tisku
    Adaptivní komprese dat vyvinutá s cílem redukovat dobu přenosudat, tj. zvýšit
    rychlost tisku –stávající algoritmy pro kompresi jsou nepoužitelné
    Jedná se o bezeztrátovou kompresi.

Princip bezztrátové komprese pomocí prediktoru

Prediktor

g[i,j]

g'[i,j]

Prediktor

g[i,j]

odchylkaT[i,j] g'[i,j]

konfigurace

Jak má vypadat prediktor?
Kolikmá být prediktorů?
Podle kterých pixelů se má predikovat?
Jak se má přenášet T[i,j]?

komprese dekomprese

Princip metody a struktura chromozomu

GA hledá optimální rozložení pixelů pro
prediktor pro každý blok obrazu, tj.
evoluce běží jen při kompresi.
Experimentálně zjištěno, že je
nejvýhodnější hledat pixely až do
vzdálenosti 128 řádků od aktuálně
predikované hodnoty.

Čip pro kompresi obrazu

Na sadě testovacích obrazů vykazoval systém zvýšení kompresního poměru o 51% v porovnání s
existujícímí JBIG systémy.
Doba komprese je srovnatelná s těmito systémy, ale evoluční systém musí být implementován v
HW (FPGA).

Konec přednášky
