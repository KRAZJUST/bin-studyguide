Úvod, inspirace v přírodě,
entropie a samoorganizace
Biologií inspirované počítače
Přednáška 1
Lukáš Sekanina
FIT VUT v Brně
2026
Organizace předmětu (2025/26)

    13 přednášek (nic neodpadá)
    4 cvičení na učebně (max. 8 bodů)
        Evoluční návrhkombinačníchobvodůCGP
        Statistické vyhodnoceníexperimentů
        Celulární automaty
        CNN
    Půlsemestrální zkouška 15 bodů
    Závěrečná zkouška
        52 bodů(minimum 2 0 bodů)
    Projekt
        25 bodů
        zadání a pokyny budou zveřejněny brzy
    Zápočet není

Obsah předmětu

    Detailní plán je v e-learningu VUT

Literatura

    Sekanina L., Vašíček Z., Růžička R., Bidlo M.,

Jaroš J., ŠvendaP.: Evoluční hardware: Od
automatického generování patentovatelných
invencí k sebemodifikujícímse strojům. Academia
Praha 2009, 328 s.

    Slidy+ odkazy.

Literatura (2)

    Biologií inspirované počítání (SW)
        RozenbergG., BäckT., KokJ.N.: Handbook of Natural
        Computing, Springer 2012, 2052 p
        Mařík a kol.: Umělá inteligence I-V., Academia, 1993-
        2007
        Kvasnička, V., Pospíchal J., TiňoP.: Evolučnéalgoritmy.
        Vydavatelství STU Bratislava, 2000
        Floreano, D., Mattiussi, C: Bio-Inspired Artificial
        Intelligence. TheMIT Press 2008
        Bentley, P.: Evolutionary Design by Computers. Morgan
        Kaufmann, 1999
        Miller J.F.: CartesianGeneticProgramming, Springer
        Verlag 2011
        Wolfram, A. A newkindofscience. Wolfram Media,
        2002: online http://www.wolframscience.com/
        BanzhafW., MachadoP., ZhangM.: Handbook of
        Evolutionary Machine Learning, Springer, 2023
    Biologií inspirovaný hardware
        TrefzerM., Tyrrell A. M.: Evolvable hardware –From
        Practice to Applications, Springer 2015
        Higuchi, T., Liu, Y., Yao, X.: EvolvableHardware.
        SpringerVerlag, 2006
        Sze V., Chen Y.H., Yang T.J., Emer J.S.: Efficient
        Processing of Deep Neural Networks. Morgan &
        Claypool Publishers, 2020

Než začneme ...

    Název kurzu: Biologií inspirované počítače
        Biologií inspirované-inspiracevětšinou v biologii (s několika výjimkami)
        počítače–bude nás zejména zajímat i fyzická realizace, ne pouze biologií inspirovaný
        algoritmusnaběžném procesoru (o tom pojednávají jiné předměty)
    Termíny „tradiční“,“konvenční“
        budou v tomto kurzu znamenat standardní techniky, přístupy a řešení, která se běžně
        používají v oblasti informatika a výpočetní technika
    Termín „netradiční“
        bude znamenat nejčastěji přírodou (biologií, fyzikou, chemií...) inspirovaný přístup v
        oblasti informatiky a výpočetní techniky, který ještě nepronikl do „mainstreamu“
    Z některých „netradičních“ se stává „mainstream“, např. deeplearning.

https://www.youtube.com/watch?v=B7KdN4PRgj4&t=125s

netradiční řešení konvenční řešení
Pozn.: Různé obory mají různé motivace:
Př. biomedicínské inženýrství vs biologií inspirovaný návrh

    Počítače pomáhají v řadě oblastí lidské činnosti, např.
        urychlení vědeckotechnických výpočtů
        biomedicínské inženýrství, počítačová tomografie, bioinformatika atd.
    V tomto kurzu se budeme ALE primárně zabývat tím, jak by biologie,

chemie a další vědy mohly pomoci vytvořit počítače (SW i HW) s
vlastnostmi, které bychom rádi uvítali a které současné většinou
počítače nemají:

    adaptivní chování, sebeoprava, sebesestavení, samoorganizace, učení,
    „inteligentní design“

