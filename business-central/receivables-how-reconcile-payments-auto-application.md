---
title: Afstemme betalinger ved hjælp af automatisk udligning
description: 'Beskriver, hvordan du afstemmer betalinger med automatisk udligning til at udligne betalinger eller indbetalinger til de relaterede åbne poster.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'payment process, direct payment posting, reconcile payment, expenses, cash receipts'
ms.search.form: '389, 1290, 1294, 1287'
ms.date: 06/22/2022
ms.author: bholtorf
---
# <a name="reconcile-payments-using-automatic-application" />Afstemme betalinger ved hjælp af automatisk udligning

**Betalingsafstemningskladden** angiver betalinger, enten indgående eller udgående, som er registreret som transaktioner på din online bankkonto eller på en betalingstjeneste. Du kan udligne betalingerne til relaterede åbne debitor-, kreditor-og bankkontoposter. Udfyld kladden ved at importere et bankkontoudtog som et feed eller en fil eller ved manuelt at angive de transaktioner, du foretager på din betalingsservice.

> [!NOTE]
> Siden indeholder automatisk matchningsfunktionalitet, der anvender betalinger på de relaterede åbne poster baseret på en sammenligning af data i en bankkontoudtogslinje (kladdelinje) med data i en eller flere åbne poster. Bemærk, at du kan overskrive de foreslåede automatiske udligninger, og du kan vælge slet ikke at bruge automatisk udligning. Du kan finde flere oplysninger i trin 7.

En betalingsafstemningskladde vedrører én bankkonto i [!INCLUDE[prod_short](includes/prod_short.md)]. Bankkontoen repræsenterer den bankkonto, hvor betalingstransaktionerne registreres. Eventuelle åbne bankposter vedrørende de udlignede debitor- eller kreditorposter bliver lukket, når du vælger handlingen **Bogfør betalinger og afstem bankkonti**. Bankkontoen afstemmes automatisk for de betalinger, du bogfører, med kladden.

Hvis du bruger siden **Betalingsafstemningskladde** til at registrere og udligne debitorbetalinger, kan du angive, at kladden skal bruge en bestemt nummerserie. Derefter kan du angive nummerserien i feltet **Betalingsafstemningsnummerserie** på en bankkonto. Hvis du bruger en bestemt nummerserie, kan du nemmere identificere poster, der blev bogført via kladden.

På samme måde som med andre kladder kan du, når du retter bogførte poster, tilbageføre poster, der blev bogført via betalings afstemningskladden fra siden **Finansjournal**. Du kan f. eks. vælge at tilbageføre poster for betalinger, der er anvendt på den forkerte kunde. Du skal først annullere udligningen af de bogførte debitorposter. Derefter kan du bruge handlingen **Tilbagefør Journal** på siden **Finansjournal** til at tilbageføre den kladde, der har bogført betalingerne. Alternativt kan du på siden **Bogførte finanskladder** bruge handlingen **Kopier markerede linjer til kladde** for at tilbageføre specifikke linjer fra den bogførte Betalingsudligningskladde. 

Når du bruger automatisk udligning, genkender [!INCLUDE[prod_short](includes/prod_short.md)] bankposter, der allerede er bogført, og som er med til at forhindre dobbelt bogføring.

Du kan indlæse banktransaktioner som. csv-bankfiler eller et andet format, som banken tilbyder. Hvis du vil indlæse bankkontoudtog, som banken sender som feeds, skal du først aktivere en dedikeret bankintegrationstjeneste og derefter knytter bankkontoen til den relaterede onlinebankkonto. Betalingsudligningskladden registrerer derefter automatisk bankfeeds, når du klikker på handlingen **Importér banktransaktioner**. Du kan desuden konfigurere en bankkonto til automatisk at indlæse nye feeds til bankkontoudtog hver time. Transaktioner for betalinger, der allerede er bogført som udlignet og/eller afstemt indlæses ikke. Du kan bruge Envestnet Yodlee Bank Feeds-tjenesten til disse transaktioner, som er forudinstalleret i nogle landeversioner af [!INCLUDE[d365fin](includes/d365fin_md.md)]. Du kan finde flere oplysninger i [Konfigurere tjenesten Envestnet Yodlee Bank Feeds](bank-how-setup-bank-statement-service.md). Du kan også kontakte din Microsoft-partner for at få hjælp til at opfylde virksomhedens eller landenes krav.

