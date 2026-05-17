Výpočetní development
Biologií inspirované počítače
Přednáška 6

Lukáš Sekanina
FIT VUT v Brně
2026

Obsah

    Development v biologii
    Development v evolučním návrhu
        Gramatiky
        Genetické regulační sítě
        Celulární automaty
            1D
            2D
    Shrnutí

Fylogeneze

Biologická evoluce– postupný vývoj organismů
jako důsledek přirozenéhovýběru (fylogeneze)

Fylogenetickýstromse sestavuje dle
morfologických znaků nebo srovnáním DNA
Ontogeneze

Development (ontogeneze)

    vývin mnohobuněčného organismu z jedné buňky (zygoty)
    je produktem biologické evoluce.

Přímé vs. nepřímé zobrazení
genotypů na fenotypy v EA

    Přímé zobrazení
        Geny přímo kódují tvar a vlastnosti fenotypu
        Př. CGP (geny přímo kódují propojení a typ komponent)
    Nepřímé zobrazení
        Chromozom obsahuje instrukce pro vytvořenífenotypu
            V přírodě jde o vytvářenífenotypu –developmentkončí až smrtí
            organismu.
            V technických aplikacích je vývin fenotypu obvykle ukončen před tím,
            než je fenotyp používán.
        Př. Kozova metoda vytvoření obvodu z embrya podle stromu GP
            Jedna z nejjednodušších variant developmentu.
            Složitější modely dovolují více interakcí mezi geny a fenotypem.

Proč development v evolučním návrhu?

    Umožňuje (částečně) odstranit nevýhody přímého

kódování.

    V případě developmentu:
        Velikost vytvářených řešení nutně nezávisí na délce chromozomu.
        Je umožněn modulární návrh (určitý modul, který je evolucí jednou
        objeven, může být znovupoužit).
        Získáme lepší evolvabilitu– schopnost lépe se adaptovat na
        prostředí, více interagovat s prostředím, geny se mohou projevovat
        různě v různém stadiu developmentua v různém prostředí.
        Existuje více mechanismů odolnosti proti poruchám.
        Interakce genů a prostředí může vést k emergentnímu chování
        fenotypu.

Stručné opakování biologie: Buňka

    Všechny organismy jsou složeny z buněk a všechny buňky vznikly
    dělením již existujících buněk.
    Lidské tělo
        ~ 1014 buněk
        ~25.10^6 buněčných dělení během 1 s
        během 24 hodin vznikne asi 10^12 buněk
        ~350 různých typů buněk
    Buněčné aktivity
        buněčné množení,
        buněčný pohyb,
        změna typu (diferenciace) a
        buněčná signalizace.

Eukaryotická buňka

DNA

