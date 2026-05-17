Neuronové sítě a
neuroevoluce
Biologií inspirované počítače
Přednáška 8
Lukáš Sekanina
FIT VUT v Brně
2026
Témata přednášky

    Úvod do problematiky umělých neuronových sítí
    Přehled vybraných hlubokých neuronových sítí
    ML a EA
    Neural architecture search a neuroevoluce

ACM named YoshuaBengio, Geoffrey Hinton, and Yann LeCunrecipients
of the 2018 ACM A.M. Turing Awardfor conceptual and engineering
breakthroughs that have made deep neural networks a critical component
of computing.
Motivace

    Mozek je jeden z nejkomplexnějších systémů vůbec
        „synonymum pro inteligenci“
        Není přesně známo, jak funguje, ale probíhá intenzivní multidisciplinární
        výzkum (neurologie, psychologie, IT, ...) –The Human Brain Projectv EU
        Z inženýrského pohledu je zajímavá také výkonnost a energetická účinnost
        (lidský mozek ~ 20 W)
    Vzniká v procesu vývoje organismu (ontogeneze) a formuje se v

procesu učení (epigeneze)

    Činnost mozku je inspirací pro umělou inteligence už od jejího vzniku
        Konekcionismus–směr bádání, který postuluje, že podstata inteligence
        spočívá v propojení velkého počtu jednoduchých neuronů a emergenci
    Pro srovnání – velikosti mozků
        Člověk: 50 –100 miliard neuronů; kočka: 76 0 mil.; myš: 71 mil.
        Včela: objem cca 1 mm^3 ; hmotnost1 mg, 950 tisícneuronů. Umožňuje
        řízení letu, rozpoznávání, navigaci, komunikaci...Odhad spotřeby energie:
        10 -^15 J/op, což je cca milionkrát méně než současná číslicová technika

Biologický neuron

    V lidském mozku je 50-100 miliard
    neuronů (1450 cm^3 , 1,3-1,4 kg, 10^15
    synaptických spojení, 20-25 W).
    Neuron-vysoce specializovaná
    buňka, schopná přijmout, vést,
    zpracovat a odpovědět na speciální
    signály (elektro-chemicky)
    Dendrity-reprezentují místa vstupu
    signálů do těla neuronu.
    Tělo buňky (soma)–„sčítá“ signály
    dané okolními neurony. Takto
    stanovený vnitřní potenciál vede k
    excitaci (vybuzení) neuronu.
    Axonové vlákno(až 1 m) přenáší
    signál daný stupněm excitace k
    synapsím.
    Synapsetvoří výstupní zařízení
    neuronů (200 –10000 na neuron). http://cs.wikipedia.org/wiki/Synapse

Umělé neuronové sítě

    ANN vzniknepropojenímumělých neuronů (a popř. dalších prvků) do

sítě

    ANN využívají distribuované a paralelní zpracování informace při

provádění výpočtů

    Znalosti jsou ukládány především prostřednictvím síly vazeb mezi

jednotlivými neuronya v topologiisítě

    Konstrukce ANN
        Jaký typ sítě a typ neuronu zvolit, kolik neuronů, jak neurony propojit, jak nastavit
        váhy(jak síť naučit, co má dělat), kolik trénovacích vektorů použít ...
    Typické aplikace
        Přírodovědné: studiu principů činnosti mozku, medicína
        Inženýrské –v IT: rozpoznávání, klasifikace, predikce, řízení, funkční aproximace,
        komprese, asociace

Umělý neuron

Funkce neuronu: Přesáhne-li suma xiwi
prahovou hodnotu b,aktivuje neuron výstup.
Pokud jsou správně nastaveny váhy, dokáže
jeden neuron rozlišit lineárně separovatelné
třídy.

bázová funkce

váhy práh(bias)

vstupy^

w 1
w 2

wn

x 1

x 2

xn

x 0 = 1

w 0 =−

𝑧= ෍

𝑖= 1

𝑛
𝑤𝑖𝑥𝑖+𝑏=෍
𝑖= 0

