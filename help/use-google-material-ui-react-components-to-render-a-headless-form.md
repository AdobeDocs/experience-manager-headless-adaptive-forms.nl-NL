---
title: UI-reactiecomponenten voor Google-materiaal gebruiken om een koploze vorm te genereren
description: Leer hoe u Google Material-UI React-componenten gebruikt om een vorm zonder kop te genereren. Deze uitgebreide handleiding begeleidt u stapsgewijs door het proces voor het maken van aangepaste Forms-componenten zonder koptekst, zodat u de Google Material-UI React-componenten kunt toewijzen en gebruiken om een Headless Adaptive Form op te maken.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: 476509d5-f4c1-4d1c-b124-4c278f67b1ef
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '863'
ht-degree: 0%

---


# Een aangepaste reactiebibliotheek gebruiken om een koploze vorm te genereren

U kunt aangepaste componenten maken en implementeren om de weergave en functionaliteit (Gedrag) van uw Zwaarloze adaptieve formulieren aan te passen aan de vereisten en richtlijnen van uw organisatie.

Deze componenten hebben twee hoofddoelen: de weergave of stijl van formuliervelden bepalen en de gegevens die via deze velden worden verzameld, opslaan in de formuliermodelinstantie. Als dit verwarrend klinkt, maak je geen zorgen - we zullen deze doelen binnenkort gedetailleerder onderzoeken. Voor nu, laten de nadruk op de aanvankelijke stappen van het creëren van douanecomponenten, die de vorm teruggeven gebruikend deze componenten, en het gebruiken van gebeurtenissen om gegevens aan een REST eindpunt te bewaren en voor te leggen.

In deze zelfstudie worden UI-componenten voor materiaal van Google gebruikt om te tonen hoe een Zwaartepunt-adaptief formulier kan worden gegenereerd met behulp van aangepaste React-componenten. U bent echter niet beperkt tot deze bibliotheek en u kunt elke React-componentenbibliotheek gebruiken of uw eigen aangepaste componenten ontwikkelen.

Door de conclusie van dit artikel, de _vorm van het Contact van ons_ die in [ wordt gecreeerd creeert en publiceert een hoofdloze vorm gebruikend starter kit ](create-and-publish-a-headless-form.md) artikel zet in het volgende om:

![](assets/headless-adaptive-form-with-google-material-ui-components.png)


De belangrijkste stappen die nodig zijn voor het weergeven van een formulier met UI-componenten voor Google-materiaal zijn:

![](assets/headless-forms-graphics-source-main.svg)

## 1. Interface voor Google-materiaal installeren

