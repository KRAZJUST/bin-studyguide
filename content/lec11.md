---
title: "11 Nanotechnologie v kontextu bio-inspirovaných počítačů"
tags: ["lecture11", "nanotechnology", "QCA", "CNFET", "molecular-electronics", "study-guide"]
---

# Nanotechnologie v kontextu bio-inspirovaných počítačů

## 1. Rozsah nanoškály a přístroje

### Co je nanoškála a proč záleží?

Nanotechnologie pracuje s objekty v rozsahu přibližně **1–100 nanometrů** (1 nm = 10⁻⁹ m). Pro srovnání: průměr lidského vlasu je ~80 000 nm, takže hovoříme o světě, kde se klasická fyzika začíná prolínat s kvantovou mechanikou.

Na této škále se mění fundamentální vlastnosti materiálů – elektrická vodivost, optické vlastnosti, mechanická pevnost. Proto nanosoučástky mohou nabízet vlastnosti, které jsou na makroúrovni nedosažitelné.

**Příklady přírodních nanosystémů:**

| Struktura | Přibližná velikost | Funkce |
|---|---|---|
| DNA (dvoušroubovice) | ~2 nm průměr | Uchovávání genetické informace |
| Protein (malý) | ~5–10 nm | Enzymatická katalýza, strukturální role |
| ATP syntáza | ~10 nm | Molekulární motor, syntéza ATP |
| Uhlíková nanotrubička (CNT) | průměr ~1–10 nm | Elektrická vodivost, mechanická pevnost |
| Ribozóm | ~25 nm | Syntéza proteinů |

Tyto příklady ukazují, že příroda zvládá vysoce funkční systémy na molekulární úrovni s obrovskou hustotou integrace a velmi nízkou spotřebou energie – právě to je inspirací pro nanotechnologický výzkum.

---

### STM – Rastrovací tunelová mikroskopie

**Princip:** STM (Scanning Tunneling Microscope) využívá kvantový jev **tunelování elektronů**. Velmi ostrý kovový hrot se přiblíží k povrchu na vzdálenost ~0,5–1 nm. Přestože hrot a povrch se fyzicky nedotýkají, elektrony mohou tunelovat přes vakuovou mezeru, pokud je přiloženo malé napětí.

Klíčová vlastnost: tunelový proud $I$ závisí **exponenciálně** na vzdálenosti $d$:

$$I \propto e^{-\kappa d}$$

kde $\kappa$ je konstanta závislá na výstupní práci elektronu. Změna vzdálenosti o pouhý 1 Å (0,1 nm) změní proud přibližně o řád. Díky tomu je STM extrémně citlivé na topografii povrchu – dosahuje **sub-atomárního rozlišení**.

```mermaid
graph LR
    subgraph STM["STM – princip"]
        A["Ostrý kovový hrot</br>(W nebo Pt-Ir)"] -->|"Tunelový proud</br>(závislý na vzdálenosti)"| B["Vodivý povrch"]
        C["Zpětnovazební</br>smyčka"] -->|"Udržuje</br>konstantní proud"| A
        D["Piezoelektrický</br>scanner"] -->|"Pohybuje hrotem</br>v x, y, z"| A
        B -->|"Výsledek: 3D mapa</br>povrchu s atomárním</br>rozlišením"| E["Počítač</br>+ zobrazení"]
    end
```

**Manipulace s atomy:** STM lze použít nejen ke zobrazení, ale i k manipulaci – přiložením silnějšího pulzu napětí lze atomy přemístit. Slavný příklad: IBM (1989) poskládal logo „IBM" z 35 atomů xenonu.

**Omezení:** STM funguje jen na **vodivých** površích (nutný tunelový proud).

---

### AFM – Mikroskopie atomových sil

**Princip:** AFM (Atomic Force Microscope) měří **síly** mezi hrotem a povrchem, nikoliv elektrický proud. Hrot je umístěn na konci pružného raménka (**cantilever**). Jak hrot skenuje povrch, síly (van der Waalsovy, elektrostatické, kapilární) způsobují ohýbání cantilevu. Toto ohýbání se měří laserovým paprskem odraženým do polohovacího detektoru.