𝑛
𝑤𝑖𝑥𝑖

𝑓 𝑧 =
1

1 +e−𝑧

n= 2
http://playground.tensorflow.org/

f
Nelineárníaktivační funkce f:

    např. sigmoida, více viz další slide

w 1 x 1 + w 2 x 2 + b= 0

b

z
Aktivační funkce

    Umožňuje omezit výstup
    neuronu, typicky na interval
    <0,1> nebo<-1,1>.
    Skokováaktivační funkce,
    kterou využíval jeden z prvních
    typů neuronu (tzv. perceptron),
    vede na obtížné učení, protože
    malé změny vah nemají často
    žádný dopad na výstup neuronu
    (neuron je rychle saturován).
    ReLU–dnes často používaná
    aktivační funkce, protože je
    jednoduchá a vede na rychlé
    učení.
    Aktivační funkce musí být
    nelineární a musí mít derivaci,
    aby bylo možné použít
    algoritmus učení založený na
    gradientním sestupu.

Učení s učitelem (příklad)

Učení s učitelem: Optimalizační problém -hledání hodnot w 1 , w 2 a b
tak, aby chyba výstupu byla co nejmenší pro zadaná trénovací data.
Současně požadujeme schopnost generalizovat–produkovat správné
výsledky i pro data, která nejsou v trénovacímnožině.

Trénování sítě (zjednodušeně):

    Náhodně nastav w 1 , w 2 a b
    Vyber i(x 1 , x 2 )z TD a vypočti y
    Pokud je yvypočteno správně, nedělej nic,
    jinak uprav w 1 , w 2 zvolenou adaptační metodou.
    Opakuj kroky 2 a 3, dokud nejsou TD klasifikována
    správně nebo nevyprší časový limit.

x 1

x 2

b

w 1

w 2

Požadovaný výstup (klasifikace do 2 tříd):
y= +1, pokud (xi 1 , xi 2 ) A
y= - 1 , pokud (xi 1 , xi 2 ) B

Trénovacídata(TD):
i: x 1 x 2 třída
1: 0.3 0.4 A
2: 0.2 0.4 A
3: 0.1 0.5 B
4: 0.8 0.7 A
5: 0.6 0.8 B
atd.

x 2

x 1

B
A
Různé typy ANN

    Existují různé typyANN, pro každou úlohu se hodí něco jiného, např.
        vícevrstvásíť, Hopfieldovasíť, Kohonenovysamoorganizujícíse mapy, sítě s
        radiálními bázovými funkcemi, DNN ...
    Př.SpikingNN – biologicky více realistické
        časované sítě, pracují s pulzy
        analogové i digitální verze
        neuromorphiccomputing(nízký příkon)
    Př. Vícevrstvá dopřední síť
        Oproti 1 neuronu dokáže realizovat libovolné spojité zobrazení z mrozměrného
        vstupního vektorového do nrozměrného výstupního prostoru s libovolnou přesností.

2 skrytéplně
propojené vrstvy

vstupní vrstvapro
uložení vstup. vektoru

výstupní vrstva
se 2 neurony

Vícevrstvá dopřední síťs
organizací 3- 4 - 3 - 2

Vícevrstvé dopředné sítě

    Obsahují sekvenci plně propojených vrstev bez zpětných vazeb
    Plně propojená vrstva – každý z kneuronů této vrstvy je připojen ke

všem mneuronům předešlé vrstvy (celkemkm vah a kbiashodnot na
vrstvu, které jsou předmětem učení)

    Pokud ANN má pracovat jako klasifikátor do C tříd, pak výstupní vrstva

obsahuje C neuronů a každý z nich udává pravděpodobnost třídy 1 ,..,C.
K tomu se v poslední vrstvě používá tzv. Softmax aktivační funkce:
𝑦 𝑧𝑖 =
𝑒𝑧𝑖
σ𝑗𝐶= 1 𝑒𝑧𝑗
Ztrátová funkce

    Dopředný výpočet ANN (pro jedenvstupní vektor) se nazývá inference.