Toto jsou typické vlastnosti živých systémů!
Co je to život?

    Co je podstatou života?
        odpovědi dávají různé filozofické a náboženské směry
    Z pohledu biologie je život
        obecná podmínka, která odlišuje organismy od neživých objektů a mrtvých
        organismů.
        soubor signálních a sebeudržovacíchprocesů v těle určitého organismu,
        které zajišťují například látkovou výměnu, dráždivost nebo reprodukci
        [wikipedie]
    Pro život jsou podstatné:
        hierarchickásamoorganizovaná vnitřní struktura
        určitá komplexita a růst
        schopnost samoregulace
            Homeostáza- samočinnéudržováníhodnotynějakéveličinynapřibližněstejnéhodnotě
        metabolismus
        adaptace v závislosti na měnícím se prostředí (evoluce)
        reaktivní chování
        reprodukce
        přítomnost nukleových kyselin a bílkovin

Problém: Je mezek (sterilní
kříženec koně a oslice) živý?
Je virus živý?

Co je to život? (2)

    Ukazuje se, že není možné odvozovat vlastnost „je živý“ u

nějakého systému z elementárních vlastností jeho
komponent (nelze aplikovat redukcionistický přístup).

    Poznámka:
        Redukcionismus– systém lze pochopit tak, že ho rozložíme na
        komponenty a ty budeme studovat - „celeknení „nicnež“ soubor
        částí“
        Holismus je postmoderní učení rozvíjející myšlenku, že „celek je víc
        než souhrn jeho částí“[Aristoteles].
    Život je tedy spíše charakterizován způsobem organizace

systému a vztahy mezi částmi systému.

    To, co chápeme jako „život“, je důsledkem emergentních

jevů.

    Emergence: Vznik globálního chování (tvarů nebo

uspořádání) na základě lokální interakce velkého množství
komponent systému (bez centrálního řízení).
Odkud se bere samoorganizace?

    Samoorganizaceje intuitivně jednoduchý koncept, který je však obtížné obecně
    formálně definovat.
    Samoorganizaceje studována ve fyzice (např. termodynamice), chemii, biologii,
    kybernetice, informatice (evoluční alg., CA, ...), ekonomii, lidské společnosti, ...
    Pokud má systém strukturu a vykazuje organizovanost, musí za to něco
    zodpovídat.
    Klíčovépojmy
        Dynamický nelineární systém
        entropie–míra neurčitosti, neuspořádanosti systému (termín zavedl R. Clausius: EN–
        energie, TROP–měnit (řecky), tj. energie přeměněná na nevyužitelnou = teplo)
    Příklady samoorganizace: všude kolem nás, např. v biologii

(A) Molekuly proteinu v plášti viru, (B) pravidelné uspořádání mikrotubulu pozorované v příčném řezu
ocáskem spermie, (C) povrchové kontury pylového zrna, (D) křídlo motýla fotografované z
bezprostřední blízkosti. Vzorek je tvořen šupinkami, přičemž každá šupinka je produktem jedné buňky.
(E) spirálovité pole semen, utvořené milióny buněk, v květu slunečnice.
http://en.wikipedia.org/wiki/Self-organization
Systém a jeho dynamika

    Systém– množina komponent a množina vztahů mezi komponentami
    Prvky (komponenty) systému
        diskrétní /spojité
        deterministické/ nedeterministické
    Vektor veličin systému (stavový vektor):

x= [x 1 , x 2 , ..., xn](pozor, není tam čas)

    Dynamika systému = vývoj xv čase (z počátečníhostavu)
        Diskrétní systém: x(k+ 1) = f (x(k)) pro k= 0, 1, 2 ...
        Spojitý systém: d/dtx(t) = f(x) pro 0 t 
    Deterministický dynamický systém: fje funkce
        Lineární systém: fje lineární zobrazení, průběhx(k)lze analyticky odvodit,
        lze např. zjistit, kdy je systém stabilní
        Nelineárnísystém: není k dispozici analytické řešení, např. logistický
        model, viz dále.
    Stochastickýsystém –f je pravděpodobnostní rozložení

Stochastické systémy (1)

    Př. Částice plynu v uzavřené komoře
        Stav i-té částice: 6 hodnot [xi, yi, zi, dxi/dt, dyi/dt, dzi/dt]
        Stav celého systému 6 x 6. 1023 hodnot na 1 mol plynu
        Dynamický model: řádově stejný počet rovnic zachování hybnosti
        Nelze s tím pracovat!
    Je potřeba přejít od deterministického