```mermaid
graph TD
    A["Laser"] -->|"Paprsek"| B["Zadní strana</br>cantileveru"]
    B -->|"Odražený paprsek"| C["Polohovací detektor</br>(4-kvadrantová fotodioda)"]
    C -->|"Signál ohybu"| D["Zpracování signálu</br>+ zpětná vazba"]
    D -->|"Regulace výšky</br>piezo-skenerem"| E["Hrot na cantilevu"]
    E -->|"Síly</br>(van der Waals,</br>elektrostatické)"| F["Povrch vzorku"]
```

**Výhody AFM oproti STM:**
- Funguje na **nevodivých** površích (biologické vzorky, polymery, oxidy)
- Lze měřit v kapalném prostředí (biologické aplikace)
- Různé módy: kontaktní, bezkontaktní, poklepový (tapping)

**Srovnání STM vs. AFM:**

| Vlastnost | STM | AFM |
|---|---|---|
| Měřená veličina | Tunelový proud | Síla (ohyb cantilevu) |
| Požadavky na vzorek | Musí být vodivý | Libovolný materiál |
| Typické rozlišení | Sub-atomární | Atomární až nm |
| Manipulace s atomy | Ano (napěťový puls) | Omezeně (kontaktní mód) |
| Prostředí | Vakuum, vzduch | Vakuum, vzduch, kapalina |

---

## 2. Přístupy k výrobě: shora-dolů vs. zdola-nahoru

### Top-down (shora dolů)

**Filosofie:** Začínáme s kusem materiálu (obvykle křemíkový wafer) a postupně odstraňujeme/upravujeme materiál, dokud nezískáme požadovanou strukturu.

**Klíčové techniky:**
- **Fotolitografie** – UV světlo přes masku exponuje fotorezist, definuje vzory
- **Elektronová litografie (EBL)** – elektron-beam pro submikronové struktury
- **Leptání** (mokré/suché) – odstraňování materiálu podle masek
- **Depozice** (CVD, PVD, ALD) – přidávání vrstev materiálu

```mermaid
flowchart TD
    A["Křemíkový wafer"] --> B["Nanášení fotorezistu"]
    B --> C["Expozice UV/EBL přes masku"]
    C --> D["Vyvolání fotorezistu"]
    D --> E["Leptání nebo depozice"]
    E --> F["Odstranění fotorezistu"]
    F --> G["Výsledná nanostruktura"]
    G -->|"Opakování pro</br>další vrstvy"| B
```

**Výhody:**
- Průmyslově ověřené, masová výroba
- Přesná kontrola polohy a rozměrů
- Kompatibilní s existující CMOS infrastrukturou

**Nevýhody:**
- Fyzikální limity miniaturizace (difrakce světla, atomová hrubost)
- Extrémně drahé vybavení (EUV litografie > 100 milionů USD/stroj)
- Rostoucí poměr plochy okrajů k objemu způsobuje nové efekty

---

### Bottom-up (zdola nahoru)

**Filosofie:** Stavíme nanostruktury „atom po atomu" nebo využíváme schopnost molekul **samoorganizace** (self-assembly) – spontánního uspořádání do cílených struktur.

```mermaid
flowchart LR
    A["Atomy /</br>molekuly"] -->|"Samoorganizace</br>(chemické vazby,</br>van der Waals)"| B["Nanoobjekty</br>(nanotrubičky,</br>nanodráty,</br>monovrstvy)"]
    B -->|"Funkcionalizace</br>a propojení"| C["Nanosoučástky</br>(přepínače,</br>senzory)"]
    C -->|"Integrace</br>do systémů"| D["Nanosystémy</br>a obvody"]
```

**Příklady samoorganizujících se systémů:**
- **Samousořádávající monovrstvy (SAM)** – thioly na zlatém povrchu
- **DNA origami** – skládání DNA do 2D/3D struktur jako scaffold
- **CNT růst katalytickými částicemi** – nanotrubičky rostou z Fe/Ni/Co katalyzátorů

**Výhody:**
- Extrémně malé rozměry (sub-nm)
- Masová paralelizace (miliony struktur najednou)
- Potenciálně velmi levné