Natrénovaná ANN, která je nasazena v nějaké aplikaci, provádí pouze
inference.

    Učení (trénování) za pomocitrénovacích dat, vyžaduje stanovení chyby,

zpětný průchodANN a úpravu vah.

    Ztrátová funkce (lossfunction, costfunction) vyjadřuje aktuální chybu

sítě během trénování. Často se používá střední kvadratická chyba, kde
tje očekávaný výstup, o aktuální výstup a n je počet výstupních
neuronů.

    Další možnosti: cross entropy
    Ztrátováfunkce musí být derivovatelná.

Gradientní sestup a zpětné šíření chyby

    Učení je nejčastěji založeno na hledání minima ztrátové funkce pomocí

gradientního sestupu(gradient descent).

    Váhy se inicializují na malé náhodně generované nenulové hodnoty.
    Minimalizace je realizována úpravou učitelných parametrů sítě, která je

založena na pohybu v opačném směru ke gradientu ztrátové funkce E.
Úprava váhy také závisí na koeficientu učení .

    Zpětné šíření chyby (backpropagation) a úpravy

vah se provádí ve směru od poslední k první vrstvě.

    K úpravě vah dochází po zjištění chyby buď
        pro každý jeden vektor z trénovací množiny nebo
        pro všechny vektory trénovací množiny nebo
        pro náhodně vybranou podmnožinu (batch) trénovacích vektorůpevnévelikosti –
        tento postup se nazývá stochasticgradient descenta je dnes nejpoužívanější
    Epocha –jeden cyklus učení, ve kterém byly zpracovány všechny

trénovací vektory

gradient
počáteční váha
krok

globální
lokální opt. optimum
w

E

’

Př. Klasifikace obrazů
Hluboké neuronové sítě - inspirace v mozku

    V lidském mozku existuje hierarchie vrstev neuronů, které z vizuálního vstupu
    postupně extrahují jednoduché prvky, z nich rozpoznávají tvary, dále objekty a
    nakonec složité útvary jakými jsou např. obličeje.
    Inspiraci zde nacházejí hluboké konvoluční neuronové sítě.

Lateral Geniculate Nucleus(LGN) –spojenízrakovéhonervudo týlníholaloku
Herzog, Michael & Clarke, Aaron. (2014). Why vision is not both hierarchical and feedforward. Frontiers in computational
neuroscience. 8. 135. 10.3389/fncom.2014.

Hluboké neuronové sítě (Deep Neural Networks)

    DNN jsou velké neuronové sítě s až tisíci vrstvami
    Dnes nejúspěšnější metodastrojové učení – klasifikace, predikce,

rozpoznávání přirozeného jazyka, hraníher, samořiditelná auta ...

    Implementace pro CPU, GPU, FPGA, ASIC, superpočítače, i jako

vzdálená služba pro zákazníky

    Bohatý SW/HW ekosystém -TensorFlow, Keras, PyTorch...
    Hlavní principy
        velkáNN s mnoha vrstvami
        NN se naučí z dat, jak reprezentovat hierarchii v datech -netřeba

ručně konstruovat příznaky(tzv. “features”) pro trénování.

    Př. Konvoluční neuronové sítě(CNN)
        Poprvé představil LeCun, 1998
        ImageNet Challenge(klasifikace obrazů)
        1,2 mil. trénovacíchobrazů
        1000 kategorií

CNN pro klasifikaci obrazů

Sze et al, Proc. of the IEEE 2017

Normalizace
hodnot na
(=0, =1).
Pooling(subsampling)

Fully Connected layer

Konvoluční vrstva

vstupní příznaková mapa (ifmap) výstupnípříznaková mapa (output feature map, ofmap)

filtr(kernel)

padding

    Konvoluční vrstvy nahrazují plně propojené vrstvy s
    cílem extrahovat důležité příznaky a snížit počet vah.
    Na vstupní data je aplikováno k(naobr. k = 1 )
    konvolučních filtrů.Jakovýsledek konvoluce vznikne k
    příznakových map(ofmap)na které jsou aplikovány
    aktivační funkce.
    Konstanty ve filtrech a biastvoří trénovatelné
    parametry CNN v této vrstvě.
    stride–určuje, o kolik pixelů se posunejefiltr (na obr.
    je stride= 1).

