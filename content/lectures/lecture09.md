Neurální hardware
Biologií inspirované počítače
Přednáška 9
Lukáš Sekanina
FIT VUT v Brně
2026
Témata přednášky

    Složitost a energetická náročnost DNN
    HW akcelerátory DNN
    Optimalizace inference DNN

FIT VUT v Brně 2
Populární CNN (do r. 2017)

FIT VUT v Brně Sze et al, Proc. of the IEEE 2017 3

Toto je nutné provést při jedné inferenci!

Vývoj CNN klasifikátorů pro ImageNet

FIT VUT v Brně https://arxiv.org/abs/2101.09336 4

ResNet- 50 :
25,5 mil. parametrů (vah)
3,9 miliard operací MAC/inferenci

AI a „memory wall“

FIT VUT v Brně Source: Amir Gholami et al. AI and Memory Wall. Published in IEEE Micro Journal 2024. 5
CNNs
Cena za AI

FIT VUT v Brně 6
Inference:

Sam Altman, OpenAI: How much
energy a ChatGPTquery uses:
The average query uses about 0.
watt-hours, about what an oven would
use in a little over one second, or a
high-efficiency lightbulb would use in a
couple of minutes. It also uses about
0.000085 gallons of water; roughly one
fifteenth of a teaspoon.
https://blog.samaltman.com/the-gentle-
singularity

Typická služba: 1 milion
odpovědí (50 - 200 kWh) denně

Zdroj: ChatGPT 5

TrénováníLLM:
Emise způsobené DNN

FIT VUT v Brně https://arxiv.org/abs/1906.02243 7

Transformer–automated
architecture search and
training (2019)

Mozky vs ANN

FIT VUT v Brně 8

20 W

Cesta k energeticky účinnějším NN

FIT VUT v Brně 9

K. Roy, AxC 2019

Common
HW
HW pro strojové učení

FIT VUT v Brně 10

Reuther A. et al. arxiv.org/pdf/1908.11348.pdf

ValpredaE. 2024

Top HW pro AI 2024- 2025

FIT VUT v Brně https://www.servethehome.com/cerebras-enters-ai-inference-blows-away-tiny-nvidia-h100-gpus-by-besting-hbm/ 11

2024:Superpočítač
CerebrasCS- 3 :TSMC 5 nm
technologii, 4 biliony
tranzistorů, 125 petaflops,
900 000 jader.
20x rychlejšína Llama3.1-
8B vsMicrosoft Azure
cloud sčipy NVIDIA H100.

2025:CloudGoogle TPU v5p
8960 TPUv5 chips
propojení 3D torus

https://cloud.google.com/tpu/docs/v5p

Top HW pro AI 2026

FIT VUT v Brně https://taalas.com/products/ 12

2026:TaalasHC1 Technology
Runs Llama 3.1 8B model
TSMC 6nm | 815mm2 | 53B Transistors
2.5 kW Server

Llama 3.1 8B model je implementován
na čipu tak, že váhy jsou přímo součástí
výpočetního HW, nenačítají se z paměti.
Akcelerátorinference má extrémní
propustnost, nízký příkon, ale není
programovatelný.

HW akcelerátory pro inferenci CNN

FIT VUT v Brně 13

Výkonnost: počet inferencí za sekundu
Energetická účinnost: počet inferencí za Watta sekundu

Měřeno pro AlexNet

Akcelerátor CNN na baterie

    Smart Glasses (pro rozpoznávání) [K. Roy, DDECS21]
        Google EdgeTPU
        RetinanetDNN (300.10^9 operací / inferenci –dáno
        architekturou DNN)
        Video: 13, 3 frame/ s
        Energie / operaci: 0,5 pJ(dánotechnologiíTPU)
        Akumulátor: 2,1Wh= 7560 Ws
    Energie/frame: 300.10^9 * 0,5. 10 -^12 = 0.15 J
    Energie/s: 0,15 * 13,3 = 1,995 J (pozn. J = Ws)
    Doba provozu: 7560 / 1,995 = 3789,5 s ~ 63 min.

FIT VUT v Brně 14

Obrázek jen pro ilustraci, nesouvisí s
příkladem.

