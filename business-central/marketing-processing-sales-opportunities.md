---
title: Behandle salgsmuligheder i salgsprocesser
description: 'I dette emne beskrives de forskellige måder, du kan behandle salgsmuligheder på i salgsprocesser og flytte et lead gennem en salgsproces.'
author: jswymer
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'relationship, prospect'
ms.date: 06/22/2021
ms.author: jswymer
---
# <a name="process-sales-opportunities" />Behandle salgsleads
Når du opretter et lead, er der flere funktioner til administration af et lead og til at flytte det til afslutning.

## <a name="to-view-opportunities" />Sådan vises salgsmuligheder
De eksisterende salgsmuligheder er tilgængelige på siden **Salgsmulighedsoversigt**. Der er forskellige måder at få adgang til siden for at behandle salgsmuligheder:

| For at få vist salgsleads for | Så |
| --- | --- |
| Alle sælgere og kontakter |Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Leadoversigt**, og vælg derefter det relaterede link. |
| En bestemt sælger |Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Sælgere**, og vælg derefter det relaterede link. Vælg sælgeren, vælg handlingen **Leads**, og vælg derefter handlingen **Oversigt**. |
| En bestemt kontakt |Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Kontakter**, og vælg derefter det relaterede link. Vælg kontakten på listen, og vælg derefter handlingen **Leads**. |

Hver af disse opgaver åbnes på siden **Salgsmulighedsoversigt**.

## <a name="to-close-opportunities" />Sådan lukkes leads
Når forhandlingerne er afsluttet, kan du lukke leads. Når du lukker et lead, kan du samtidig angive, om det blev vundet eller tabt, og hvorfor det lukkes. For at angive en årsag, skal du have defineret lukkekoder for leads.

1. På siden **Salgsmulighedsoversigt** skal du vælge salgsmuligheden og derefter vælge handlingen **Luk**. Siden **Luk salgsmulighed** åbnes.
2. Udfyld de relevante felter, og vælg derefter knappen **OK**.

   Felterne **Leadlukkekode** og **Lukket den** er obligatoriske og skal udfyldes, før du kan vælge knappen **OK**.

   I feltet **Leadlukkekode** kan du vælge en af de eksisterende leadlukkekoder eller tilføje en ny kode. Du kan tilføje en ny kode ved at vælge **Vælg fra komplet liste** på listen og derefter vælge **ny**. På den nye tomme linje skal du udfylde felterne **Kode**, **Type** og **Beskrivelse** og derefter vælge knappen **OK**.

## <a name="to-create-quotes-for-opportunities" />Sådan oprettes tilbud til leads
> [!NOTE]
> Du kan kun oprette salgstilbud fra Leads, hvor kontakttypen er Virksomhed.

1. På siden **Salgsmulighedsoversigt** skal du vælge salgsmuligheden og derefter vælge handlingen **Tildel salgstilbud**. Siden **Salgstilbud** åbnes.
2. Udfyld de relevante felter.

## <a name="to-create-sales-orders-for-opportunities" />Sådan oprettes salgsordrer til leads
Du kan oprette salgsordrer ud fra de tilbud, som du har oprettet til leads. Før du kan oprette salgsordrer til dine kontaktpersoner, skal du oprette kontaktpersonen som debitor. Du kan finde flere oplysninger i [Oprette kontakter](marketing-create-contact-companies.md).

1. På siden **Salgsmulighedsoversigt** skal du finde den salgsmulighed, du har oprettet et salgstilbud til.
2. Vælg handlingen **Tildel salgstilbud**. Siden **Salgstilbud**, der indeholder det salgstilbud, som du har knyttet til salgsmuligheden, åbnes.
3. Udfyld de øvrige felter, og vælg derefter handlingen **Lav ordre**.

Når du arbejder med leads, kan det være nødvendigt at afgive tilbud til den kontakt, som leadet vedrører.

## <a name="to-delete-opportunities" />Sådan slettes leads
Du kan slette lead, hvis du f.eks. har afsluttet en handel. Men du kan kun slette lukkede leads. Der er to måder at slette lukkede leads. Du kan slette individuelle lukkede salgsmuligheder fra siden **Salgsmulighedsoversigt**, eller du kan starte kørslen **Slet lukkede salgsmuligheder** for at slette flere salgsmuligheder baseret på et angivet kriterium.

Når du vil slette lukkede salgsmuligheder fra siden **Salgsmulighedsoversigt**, skal du vælge salgsmuligheden og derefter vælge handlingen **Slet**.

Du sletter lukkede leads med kørslen **Slet lukkede leads** ved at følge disse trin:

1. Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Slet leads**, og vælg derefter det relaterede link.
2. I afsnittet **Lead** skal angive filtre, der angiver de lukkede leads, der skal slettes.
3. Vælg knappen **OK**.

Når du har slettet en salgsmulighed, fjernes det automatisk fra siden **Salgsmulighedsoversigt**.

## <a name="to-move-an-opportunity-through-sales-cycle-stages" />Sådan flyttes et lead via salgsprocesfaser
Hvis et lead følger en salgsproces, kan du flytte det frem eller tilbage i de forskellige faser, f.eks flytte til den næste eller forrige fase og også springe en fase over.

1. Vælg handlingen **Opdater** på siden **Salgsmulighedsoversigt**. **Opdater lead** åbnes.
2. Brug feltet **Handlingstype** til at flytte leadet gennem salgsprocesfaserne:
   * **Næste** flytter et lead én fase frem.
   * **Spring over** flytter et lead en eller flere faser frem i salgsprocessen, som du angiver i feltet **Præsentation**. Du kan kun springe faser over, der er indstillet til at tillade overspringning.
   * **Forrige** flytter et lead én fase tilbage.
   * **Gå til** flytter et lead en eller flere faser tilbage i salgsprocessen, som du angiver i feltet **Præsentation**.
   * Med **Opdater** kan du ændre oplysninger (f.eks. for at ændre vurderingen af succespotentialet eller de anslåede værdier) uden at flytte til en anden fase.
3. Udfyld de øvrige felter efter behov, og vælg derefter knappen **OK**.

## <a name="see-also" />Se også
[Salg](sales-manage-sales.md)  
[Oprette og administrere kontakter](marketing-contacts.md)  
[Arbejd med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