Konvoluční vrstva (3 kanály)

    Při zpracování RGB obrázku používá konvoluční
    vrstva pro vytvoření jedné příznakové mapy tři kanály
    (R, G, B) a trojici filtrů. Tyto filtry je možná chápat jako
    3D filtr.

Konvoluční vrstva - zobecnění

O–output featuremap(ofmap)
I-input featuremap(ifmap)
W–filters
B–biasses
Uis a given stride size
N–počet 3D vstupů (batchsize)
M-počet 3D filtrů/ kanálůofmap
C-počet ifmap/kanálů(filtrů)
H/W–výška/šířka ifmap
R/S–výška/šířka filtru
E/F–výška/šířkaofmap

Sze et al, Proc. of the IEEE 2017)

CNN: LeNet

    LeNetpro klasifikaci obrazů
    http://yann.lecun.com/exdb/lenet/index.html
    Využita pro klasifikaci ručněpsaných
    ZIPkódů na poštovních obálkách US
    PostalOffice ještě před nástupem éry
    DNN.
    7 vrstev
    Vstup: 32x32 černobílých hodnot
    Výstup: 10 tříd (‘0’ –‘9’)

LeNet – počet parametrů (vah)

Dosahujecca 99 %přesnosti
klasifikace na MNIST (60 tis.
trénovacích a 10 tis.
testovacích ručně psaných
číslic)

6 x 5x5 x 16 + 16 (bias) = 2416

Další vylepšení CNN

    InicializaceCNN – použití normálního rozložení při náhodném

generování vah vede na rychlou saturaci neuronů. Proto se používají
jiná rozložení, např. Xavier Glorot.

    Batchnormalization – přepočet distribuce výstupů v předchozí vrstvě

tak, aby se blížily normálnímu rozdělení.

    Dropout– náhodně zvolené procento neuronů v každé vrstvě se

neúčastní trénování (vede na lepší schopnost generalizovat)

    Residuální bloky – zlepšují trénování velmi hlubokých sítí
    atd.

Populární CNN (do r. 2017)

Sze et al, Proc. of the IEEE 2017

Toto je nutné provést při jedné inferenci!
Vývoj CNN klasifikátorů pro ImageNet

FIT VUT v Brně https://arxiv.org/abs/2101.09336 24
Vision Transformers

“Inspired by the Transformer scaling successes in NLP, we experiment withapplying a standard
Transformer directly to images, with the fewest possiblemodifications. To do so, we split an image
into patches and provide thesequence of linear embeddings of these patches as an input to a
Transformer.Image patches are treated the same way as tokens (words) in an NLP application.We
train the model on image classification in supervised fashion.”(Dosovitskiyet al., 2020)
Sítě kodér-dekodér pro překlad
Kodér

(rozbaleno)

Dekodér (rozbaleno)

Základemje RNN-RecurrentNeuralNetwork, popř. LSTM - Long Short-TermMemory
Kodér–sekvenčně konvertuje vstupní sekvenci tokenů na 1D (skrytý) vektor
Dekodér–sekvenčně vytváří výstupní sekvenci s využitím 1D (skrytého) vektoru
Skrytý vektor -zapouzdřuje informace o všech vstupech.
Modely kodér-dekodér jsou společně trénovány tak, aby maximalizovaly podmíněné
pravděpodobnosti cílové sekvence vzhledem ke vstupní sekvenci.
Nevýhody:

    Sekvenční povaha vedena pomalé učení, obtížně paralelizovatelné.
    Při kódování a trénování dlouhých sekvencí dochází ke ztrátě informace.

Transformery a mechanismus pozornosti

Attention Is All You Need (Vaswani et al, NIPS 2017)

Jak modelovat
závislosti/pozornosti
(attention) mezi tokeny
na vstupu? Jak to
nedělat sekvenčně?