popisu k stochastickému modelu

    Poznámka z teorie pravděpodobnosti
        Distribuce diskrétnínáhodné veličiny X:

P(x) Pr (X = x)

    Hustota spojitén.v.X: f(x)taková, že

Pr (a X< b) = ab f (x) dx
Stochastické systémy (2)

    Zpět k příkladu – částice plynu a stochastický model
        Pomocí hustoty pravděpodobnosti, např.
            Maxwell-Boltzmannovo rozložení rychlosti částic
            pravděpodobnostnírozložení energie částic apod.
    Model může být odvozen experimentálně nebo změřen
    Stochastický model rozložení oproti deterministickému

modelu dynamiky:

    Nerozlišuje stavy xi(t)konkrétních částic v konkrétníchčasech t.
    Pouze poskytuje pravděp. stavu x pro libovolnou částici v čase t.
    Modelem stochastického systému s n stavovými

proměnnými X 1 , X 2 , ..., Xn je

    sdružená hustota f(x 1 , x 2 , ...,xn)pro spojité, resp.
    sdružená distribuce P(x 1 , x 2 , ..., xn)pro diskrétní veličiny.

Entropie ve fyzice

    Boltzmannovaentropie ve statistické fyzice: S= kBln W[JK-^1 ]
        kB = 1,38 · 10−23J·K−1je Boltzmannovakonstanta.
        Př. n = 4 molekuly plynu v izolované nádobě
            Molekula se nachází buď v pravé(R)nebo levé (L) části nádoby
            Mikrostav–konkrétní rozmístění molekul,např. AB:CD, ABD:C, celkem
            2 n(předpoklad: všechny mikrostavyjsou stejně pravděpodobné)
            Makrostav–mikrostavyse stejným počtem molekul v jednotlivých
            částech nádoby.
            Početmikrostavůna makrostav:
            W= n! / (nL!. nR!)

A B D C

        termodynamický zákon
        Entropie izolovaného systému roste při ději
        nereverzibilním a nemění se při
        reverzibilnímději. Entropie uzavřeného
        systému neklesá.
        Nejpravděpodobnější makroskopický stav
        má nejvyšší entropiia odpovídá stavu
        termodynamické rovnováhy.

K ód makro -
stavu

Mikrostavy W P ravděp.
makrostavu
I ABCD:- 1 0,

II ABC:D,ABD:C,
ACD:B,BCD:A

4 0,

III AB:CD,AC:BD,
AD:BC,BC:AD,
BD:AC,CD:AB

6 0,

IV A:BCD,B:ACD,
C:ABD,D:ABC

4 0,

V -:ABCD 1 0,

Suma 2 n= 24 16

    Termodynamická entropie S= Q / T[JK-^1 ]
        makroskopický přístup –změna entropie přidáním nebo odebráním tepla Q
        při dané teplotě T.

Mikrostav: ABD:C

Informační entropie – úvodní příklad

    Př. Nechť částice plynu je buď ve stavu l(levá komora)

nebo p (pravá komora), pakrozlišujeme dva možné
stavy {l, p}.

    Xje diskrétnínáhodná veličina s distribucí P(l)= Pr(X= l),
    P(p) = Pr (X= p).
    Zprávoulresp. pkódujeme výsledek náhodného pokusu,
    tedy zda X= lresp. X= p.
    Jak kvantifikovat množství informaceI(l)resp. I(p)v

takové zprávě?

    V případě max. uspořádaného systému na obrázku platí
    P(l)= 1, tedy stav lje jistý a zpráva nenese žádnou
    informaci I= 0.
    Pro počítání množství informace se hodí logaritmická
    funkceI(s) = -log P(s),protože mj. splňuje požadavek na
    aditivitu, tj. I(a, b) = I(a) + I(b).
    Př. Nechť P(l)= 0,9 a P(r)= 0, 1.
    Pak I(l)= -log 2 0,9 = 0,152 a I(p)= -log 2 0,1 = 3,
    Informační entropie je střední hodnota: H= 0,90,152 +
    0,13,222 = 0,468 bitu

Informační entropie

    V informaticepoužíváme obecnější definici entropie, a tojako průměrné

množství informace potřebné k popisu(tj. odstranění neurčitosti) stavu.

    Nechť systém má konečnou množinu stavů Q ={q 1 , ..., qn}a