**Nevýhody a výzvy:**
- **Přesné umístění** – těžko kontrolovat, kde přesně vznikne struktura
- **Orientace** – nanotrubičky rostou různými směry
- **Defekty a variabilita** – každá struktura je trochu jiná
- **Adresování** – jak se dostat ke konkrétní nanosoučástce z makrosvěta
- **Propojení** – rozhraní nano ↔ makro je fundamentální problém

---

## 3. Molekulární elektronika a CNFET

### Uhlíkové nanotrubičky (CNT) – základ CNFET

Uhlíkové nanotrubičky jsou válcové struktury z grafenu (hexagonální síť uhlíku) s průměrem ~1–10 nm a délkami až mikrometry. Mají výjimečné vlastnosti:

- **Elektrická pohyblivost nosičů** – až 100× vyšší než v křemíku
- **Mechanická pevnost** – jedno z nejpevnějších materiálů
- **Tepelná vodivost** – velmi vysoká

**Důležité:** CNT mohou být buď **kovové** (vedou jako vodič) nebo **polovodičové** (lze řídit gate elektrodou), v závislosti na způsobu stočení grafenové vrstvy (chiralita).

### CNFET – Carbon Nanotube Field Effect Transistor

CNFET je tranzistor, kde kanál mezi source a drain tvoří jedna nebo více uhlíkových nanotrubiček místo křemíkového kanálu.

```mermaid
graph LR
    subgraph CNFET["Struktura CNFET"]
        S["Source</br>(kontakt)"] -->|"Nanotrubičkový</br>kanál"| D["Drain</br>(kontakt)"]
        G["Gate elektroda</br>(dielektrikum pod/nad)"] -->|"Elektrické pole</br>řídí vodivost kanálu"| CNT["CNT kanál"]
        S --- CNT
        CNT --- D
    end
```

**Proč CNFET slibuje výhody oproti Si-MOSFET:**

| Vlastnost | Si-MOSFET | CNFET |
|---|---|---|
| Pohyblivost elektronů | ~1400 cm²/Vs | ~10 000+ cm²/Vs |
| Rozměry kanálu | ~5–10 nm (limity) | ~1–2 nm přirozeně |
| Spotřeba energie | Referenční | Potenciálně nižší |
| Subthreshold swing | ~60 mV/dec (klasický limit) | Blíže limitu |
| Kompatibilita s CMOS | — | Částečně kompatibilní |

**Praktické problémy výroby CNFET:**

1. **Kovové nanotrubičky** – ~30 % syntetizovaných CNT je kovových místo polovodičových; kovové CNT zkratují kanál a zničí funkci tranzistoru. Řešení: selektivní depozice, elektrické „vypalování" kovových CNT, třídění v roztoku.

2. **Přesné umístění** – CNT musí ležet přesně mezi source a drain. Řeší se: dielektroforéza, chemická funkcionalizace povrchu, litografické vzory jako „vodicí dráhy".

3. **Variabilita** – každý CNFET má trochu jiné parametry (chiralita, délka, přítomnost defektů). To komplikuje návrh velkých obvodů.

4. **Adresovatelnost ve velkém měřítku** – přechod od jednoho CNFET k obvodům s miliony tranzistorů je technologicky náročný.

---

## 4. Kvantové celulární automaty (QCA)

### Princip QCA

QCA (Quantum-dot Cellular Automata) je radikálně jiný přístup k výpočtům než tranzistorová logika. Místo proudu jako nosiče informace se používá **poloha elektronu** (polarizace buňky).

**Základní buňka QCA** obsahuje:
- 4 kvantové tečky (quantum dots) uspořádané do čtverce
- 2 elektrony, které obsadí 2 ze 4 teček
- Elektrony se odpuzují (Coulombova interakce) → zaujmou protilehlé rohy

```mermaid
graph TD
    subgraph P1["(logická 0)"]
        direction LR
        A1["● (elektron)"] --- B1["○"]
        C1["○"] --- D1["● (elektron)"]
    end
    subgraph P0["(logická 1)"]
        direction LR
        A2["○"] --- B2["● (elektron)"]
        C2["● (elektron)"] --- D2["○"]
    end
```

Sousední buňky se elektrostaticky ovlivňují – polarizace jedné buňky nutí sousední buňku přijmout stejnou polarizaci (paralelní uspořádání) nebo opačnou (invertující uspořádání). Takto se informace **šíří bez klasického proudu**.