Apple Vision Pro
ČipM2 poskytuje
bezkonkurenční výkon,
zatímco zbrusu nový čip
R1 zpracovává vstupy z
12 kamer, 5 senzorů a 6
mikrofonů, aby zajistil,
že se obsah zobrazuje
přímo před očima
uživatele v reálném
čase. R1 přenáší nové
obrazy na displeje
během 12 milisekund –
8x rychleji než mrknutí
oka. Apple Vision Pro je
navržen pro celodenní
používání při zapojení
do sítě a až
dvouhodinové používání
s externí výkonnou
baterií. (alza.cz, 2024)

Akcelerátory CNN

FIT VUT v Brně 15

    CPU

https://cloud.google.com/blog/products/ai-machine-learning/what-makes-tpus-fine-tuned-for-deep-learning

    GPU

Akcelerátory CNN

FIT VUT v Brně https://cloud.google.com/blog/products/ai-machine-learning/what-makes-tpus-fine-tuned-for-deep-learning 16

    HW architectura–systolické pole
    Step 1: loading kernel Step 2: loading data and then passing

Výhody

    výkonnost
    redukovaný přístup do paměti
    nízký příkon

Nevýhody

    nízká flexibilita
    ASIC –drahý návrh, produkce
    složité plánování operací

Akcelerátory CNN

FIT VUT v Brně 17

CPU a GPU
(pro učení i inferenci)

ASIC a FPGA
(prakticky jen pro inferenci)

Principyakcelerace (redukce příkonu):

    Maximalizovat paralelní výpočet a
    znovupoužití mezivýsledků (to lze dobře
    zejména u “spatial architectures”)
    Minimalizovat komunikaci s (externí)
    pamětí.
    Aproximacevýpočtu

PE –
Processing
Element

Automatizovaný HW/SW codesign pro CNN

FIT VUT v Brně 18

Kromě struktury natrénované DNN (tj.
vč. vah) a popisu architektury
akcelerátoru je potřeba dodat
informace o energetické náročnosti
elementárních operací, například pro
čtení z paměti.
Výpočet CNN je obvykle plánován po
vrstvách.

Eyeriss(MIT, 2016)

Červeně v závorkáchje pro představu uveden obdobný proces -kompilace programu pro procesor.

Typické strategie organizace datových toků

FIT VUT v Brně 19

Stacionární váhy – váhy jsou načteny do registrů
PE a jsou tam ponechány, dokud jsou k dispozici
nějaké vstupy (Act)přicházejícíz paměti. Výstupy
jsou postupně akumulovány v různých PE.
Minimalizuje energii nutnou pro čtení vah.
Stacionární částečné součty – v registrech PE jsou
uchovány částečné součty s cílem snížit energii pro
jejich načítání a ukládání. Váhy a Actjsou načítány z
paměti do PE. Actpostupně prochází různými PE.

Bez lokálního znovupoužití – nepoužívá lokální
registry, intenzivně je využíván globalbuffer, které je
zvětšen s cílem minimalizovat přístup do externí
paměti.

Stacionární řádek – cílem
je maximalizovat znovu-
použití všech dat. Příklad
na obrázku je pro 1D
konvoluci ve 3 krocích.
Zobecnění: Systolické 2D
pole

Př. Optimalizace datových toků a paměti

FIT VUT v Brně ValpredaE. 2024 20
Predikce vlastností dané DNN v HW
akcelerátoru

FIT VUT v Brně 21

Př.
Existuje 480 tisíc různých
namapovánívýpočtu
vrstvyVGG_conv3_2 na
HW akcelerátor Eyeriss.

SW nástroje např. Timeloopa
Accelergyumožňují s malou
chybou predikovat HW
parametry (příkon, latence,
...) zadané DNN pro HW
akcelerátor, jehož HW
architektura je specifikována
(podpora různých technologií
výroby čipu).
Timeloop hledá nejvýhodnější
namapováníDNN na
specifikovaný HW.

Akcelerátor Eyeriss (MIT, 2016)

FIT VUT v Brně

AlexNet

Nejvíce energie
spotřebuje paměťový
subsystém a přenos dat!
22

Optimalizace v HW akcelerátorech CNN

FIT VUT v Brně 23

    Aproximacemi rozumíme takové zjednodušení HW nebo SW, které vede na
    přijatelnou chybu výpočtu při významném snížení příkonu nebo latence.
    Optimalizace CNN probíhá s ohledemnebo bez ohleduna akcelerátor
    Přístupy
        Zjednodušené datové typy a
        kvantizace(další slide)
        Aproximace aritmetických operací
        (zejména násobení)
        Aproximace paměťových buněk a
        přístupu do paměti
        Odstranění méně důležitých
        neuronů či propojení(pruning)
        Sdílení a komprese vah