pravděpodobnostní distribuci P(qi). Potom je informační(Shannonova)
entropie H(Q)definována jako střední hodnota:

    Pozn.: Formálnědefinujemelog 2 (0)  0 ; Pokudje základ logaritmu 2, je Hv bitech.
    Informaceje úbytek entropie způsobený přijetím zprávy:
    Využití informační entropie: komprese dat, ztrátová funkce cross-

entropyatd.


=

=−

n

i

H Q P qi P qi

1

( ) ( )log 2 ( )
I =Hpred_prijetim−Hpo_prijeti
Vlastnosti informační entropie

    Systém se dvěma stavy P(s 1 ) = p, P(s 2 ) = 1 –p.
    Maximální možnou entropii má systém (o n

stavech), který vykazuje rovnoměrné
rozdělení pravděpodobnosti: H = log 2 n

    Př. Pokud je pravděpodobnost výskytu symbolu v
    abecedě s nsymboly 1/n, pak dostáváme nejvíce
    informace. Zprávy nelze komprimovat. Paradox:
    nejvíce informace obsahuje šum.
    Pozor, informační entropie nekvantifikuje význam či
    užitečnost zprávy.
    Minimálnímožnou entropii má zcela

deterministický systém: H = 0
Teorie disipativních struktur

    teorie popisující a vysvětlující samoorganizaci
    disipativní struktura(termín zavedl I. Prigogine –nositel Nobelovy ceny za chemii v r.

1977) –otevřený dynamický systém, který vykazuje dynamickou samoorganizaci.
Systém neustále generuje entropii, ale entropie je aktivně rozptylována(dissipated) nebo
odváděna ze systému.Takže systému roste míra uspořádanosti.

    To není v rozporu s druhým termodynamickým zákonem, protože se nejedná o izolovaný

systém. Příkladem jsou živé organismy.

    Samoorganizace vzniká v dynamických nelineárních systémech, které jsou daleko od

termodynamické rovnováhy.

Na obrázku vlevo jsou molekuly v
buňce i v okolním vesmíru nakresleny v
poměrně neuspořádaném stavu. Na
obrázku vpravo buňka přijala
energii z molekul potravy a uvolnila
teplo reakcí, která uspořádá molekuly
obsažené v buňce. Protože teplo
zvyšuje neuspořádanost v okolí buňky
(znázorněna klikatými šipkami a
deformovanými molekulami, které
ilustrují tepelný pohyb), je růstem a
dělením buňky splněna druhá věta
termodynamiky.

Vlastnosti samoorganizujících se systémů

    dynamické systémy (vyvíjí se v čase)
    nelineární komponenty
    existují zpětné vazby
    chybí centrální řízení
    jedná se o otevřené systémy, které se nacházejí daleko od stavu

rovnováhy

    vykazují globální uspořádání, které vzniká na základě lokálních

interakcí

    spontánně vznikají nové struktury
    robustnost

Atraktory

    Atraktordynamického systému je množina stavů,
    do kterých systém směřuje. Jedná se o množinu
    hodnot, kterých může nabývat stavový vektor
    dynamického systému po dostatečně dlouhém
    časovém úseku od chvíle, kdy je systém
    inicializován.
    Typy atraktorů:
        atraktorem systému může být množina pevných
        bodů-systém se ustálil v nějakém stabilním stavu
        atraktorem může být množina periodických bodů
        nebo množina kvaziperiodických bodů -systém se
        po určité době ustálí tak, že osciluje mezi několika
        stavy.
        atraktor je chaotický-výsledný stav systému nelze v
        podstatě nijak dopředu předpovědět.
        atraktor je "podivný"(strange attractor) -
        komplikovaný atraktor, který vykazujevlastnosti
        pravidelného, ale současně i chaotického atraktoru.
        Dále platí, že všechny chaotické atraktory jsou
        současně podivnými atraktory (naopak to neplatí).
    Hodnoty stavových proměnných lze zobrazit
    bodem ve fázovém diagramu. Pro kyvadlo je na x-
    ové ose výchylka a na y-ové ose rychlost (tj.
    derivace x).

x

x’

atraktor tlumeného kyvadla

atraktor ideálního kyvadla

-0.

0

0.

1

1.

2

-1 -0.5 0 0.5 1 1.
x