---

### QCA vodič (Information Wire)

Řetězec buněk se stejnou orientací tvoří vodič – polarizace se propaguje podél řetězce:

```mermaid
graph LR
    I["Vstup</br>(buňka s P=+1)"] --> C1["Buňka 1</br>P=+1"] --> C2["Buňka 2</br>P=+1"] --> C3["Buňka 3</br>P=+1"] --> O["Výstup</br>P=+1"]
    style I fill:#4CAF50,color:#fff
    style O fill:#2196F3,color:#fff
```

**Ohyb vodiče o 90°** se realizuje buňkou otočenou o 45° – tzv. „rohová buňka".

---

### QCA majoritní hradlo

Majoritní hradlo (Majority Gate) je základní logický prvek QCA. Má 3 vstupy (A, B, C) a jeden výstup:

$$Y = \text{majority}(A, B, C) = AB + BC + AC$$

Výstup je ten bit, který se vyskytuje mezi vstupy **nejčastěji**.

```mermaid
graph TD
    A["Vstup A"] --> M["Středová buňka</br>(device cell)"]
    B["Vstup B"] --> M
    C["Vstup C"] --> M
    M --> Y["Výstup Y</br>= majority(A,B,C)"]
    style M fill:#FF9800,color:#fff
```

**Příklady:**

| A | B | C | Y = maj(A,B,C) | Zdůvodnění |
|---|---|---|---|---|
| 0 | 0 | 1 | **0** | dvě 0, jedna 1 → převládá 0 |
| 1 | 0 | 1 | **1** | dvě 1, jedna 0 → převládá 1 |
| 1 | 1 | 0 | **1** | dvě 1, jedna 0 → převládá 1 |
| 0 | 0 | 0 | **0** | všechna 0 |
| 1 | 1 | 1 | **1** | všechna 1 |

**Realizace AND a OR pomocí majoritního hradla:**

Jeden vstup lze „přibít" (fixovat) na konstantní hodnotu:
- Fixovat C = 0 → $Y = \text{maj}(A, B, 0) = AB$ = **AND**
- Fixovat C = 1 → $Y = \text{maj}(A, B, 1) = A + B$ = **OR**

```mermaid
graph LR
    subgraph AND_gate["AND hradlo: C=0 (fixní)"]
        A1["A"] --> M1["Majority</br>cell"]
        B1["B"] --> M1
        C1["0 (fixní)"] --> M1
        M1 --> Y1["Y = A·B"]
    end
    subgraph OR_gate["OR hradlo: C=1 (fixní)"]
        A2["A"] --> M2["Majority</br>cell"]
        B2["B"] --> M2
        C2["1 (fixní)"] --> M2
        M2 --> Y2["Y = A+B"]
    end
```

**Invertor (NOT):** Realizuje se pomocí buněk natočených o 45°, kde sousední buňka přebírá opačnou polarizaci.

---

### Výhody a výzvy QCA

**Výhody:**
- Extrémně vysoká hustota integrace (buňky ~20 nm)
- Výpočty bez klasického proudu → teoreticky velmi nízká disipace
- Rychlé šíření polarizace (blíží se rychlosti světla v materiálu)

**Výzvy:**
- Praktická realizace vyžaduje kryogenní teploty (molekulární QCA slibují pokojové teploty)
- Výroba s atomární přesností
- Propojení s klasickými obvody (I/O rozhraní)
- Variabilita a spolehlivost

---

## 5. Molekulární přepínače, in-memory a syntetická biologie

### Pole molekulárních přepínačů

Molekulární přepínač je molekula, která může přepínat mezi dvěma stabilními stavy (např. dvě konformace, dvě oxidační stadia) pod vlivem elektrického pole, světla nebo chemické reakce.

**Příklad – křížová mřížka (crossbar array):**

```mermaid
graph TD
    subgraph Crossbar["Crossbar pole molekulárních přepínačů"]
        direction TB
        H1["Horní vodič 1"] 
        H2["Horní vodič 2"]
        H3["Horní vodič 3"]
        D1["Dolní vodič 1"] 
        D2["Dolní vodič 2"]
        D3["Dolní vodič 3"]
        S11["přepínač"] 
        S12["přepínač"]
        S13["přepínač"]
    end
```