V jádře najdeme velmi dlouhou
dvoušroubovici DNA, která nese
genetickouinformaci(cca 1 metr DNA,
který obsahuje 3. 109 nukleotidů).
Nukleotidy: adenin(A), thymin(T), guanin
(G) a cytosin(C).
Párování: A-T, C-G
U člověka:
23 párů chromozomů
cca 20 tisíc genů
cca 1000 nukleotidů na gen
Proteiny a enzymy

    Proteiny(bílkoviny) jsou makromolekuly, které
    můžeme považovat za nástroje, senzory i
    stavební materiál organismů.
    Jejich tvar, chemické vlastnosti a množství v
    čase či prostoru jsou pod kontrolou genů.
    Průměrná lidská buňka obsahuje asi 10 000
    různých typů proteinů.
    Každý typ proteinu je určen lineárním řetězcem
    aminokyselin, jejichž pořadí určujetrojrozměrnou
    strukturu a biologickou aktivitu proteinů.
    Předpovědět strukturu proteinu na základě
    posloupnosti aminokyselin je velmi obtížná
    úloha. Nový přístup: AplhaFold2 (DeepMind,
    Enzymy jsou proteiny, které se nejprve pevně
    vážou k jiným molekulám a poté katalyzují
    vytváření či štěpení vazeb v těchto molekulách.

Ústřední dogma molekulární genetiky

T U (uracil)

    Pozn. Toto tradiční schéma bylo v poslední době zproblematizováno novými
    objevy epigenetiky, která studuje změny v genové expresi (a tedy obvykle i ve
    fenotypu), které nejsou způsobeny změnou písmen v DNA. Také epigenetické
    jevy mohou být děděny z buňky na buňku a z generace na generaci.

Schéma exprese eukaryotického genu

Každý gen má před (často i za) vlastní kódující sekvencí regulační sekvenci (naznačeno v obrázku jako
promotor), která rozhoduje o tom, zda a kdy se bude daný gen exprimovat. Přepisem do RNA
(transkripce), vznikne nejdříve pre-mRNA, z níž jsou posléze vystřiženy introny. Je třeba si uvědomit, že
vzniklá mRNAnení pouze kódující sekvence (tj. sekvence, která přímo kóduje aminokyseliny proteinu),
ale je delší, má na začátku a na konci netranslatovanéoblasti, které jsou důležité pro regulaci exprese.
Kódující sekvence, která začíná START kodónem (AUG) a končí STOP kodónem, je pak v procesu
translace rozeznávána antikodónytRNA, které přináší konkrétní aminokyseliny, které se spojují ve
výsledný protein.
Genetický kód

    Kodon (tři písmena
    genetického kódu) kóduje
    jednu aminokyselinu.
    Kodon AUGsignalizuje
    začátek proteinu.
    Kodony UAA, UAG, UGA
    signalizují konec sekvence.

Buněčné dělení

    Slouží k reprodukci buňky
    Mitóza je typ buněčného dělení, kdy dceřiné buňky
    získávají úplnou kopii genetické informace z
    mateřské buňky.
    - U jednobuněčných a primitivnějších
    mnohobuněčných organismů tak dochází k
    nepohlavnímu rozmnožování, kdy vznikají geneticky
    identické buňky či organismy (klony).
    Meiózaje redukční buněčné dělení, které
    umožňuje produkci buněk s polovičním počtem
    chromozomùnež se nachází v mateřské buňce.
    Tyto buňky se nazývají gamety.
    - Protože vytvořená buňka (vajíčko) může po určité
    době splynout s další vhodnou gametou (spermií),
    může vzniknout buňka se stejným počtem
    chromozomů jako měly obě mateřské buňky. Tento
    proces je základem pohlavníhorozmnožování.

Development v biologii

    Development (vývin) je proces, který mění jednobuněčné embryo
    (zygotu) na složitý organismus.
    - Kapacita DNA není postačující pro celý “popis”organismu. DNA obsahuje
    “předpis”pro konstrukci organismu.
    Development zahrnuje:
        buněčné dělení
        buněčnou diferenciace–buňky se specializují
        morfogenezi –změna tvaru a formy embrya
        růst
        buněčnou smrt
    Základní charakteristikou je vznik samouspořádání.
    V buňce existuje složitá interakce genů a proteinů–ne plně
    prozkoumáno!
    - Instrukce zakódované v genomu určují, kde a kdy bude syntetizován určitý
    protein během developmentu.
    - Proteiny povolují nebo zakazují aktivaci genu.
    Epistáze– jeden znak organismu je ovlivněn větším počtem genů
    Pleiotropie– jeden gen ovlivňuje několik různých znaků organismu
    Development rovněž představuje důležitý mechanismus pro zajištění
    opravy při poškození organismu.

Genetické regulační sítě (GRS)

    Modelují interakce mezi geny a proteiny
        V buňce existuje mnoho GRS, mohou být velmi složité, ne plně
        prokoumány.
        Uzel = gen, hrana =protein. Gen vytváří protein (šipka ven), jen
        když existuje protein, který ho aktivuje (šipka dovnitř).
    Př. Síť aktivuje gen 6, který generuje protein E.

Jak protein (TF) spustí expresi genu?
Na regulační sekvenci se vážou tzv.
transkripční faktory(proteiny), které
rozeznávají určitou konkrétní sekvenci a po
navázání mohou aktivovat nebo naopak
bránit přepisu kódující sekvence do RNA a
vznik nějakéhoproteinu.

Diferenciace buněk

    Diferenciace (specializace)
        buňky se po dosažení určité složitosti organismu
        specializují, např. na neurony, bílé krvinky, ...
    Různé typy buněk v mnohobuněčném organismu
        vznikají expresí odlišných genů během ontogeneze
        různé buňky generují různé proteiny (pozn. buňka
        aktivuje jen část svých genů)
        kromě genetické informace má pro nástup diferenciace
        význam i čas, poloha a prostředí
    Kmenové buňky - mají schopnost se přeměnit na

jiný typ buněk.

    Tato schopnost umožňuje tělu vytvořit nové buňky a
    opravit tak poškozené části těla.
    Nacházejí se např. v kostní dřeni, placentě.

FIT VUT v Brně 17

Odkud buňky vědí, jak se specializovat?

    Pro vysvětlení existují různé teorie –např. teorie poziční informace, reaktivně-
    difúzní modely apod.
    Princip teorie poziční informacevysvětluje příklad „francouzské vlajky“ v 1D
    struktuře: Každá z buněk má potenciál se specializovat do modré, bílé nebo
    červené barvy. Typ každé buňky je určen její pozicí, která je definována
    koncentrací morfogenu(látka, která ovlivňuje vývoj okolních buněk). Na
    základě poziční informace se buňky diferencují.
    Tímto způsobem se míchá mnoho
    podobných transkripčních faktorů
    (proteinů) odpředu dozadu i odshora
    dolů ve vyvíjejícím se embryu a
    nakonec je poměrně detailně
    rozkreslena mapa vyvíjejícího se
    embrya –každá část má namixované
    přesné množství různých faktorů,
    které tak zapínají vývojové geny,
    potřebné pro danou část embrya.
    Takto namixované koktejly faktorů
    nakonec vedou k trvalému zapnutí tzv.
    homeotickýchgenů, které určují
    jednotlivé části těla.

18

např. hlístice, octomilka, myš apod. slouží mj. pro výzkum ontogeneze organismů.
(a) Hlístice: délka 1 mm, sameček má ~959 buněk, ~3000 genů. Podařilo se zjistit
úplný původ každé buňky–jak vznikly v průběhu buněčných dělení.
(b) Octomilka a její mutant se zdvojeným hrudním článkem
(c) U octomilky existuje gen, jehož mutace způsobí absenci očí (eyeless). U myši byl
nalezen homologický gen (Pax6), jehož mutace způsobuje stejný efekt. Proteinová
sekvence ukazuje, jak moc si jsou tyto proteiny u takto vzdálených druhů podobné.
Modelové organismy

(a)

(b)

(c) (d)Homeotickégeny
u octomilky a myši

Výpočetní development (Kumar, 2004)

    je souhrnný název pro počítání inspirované biologickým

developmentem.

    Zahrnuje následující příbuzné oblasti:
        zobrazení genotyp -fenotyp v EA
        vývojové reprezentace (zakódování vhodná pro development)
        embryogeneze
        formace, morfogeneze, diferenciace, růst
        generativní systémy
        ...
    Příklady, které si uvedeme
        speciální gramatiky
        genetické regulační sítě
        celulární automaty
        development jako obecný program
            Např. Kozova metoda návrhu analogových obvodů pomocí GP

L-systémy

    Gramatický přístup k modelování vývinu
    Lindenmayerovy systémy (L-systémy) jsou paralelní

přepisovací systémy – gramatiky.

    0L-systém (bezkontextová pravidla)
        Abeceda – množina symbolů (různých typů buněk)
        Axiom (embryo) – počáteční řetězec
        Množina přepisovacích pravidel

({a, b, c},
aabcac,
{a→ab,
bc→ba,
c→b}).
aabcac
ababbaabb

Jeden vývojový krok:
paralelní přepis všech
buněk na základě
uvedených pravidel

L-systémy: Příklad – Kochova vločka

Abeceda a její interpretace:

Axiom: F

FIT VUT v Brně
0L-systémy a Chomského klasifikace

CfA. Meduna, TID 2007

Varianty a rozšíření L-systémů

    D0L-systém – deterministický bezkontextový L-systém
    PD0L-systém – “propagating” D0L-systém, nelze

přepisovat na prázdný řetězec (zkracovat)

    EOL-systém – konečný řetězec tvořen pouze terminálními

symboly (podmnožina abecedy L-systému)

    T0L-systém – “tabulkový” L-systém obsahující několik

množin přepisovacích pravidel, v jednom derivačním kroku
lze aplikovat pravidla pouze z jedné množiny

    a mnoho dalších, z nichž pro nás zajímavé zejména...

...zakazující/podmínkové L-systémy

    S každým přepisovacím pravidlem pi je asociována množina Fi

(Forbidding set) řetězců, které zakazují aplikaci daného pravidla v
případě, že se některý fFi vyskytuje jako podřetězec v aktuálním
derivačním kroku. Podobně lze formulovat nutný výskyt podřetězce
jako podmínku (Condition) pro aplikaci pravidla.

a parametrické L-systémy

    S každým symbolem může být asociována množina parametrů,
    které jsou uvedeny v závorce. Parametr např. určuje délku
    vykreslované úsečky. Pravidlo je možné použít, jen pokud je
    splněna určitá podmínka. Přepisovací pravidla mají tvar:
    předchůdce | podmínka → následník.
    Například: A(t) | t > 5 → B(t+1)CD(2t) , kde t je parametr.
    Potom A(9) bude nahrazeno řetězcem: B(10)CD(18)

Evolučně se navrhuje

    Definice a parametry L-systému (pravidla, axiom, ...)
    Posloupnost aplikace přepisovacích pravidel

Evoluční návrh stolu

    Case study: evoluce L-systémů pro návrh stolů
    Zřejmé výhody nepřímých, generativních reprezentací

Příklad růstu stolu, antény, ...

Hornby, G.. S. and Pollack, J. B. The Advantages
of Generative Grammatical Encodings for
Physical Design. Congress on Evolutionary
Computation. 2001.
Genetické regulační sítě

    Paralelní systém, interakce genů a
    proteinů je modelována sítí.
    Model genu –regulační
    (podmínková) část a kódováčást.
    Pokud je splněna podmínka, je
    vykonána akce (syntéza proteinu).
    Použití: např. řízení komplexních
    systémů.

podmínka akce

Př. Buňka, která zjistí přítomnost proteinu
B, má vyrábět určité množství B. Proto
spustí výrobu A a následně C nutných pro
výrobu B. V okamžiku, kdy je k dispozici
dostatek B (>>B), začne syntetizovat
protein D, jehož přítomnost pozastaví
výrobu B. Poklesne-li však koncentrace B
pod určitou úroveň, přestane být
syntetizován protein D a obnoví se
syntéza B.

Celulární automaty (CA)

    CA je paralelnívýpočetní model s lokální interakcí výpočetních
    elementů.
    Elementy – buňky –jsou uspořádány do pravidelné mříže.
    Každá buňka se může nacházet v jednom stavu z konečné množiny
    stavů.
    Každá buňka obsahuje tzv. lokální přechodovou funkciurčující její
    následující stav v závislosti na kombinaci stavů buněk v definovaném
    sousedství.
    V případě konečného počtu buněk jsou definovány tzv. okrajové
    podmínky– nejčastěji cyklické nebo konstantní.
    Stavy buněk jsou aktualizovány synchronněv diskrétních časových
    krocích.
    Konfigurací CA, označme c(t), rozumíme stav všech jeho buněk CA v
    čase t.
    Výpočtem CA rozumíme posloupnost konfigurací c(0), c(1), c(2) ...
    Emergentní chování – viz první přednáška.

Binární uniformní 1D CA

    N buněk, každá může být ve stavu 0 nebo 1 (binární CA)
    Lokální přechodová funkce je stejná pro všechny buňky (uniformní CA)
    Rádius rudává počet buněk bezprostředně sousedících s buňkou ina každé
    straně. Tyto buňky tvoří společně s buňkou i„sousedství“. Na obr. je r = 3.
    Neexistující sousedé buněk na okraji celulární struktury jsou považováni za
    log. 0 –konstantní (nulové) okrajové podmínky
    Stav i-té buňky v čase t+1 je vypočten pomocí lokální přechodové funkce F,
    uvažujmě např. XOR:
    - Qit+1 = F(Qi-^3 t, Qi-^2 t, Qi-^1 t, Qit, Qi+1t, Qi+2t, Qi+3t,)

0 0 1 0 1 1 0 0 0 1 0 1 1 0

1 i- 3 i- 2 i- 1 i i+1 i+2 i+3 149
C0

Př. F = xor

C1 0 0 0 0 1 1 1 1 1 0 0 1 0

Výpočet se provede paralelně pro všechny buňky

1
1D CA –lineární struktura buněk

Binární 1D, CA, r=1, pravidlo 250

1 1 1 0 0 0
Příklady vývoje 1D CA pro různá pravidla
c(0) = ...0001000...
1D CA: vývoj pro pravidla 0- 255
Wolframovy třídy pro 1D CA

    Vývoj z libovolné počáteční konfigurace
        třída 1 – skončí v homogenní konfiguraci
        třída 2 – dostane se do stabilní nehomogenní

konfigurace nebo cyklu s konečnou periodou

    třída 3 – generovaný vzor se zdá být náhodným
    třída 4 – zahrnuje lokální nepravidelné struktury,

případně rozšiřující se vzory

    mnohé lastury mají stejnou strukturu

Příklady 1D CA – Wolframovy třídy
Kvantitativní hodnocení dynamiky CA

    Parametr λ-míra schopnosti přenosu a uchování informace v CA
    (zaveden Langtonem)
    Parametr λ = (KN–n)/ KN
        N je počet sousedů (včetně buňky samé)
        K počet možných stavů buňky
        n počet pravidel buňky, které vedou ke klidovému stavu
    Parametr λ vyjadřuje poměr počtu pravidel, jejichž výstupem jsou
    neklidové stavy k celkovému počtu pravidel
    - Pozn. Pokud má buňka v klidovém stavu ve svém okolí také jenom buňky v
    klidovém stavu, potom se její hodnota v dalším kroku nezmění.
    - “Klidový” stav může být zvolen libovolně jako jeden z množiny stavů
    automatu.
    Pro CA s více stavy a pravidlyLangton zjistil, že
        nízké hodnoty λ –informace je v CA „zmrazená“, nepřenáší se (~ třída 1,2)
        pro λ ≈ 0.5 –přenos informace je možný, ale ne tak rychlý, aby se ztrácela
        vazba na její původní místo, hranice mezi chaosem a řádem (~ třída 4)
        λ → 1 –informace se přenáší lehce až chaoticky (~ třída 3)
        Pozn: symbol ~zde znamená „velmi přibližně“!

Další typy CA

    Podle dimenze buněčné struktury: 1D, 2D,...
    Podle lokálních přechodových funkcí buněk:
        neuniformní CA: každá buňka může obsahovat odlišnou
        lokální přechodovou funkci
        kvazi-uniformní CA
    Synchronní vs asynchronní CA
    2D CA: buněčná struktura v podobě pravidelné mříže
        okrajové podmínky analogicky s 1D CA
        nejrozšířenější tvary buněčných sousedství

Von Neumannovo sousedství: 5 buněk Moorovo sousedství: 9 buněk

Př. Pokud je jeden soused (kromě mě) v 1, nastav mě do 1

FIT VUT v Brně 38
Hra Game of Life (Conway, 60. léta)

    Uniformní binární 2D CA, Moorovookolí;
    stav 1 –živá buňka (černá), 0 –neživá buňka (bílá)
    Přechodová funkce (pozn.: = 0,273):
        Any live cell with two or three live neighbours survives.
        Any dead cell with three live neighbours becomes a live cell.
        All other live cells die in the next generation. Similarly, all other dead cells
        stay dead.
    Podle počáteční konfigurace dochází k vývoji obrazce, studováno mnoho
    případů –nejzajímavější jsou cyklické posunující se struktury (viz animace
    na http://en.wikipedia.org/wiki/Conway's_Game_of_Life))

Př. Gosper's Glider Gun creating "gliders".

glider

block blinker

„Elektronické obvody“ v CA (WireWorld)

    2D CA, 4 stavy v buňce (různé barvy),
    Barvy stavů:
        Bílá -pozadí
        Žlutá –hlava „elektronu“
        Červená –ocas „elektronu“
        Černá 3 -vodič
    Příklady hradel OR, XOR a AND
    Příklad: 8b násobička
    Uvedeným způsobem lze sestrojit
    zařízení simulující Turingův stroj.

Growing neural CA

    2D CA, stav= 16 float hodnot, přechodová funkce = CNN (8 tis. parametrů) trénovaná
    tak, aby po určitém počtu kroků dosáhl CA požadovaný tvar definovaný obrázkem,
    asynchronní aktualizacestavubuněk, viz https://distill.pub/2020/growing-ca/

(^12481632)
128
(^4864)
Sebereplikace (50. léta)

    Určité struktury je možné při vhodně zvolených pravidlech

CA replikovat.

    Je možné replikovat libovolnou strukturu, např. strukturu
    realizující nějaký užitečný (univerzální) výpočet?
    Von Neumann ukázal, že je to možné
        Model zpracován do CA s 29 stavy a 5-sousedstvím – prakticky
        nerealizovatelné (20M pravidel)
        Princip realizace: WireWorld

Von Neumannův konstruktor

    (A) Von Neumannův univerzální konstruktor (Uconst) umí postavit
    libovolný konečný stroj (Ucomp), pokud dostane jeho popis
    D(Ucomp).
    (B) Von Neumannův univerzální konstruktor (Uconst) umí postavit
    vlastní kopii (Uconst’),pokud dostane svůj popisD(Uconst).

(A) (B)
Von Neumannův konstruktor

    Von Neumannův univerzální konstruktor (Uconst) umí postavit vlastní
    kopii (Uconst’)a kopii libovolného konečného stroje (Ucomp’),pokud
    dostane popisobou D(Uconst+ Ucomp)–princip replikace
    samoreplikujícího se stroje.

Replikace pomocí smyček

    Langton (1984) – univerzalita není nutná k reprodukci,

informace řídící reprodukci může být zakódována ve
struktuře „organismu“.

    Zapouzdřená smyčka – 9 stavů, von Neumannovo

sousedství, zhruba 200 pravidel (+ další symetrická pro
ostatní 3 rotace), reprodukce ve 151 krocích

Langtonova smyčka

    2 skupiny stavů mají různé funkce
        základní prvky – 0, 1, 2
            2 vytváří trubici, 1 naplňuje trubici a vede v ní signály
        signály – 3, 4, 5, 6, 7
            4 zajišťuje zatáčení, 7 zajišťuje rovný růst „pupeční šňůry“
            atd.

Langtonova smyčka (pokr.)

    Růst pupeční šňůry
    Zatáčení pupeční šňůry

Langtonova smyčka (pokr.)

    Spojení smyčky

a rozpuštění šňůry
Langtonova smyčka (pokr.)

    Generování nové šňůry – celkový pohled
    Podobně fungují ostatní funkce (stavy se využívají jako messengery
    a indikátory)
    Když se smyčka už nemá kam šířit, tak „zemře“ – už se v ní nic
    neděje

Langtonova smyčka (pokr.)

Generace: 1 2

3 4 5
Aplikace CA

    Generování pseudonáhodných čísel
    Generování testovacích vektorů
    Novévýpočetní modely (Cell-Matrix apod.)
    Simulace dopravy
    Simulace chování plynů
    Studium feromagnetismu
    Simulace růstu krystalů
    Simulace difúze tepla a znečištění
    Simulace turbulentní proudění
    Modelování ekonomických procesů
    Generování textur, komprese
    Studium gramatik v teorii formálních jazyků
    a mnoho dalších...

Shrnutí

    Biologická ontogeneze jako inspirace pro výpočty v

komplexních systémech složených z velkého množství
lokálně interagujících primitiv, kde je pozorovatelné
emergentní chování, samoorganizace, uspořádání a
sebereplikace.

    Kdy je užitečné použít development v EA?
        Typicky se použije, pokud máme problém se škálovatelností,
        potřebujeme zavést modularitu, složitější interakci genotypu a
        fenotypu a prostředí,...
        Asi nejlepší příklad: anténa pro misi ST5
    Nevýhody
        Jak využít developmentpro konkrétní úlohu? Není jasné, jaký
        model je výhodný a povede ke zjednodušení evolučního návrhu.
        Vytvoření fenotypu může být časově náročné.

Literatura

    Wolpert, L. et al.: PrinciplesofDevelopment, 3. Edice, Oxford University Press, New
    York, 2007
    Wolfram, A. A newkindofscience. Wolfram Media, 2002: online
    http://www.wolframscience.com/
    Kumar S., Bentley, P.: On Growth, Form and Computers. Elsevier Academic Press, 2003
    Mařík a kol.: Umělá inteligence I-V., Academia, 1993- 2007
    Albertset al: Základy buněčné biologie. EsperoPublishing, Ústí nad Labem, 2004
    http://en.wikipedia.org/wiki/Conway's_Game_of_Life
    Žaloudek, L.: projekt FRVŠ FR2112/2009/G1
    Doležal, T.: Základymoderní biologie, JČU, 2020