x’

Lorenzův podivný atraktor
dx/ dt= a(y-x)
dy/ dt= x(b-z) -y
dz/ dt= xy-cz
pro a= 10, b= 28, c= 8 / 3

Chaos

    Chaos je z časového hlediska budoucí stav deterministického

dynamického systému, který není předvídatelný v důsledku velké
citlivosti systému na počáteční podmínky.

    V takových systémech se při volbě minimálně dvou nekonečně

blízkých počátečních bodů (reprezentujících počáteční podmínky
systému) tyto dva body posléze exponenciálně vzdalují, takže
budoucí stav systému není možné žádným způsobem předpovědět.

    Typickým představitelem chaotického systému je jakýkoli relevantní

model počasí. I malé změny v počátečních podmínkách vykazují v
budoucnosti dramatické změny

    “Pouhé mávnutí motýlím křídlem v Tokiu může způsobit hurikán ve
    Washingtonu”(tzv. butterfly effect).

Bifurkace (rozdvojení)

    Bifurkace-jev, při kterém dochází k velkým změnám vnitřního stavu

ve sledovaném systému v případě, že se vstupní parametry jen
nepatrně změní.

    Chaosnastává v případě, že v systému začíná docházet k velkému

množství na sebe navazujících bifurkací.

    Bifurkační diagram-nástroj pro studium bifurkace. Na horizontální

osu jsou naneseny hodnoty vstupního parametru ave vertikálním
směru jsou vyneseny hodnoty jednoho z vnitřních stavů, jichž
systém v po sobě následujících krocích nabývá.

    Pro některé vstupní hodnoty je systém stabilizován, pro další hodnoty dochází k
    periodickému překmitávání mezi několika stavy a pro zbylé hodnoty se systém
    chová chaoticky (nepředvídatelně).

Př. Logistická rovnice

Logistická rovnice popisuje velikost populace v následující

generaci k+1(nelineární systém, neexistuje analytické řešení).

Předpokládejme normovanou velikost populace 0 x 1.

parametr růstu úbytek potravy

p = 2 –stabilní stav

p  3 – periodický
průběh s periodou 2

p 3.5 –perioda je 4

p 3.57 –chaotický signál, x(k)
nabude časem všech hodnot z
intervalu (0, 1)

Logistická rovnice – bifurkační diagram

Vodorovně: hodnota parametru p.
Svisle: všechny hodnoty dosažené pro x(k) (k= 0až nekonečno) pro dané p.

Algoritmická entropie

    V logistické rovnici uvažme p=4 a x 0 =0,3
    a generujmebinární zprávu x 1 ’, x 2 ’, ...za
    předpokladu, že xi’= 1pro xi0,5a xi’ =
    0 pro xi< 0,5.
    Lze tuto zprávu zkomprimovat?
    Informační teorieříká, že nelze,protože
    H→1 [důkaz v literatuře].
    Ve skutečnosti zprávu lze zkomprimovat,
    a to jako program, který ji generuje.
    Algoritmickáentropie, též
    KolmogorovskásložitostK(J, Z)zprávy
    (posloupnosti) Z,je délkanejkratšího
    programu(v jazyceJ), kterýgenerujeZ.
    Důležité výsledky:
    Žádná zpráva nemůže být složitější než systém, který ji generuje.
    Určení algoritmické entropie je nerozhodnutelný problém.
    Nelineární dynamické systémy jsou simulovatelné na Turingově stroji
    (vstupní data = počáteční podmínky, ustálený stav = výsledek výpočtu).

Příklad samoorganizace z informatiky:
Celulární automat (CA)

    CA je paralelní výpočetní model s lokální interakcí výpočetních elementů.
    1D uniformní synchronní celulární automat s 3-sousedstvím
        Nbuněk, každá může být ve stavu0 nebo 1, na okrajích je 0
        stav i-té buňky v čase (t+ 1)se počítá pomocí lokální přechodové funkceF:
        Qit+1 = F(Qi-^3 t, Qi-^2 t, Qi-^1 t, Qit, Qi+1t, Qi+2t, Qi+3t,)
    Pomocí CA řešíme úlohu: majorita(N= 149)
        Najdi Ftak, aby po 2Nkrocích byly všechny buňky ve stavu 0, pokud je více nul
        než jedniček v počátečním stavu C0a aby byly všechny buňky ve stavu 1, pokud je
        více jedniček než nul v počátečním stavu C0. (Bude testováno na 10000 náhodně
        zvolených konfiguracích).
    Výpočtem CA rozumíme posloupnost konfigurací c(0), c(1), c(2) ...