MAC

Afinní kvantizace

FIT VUT v Brně 24

    Př. Zobrazujeme xz FP32 v intervalu <, > načísloQv INT 8 , přičemž

0 se zobrazí obecně na z. Přesnost INT8 je b= 8 bitů.

𝑓 𝑥 = 𝑠∙𝑥+𝑧

𝑠 =

2 𝑏− 1
𝛼−𝛽

z=−round 𝛽∙𝑠 − 2 𝑏−^1

clip (x, , ) = ቐ

𝛽,𝑥 <𝛽
𝑥,𝛽 ≤𝑥 ≤ 𝛼
𝛼,𝑥 >𝛼

𝑄 = clip(round 𝑓 𝑥 ,− 2 𝑏−^1 , 2 𝑏−^1 − 1 )

FP32

FX8

Afinní transformace:

Scale:

Zero:

    Př. 𝑥= 1 ;𝑏= 8 ; 𝛽 =− 3 ; 𝛼 = 4 ; 𝑠=^2557 =36,43
    𝑧=−round − 3 ∙ 36 , 43 − 128 = − 19 𝑓 1 = 36 , 43 ∙ 1 + − 19 = 17 , 43
    𝑄(𝑥= 1 ) = 17

Datové typy v akcelerátorech CNN

FIT VUT v Brně 25

    Ovlivňují:
        přesnost
        výkonnost
        plocha na čipu
        příkon
        velikost paměti vah
    Jak se typickypoužívají
        (1) trénování je vFP; (2)
        datový typ je následně
        zjednodušen u
        vybraných částí NN (FX
        pro váhy ...);(3)
        dotrénování (fine-
        tuning) CNN s cílem
        eliminovat chybu
        lze i přímo trénovat NN
        s kvantizovanými
        vahami (quantization-
        aware training)
        - Floating point(32 bit)
        - Minifloat, např. 8 bit vRistretto
        - Uniform Fixed Point( m bitů před a n bitů

za řádovou čárkou)

    Dynamic Fixed Point( b , f )
        b - bitováhodnota se interpretuje:
        kde f je počet bitů za řádovou čárkou, s je
        znaménkový bita xi jsou jednotlivé bity
        čísla.
        Různé vrstvy NN (i různé části vrstvy)
        mohou použít různé hodnoty f
    Kvantizacena mocniny 2
        Pouze pro váhy, ostatní hodnoty se
        počítají v nějaké variantě FX
    Binární/ternární reprezentace
        Pouze pro váhy, ostatní hodnoty se
        počítají v nějaké variantě FX

Aproximativní násobičky v ResNet

FIT VUT v Brně 26

All exact 8-bit multiplications of all convolutional layers of ResNet- 26 were replaced with
one approximate implementation. Repeated for 3 5 different approximate 8-bit multipliers
to identify the besttradeoffs between the Accuracy on CIFAR-10 and Energy [Pinoset al
IEEE JETCAS 13(1), 2023].

*

+
8

N
8+N

    Vylepšení
    kompromisu přesnost vs
    energie
    Redukcepaměti vah

WEIGHT, N = {8, 7, 6, 5, 4}

FIT VUT v Brně 27
Literatura

    Sze, V., Chen, Y., Yang, T., Emer, J.S.: Ecientprocessing of deep neural networks: A
    tutorial and survey. Proceedings of the IEEE 105(12), 2295{2329 (2017)
    SekaninaL.: Neural Architecture Search and Hardware Accelerator Co-Search: A
    Survey. IEEE Access, Vol. 9, 2021, p. 151337- 151362
    Banzhaf W., Machado P., Zhang M.: Handbook of Evolutionary Machine Learning,
    Springer, 2023
    ValpredaE. Hardware/Neural Network Codesign for Energy-Efficient Inference on Edge
    Devices with Optimal Mapping and Compression. PhD Thesis, Politecnicodi Torino,
    2024
    PinosM., Mrazek V., VaverkaF., VasícekZ., SekaninaL.: Acceleration Techniques for
    Automated Design of Approximate Convolutional Neural Networks. IEEE J. Emerg. Sel.
    Topics Circuits Syst. 13(1): 212-224 (2023)
    dalšíodkazyna slidech