V každém průsečíku horního a dolního vodiče sedí molekulární přepínač. Přiložením napětí na zvolený horní + dolní vodič lze individuálně adresovat a přepínat konkrétní molekuly. Hustota integrace je extrémně vysoká.

**In-memory computing (výpočty v paměti):**

Tradiční architektury (von Neumann) mají **paměť oddělenou od procesoru** – přenos dat mezi nimi je energeticky nákladný a tvoří úzké hrdlo (memory wall). Molekulární přepínače a **memristory** umožňují kombinovat paměť a výpočet na jednom místě.

```mermaid
flowchart LR
    subgraph Traditional["Tradiční architektura"]
        CPU1["CPU</br>(výpočty)"] <-->|"Datová sběrnice</br>(energy bottleneck)"| RAM1["RAM</br>(paměť)"]
    end
    subgraph InMemory["In-memory computing"]
        MEM["Paměťové buňky</br>(memristory/přepínače)</br>= výpočet i uložení"]
    end
    Traditional -->|"Problém:</br>energy/bandwidth wall"| InMemory
```

**Kdy dává smysl in-memory přístup:**
- Neuronové sítě (maticové násobení přímo v paměti)
- Zpracování velkých dat (genomika, databáze)
- Hraniční zařízení (edge AI) s nízkým příkonem

---

### Mikrofluidika a syntetická biologie

**Mikrofluidické biočipy** manipulují s extrémně malými objemy kapalin (nanolitry až pikolitry) v mikrokanálcích. Výhody: rychlé reakce, malá spotřeba reagentů, paralelizace.

**Syntetická biologie** navrhuje genetické obvody v živých buňkách pomocí standardizovaných genetických „součástek" (promotory, represory, reportéry). Buňka pak provádí výpočet prostřednictvím genové exprese.

```mermaid
flowchart TD
    A["Vstupní signál</br>(chemická látka,</br>světlo)"] --> B["Genetický obvod</br>v buňce</br>(transkripční faktory,</br>represor/induktor)"]
    B --> C["Výstupní signál</br>(fluorescence,</br>enzymová aktivita)"]
    B -->|"Logické hradlo</br>v buňce"| D["AND/OR/NOT</br>logika z</br>genetických</br>součástek"]
```

**Kombinace mikrofluidiky + syntetické biologie:**
- Automatizované molekulární protokoly (PCR, syntéza DNA, diagnostika)
- Biosenzory – buňky reagující na přítomnost toxinu/patogenu výstupním signálem
- DNA computing – výpočty s molekulami DNA v roztoku

---

## 6. Výzvy: spolehlivost, adresování a rozhraní

### Propojení nanosvěta s makrosvětem

Největší praktický problém nanotechnologií je **impedance měřítek** – jak komunikovat s objektem o rozměru 2 nm z makroskopického přístroje.

```mermaid
graph TD
    subgraph Scales["Hierarchie měřítek"]
        A["Makrosvět</br>(mm–cm)</br>Tisky, kontakty, PCB"] 
        B["Mikrosvět</br>(μm–mm)</br>CMOS obvody, bonding pads"]
        C["Nanosvět</br>(nm–μm)</br>Nanotrubičky, QCA buňky,</br>molekuly"]
        A -->|"Litografické propojení</br>wirebonding"| B
        B -->|"???</br>Kritické rozhraní"| C
    end
```

**Strategie adresování:**

| Strategie | Princip | Příklad |
|---|---|---|
| Hierarchické adresování | Makro → mikro → nano ve vrstvách | CMOS + nanodrátová mřížka |
| Multiplexing | 1 makrovodič adresuje N nanosoučástek | Crossbar s demultiplexerem |
| Samoorganizující se adresování | Molekuly se samy připojí na správné místo | DNA-directed assembly |
| Elektrické mapování | Přečtení funkčnosti po výrobě, obejití vadných | FPGA-like konfigurace |

---

### Výrobní tolerance a variabilita

Nanosoučástky trpí inherentní variabilitou – každá je trochu jiná kvůli atomistické povaze materiálů.

