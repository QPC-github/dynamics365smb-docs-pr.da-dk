---
title: Konfigurere arbejdscentre og produktionsressourcer
description: 'Et arbejdscenterkort organiserer produktionsressources faste værdier og krav og styrer på den måde den produktionsafgang, der udføres på arbejdscentret.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '99000754, 99000755, 99000756, 99000758, 99000760, 99000761, 99000762'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="set-up-work-centers-and-machine-centers" />Konfigurere arbejdscentre og produktionsressourcer

Programmet skelner mellem tre typer kapacitet. Disse er arrangeret hierarkisk. Hvert niveau indeholder underordnede niveauer.  

Det øverste niveau er arbejdscentergruppen. Arbejdscentre er knyttet til arbejdscentergrupper. Hvert arbejdscenter kan tilhøre en arbejdscentergruppe.

Du kan knytte forskellige produktionsressourcer til hvert arbejdscenter. En produktionsressource kan muligvis kun tilhøre et arbejdscenter.  

Den planlagte kapacitet for arbejdscentre består af disponeringen i de tilsvarende produktionsressourcer og den supplerende planlagte disponering i arbejdscentret. Den planlagte disponering i arbejdscentergruppen er derfor summen af alle tilsvarende produktionsressourcer og arbejdscentre.  

Tilgængeligheden er lagret i kalenderposter.  

> [!IMPORTANT]
> Før du opretter arbejdscentre eller produktionsressourcer, skal du oprette produktionskalendere. Du kan finde flere oplysninger i [Opsætte produktionskalendere](production-how-to-create-work-center-calendars.md).

## <a name="to-set-up-a-work-center" />Sådan opsættes et arbejdscenter

Nedenstående beskrives primært, hvordan du opretter et arbejdscenter. Trinnene til at oprette en produktionsressourcekalender er identiske med undtagelse af oversigtspanelet **Ruteopsætning**.  

1. Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **arbejdscentre**, og vælg derefter det relaterede link.  
2. Vælg handlingen **Ny**.  
3. Udfyld felterne efter behov. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Markér den højniveau ressourcegruppe, som arbejdscenteret er organiseret under, i feltet **Ressourcegruppe**, hvis det er relevant. Vælg handlingen **Ny** på rullemenuen.  
5. Vælg det arbejdscenter, der skal bruges, hvis arbejdscentret ikke er disponibelt, eller hvor behovet overstiger kapaciteten, i feltet **Alternativt arbejdscenter**. Det alternative arbejdscenter er kun til oplysning og medtages ikke automatisk i planlægningsprocesserne.
6. Vælg feltet **Spærret**, hvis du vil forhindre, at arbejdscentret bruges i enhver behandling. Det betyder, at der ikke kan bogføres afgang for en vare, der produceres på arbejdscentret. Du kan finde flere oplysninger i [Bogføre produktionsafgang](production-how-to-post-output-quantity.md).
7. Skriv omkostningen ved at producere en enhed på dette arbejdscenter, inklusive alle andre kostelementer, i feltet **Købspris**. Denne omkostning kaldes ofte *direkte arbejdsomkostning”*.  
8. I feltet **Indir. omkost.pct** skal du angive de generelle driftsomkostninger ved at bruge arbejdscentret som en procentdel af købsprisen. Dette procenttal lægges til købsprisen ved beregningen af kostprisen.  
9. I feltet **IPO-bidrag** skal du angive alle ikke-driftsmæssige omkostninger for arbejdscentret, f.eks. reparationsudgifter, som et direkte beløb.  

    Feltet **Kostpris** indeholder den beregnede kostpris ved produktion af en enhed på arbejdscentret, inklusive alle kostelementer, som følger:  

    Kostpris = Købspris + (Købspris x Indir. omkost.pct) + IPO-bidrag.  

10. Angiv i feltet **Kostprisberegning**, om ovenstående beregning skal baseres på den forbrugte tid: **Tid** eller på antallet af producerede enheder: **Enheder**.  
11. Vælg feltet **Specifik kostpris**, hvis du vil definere arbejdscentrets kostpris på den rutelinje, hvor det benyttes. Dette kan være relevant for operationer, hvor kapacitetsomkostningerne er væsentligt anderledes end for andre produktioner på arbejdscentret.  
12. Vælg i feltet **Trækmetode**, om outputbogføring på dette arbejdscenter skal beregnes og bogføres manuelt eller automatisk med en af følgende metoder.

    |Indstilling|Beskrivlse|
    |------|-----------|
    |**Manuelt**| Forbrugt tid, output og spild bogføres manuelt i afgangskladden eller produktionskladden.|
    |**Forlæns**|Afgang beregnes og bogføres automatisk, når produktionsordren frigives.|
    |**Baglæns**|Afgang beregnes og bogføres automatisk, når produktionsordren afsluttes.|

    > [!NOTE]
    > Den trækmetode, der vælges her, kan tilsidesættes for enkelte operationer, hvis det er nødvendigt, ved at ændre indstillingen på rutelinjerne.