Door gebrek, gebruikt de aanzetuitrusting [&#128279;](https://spectrum.adobe.com/) componenten van het Spectrum van de Adobe . Laat het plaatsen om [ Materiële UI van Google te gebruiken ](https://mui.com/):

1. Zorg ervoor dat de startkit niet wordt uitgevoerd. Om de starteruitrusting tegen te houden, open uw terminal, navigeer aan **reactie-starter-kit-a-headless-vormen**, en druk CTRL-C (het is het zelfde op Vensters, Mac &amp; Linux).

   Probeer niet om de terminal te sluiten. Als u de terminal sluit, wordt de startkit niet gestopt.

1. Voer de volgende opdracht uit:

```shell
    
    npm install @mui/material @emotion/react @emotion/styled --force
    
```

De Npm-bibliotheken voor materiaal van Google worden geïnstalleerd en de bibliotheken worden toegevoegd aan afhankelijkheden van startsets. U kunt nu Materiële UI-componenten gebruiken om formuliercomponenten te genereren.


## 2. Aangepaste Reactie-componenten maken

Laten wij een douanecomponent tot stand brengen die standaard [&#128279;](https://spectrum.adobe.com/page/text-field/) component van de tekstinput  met [ de Materiële UI van Google component van het Gebied van de Tekst ](https://mui.com/material-ui/react-text-field/) vervangt.

Een afzonderlijke component wordt vereist voor elk componenttype ([ fieldType ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) of :type) dat in een definitie van de Vorm zonder titel wordt gebruikt. Bijvoorbeeld, in de vorm van het Contact Us die u in de vorige sectie creeerde, zijn de Naam, E-mail, en de gebieden van de Telefoon van type `text-input` ([ fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def)) en het berichtgebied van type `multiline-input` ([ &quot;fieldType&quot;: &quot;multiline-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/reference-json-properties-fieldtype--multiline-input)).


Laten wij een douanecomponent tot stand brengen om alle vormgebieden te bedekken die [ fieldType gebruiken: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) bezit met [ Materiële UI de component van het Gebied van de Tekst ](https://mui.com/material-ui/react-text-field/).


Om de douanecomponent tot stand te brengen en de douanecomponent met het [ fieldType ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) bezit in kaart te brengen:

1. Open de **reactie-starter-kit-a-headless-vormen** folder in een coderedacteur en navigeer aan `\react-starter-kit-aem-headless-forms\src\components`.


1. Creeer een exemplaar van de **schuif** of **richtext** omslag, en noem de gekopieerde omslag anders aan **materialtextfield**. De schuifregelaar en richtext zijn twee voorbeelden van aangepaste componenten die beschikbaar zijn in de startapp. U kunt deze gebruiken om uw eigen aangepaste componenten te maken.

   ![ de materialtextfield douanecomponent in VSCode ](/help/assets/richtext-custom-component-in-vscode.png)

1. Open het `\react-starter-kit-aem-headless-forms\src\components\materialtextfield\index.tsx` -bestand en vervang de bestaande code door de onderstaande code. Deze code keert terug en geeft a [ Materiële UI de component van het Gebied van de Tekst van A &lbrace;](https://mui.com/material-ui/react-text-field/) terug.

```JavaScript
 
     import React from 'react';
     import {useRuleEngine} from '@aemforms/af-react-renderer';
     import {FieldJson, State} from '@aemforms/af-core';
     import { TextField } from '@mui/material';
     import Box from '@mui/material/Box';
     import { richTextString } from '@aemforms/af-react-components';
     import Typography from '@mui/material/Typography';


     const MaterialtextField = function (props: State<FieldJson>) {

         const [state, handlers] = useRuleEngine(props);

         return(

         <Box>
             <Typography component="legend">{state.visible ? richTextString(state?.label?.value): ""} </Typography>
             <TextField variant="filled"/>
         </Box>

         )
     }

     export default MaterialtextField;
```


Het `state.visible` -onderdeel controleert of de component is ingesteld op zichtbaar. Als dit het geval is, wordt het label van het veld opgehaald en weergegeven met `richTextString(state?.label?.value)` .

![](/help/assets/material-text-field.png)


Uw aangepaste component `materialtextfield` is gereed. Laten wij deze douanecomponent plaatsen om alle instanties van [ fieldType te vervangen: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) met het Materiële UI- Gebied van de Tekst van Google.

## 3. Aangepaste component toewijzen met formuliervelden zonder kop

Het proces van het gebruik van bibliotheekcomponenten van derden voor het weergeven van formuliervelden wordt ook wel aangeduid als toewijzing. U brengt elk ([ fieldType ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input)) aan overeenkomstige component van derdebibliotheek in kaart.

Alle informatie over toewijzingen wordt toegevoegd aan het `mappings.ts` -bestand. De `...mappings` verklaring in het `mappings.ts` dossier verwijst naar de standaardafbeeldingen, die ([ fieldType ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) of :type) met [ componenten van het Spectrum van de Adobe ](https://spectrum.adobe.com/page/text-field/) bedekken.

Als u toewijzingen wilt toevoegen voor de component `materialtextfield` , die u in de laatste stap hebt gemaakt:

1. Open het `mappings.ts` -bestand.

1. Voeg de volgende instructie import toe om de component `materialtextfield` op te nemen in het `mappings.ts` -bestand:


   ```JavaScript
       import MaterialtextField from "../components/materialtextfield";
   ```

1. Voeg de volgende instructie toe om de `text-input` toe te wijzen aan de component materialtextfield.


   ```JavaScript
       "text-input": MaterialtextField
   ```

   De uiteindelijke code van het bestand ziet er als volgt uit:

   ```JavaScript
         import { mappings } from "@aemforms/af-react-components";
         import MaterialtextField from "../components/materialtextfield";
   
   
         const customMappings: any = {
           ...mappings,
           "text-input": MaterialtextField
        };
        export default customMappings;
   ```

1. Sla de app op en voer deze uit. De eerste drie gebieden van de vorm worden teruggegeven gebruikend [ Materiële UI het Gebied van de Tekst van Google ](https://mui.com/material-ui/react-text-field/):

   ![](assets/material-text-field-form-rendetion.png)


   Op dezelfde manier kunt u aangepaste componenten maken voor het bericht (&quot;fieldType&quot;: &quot;multiline-input&quot;) en de velden Service (&quot;fieldType&quot;:&quot;number-input&quot;) beoordelen. U kunt de volgende gegevensopslagplaats van de Git voor douanecomponenten van bericht klonen en de de dienstgebieden schatten:

   [ https://github.com/singhkh/react-starter-kit-aem-headless-forms](https://github.com/singhkh/react-starter-kit-aem-headless-forms)

## Volgende stap

U hebt het formulier gegenereerd met aangepaste componenten die gebruikmaken van de gebruikersinterface van Google-materiaal. Hebt u geprobeerd het formulier te verzenden door op de knop Verzenden te klikken (toegewezen aan de overeenkomstige UI-component voor Google-materiaal)? Zo niet, ga dan maar door en probeer het.

Verzendt het formulier de gegevens naar een gegevensbron? Nee? Maak je geen zorgen. Dit komt omdat het formulier niet is geconfigureerd voor communicatie met de runtimebibliotheek.

Hoe kunt u uw formulier configureren om ermee te communiceren? Er komt binnenkort een artikel dat alles in detail zal uitleggen. Blijf op de hoogte!