```mermaid
flowchart TD
    V["Variabilita\nrozměrů a materiálů"] --> P1["Rozptyl parametrů\n(Vth, proud, odpor)"]
    V --> P2["Výskyt defektů\n(chybějící atomy,\nvacancy, dislokace)"]
    P1 --> E1["Chybná logická\nfunkce obvodu"]
    P2 --> E2["Zkraty nebo\npřerušení vodičů"]
    E1 --> S["Snížená spolehlivost\na výtěžnost výroby"]
    E2 --> S
    S --> R1["Testování a\nkalibrace každé\nsoučástky"]
    S --> R2["Redundance\n(více cest, TMR)"]
    S --> R3["Online detekce\na korekce chyb"]
```

**Triple Modular Redundancy (TMR):** Tři identické obvody zpracují stejný vstup, výsledek se rozhodne majoritním hlasováním – i při výpadku jednoho obvodu je výsledek správný.

---

## 7. Reverzibilita a logické brány

### Co je logická reverzibilita?

Klasická logická hradla (AND, OR, NAND) jsou **ireverzibilní** – z výstupu nelze jednoznačně rekonstruovat vstupy. Například AND(0,1) = AND(1,0) = AND(0,0) = 0 → z výstupu 0 nevíme, jaké vstupy vstoupily.

**Logicky reverzibilní** hradlo má bijektivní mapování: každý výstup odpovídá přesně jedné kombinaci vstupů, tedy lze zpětně rekonstruovat vstupy z výstupů.

**Landauerův princip (1961):** Každá logická operace, která **maže informaci** (ireverzibilní), musí disipovat alespoň $k_B T \ln 2$ energie. Při pokojové teplotě je to ~$2.8 \times 10^{-21}$ J na bit – zdánlivě malé, ale při miliardách operací za sekundu to může být limitující.

Reverzibilní logika tento limit obchází – pokud informace nezanikne, nemusí být nutně disipována energie.

---

### Toffoliho hradlo (CCNOT)

**Controlled-Controlled-NOT** – třívstupové, třívýstupové hradlo.