Kodér Dekodér

it

„it“ attends to „animal“ and „street“ with the highest probability.

Self-attention: ohodnocení důležitosti tokenu

FIT VUT v Brně https://jalammar.github.io/illustrated-gpt2/ 28

Query:Je reprezentaceaktuálníhotokenu, klteráse používák porovnáníse všemiostatnímitokeny.
Key: Reprezentuje token při operaci porovnání.
Value: Skutečnáreprezentacetokenu, vzniká součinem se skóre (relevancí) a součtem s ostatními.

Důležitost (attention) vzhledem k 1. tokenu

Výpočet pro 1. token Výpočet pro všechny tokeny (paralelně)

Transformer: Self-attention

FIT VUT v Brně Shikhar Agnihotri, Liangze Li: Introductionto DeepLearning, 2023 29

h times Z^1 Z^2 Z^3 Z^4 Z^5

Transformer – kodér

FIT VUT v Brně 30
N-krát Kodér

Fei-Fei Li, JiajunWu, RuohanGao: CS231n, StanfordUniv., 2022

Transformer – dekodér

FIT VUT v Brně Fei-Fei Li, JiajunWu, RuohanGao: CS231n, StanfordUniv., 2022 31
Transformer, BERT, GPT

FIT VUT v Brně 32

    Původní Transformer(Vaswani et al., 2017) kombinuje kodér

(sestavený z N bloků, každý má self-attention vrstvu a MLPpro každý
token) a de kodér (sestavený z N bloků, každý má self-attention vrstvy s
maskováním, cross attention vrstvy a MLPpro každý token).

    BidirectionalEncoderRepresentationsfrom Transformers(BERT)
        BERT (Devlin et al., 2018) využívástruktury kodéru v Transformeru.
        Je trénován, aby doplnil zamaskované slovo ve větě.
    Generative Pre-trained Transformer(GPT)
        GPT (Radford, 2018; Radford et al., 2019) má strukturu dekodéru v Transformeru
        (bezattentionvektoru z kodéru).
        Je trénován, aby doplnil token na konec zadané vstupní posloupnosti. Nová
        posloupnost se stává vstupem v dalším kroku atd. (autoregrese).

https://jalammar.github.io/illustrated-gpt2/

GPT- 2

FIT VUT v Brně 33

    GPT- 2 Small: embedding(dimenze) 768, 12 x dekodér, 12 x attentionheads, max
    1024 tokenů; cca 120 milionů parametrů
    Velikost slovníku: 50257 slov; Trénování: 40 GB dataset WebText(OpenAI)

https://jalammar.github.io/illustrated-gpt2/

Embedding size
768 1024 1280 1600

Tato zakódování jsou
předmětem učení!

GPT- 2 Small

https://jalammar.github.io/illustrated-gpt2/ 34

Příprava vstupu pro dekodér.
<s> je start token

Výpočet přes všech 12 dekodérů.

Převod výstupního vektoru
posledního dekodéru na token.

Výpočet uvnitř bloku je
na dalších 2 slidech.

1 2

3 4

5 6

FIT VUT v Brně https://jalammar.github.io/illustrated-gpt2/ 36

8
9

10 11

12

Počet
parametrů

je vstupem do dalších 11 dekodérů

LLM Visualization (bbycroft.net/llm)
Vývoj LLMs
Vývoj LLMs – dle výkonnosti
AI a „memory wall“

FIT VUT v Brně Source: Amir Gholami et al. AI and Memory Wall. Published in IEEE Micro Journal 2024. 40
CNNs
Př. LLMs pro generování hardware

FIT VUT v Brně ShailjaThakuret al. VeriGen: A Large Language Model for Verilog Code Generation. ACM TODAES^2 9(3), 2024 41
Evolutionary machine learning
1. Využití EA ke zlepšení, podpoře nebo rozšíření metod ML.
2. Využití ML kezlepšení, podpořenebo rozšířeníEA.

Nan Li et al. Survey on Evolutionary Deep Learning: Principles, Algorithms, Applications,
and Open Issues. ACM Comput. Surv. 56(2): 41:1-41:34 (2024)