13. Brug feltet **Enhedskode** til at angive den tidsenhed, som arbejdscentrets kostprisberegning og kapacitetsplanlægning udføres i.
    For konstant at kunne overvåge forbrug skal du først oprette en enhedsmetode. De enheder, du angiver, er basisenheder. F.eks. beregnes procestiderne i timer og minutter.

    > [!NOTE]  
    > Hvis du vælger at bruge Dage, skal du huske, at 1 dag = 24 timer - og ikke 8 (arbejdstimer).

14. I feltet **Kapacitet** skal du angive, om arbejdscentret har mere end én maskine eller person, der arbejder samtidigt. Hvis din [!INCLUDE[prod_short](includes/prod_short.md)]-installation ikke omfatter funktionaliteten Produktionsressource, skal værdien i dette felt være **1**.  
15. Angiv den procentdel af den forventede standardafgang, som arbejdscentret normalt producerer, i feltet **Effektivitet**. Hvis du angiver **100**, betyder det, at arbejdscentret har en faktisk afgang, der er den samme som standardafgangen.  
16. Markér afkrydsningsfeltet **Fælles kalender**, hvis du også bruger produktionsressourcer. Dette sikrer, at kalenderposter er akkumuleres fra produktionsressourcekalendere.  
17. Vælg en produktionskalender i feltet **Produktionskalenderkode**. Du kan finde flere oplysninger i [Opsætte produktionskalendere](production-how-to-create-work-center-calendars.md).  
18. I feltet **Køtid** skal du angive et fast tidsrum, der skal forløbe, før det tildelte arbejde kan begynde på arbejdscentret. 

> [!NOTE]
> Brug køtid til at angive en buffer mellem den tid, en komponent ankommer til en produktionsressource eller et arbejdscenter, og hvornår driften faktisk starter. F. eks. leveres en del til en produktionsressource kl. 10:00, men det tager en time at montere det på maskinen, så driften kan ikke starte før kl. 11:00. For at kunne redegøre for den pågældende time skal køtiden være én time. Værdien i feltet **Køtid** på det specifikke produktionsressource- eller arbejdscenterkort plus summen af værdien i felterne **Opstillingstid**, **Driftstid**, **Ventetid** og **Transporttid** på varerutelinjen lægges sammen for at vise varens produktionstid. Dermed får du den nøjagtige overordnede produktionstid.  

## <a name="considerations-about-capacity" />Overvejelser om kapacitet

Den kapacitet og effektivitet, der er angivet for et arbejds- og produktionsressource, påvirker ikke blot den tilgængelige kapacitet. De har også indflydelse på den samlede produktionstid, som består af opstillingstid og operationstid, som begge er defineret på rutelinjen.  

Når en bestemt rutelinje er allokeret til en arbejdscenter-eller produktionsressource, beregner systemet, hvor meget kapacitet der er behov for, og hvor lang tid det tager at fuldføre operationen.  

### <a name="run-time" />Operationstid

For at beregne operationstiden allokerer systemet den nøjagtige tid, der er angivet i feltet **Operationstid på rutelinjen**. Hverken effektivitet eller kapacitet påvirker den allokerede tid. Hvis operationstiden f. eks. er defineret som 2 timer, er den tildelte tid to timer, uanset værdierne i felterne effektivitet og kapacitet i arbejdscentret.  

> [!NOTE]
> Den kapacitet, der bruges i beregningerne, defineres som den minimale værdi mellem den kapacitet, der er defineret i arbejdscentret eller produktionsressourcen, og den samtidige kapacitet, der er defineret for rutelinjen. Hvis et arbejdscenter har en kapacitet på 100, men den samtidige kapacitet for rutelinjen er 2, vil der blive brugt *2* i beregningen.

*Varigheden* af en operation anses i modsatte for både effektivitet og kapacitet. Varighed beregnes som *Operationstid/effektivitet/kapacitet*. Følgende oversigt viser nogle få eksempler på beregningen af varighed for det samme operationstid, som defineres som 2 timer for rutelinjen:

- Effektivitet 80 % betyder, at du skal bruge 2,5 timer i stedet for to timer  
- Effektivitet 200 % betyder, at du kan færdiggøre arbejdet en gang – du kan grave hullet to gange hurtigere, hvis du har en excavator, som er dobbelt så stor som den mindre  

    Du kan opnå samme resultat, hvis du bruger to mindre Excavators i stedet for en stor en – Brug *2* som kapacitet og *100 %* som effektivitet  