Med handlingen **Knyt tekst til konto** kan du oprette tilknytninger mellem tekst på betalinger og specifikke debet-, kredit- og modkonti, så disse betalinger bliver bogført på de angivne konti, når du bogfører kladden til betalingsafstemning. Tilknytning er brugbar f.eks. for tilbagevendende indbetalinger eller udgifter såsom hyppige køb af benzin eller bankgebyrer og -renter, der regelmæssigt forekommer på bankens kontoudtog, og ikke behøver et relateret forretningsdokument. (Se trin 10) Du kan finde flere oplysninger i [Knytte tekst på tilbagevendende betalinger til automatisk afstemning af konti](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

Kladdelinjer kan ikke have foreslået udligning, hvilket kan ske af forskellige årsager. Dette kan være af forskellig årsag, f.eks. et manglende dokument, eller fordi en debitor har betalt, at der findes en overskydende beløb efter anvendelsen af betalingen på en anden kladdelinje. I sådanne tilfælde kan du bruge handlingen **Overfør difference til konto** til at oprette og bogføre den manglende finanspost, f.eks. et refusion, som kræves for at udligne betalingen. (Se trin 11) Du kan finde flere oplysninger i [Afstemme betalinger, der ikke kan udlignes automatisk](receivables-how-reconcile-payments-cannot-apply-auto.md).

Du kan bruge funktionen **Udlign automatisk** enten automatisk, når du importerer en bankfil eller -feed med betalingstransaktioner, eller når du aktiverer den for at udligne betalinger til deres relaterede åbne poster, der er baseret på en afstemning af tekst på en bankkontoudtogslinje (kladdelinje) med tekst i en eller flere åbne poster. Denne automatisering er baseret på regler, som du har defineret på siden **Betalingsudligningsregler**, hvor du også kan angive, om et ansøgningsforslag kræver gennemsyn. Du kan finde flere oplysninger i [Konfigurere regler for automatisk udligning af betalinger](receivables-how-set-up-payment-application-rules.md).

På kladdelinjer, hvor betaling er udlignet automatisk til en eller flere åbne poster, har feltet **Matchtillid** en værdi mellem **Lav**, **Mellem** eller **Høj** for at angive kvaliteten af den dataafstemning, som den foreslåede betalingsudligning er baseret på.

Nogle betalingsansøgninger kræver din vurdering som defineret af den anvendte sammenholdelses regel, f.eks. linjer med **Lav** matchtillid. Andre linjer kræver gennemsyn og manuel ændring, fordi der er en værdi i feltet **Difference**. Hvis du vil have vist en eller flere betalingsansøgninger, skal du vælge de **linjer, du vil gennemgå**, eller **linjer med difference** nederst. Siden **Anmeldelse af betalingsansøgning** åbnes med alle relevante oplysninger om den debitor eller kreditor, som betalingen er udlignet med, de tilsvarende detaljer og de handlinger, som linjen skal behandles i, f. eks handlingen **Accepter udligning**. (Se trin 7 og 8)

For hver kladdelinje på siden **Betalingsudligningskladde** kan du åbne siden **Betalingsudligning** for at få vist alle åbne kandidatposter for betalingen og se detaljerede oplysninger for hver post om den dataafstemning, som en betalingsudligning er baseret på. Her kan du manuelt udligne betalinger eller udligne betalinger igen, der er udlignet automatisk til en forkert post. (Se trin 10) Du kan finde flere oplysninger i [Gennemse eller udligne betalinger efter automatisk udligning](receivables-how-review-apply-payments-auto-application.md).

> [!NOTE]  
> Du kan starte importen af banktransaktioner på samme tid, som du åbner siden **Betalingsudligningskladde** for en eksisterende betalingsafstemningskladde. Følgende procedure beskriver, hvordan du importerer banktransaktioner på siden **Betalingsudligningskladde**, når du har oprettet en ny kladde.

## <a name="to-reconcile-payments-using-automatic-application" />Sådan afstemmer du betalinger ved hjælp af automatisk udligning
1. Vælg ![Lightbulb, der åbner funktionen Fortæl mig.](media/ui-search/search_small.png "Fortæl mig, hvad du vil foretage dig") ikon, skriv **Betalingsudligningskladder**, og vælg derefter det relaterede link.
2. Hvis du vil arbejde i en ny betalingsafstemningskladde, skal du vælge handlingen **Ny kladde**.
3. Brug siden **Betalingsbankkontooversigt** til at vælge den bankkonto, som du vil afstemme betalinger for, og vælg derefter knappen **OK**.
   Siden **Betalingsudligningskladde** åbnes forberedt til den valgte bankkonto.
4. Vælg handlingen **Importer banktransaktioner**.
   Hvis bankkontoen for den valgte kladde ikke er sat op til at indlæse banktransaktioner, hjælper [!INCLUDE[d365fin](includes/d365fin_md.md)] med at gøre det.
5. Brug siden **Vælg den fil, der skal importeres** til at vælge den fil, der indeholder banktransaktioner for betalinger, der skal afstemmes, og vælg derefter knappen **Åbn**.  
6. Hvis tjenesten Envestnet Yodlee Bank Feeds er aktiveret, skal du på siden **Bankkontoudtogsfilter**, der åbnes automatisk, angive datointervallet for bankkontoudtog, der skal importeres.

    Siden **Betalingsudligningskladde** er fyldt med linjer for betalinger, der repræsenterer banktransaktioner i det importerede bankkontoudtog.

     På linjer, hvor betaling er udlignet automatisk til den relaterede åbne post, har feltet **Matchtillid** en værdi mellem Lav og Høj for at angive kvaliteten af den dataafstemning, som den foreslåede betalingsudligning er baseret på. Derudover bliver felterne **Kontonavn**, **Kontotype** og **Kontonr.** udfyldt med oplysninger om debitoren eller kreditoren, som betalingen udlignes for.

    De automatiske programmer, tilsvarende kvaliteter, og om linjer kræver gennemsyn, er defineret af regler. Du kan redigere reglerne, så resultaterne justeres. Du kan finde flere oplysninger i [Konfigurere regler for automatisk udligning af betalinger](receivables-how-set-up-payment-application-rules.md).

7. Hvis du vil gennemgå, acceptere/fjerne eller manuelt ændre flere betalingsansøgninger, der har en værdi i feltet **Difference**, skal du vælge handlingen **Linjer med difference** nederst.

    Siden **Anmeldelse af betalingsansøgning** åbnes, og det første program, der skal gennemgås, vises. Det næste program, der skal gennemses, vises på siden, når du behandler det foregående. Gennemsynet omfatter oplysninger om den debitor eller kreditor, som betalingen er udlignet med, de tilsvarende detaljer og de handlinger, som linjen skal behandles i, f. eks handlingen **Accepter udligning** og **Anvend manuelt**.

8. Hvis du vil gennemgå, acceptere eller fjerne eller manuelt ændre flere betalings programmer, som reglen er indstillet til gennemsyn, skal du vælge de **linjer, der skal gennemgås**. 

9. Hvis du vil ændre en automatisk udligning, skal du vælge en kladdelinje og derefter handlingen **Udlign manuelt**, der skal gennemgås, eller udlign betalingen manuelt på siden **Betalingsudligning**. Du kan finde flere oplysninger i [Gennemse eller udligne betalinger efter automatisk udligning](receivables-how-review-apply-payments-auto-application.md).

10. Vælg en ikke-udlignet kladdelinje for en tilbagevendende indbetaling eller en udgift, f.eks køb af benzin, og vælg derefter handlingen **Knyt tekst til konto**. Du kan finde flere oplysninger i [Knytte tekst på tilbagevendende betalinger til automatisk afstemning af konti](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md)

    Når du er færdig med at knytte betalingstekst til konti, skal du vælge handlingen **Udlign manuelt**.

    Når der oprettes en tekst-til-konto-tilknytning, indeholder den resulterende automatiske betalingsudligning automatisk **Høj - Tilknytning af tekst til konto** i feltet **Match tillid**.

11. For en kladdelinje er der ikke noget foreslået program, da der ikke findes en post, som kan udlignes, skal du vælge handlingen **Overfør difference til konto** for at oprette og bogføre den manglende finanspost, der skal bruges til at udligne betalingen med. Du kan finde flere oplysninger i [Afstemme betalinger, der ikke kan udlignes automatisk.](receivables-how-reconcile-payments-cannot-apply-auto.md)

12. Hvis der ikke kræves yderligere linjer, og feltet **Difference** er tomt på alle linjer, skal du vælge **Bogfør**-handlingen og derefter vælge en af følgende indstillinger:

    - **Bogfør betalinger og afstem bankkonti** - Hvis du vil bogføre betalingerne som udlignet, og også lukke de relaterede bankposter som afstemt.
    - **Bogfør kun betalinger** - Hvis du kun vil bogføre betalingerne som udlignet, men lade de relaterede bankposter være åbne. Det er nødvendigt, at du afstemmer bankkontoen separat. Du kan finde flere oplysninger i f.eks. [Afstemme bankkonti](bank-how-reconcile-bank-accounts-separately.md).
    - **Kontrollér rapport** - For at få vist resultatet af bogføringen, inden du bogfører. Rapporten **Bankkontoudtog** åbnes og viser de samme felter som i bunden af siden **Betalingsudligningskladde**.

Når du bogfører betalings afstemningskladden, lukkes de udlignede åbne poster. Debitor-, kreditor-eller finanskontiene opdateres. De angivne debitor-, kreditor- og finanskonti opdateres for betalinger på kladdelinjer, der er baseret på tekst-til-kontotilknytning. For alle kladdelinjer oprettes bankposter. Hvis du vælger handlingen **Bogfør betalinger og afstem bankkonti**, bliver eventuelle åbne bankposter vedrører de udlignede debitor- eller kreditorposter lukket. Det betyder, at bankkontoen automatisk afstemmes for de betalinger, du bogfører, med kladden.

Du kan sammenligne værdien i feltet **Saldo på bankkonto efter bogføring** med værdien i feltet **Kontoudtogs slutsaldo** for at spore, hvornår bankkontoen er afstemt baseret på betalinger, du bogfører.

> [!NOTE]  
>   Hvis du ikke vil afstemme bankkontoen fra siden **Betalingsudligningskladde**, skal du bruge siden **Bankkontoafstemning**. Du kan finde flere oplysninger i [Afstemme bankkonti](bank-how-reconcile-bank-accounts-separately.md).

## <a name="see-related-microsoft-trainingtrainingmodulesuse-journals-dynamics-365-business-central" />Se relateret [Microsoft-træning](/training/modules/use-journals-dynamics-365-business-central/)

## <a name="see-also" />Se også

[Administrere tilgodehavender](receivables-manage-receivables.md)  
[Salg](sales-manage-sales.md)  
[Arbejd med [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