| Vstupy (A, B, C) | Výstupy (A', B', C') |
|---|---|
| A, B, C | A, B, C XOR (A AND B) |

- Vstupy A, B se přenáší beze změny na výstupy A', B'
- Výstup C' = C XOR (A AND B) – pokud A=1 a B=1, C se invertuje; jinak se přenáší

```mermaid
graph LR
    A["A"] -->|"A' = A"| A2["A'"]
    B["B"] -->|"B' = B"| B2["B'"]
    C["C"] --> T["Toffoli</br>hradlo"] --> C2["C' = C ⊕ (A·B)"]
    A --> T
    B --> T
    style T fill:#9C27B0,color:#fff
```

Toffoliho hradlo je **univerzální** pro reverzibilní výpočty – z něj lze sestavit libovolnou booleovskou funkci.

---

### Fredkinovo hradlo (CSWAP)

**Controlled-SWAP** – přepíná (swapuje) vstupy B a C pokud A=1.

| A | B | C | A' | B' | C' |
|---|---|---|---|---|---|
| 0 | B | C | 0 | B | C |
| 1 | B | C | 1 | C | B |

```mermaid
graph LR
    A["A (control)"] -->|"A' = A"| A2["A'"]
    B["B"] --> F["Fredkin</br>hradlo</br>(CSWAP)"] --> B2["B' = (A=0)?B:C"]
    C["C"] --> F --> C2["C' = (A=0)?C:B"]
    A --> F
    style F fill:#009688,color:#fff
```

**Analogie:** Fredkinovo hradlo je jako přepínač – pokud je kontrolní vstup A=1, přepne B a C; jinak projdou beze změny.

---

### Propojení reverzibility s nanotechnologiemi

```mermaid
flowchart TD
    L["Landauerův</br>limit:</br>k_B·T·ln2 na mazaný bit"] --> R["Reverzibilní logika:</br>nulové mazání informace</br>→ teoreticky nulová disipace"]
    R --> A["Adiabatické obvody:</br>pomalé spínání,</br>energii vracíme do zdroje"]
    R --> QCA2["QCA:</br>bez klasického proudu,</br>blíže reverzibilitě"]
    R --> NM["Nanosystémy:</br>pracují blízko</br>kvantových limitů"]
    style L fill:#F44336,color:#fff
    style R fill:#4CAF50,color:#fff
```

V nanosystémech pracují zařízení blízko fyzikálních limitů, kde každý elektron a každá tepelná fluktuace hraje roli. Reverzibilní a adiabatické koncepty proto nabývají na praktickém významu – nejde jen o teoretickou eleganci, ale o nutnost při extrémně nízkém příkonu.

---

## 8. Aplikace a perspektivy

### Krátkodobý potenciál nanosystémů

```mermaid
graph TD
    subgraph Short["Krátkodobý horizont (5–15 let)"]
        S1["Nanosenzory\n✓ Vysoká citlivost\n✓ Detekce jednotlivých\n  molekul/atomů\n✓ Medicínská diagnostika,\n  environmentální monitoring"]
        S2["In-memory systémy\n(memristory)\n✓ Snížení energy wall\n✓ Neuronové sítě v HW\n✓ Nevyžadují náhradu CMOS"]
        S3["Neuromorfní systémy\n✓ Nízký příkon pro\n  edge AI aplikace\n✓ Spiking neural networks\n✓ Fyzikálně inspirované\n  učení"]
    end
```

**Proč právě tyto oblasti:**
- **Senzory:** Nevyžadují složité integrované obvody; nanosoučástka plní jednoduchou funkci (vazba molekuly → změna odporu/kapacity). Jsou komerčně blíže.
- **In-memory:** Lze integrovat s existující CMOS technologií (hybridní přístup). Memristory jsou již ve výzkumné výrobě (HP, IBM).
- **Neuromorfní:** CMOS neuromorfy existují (Intel Loihi, IBM TrueNorth). Nanosystémy mohou dále snížit příkon.

---

### Dlouhodobé výzvy

```mermaid
mindmap
  root["Výzvy pro praktické\nnanosystémy"]
    Výroba
      Kontrola variability
      Výtěžnost \(yield\)
      Standardizace procesů
      Škálování na wafer-level
    Rozhraní
      Nano-CMOS interface
      Adresování obrovského\npočtu nanosoučástek
      Spolehlivé propojení
    Spolehlivost
      Detekce a korekce chyb
      Dlouhodobá stabilita
      Radiační odolnost
    Ekosystém
      EDA nástroje pro nanodesign
      Standardizace komponent
      Vzdělávání inženýrů
      Regulační rámce
```

**Co je potřeba dosáhnout:**

1. **Kontrola výroby** – variabilita musí klesnout pod úroveň, kde ji lze kalibrovat nebo kompenzovat.
2. **Spolehlivé nano-makro rozhraní** – hierarchické adresování, multiplexing, CMOS-nano hybridní architektura.
3. **Standardizace** – podobně jako JEDEC standardy pro paměti nebo CMOS procesní uzly. Bez toho nelze budovat ekosystém návrhu a výroby.
4. **EDA nástroje** – návrhové nástroje musí rozumět statistické povaze nanosoučástek (Monte Carlo analýza variability, fault-tolerant design flow).

Bez těchto kroků zůstane nanotechnologie převážně v laboratorní fázi – slibná, ale nedostupná pro masové aplikace.

---

## Shrnutí: Přehled klíčových konceptů

```mermaid
mindmap
  root["Nanotechnologie\nv bio-inspirovaných\npočítačích"]
    Nástroje
      STM - tunelový proud
      AFM - síly, cantilever
    Výroba
      Top-down - litografie, leptání
      Bottom-up - samoorganizace
    Součástky
      CNFET - CNT kanál
      QCA - polarizace buněk
      Molekulární přepínače
      Memristory
    Logika
      Majoritní hradlo
      Reverzibilní obvody
      Toffoli, Fredkin
    Aplikace
      Senzory
      In-memory computing
      Neuromorfní systémy
      Syntetická biologie
    Výzvy
      Variabilita
      Adresování
      Nano-makro rozhraní
      Standardizace
```

---

*Poznámka: Některé části (reverzibilita a logická hradla) nebyly explicitně součástí přednáškových materiálů, ale jsou standardní součástí kontextu nízkoenergetických nanosystémů.*