Du kan være vanskelig med brøk kapaciteten, og vi gennemgår den senere. 

### <a name="setup-time" />Opstillingstid

Tidsfordelingen for opstillingstiden afhænger af kapaciteten og beregnes som *Opstillingstid * kapacitet*. Hvis kapaciteten f. eks. er angivet til *2*, fordobles den allokerede opstillingstid, fordi du skal konfigurere to computere til operationen.  

*Varigheden* af opstillingstiden afhænger af effektiviteten og beregnes som *Opstillingstid/effektivitet*. 

- Effektivitet 80 % betyder, at du skal bruge 2,5 timer i stedet for to timer til konfiguration  
- Effektivitet 200 % betyder, at du kan afslutte opsætningen i 1H i stedet for 2 timer, der er defineret i rutelinjen  

Den fraktale kapacitet er ikke noget at kende, og den anvendes i meget specifikke tilfælde.

### <a name="work-center-processing-multiple-orders-simultaneously" />Arbejdscenterbehandling af flere ordrer samtidigt

Lad os bruge en forbrugsstand som eksempel. Den har samme opsætnings-og operationstid for hver behandlet Lot. Men hvert Lot kan indeholde flere enkelte ordrer, der er malet samtidigt.  

I dette tilfælde administreres den tid og det beløb, der er tildelt ordrer, af opstillingstiden og den samtidige kapacitet. Det anbefales, at du ikke bruger operationstid på rutelinjerne.  

Den allokerede opstillingstid for hver enkelt ordre vil være i omvendt rækkefølge af det antal ordrer (antal), der afvikles samtidigt. Her er nogle flere eksempler på beregningen af opstillingstid, hvor den er defineret som to timer for rutelinjen:

- Hvis der er to ordrer, skal den samtidige kapacitet på rutelinjen indstilles til 0,5.

    Den allokerede kapacitet for hver vil derfor være én time, men varigheden af hver ordre vil fortsat være to timer.
- Hvis der er to ordrer med et antal på én og fire, er den samtidige kapacitet for rutelinjen i den første ordre 0,2 og 0,8 for den anden.  

    Derfor vil den allokerede kapacitet for den første ordre være 24 min. og for den anden 96. Varigheden af begge ordrer forbliver to timer.  

I begge tilfælde er den samlede allokerede tid for alle ordrer to timer.


### <a name="efficient-resource-can-dedicate-only-part-of-their-work-date-to-productive-work" />Effektiv ressource kan dedikeres en del af deres arbejdsdato til produktiv arbejde

> [!NOTE]
> Dette scenarie kan ikke anbefales. Det anbefales, at du bruger effektivitet i stedet. 

En af dine arbejdscentre repræsenterer en erfaren arbejder, der arbejder med 100 % effektivitet på opgaver. Men de kan kun bruge 50 % af deres arbejdstid på opgaver, fordi resten af den tid, de løser administrative opgaver. Denne arbejder har mulighed for at udføre en opgave på to timer i præcis to timer, så du skal vente endnu to timer, mens personen handler med andre tildelinger.  

Den allokerede operationstid er to timer, og varigheden er fire timer.  

Brug ikke opstillingstid i sådanne scenarier, da systemet kun allokerer 50 % af tiden. Hvis opstillingstiden er angivet til *2*, er den allokerede opstillingstid én time, og varigheden er to timer.

### <a name="consolidated-calendar" />Fælles kalender

Når feltet **Fælles kalender** er markeret, har arbejdscentret ikke sin egen kapacitet. Dens kapacitet er i stedet lig med summen af kapaciteten for alle de produktionsressourcer, der er knyttet til arbejdscentret.  

> [!NOTE]
>  Produktionsressourcens effektivitet konverteres til arbejdscentrets kapacitet.

Hvis du f. eks. har to produktionsressourcer med en effektivitet på henholdsvis 80 og 70, vil den fælles kalenderpost have en effektivitet på 100, en kapacitet på 1,5 og en samlet kapacitet på 12 timer (ottetimers skift * 1,5 kapacitet). 

> [!NOTE]
>  Brug feltet **Fælles kalender**, når du strukturerer ruterne for at planlægge produktionsoperationer på produktionsressourceniveauet, ikke på arbejdscenter niveauet. Når du konsoliderer kalenderen, bliver **Arbejdscenterbelastning**-siden og -rapporter en oversigt over den samlede belastning i alle produktionsressourcer, der er knyttet til ressourcen.

