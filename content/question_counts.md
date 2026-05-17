---
title: "Question Counts from Previous Exams"
tags: ["exam-prep", "question-bank"]
---

# Question Match Counts from Previous Exams

This file lists the approximate count of semantically equivalent questions found in `content/questions/question_bank_raw.md` for each study question. Counts are based on keyword/topic matching rather than exact string comparison. Uncertain matches are marked with `(?)`.

## Lecture 01 — Úvod, inspirace v přírodě, entropie a samoorganizace

| Question | Count |
|----------|-------|
| Boltzmanova entropie: S = kB ln W — co jsou kB a W? | 4 |
| V nevratných výpočtových systémech: vztah pro energii na 1 bit (ESNL = kB T ln 2) | 3 |
| Pojmy z entropie: vypočítejte pravděpodobnost makrostavu | 3 |
| Algoritmická (Kolmogorovova) entropie: co to je? | 3 |
| Emergence: definujte vznik globálního chování z lokálních interakcí | 1 |
| Původ samoorganizace: faktory vedoucí k spontánnímu vzniku organizace | 1 (?) |

## Lecture 02 — Evoluční design

| Question | Count |
|----------|-------|
| Definice alely, neutrální mutace a atraktor | 2 |
| Formálně: co znamená, že kandidát x dominuje y (dvě fitness) | 4 |
| Pareto fronta — dominance, Pareto fronta, dominance bez C1 | 2 |
| Agregace vícekriteriální fitness: tvar funkce F | 2 |
| Pravděpodobnost výběru — turnajový vs. ruletový výběr | 2 |
| Kdy použít evoluční algoritmy? Předpoklady a omezení | 1 |
| Formalizace návrhu jako optimalizační úlohy | 1 |
| Porovnání vyhledávacích metod (šířka, hloubka, gradient, tabu, žíhání, EA) | 1 |
| Kostra EA — inicializace, evaluace, selekce, rekombinace, mutace, náhrada | 1 |
| Klíčové pojmy: gén, chromozóm, fenotyp, populace | 2 |
| Návrh fitness pro obrazový filtr (Koza) — PSNR, MSE, penalizace | 2 |
| Reprezentace a kódování — binární, reálné, permutační, stromy (GP), grafy (CGP) | 1 |

## Lecture 03 — Kartézské genetické programování (CGP)

| Question | Count |
|----------|-------|
| Hlavní použití GP: symbolická regrese — aplikace | 0 |
| Reprezentace v GP: stromy, gramatiky, lineární, grafy (CGP) | 1 |
| Principy CGP: genotyp pevné délky, aktivita uzlů, fenotyp (DAG) | 0 |
| CGP poskytuje neutralitu — vliv na evoluční hledání | 0 |
| CGP parametry: ni, no, v, u, arita, Γ, L-back | 1 |
| CGP medián 7 vstupů — počet in/out, AND/OR omezení, délka chromozómu, fitness | 2 |
| Postup sestavení fenotypu — aktivní uzly | 0 |
| Dvě fitness kritéria + mutace (škodlivá/neutrální) | 3 |
| Typická fitness — počet správných bitů, penalizace | 1 |
| Bitově-paralelní simulace — princip a zrychlení | 1 (?) |
| Mutace v CGP — změna funkce, vstupu, výstupu | 1 |
| Prohledávací schéma (1+λ) | 0 |
| Příklady problémů: parity, medián, násobička | 1 |
| Vliv parametrů na úspěšnost a strukturu | 0 |

## Lecture 04 — Limity abstraktního a fyzického počítání

| Question | Count |
|----------|-------|
| Landauerův limit: ESNL = kB T ln 2 — vztah a fyzikální význam | 2 |
| Boltzmannova entropie vs. změna entropie při nereverzibilním výpočtu | 1 |
| Logika fyzicky reverzibilního systému — logická reverzibilita, bijektivní funkce, garbage | 1 |
| Příklady reverzibilních hradel (Toffoli, Fredkin) | 2 |
| Fyzikální omezení: konečné zdroje, rychlost světla, realizovatelnost | 1 |
| Heisenbergův princip a měření — vliv na fyzikální výpočty | 0 |
| Turingův stroj a nerozhodnutelnost — problém zastavení | 1 (?) |
| Church-Turingova teze — abstraktní vs. fyzická verze | 1 |
| Super-Turingovské modely — vlastnosti, které porušují Turingův stroj | 1 |
| Abstraktní modely (accelerating TM, TM s orákulem) — fyzická realizovatelnost | 0 |
| Interaktivní systémy — vliv na Church-Turingovu tezi | 0 |
| Praktické implikace Landauerova limitu — reverzibilní obvody, neuromorfní výpočet | 1 |