0 0 1 0 1 1 0 0 0 1 0 1 1 0

1 i- 3 i- 2 i- (^1) i i+1 i+2 i+3 149
C0
Př. F= xor
C1 0 0 0 0 1 1 1 1 1 0 0 1 0

Výpočet se provede paralelně pro všechny buňky
1
Emergentní chování celulárního automatu

    Neexistuje F, které řeší
    problém majority perfektně.
    Nejlepší známá F má
    úspěšnost max. 86%.
    Emergentní vlastnost CA:
        Schopnost vyřešit globální
        problém (je víc jedniček nebo
        nul?) pouze na základě lokální
        interakce!
    Významné funkce F:

C0

C0 obsahuje více „1”

Příklady běhů CA pro dvě C0 (N= 149 )

čas
C297

C0 obsahuje více „0”

Log. 0 znázorněna bílou, log. 1 černou barvou

Tradiční umělá inteligence

    je založená na návrhovém přístupu „shora-dolů“
        dekompozici, formální logice, reprezentaci znalostí ...
        takto ale biologicky „inteligentní“ řešení vytvořena nebyla
    je velmi úspěšná v případech, kdy je problém dobře

formálně popsán

    Př. Šachy -počítač DeepBlueporazil mistra světa v šachu
    Kasparova(1997)
    Pozn. Hra Go – špičkové úrovně dosaženo pomocí hlubokých
    neuronových sítí až v r. 2016 (ne tradiční umělou inteligencí!)
    nefunguje dobře pro neurčitě definované problémy
    Př. Vytvoř řízení pro humanoidního robota tak, aby uměl vyjít
    schody.

Výpočetní inteligence

    Výpočetní inteligence (computationalintelligence) nebo také soft-computingje
    rychle se rozvíjející oblastí umělé inteligence.
    Soft computing(Zadeh1995, volný překlad doc. Zbořila): Soft computingje, na
    rozdíl od tradičního hard computing , zaměřen na akceptování všudypřítomné
    nepřesnosti reálného světa. Základním principem je využití tolerance
    nepřesnosti, nejistoty a částečné pravdivosti pro dosažení ovladatelnosti,
    robustnosti, nízké ceny řešení a lepšího vztahu s realitou. Funkčním modelem
    soft computing je lidská mysl.
    - Výpočetní inteligence se inspiruje procesy, které můžeme pozorovat v přírodě a ve
    společnosti, snaží se je napodobit pro řešení obtížných problémů.
    Inspirace v procesech:
        Fylogeneze–evolucegenomu
        Ontogeneze–vývin mnohobuněčného organismu
        Epigeneze–interakceorganismu s prostředím pomocí učení (nervový systém,
        imunitní systém a endokrinní systému)
        a v dalším, např. lidské společnosti, kolonií interagujících agentů, usuzování
        jedinců, konfliktů predátor-oběť, systémů na hraně mezi chaosem a řádem

Výpočetní inteligence (2)

    Oblasti výpočetní inteligence
        umělý život
        neuronové sítě
        evoluční algoritmy
        fuzzy systémy
        celulární automaty
        membránovépočítání
        a jiné
    V mnoha případech se jedná o tvorbu algoritmů s inspirací v přírodě,

které potom běží na běžných procesorech. Na základě těchto jevů tedy
vytváříme výpočetní modely.

    Existují akcelerátory těchto algoritmů pro FPGA, GPU i ASIC.
    Natural computing (počítání podle přírody) zahrnuje
        soft computing(computational intelligence)
        nekonvenční počítače

Nekonvenční počítače

    Biologické, chemické, fyzikální a jiné přírodní jevy přímo fyzicky realizují
    výpočet.
    - Realizace není nutně založena na použití polovodičů.
    Příklady
        Molekulární výpočty –počítání přímo s molekulami
            DNA počítání
            Počítání s kapalnými krystaly
            aj.
        Syntetická biologie
        Kvantové počítače
        Optické počítání
        Chemické počítače
        Analogové počítače
        Reakčně-difúzní chemické systémy
        Mechanické počítání
    Pro určitou třídu úloh představují efektivní řešení
        Např. na kvantovém počítači nebo DNA počítači lze řešit určité NP problémy v
        polynomiálním čase
    Zkoumány zejména v souvislosti s nástupem nanotechnologií –jako nové
    potenciální výpočetní platformy pro jistou specifickou třídu úloh.