### <a name="example---different-machine-centers-assigned-to-a-work-center" />Eksempel - Du kan knytte forskellige produktionsressourcer til et arbejdscenter

Det er vigtigt at planlægge, hvilke kapaciteter der udgør den samlede kapacitet, når der angives produktionsressourcer og arbejdscentre.

Hvis forskellige produktionsressourcer, f.eks. 210 Pakkebord og 310 Malerkabine, knyttes til et arbejdscenter, er bedømmelsen af de enkelte kapaciteter i produktionsressourcerne vigtig, fordi fejl i en produktionsressource kan forstyrre hele processen. Produktionsressourcerne kan angives i overensstemmelse med deres kapacitet, men skal muligvis ikke medtages i planlægningen. Hvis feltet **Fælles kalender** deaktiveres, er det kun arbejdscentrets kapacitet, som knyttes til planlægningen, men ikke produktionsressourcerne.

Hvis identiske produktionsressourcer, f.eks. 210 Pakkebord 1 og 220 Pakkebord 2, kombineres i et arbejdscenter, kan arbejdscentret betragtes som summen af de tilknyttede produktionsressourcer. Derfor vises arbejdscentret med ingen kapacitet. Ved at aktivere feltet **Fælles kalender** knyttes den fælles kapacitet til arbejdscentret.

Hvis kapaciteter i arbejdscentre ikke skal bidrage til den samlede kapacitet, skal du angive effektivitet = 0.

## <a name="to-set-up-a-capacity-constrained-machine-or-work-center" />Hvis du vil oprette en produktionsressource eller et arbejdscenter med kapacitetsbegrænsning

Du skal oprette produktionsressourcer, som du betragter som kritiske, og udpege dem som i stand til at håndtere en begrænset belastning i stedet for den ubegrænsede belastning, som andre ressourcer kan håndtere. En kapacitetsbegrænset ressource kan f.eks. være et arbejdscenter eller en produktionsressource, der er identificeret som flaskehals, og som du derfor vil tildele en begrænset (endelig) belastning for.

[!INCLUDE[prod_short](includes/prod_short.md)] understøtter ikke detaljeret produktionskontrol. Det planlægger en mulig udnyttelse af ressourcer ved at tilbyde en grov plan, men det opretter og vedligeholder ikke automatisk detaljerede planer, der er baseret på prioriteter eller optimeringsregler.

På siden **Kapacitetsbegrænsede ressourcer** kan du foretage en opsætning, der undgår overbelastning af bestemte ressourcer og sikrer, at ingen kapacitet er ikke-allokeret, hvis det kan forbedre gennemløbstiden for en produktionsordre. I feltet **Aktionsgrænse (% af den samlede kapacitet)** kan du tilføje aktionsgrænsetid for ressourcer for at begrænse tab på opdeling af operationer. Dette gør det muligt for systemet at planlægge belastning på den sidst mulige dag ved at overskride den kritiske belastningsprocent en smule, hvis dette kan reducere antallet af operationer, der er opdelt.

Ved planlægning med kapacitetsbegrænsede ressourcer sikrer systemet, at der ikke indlæses nogen ressource over dens definerede kapacitet (kritisk belastning). Dette gøres ved at tildele hver operation til det nærmeste tilgængelige tidsrum. Hvis tidsrummet ikke er stort nok til at fuldføre hele handlingen, bliver handlingen opdelt i to eller flere dele, der er placeret i de nærmeste ledige tidsrum.

1. Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Kapacitetsbegrænsede ressourcer**, og vælg derefter det relaterede link.
2. Vælg handlingen **Ny**.
3. Udfyld felterne efter behov.

> [!NOTE]
> Operationer i arbejdscentre eller produktionsressourcer, der er opsat som begrænsede ressourcer planlægges altid serielt. Det betyder, at hvis en begrænset ressource har flere kapaciteter, kan disse kapaciteter kun planlægges i sekvenser, ikke parallelt, som det ville være tilfældet, hvis arbejds- eller produktionscenteret ikke var sat op som begrænset ressource. I en begrænset ressource vil feltet Kapacitet på arbejdscenteret eller produktionsressource være større end 1.

> I tilfælde af opdeling af operationen er opstillingstiden kun tildelt én gang, da det antages, at nogen manuel regulering er udført for at optimere planen.

## <a name="see-also" />Se også

[Opsætte produktionskalendere](production-how-to-create-work-center-calendars.md)  
[Konfigurere produktion](production-configure-production-processes.md)  
[Produktion](production-manage-manufacturing.md)  
[Skabelon](production-planning.md)  
[Lagerbeholdning](inventory-manage-inventory.md)  
[Køb](purchasing-manage-purchasing.md)  
[Arbejd med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