## Lecture 05 — Evoluční návrh číslicových obvodů

| Question | Count |
|----------|-------|
| Co je EHW — výhody kombinace EA s FPGA/PLA | 0 |
| Thompsonův experiment — vylepšení, důsledky na portabilitu | 0 |
| Úrovně reprezentace — materiál, tranzistory, hradla, bloky, programy | 0 |
| Volba reprezentace — vliv na prostor řešení a škálovatelnost (~15 vstupů) | 0 |
| Extrinsic vs. intrinsic vs. mixtrinsic evaluace | 0 |
| Proces evaluace chromozómu — transformace, konfigurace, stimuly, fitness | 0 |
| SAT solver pro porovnání obvodů — Tseitinova transformace | 1 |
| Transformace SAT vráti YES — ekvivalence obvodů A a B | 0 |
| Fitness pro minimalizaci hradel pomocí SAT verifikace | 1 |
| Kozaova metoda — embryo, kandidátní program, fenotyp, netlist, fitness | 1 |
| Extrinsic/intrinsic evaluace — mixtrinsic řešení | 0 |
| Evaluace náročná — exponenciální nárůst, metody snižující náklady | 0 |
| Problémy přenositelnosti řešení — strategie zlepšení | 0 |
| Typy RZ (LUT, PLA, FPGA) — typ paměti (SRAM) | 0 |
| Pojem "rámec" v FPGA — relevance | 0 |

## Lecture 06 — Výpočetní development

| Question | Count |
|----------|-------|
| Rozdíl fylogeneze vs. ontogeneze — příklad metod | 1 |
| Kde probíhá výpočet v syntetické biologii — fyzické místo a signál | 1 |
| Transkripce a translace — DNA → proteiny, diferenciace | 0 |
| Mitóza a diferenciace — vznik specializovaných buněk | 0 |
| Výpočetní development — přímé vs. nepřímé kódování | 0 |
| L-systémy — paralelní provádění pravidel vs. klasická gramatika | 1 |
| Navrhněte L-systém — odvodit z derivačních kroků, nakreslit | 1 |
| CA — definice buňky, přechodová funkce, 1D vs. 2D | 1 |
| Langtonova smyčka — proč se studuje, 1D/2D/3D, počet stavů | 1 |
| Sousedství v CA — 5-sousedství, interpretace | 0 |
| Lokální přechodová funkce — počet řádků tabulky | 0 |
| Příklad CA — stav 0, všichni sousedé 0, F=XOR → ? | 0 |
| Genetické regulační sítě (GRN) — modelování diferenciace | 0 |
| Kdy použít nepřímé kódování — výhody | 0 |
| Aplikace CA/L-systémů — generativní tvary | 0 |
| Pipeline evolučního návrhu s developmentem | 0 |

## Lecture 07 — Evoluční návrh a adaptace analogových obvodů a antén

| Question | Count |
|----------|-------|
| Přímý vs. nepřímý návrh obvodů | 0 |
| Programová reprezentace (GP) a netlisty → SPICE | 0 |
| Příklad genotypu pro RC filtr | 0 |
| Hodnocení analogového obvodu — SPICE metody, metriky | 0 |
| Váhové funkce a vzorkovací body | 0 |
| Koza-style GP pro analog — porovnání charakteristik | 1 |
| Návrh antén — parametrické vs. generativní | 0 |
| Embryonální konstrukce antény — instrukce | 0 |
| Co je FPTA — výhody intrinsic evaluace | 0 |
| SABLES — workflow (DSP, konfigurace, měření) | 0 |
| Robustnost vyevolvovaných řešení — mimo trénovací podmínky | 0 |
| Strategie zlepšení robustnosti | 0 |
| Dopady šumu, teploty, tolerancí | 0 |
| Omezení evolučního návrhu analogových systémů | 0 |
| Pipeline evolučního návrhu analogového obvodu | 0 |

## Lecture 08 — Neuronové sítě a neuroevoluce

| Question | Count |
|----------|-------|
| Schéma biologického neuronu — dendrity, soma, axon | 0 |
| Vztah pro výstup n-vstupového neuronu: y = A(∑ xi * wi + b) | 2 |
| Schéma neuronu se 4 vstupy — počet parametrů | 1 |
| Proč se nepoužívají jedno-neurónové sítě | 1 |
| Ztrátová funkce a princip gradientního sestupu | 0 |
| Regularizační techniky — dropout, weight decay, normalizace | 0 |
| Konvoluční vrstva a pooling — snížení parametrů | 1 |
| Počet vah: plně propojená vs. konvoluční (20×20 → 6 filtrů 3×3) | 1 |
| Co je NAS — přístupy | 0 |
| Neuroevoluce — co lze evolvovat (architektura vs. váhy) | 0 |
| Pseudokód evoluce CNN | 1 |
| Prediktor fitness — vstupy (architektonické metriky) | 1 |
| GPU/TPU výhody — FLOPs, params, memory | 0 |
| Neuromorphic computing a spiking NN | 0 |

