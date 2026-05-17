---
title: "10 DNA počítače"
tags: ["lecture10","dna-computing","Adleman","PCR","study-guide"]
---

# 10 DNA počítače

## Adleman and DNA computing basics

> [!info] Nakreslete graf, na který se převede řešení SAT problému pro formuli y = (x1 ∨ x2 ∨ x3). Označte uzly a hrany a ukažte konkrétní cestu pro hodnoty x1=1, x2=0, x3=0.
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Adlemanův algoritmus*

Vysvětlení:
Graf má vrstvy pro proměnné, kde každá proměnná má dvě větve (0/1).
Cesta reprezentuje přiřazení hodnot (např. volba hrany „1“ pro $x_1$).
Pro $x_1=1, x_2=0, x_3=0$ jde cesta přes uzly/hranami označené 1‑0‑0.
Tato cesta odpovídá řetězci DNA, který zůstane po filtrování.

> [!info] Popište kroky Adlemanova postupu: generování všech cest (ligace), filtrování podle počátečního a koncového vrcholu, filtrování podle délky, kontrola přítomnosti všech vrcholů, detekce zbývajících platných cest.
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Adlemanův algoritmus*

Vysvětlení:
1) LIGACE: vytvoří se velké množství náhodných cest (DNA řetězců).
2) Filtrace na správný start/finish (Vin, Vout).
3) Filtrace na správnou délku (počet vrcholů).
4) Ověření přítomnosti všech vrcholů v cestě.
5) Zbylé řetězce představují řešení.

## Oligonucleotide encoding and examples

> [!info] Vrcholy jsou kódovány jako oligonukleotidy (příklad): R = AAATTTCC, S = GGAACCCC. Jaký bude kód cesty z vrcholu S do R? (v zadání byl příklad: GGGGTTTA — vysvětlete, jak vznikne).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Přípravný krok 1: Vytvoření oligonukleotidů reprezentujících uzly grafu G*

Vysvětlení:
Každý uzel se rozdělí na dvě poloviny (např. 10‑mer + 10‑mer; v příkladu 4‑mer + 4‑mer).
Hrana S→R je oligonukleotid, jehož první polovina je komplementární k „pravé“ polovině S a druhá k „levé“ polovině R.
Tím je zajištěna orientace hrany.
Výsledný řetězec (např. GGGGTTTA) vznikne spojením těchto komplementárních polovin.

> [!info] Co se nachází v počáteční zkumavce při Adlemanově postupu pro 3 proměnné? (zapište všechny kombinace binárně: 000, 001, 010, 011, 100, 101, 110, 111).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Adlemanův algoritmus*

Vysvětlení:
V počáteční zkumavce jsou všechny možné kombinace 3 proměnných.
Tj. 000, 001, 010, 011, 100, 101, 110, 111.
Molekuly DNA reprezentují všechny cesty (všechny přiřazení).

> [!info] Co zůstane v zkumavce na konci výpočtu (po filtrování) pro formuli y = (x1 ∨ x2 ∨ x3)? (uvedení binárních kombinací, pro které je formule 1: 001, 010, 011, 100, 101, 110, 111).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Adlemanův algoritmus*

Vysvětlení:
Zůstávají přiřazení, která splňují $x_1 \lor x_2 \lor x_3$.
To jsou všechny kombinace kromě 000.
Konkrétně: 001, 010, 011, 100, 101, 110, 111.

## Laboratory operations and PCR

> [!info] Popište základní laboratorní operace používané při DNA počítání: denaturace, hybridizace, ligace, PCR, gel‑elektroforéza, enzymové štěpení/ligace.
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Operace s DNA*

Vysvětlení:
Denaturace oddělí dvojvlákna (zahřátím či změnou pH).
Hybridizace (renaturace) znovu spáruje komplementární řetězce.
Ligace spojuje fragmenty DNA do delších řetězců.
PCR amplifikuje cílové fragmenty, gel‑elektroforéza je třídí podle délky.
Enzymové štěpení řeže DNA v definovaných místech.

> [!info] Jak se mění počet DNA fragmentů po jednom cyklu PCR (ideálně)? (vysvětlete princip amplifikace a proč se počet fragmentů přibližně zdvojnásobí).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Množení DNA a PCR*

Vysvětlení:
PCR v každém cyklu replikuje každý fragment do dvou kopií.
Ideálně se počet fragmentů zdvojnásobí.
Po $n$ cyklech je to přibližně $2^n$ kopií.
V praxi růst zpomaluje kvůli limitům reakce.

## Advantages, limitations and practical issues

> [!info] Uveďte hlavní výhody DNA počítání (masivní paralelizmus, vysoká hustota uložení) a hlavní praktické omezení (chyby v laboratoři, materiálové a časové náklady, detekce a škálovatelnost).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Úvod*

Vysvětlení:
Výhody: masivní paralelismus a extrémně vysoká hustota uložení informace.
DNA operace lze provádět nad obrovským množstvím řetězců současně.
Omezení: chybovost laboratorních operací, nákladné materiály a čas.
Škálování je omezené i detekcí výsledků.

> [!info] Jak se navrhují oligonukleotidy pro uzly a hrany, aby byla zajištěna orientace hran a minimalizovaly nežádoucí hybridizace? (klíčová pravidla: unikátnost, komplementarita polovin, teplota Tm).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Přípravný krok 2: Vytvoření oligonukleotidů reprezentujících hrany grafu G*

Vysvětlení:
Oligonukleotidy uzlů musí být unikátní a navzájem nekonfliktní.
Hrany se tvoří jako spojení komplementárních polovin uzlů, což určuje orientaci.
Sekvence se volí tak, aby měly podobnou teplotu tání (Tm) a málo nechtěných vazeb.
Minimalizuje se riziko nežádoucí hybridizace a zkratů.

## Connections to course concepts

> [!info] Vysvětlete, kde „probíhá“ výpočet v DNA computing a jaká je fyzikální podstata logických 1 a 0 v molekulárních obvodech (např. přítomnost/absence fragmentu, fluorescenční značky, hybridizace).
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Úvod*

Vysvětlení:
Výpočet probíhá v chemických reakcích: hybridizace, ligace, PCR a selekce.
Logická 1/0 je fyzicky reprezentována přítomností nebo absencí DNA fragmentu.
Detekce může být fluorescenční nebo pomocí gelu.
Výsledek je dán tím, které řetězce přežijí filtrování.

> [!info] Jak byste formálně zapsali mapping SAT → DNA pipeline pro jednoduchou CNF klauzuli (stručný postup od formule k sadě oligonukleotidů a experimentálnímu filtru)?
> 📖 **Zdroj:** [content/lectures/lecture10.md](content/lectures/lecture10.md) → *Řešení HPP pomocí Adlemanova postupu*

Vysvětlení:
1) Z formule vytvořím graf, kde cesty odpovídají přiřazením proměnných.
2) Uzly a hrany kóduji oligonukleotidy (komplementární poloviny).
3) Vygeneruji všechny cesty ligací.
4) Filtrováním odstraním cesty nesplňující klauzuli.
5) Zbylé řetězce jsou řešení SAT.

---