Evolutionary machine learning: GP a LLM

FIT VUT v Brně HembergE. et al. GPTP XXI, 2024 43
Neural Architecture Search (NAS) a
Hardware-Aware NAS

0.1
0.7

    0.2

0.6
0.8
0.0

TRAINING
ACCURACY

Training data Training

TEST
ACCURACY
Test data

NAS
NAS

Estimate HW
parameters

HW/SW
implementation
(for Inference)

Hardware-Aware
is a multi-objective
design problem!
Neuroevoluce – základní přístupy

    EA je použit pro nalezení
        hodnot vah pro předem danou topologie sítě, tj. využití namísto

učícího algoritmu

    obvykle méně škálovatelné než tradiční trénovací algoritmy (gradientní
    sestup a zpětné šíření chyby), ale lze dobře paralelizovat
    Úspěšné příklady: https://openai.com/research/evolution-strategies
    topologiesítě, ale váhy jsou získány učením
    dnes nejčastější přístup
    topologie i vah sítě
    Zakódování ANN pro EA
    přímé– chromozom obsahuje kompletní popis struktury (popř. i vah)

sítě (není škálovatelné)

    nepřímé– chromozom obsahuje předpispro vytvoření topologie sítě
    Pozn. Neural Architecture Search (NAS)
    metody automatizovaného návrh NN (neuroevoluce je jednou z NAS

metod) K. O. Stanley, J. Clune, J. Lehman, and R. Miikkulainen: Designingneuralnetworksthrough

neuroevolution, NatureMach. Intell., vol. 1,pp. 24-35, Jan. 2019.

Neuroevoluce – přímé kódování (příklad)

    Např. algoritmus NEAT
        Stanley, Miikkulainen: Evolving neural
        networks through augmenting
        topologies, Evol. Comput., 2002
    Není škálovatelný
    Dnes se používá pro návrh DNN,

ale na úrovni vrstev, ne neuronů.
Neuroevoluce – přímé kódování pro CNN (příklad)
CNN~ posloupnostintegerů

(Node ID; Operation; Parameter; Source ID 1; Source ID 2).
Set of operations: (1) convolution, (2) max. pooling, (3)
average pooling, (4) identity, (5) add, (6) concatenation, (7)
terminal node [87].

Po vrstvách

    Kóduje celou
    CNN po vrstvách,
    některé vrstvy
    mohou být
    předem
    specifikovány.
    Velký
    prohledávaný
    prostor.

Po blocích/buňkách

    Hledá se podgraf
    (cell), který se
    násobně
    znovupoužije v CNN.
    Menší prohledávaný
    prostor.

Neuroevoluce – nepřímé kódování

    Celulárníkódování
        Obdoba Kozovy konstrukce fenotypu
        (na obr.vpravo je několik kroků) z
        „embrya“ podle kandidátního
        programu (vlevo na obrázku).
    HyperNEAT(Hypercube-based

NEAT)

    Poleuzlů (substrát), které mají
    souřadnice.
    Evolučně se hledáfunkce(CPPN),
    která určuje váhumezi dvěma uzly s
    libovolně zvolenými souřadnicemi.
    CPPN –Compositional Pattern-
    ProducingNetwork
    Pokud je vypočtená váha menší než
    zvolená hodnota, je chápana jako 0, a
    mezi těmito uzly není spojení.
    Výborně škálovatelné –pro určité
    úlohy (ANN s miliony uzlů)

Kombinace evoluce topologie NN s učením vah
NNSW -SWpro trénování NN.
Jsou potřeba třidatové sady:
Dtrain–pro trénování
Dval–pro validaci
Dtest–pro finálnítestování 49
Snížení výpočetní náročnosti evaluace kandidátní DNN

FIT VUT v Brně Results on NASBench-101 (CIFAR-10) by Wen W. et al. ECCV 2020 50