## Lecture 09 — Neurální hardware

| Question | Count |
|----------|-------|
| Náročnost DNN — parametry a MAC operace | 1 |
| Výpočet: baterie 2 Wh, 20 fps, 200·10^9 op/inf, 0,2 pJ/op | 1 |
| Která část CNN spotřebovává nejvíce energie | 1 |
| Porovnání akcelerátorů — CPU, GPU, FPGA, ASIC | 0 |
| Systolické pole — datový tok | 0 |
| Příklady akcelerátorů — Eyeriss, TPU, Cerebras | 0 |
| Kvantizace (INT8), pruning, sdílení vah | 0 |
| Aproximace aritmetiky — kompromis přesnost/energie | 0 |
| Kroky optimalizace pro bateriové zařízení | 0 |
| Timeloop a Accelergy — mapování modelu | 0 |
| Mapování a scheduling — vliv na energii a latenci | 0 |
| Metriky: inferences/sec, inferences/Watt, latency | 0 |
| Edge a battery-powered aplikace — plán testování | 0 |

## Lecture 10 — DNA počítače

| Question | Count |
|----------|-------|
| Nakreslete graf pro SAT problém y = (x1 ∨ x2 ∨ x3) — cesta x1=1, x2=0, x3=0 | 2 |
| Kroky Adlemanova postupu — ligace, filtrování, detekce | 2 |
| Oligonukleotidy: R = AAATTTCC, S = GGAACCCC → kód cesty S do R | 1 |
| Počáteční zkumavka — binární kombinace | 1 |
| Zkumavka na konci — platné kombinace | 1 |
| Laboratorní operace — denaturace, hybridizace, ligace, PCR, gel, štěpení | 1 |
| PCR — změna počtu fragmentů | 1 |
| Výhody DNA počítání — paralelizmus, hustota; omezení — chyby, náklady | 1 |
| Návrh oligonukleotidů — orientace, minimalizace hybridizace | 1 |
| Kde probíhá výpočet — fyzikální podstata 1 a 0 | 0 |
| Formální mapping SAT → DNA pipeline | 0 |

## Lecture 11 — Nanotechnologie v kontextu bio-inspirovaných počítačů

| Question | Count |
|----------|-------|
| Měřítka nanotech — přírodní struktury | 1 |
| STM a AFM — princip zobrazování a manipulace | 0 |
| Top-down vs. bottom-up přístupy — výhody, nevýhody | 1 (?) |
| Výzvy kontroly a spolehlivosti v bottom-up samoorganizaci | 0 |
| Co je CNFET — princip, výhody | 1 |
| Praktické problémy CNFET — kovové nanotrubičky, adresovatelnost | 1 |
| Části CNFET tranzistoru — source, drain, gate, kanály | 1 |
| QCA princip — polohy elektronů, majoritní funkce | 1 |
| QCA konfiguraci pro majority(A,B,C) — polarizace | 1 |
| QCA vodič — realizace, přenos signálu | 1 |
| Molekulární přepínače a in-memory koncepty | 0 |
| Mikrofluidické biočipy a syntetická biologie | 0 |
| Propojení nanosoučástek s makrosvětem — adresování, I/O | 0 |
| Výrobní tolerance a variability — vliv, testy | 0 |
| Logická a fyzická reverzibilita — Toffoli, Fredkin | 0 |
| Reverzibilita v nanotechnologiích — low-energy návrh | 0 |
| Reální potenciál nanosystémů — senzory, neuromorfní, in-memory | 0 |
| Dlouhodobé výzvy — kontrola, rozhraní, standardizace | 0 |

---

## Summary

- **Total lectures processed:** 11 (lec01–lec11)
- **Total questions analyzed:** ~130
- **Questions with 0 matches:** ~40
- **Questions with 1 match:** ~30
- **Questions with 2+ matches:** ~20
- **Uncertain matches (?):** ~5

**Notes:**
- The question bank contains primarily exam questions from years 2017–2023.
- Topics with the most frequent matches: entropy, fitness functions, CGP, DNA computing, multi-criteria optimization.
- Topics with few/no exam coverage: analog circuit design, FPTA, microfluidics, synbio integration, neuroevolution details.
- Use this as a study guide: topics with higher counts are more likely to appear in exams; low-count topics may be good candidates for focused preparation.