Důležitost fyzického těla
(Embodied intelligence)

    Pro výpočet je klíčová fyzikální podstata výpočetního systému a

existence reálného prostředí, se kterým tento systém interaguje.

    Teprve „tělo“ ve spolupráci se „smysly“ a „mozkem“ umožňuje poznání

(sémantiky) světa, umožňuje imitační učení, pohyb agenta, jeho
interakci s jinými agenty.

    Pouhá SW simulace je nepostačující!!!
    Př. Autonomní řízení robota v reálném prostředí
        simulátor robota a prostředí nedává shodné výsledky jako reálný
        experiment

Literatura

    viz literatura na začátku přednášky + odkazy na slidech
    Tišnovský, P.: Fraktály v počítačové grafice III.
        http://www.root.cz/clanky/fraktaly-v-pocitacove-grafice-iii/#k02
    Mařík V.: Kybernetika a umělá inteligence, FEL ČVUT, 2007
    Informace, entropie a fyzika
        http://popelka.ms.mff.cuni.cz/~lessner/mw/index.php/U%C4%8Debnice/Informace/Informace,_en
        tropie_a_fyzika
    Následuje doplňující materiál – další příklady

emergence v IT
Tierra – umělý život a emergence (r. 1991)
https://en.wikipedia.org/wiki/Tierra_(computer_simulation)

    Tierrapředstavuje virtuální počítač s darwinovským operačním systémem,

jehož architektura byla navržena tak, že spustitelný kód je evolvovatelný.

    To znamená, že strojový kód může být mutován a rekombinován. Do systému

byl vložen program, který byl schopen vytvořit vlastní kopie. Evolucí vznikly
další programy z těchto původních programů.

    OS provádí správu paměti, poskytuje prostředky pro sdílení CPU a udržuje

informaci o parametrech, např.: čas vytvoření a smrti programu, dostupná
paměť a čas CPU pro jedince apod. Programy využívají přidělený čas k tomu,
aby se množily.

    Vznikl tak syntetický organismus, kde čas CPU představuje zdroj energie a

paměť představuje materiální zdroje. V systému funguje přírodní výběr,
vznikají noví jedinci. Jedinci vznikající v systému soutěží o tyto zdroje. V
systému vznikly ekologické komunity. Bylo možné pozorovat evoluční závody
ve zbrojení, vznik parasitismu a další jevy, které známe z přírody.

    Tierra -Evolutionary race between hosts and parasites in a soup of the Tierra Synthetic Life program developed by
    Tom Ray. Each image represents a soup of 60,000 bytes, divided into 60 segments of 1000 bytes each. Each
    individual creature is represented by a colored bar, colors correspond to genome size (e.g., red = 80, yellow = 45, blue
    = 79)

1) Hosts, red, are very common. Parasites,
yellow, have appeared but are still rare. 2) Hosts, are now rare because parasites have become very common. Immune hosts, blue, have appeared but are rare

3) Immune hosts are increasing in frequency, separating the
parasites into the top of memory.

4) Immune hosts now dominate memory, while parasites and
susceptible hosts decline in frequency. The parasites will
soon be driven to extinction.

Evoluční schovávaná (r. 2019)

https://openai.com/blog/emergent-tool-use/

Samostatní agenti (řízení neuronovou sítí)
se pohybují a mají k dispozici:

    zrak –vidí, co je před nimi, pokud to není
    za překážkou
    orientaci v prostoru –každá postavička
    ví, jak daleko je nejbližší překážka
    pohyblivé objekty –postavičky mohou
    chytit, přemístit a pustit objekt
    zámky –postavičky mohou zamykat
    objekty
    Modří jsou schovávači a jsou červení
    hledači.

Swarm robots(sbots) –inspirace v chování hmyzu:

Samoorganizujícíse a samosestavujícíse formace robotů

(2001 -2005) http://www.swarm-bots.org/

sestavení formace nutné k odtažení oběti

sestavení formace nutné k
překonání terénní nerovnosti