Prediktorypřesnostia dalšíchparametrůDNN: Cílem je nahradit
časově náročné trénování kandidátní DNN (které je nutné pro
stanovení chyby DNN) pomocí natrénovaného ML modelu (např.
založeného na malé NN). Pro trénování prediktoru ke třeba zvolit
vhodné příznaky, nasbírat trénovacía testovací data a natrénovat
prediktor. Prediktor je v NAS algoritmu použit během evoluce.

Metody:

    redukce
    trénovací/validační
    množiny
    redukce počtu
    epoch, generací,
    velikosti populace
    sdílení vah atd.
    prediktory
    přesnosti DNN
    prediktory HW
    parametrů DNN
    využití tzv. super
    net

Neuroevoluce pomocí CGP

SuganumaM. et al. GECCO 2017

genotype

Uzel CGP představuje jednu vrstvu CNN. phenotype
Neuroevoluce – NSGA-Net

ZhichaoLu et al. NSGA-Net, GECCO 2019

Encoding:CNN is a set of phases; max. 6 nodes in each phase encoded using a bit string. A node can be convolution,
pooling, batch-normalization...

Search method:
NSGA-II (classification error vs the number of FLOPs), crossover, bit flip mutation, Bayesian Optimization Algorithm,
population size = 40, generations = 20+10, i.e. 1200 network architectures are created in a single run
Training (during the evolution): SGD (Stochastic Gradient Descent) for 25 epochs
Validation of evolved CNNs: 600 epochs, batch size 96, data preprocessing, regularization ...

Crossover:

Differentiable Neural Architecture Search (DARTS)

H. Liu, K. Simonyan, and Y. Yang:DARTS:
Differentiable architecturesearch,ICLR
2019
10x-500x urychlení oproti NAS
na ImageNet.

Váhywand reálné proměnné
reprezentující architekturu DNN jsou
souběžněhledánygradientní
metodou.
Reprezentace DNN:
Uzelx(i): Feature map
Hranao(i,j): Operace, např.z množiny
{Conv3(červená), Conv5(zelená),
AvgPool(modrá)}

Běžné kódování jedné
hrany:
1 diskrétní proměnná
pro 3 možnosti

Kódování v
DARTS pro jednu
hranu :
3 reálné
proměnné( 1  2
 3 ) kódují
pravděpodobnost
výběru operace

Nejpravděpo-
dobnější
operaceje
vybrána
(diskretizace)

Literatura

    LeCunY., BengioY., Hinton G.: Deep learning. Nature Vol. 521, 2015
    Sze, V., Chen, Y., Yang, T., Emer, J.S.: Ecientprocessing of deep neural networks: A
    tutorial and survey. Proceedings of the IEEE 105(12), 2295{2329 (2017)
    FurberS.B.: Brain-inspired computing. IET Computers & Digital Techniques, 10(6), 2016,
    p. 299- 305
    SuganumaM. et al.: A genetic programming approach to designing convolutional neural
    network architectures. GECCO 2017, pp. 497- 504
    Lu Z., Whalen I., BoddetiV., DhebarY.D., Deb K., Goodman E.D., Banzhaf W.: NSGA-
    Net: neural architecture search using multi-objective genetic algorithm. GECCO 2019:
    419 - 427
    SekaninaL.: Neural Architecture Search and Hardware Accelerator Co-Search: A
    Survey. IEEE Access, Vol. 9, 2021, p. 151337- 151362
    Banzhaf W., Machado P., Zhang M.: Handbook of Evolutionary Machine Learning,
    Springer, 2023
    KrohnJ., BeyleveldG., BassensA.: Deep Learning Illustrated, Addison-Wesley, 2019
    http://playground.tensorflow.org/
    https://openai.com/research/evolution-strategies
    ValpredaE. Hardware/Neural Network Codesign for Energy-Efficient Inference on Edge
    Devices with Optimal Mapping and Compression. PhD Thesis, Politecnicodi Torino,
    2024
    Fei-FeiLi, JiajunWu, RuohanGao: CS231n course, StanfordUniv., 2022
    https://jalammar.github.io/illustrated-gpt2/
    https://jalammar.github.io/illustrated-transformer/
