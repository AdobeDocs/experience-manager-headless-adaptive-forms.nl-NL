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
source-wordcount: '934'
ht-degree: 0%

---


# Een aangepaste reactiebibliotheek gebruiken om een koploze vorm te genereren

U kunt aangepaste componenten maken en implementeren om de weergave en functionaliteit (Gedrag) van uw Zwaarloze adaptieve formulieren aan te passen aan de vereisten en richtlijnen van uw organisatie.

Deze componenten hebben twee hoofddoelen: de weergave of stijl van formuliervelden bepalen en de gegevens die via deze velden worden verzameld, opslaan in de formuliermodelinstantie. Als dit verwarrend klinkt, maak je geen zorgen - we zullen deze doelen binnenkort gedetailleerder onderzoeken. Voor nu, laten de nadruk op de aanvankelijke stappen van het creëren van douanecomponenten, die de vorm teruggeven gebruikend deze componenten, en het gebruiken van gebeurtenissen om gegevens aan een REST eindpunt te bewaren en voor te leggen.

In deze zelfstudie worden UI-componenten voor materiaal van Google gebruikt om te tonen hoe een Zwaartepunt-adaptief formulier kan worden gegenereerd met behulp van aangepaste React-componenten. U bent echter niet beperkt tot deze bibliotheek en u kunt elke React-componentenbibliotheek gebruiken of uw eigen aangepaste componenten ontwikkelen.

Aan de hand van dit artikel _Contact opnemen_ formulier gemaakt in [Een formulier zonder kop maken en publiceren met de startkit](create-and-publish-a-headless-form.md) artikel verandert in het volgende:

![](assets/headless-adaptive-form-with-google-material-ui-components.png)


De belangrijkste stappen die nodig zijn voor het weergeven van een formulier met UI-componenten voor Google-materiaal zijn:

![](assets/headless-forms-graphics-source-main.svg)

## 1. Interface voor Google-materiaal installeren

Standaard wordt de startkit gebruikt [Spectrum van Adobe](https://spectrum.adobe.com/) componenten. Laten we het gebruiken [UI voor Google-materiaal](https://mui.com/):

1. Zorg ervoor dat de startkit niet wordt uitgevoerd. Om de starteruitrusting tegen te houden, open uw terminal, navigeer aan **response-starter-kit-aem-headless-forms** en druk op Ctrl-C (hetzelfde is het geval in Windows, Mac en Linux).

   Probeer niet om de terminal te sluiten. Als u de terminal sluit, wordt de startkit niet gestopt.

1. Voer de volgende opdracht uit:

```shell
    
    npm install @mui/material @emotion/react @emotion/styled --force
    
```

De Npm-bibliotheken voor materiaal van Google worden geïnstalleerd en de bibliotheken worden toegevoegd aan afhankelijkheden van startsets. U kunt nu Materiële UI-componenten gebruiken om formuliercomponenten te genereren.


## 2. Aangepaste Reactie-componenten maken

Laten we een aangepaste component maken die standaard vervangt [tekstinvoer](https://spectrum.adobe.com/page/text-field/) component met [Tekstveld Google Material UI](https://mui.com/material-ui/react-text-field/) component.

Voor elk componenttype ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) of :type) wordt gebruikt in een definitie voor een formulier zonder koptekst. In het formulier Contact opnemen dat u in de vorige sectie hebt gemaakt, zijn bijvoorbeeld de velden Naam, E-mail en Telefoon van het type `text-input` ([fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def)) en het berichtveld is van het type `multiline-input` ([&quot;fieldType&quot;: &quot;multiline-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/reference-json-properties-fieldtype--multiline-input)).


Laten we een aangepaste component maken om alle formuliervelden te bedekken die de [fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) eigenschap met [Tekstveld voor materiaalinterface](https://mui.com/material-ui/react-text-field/) component.


Om de douanecomponent tot stand te brengen en de douanecomponent met in kaart te brengen [fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) eigenschap:

1. Open de **response-starter-kit-aem-headless-forms** in een code-editor en navigeer naar `\react-starter-kit-aem-headless-forms\src\components`.


1. Maak een kopie van het dialoogvenster **schuifregelaar** of **richtext** en wijzig de naam van de gekopieerde map in **materialtextfield**. De schuifregelaar en richtext zijn twee voorbeelden van aangepaste componenten die beschikbaar zijn in de startapp. U kunt deze gebruiken om uw eigen aangepaste componenten te maken.

   ![De aangepaste component materialtextfield in VSCode](/help/assets/richtext-custom-component-in-vscode.png)

1. Open de `\react-starter-kit-aem-headless-forms\src\components\materialtextfield\index.tsx` en vervang de bestaande code door de onderstaande code. Deze code retourneert en geeft een [Tekstveld Google Material UI](https://mui.com/material-ui/react-text-field/) component.

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


De `state.visible` onderdeel controleert of de component is ingesteld op zichtbaar. Als dit het geval is, wordt het label van het veld opgehaald en weergegeven met `richTextString(state?.label?.value)`.

![](/help/assets/material-text-field.png)


Uw aangepaste component `materialtextfield` is klaar. Laten we deze aangepaste component instellen om alle instanties van  [fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) met het tekstveld UI-tekst voor materiaal van Google.

## 3. Aangepaste component toewijzen met formuliervelden zonder kop

Het proces van het gebruik van bibliotheekcomponenten van derden voor het weergeven van formuliervelden wordt ook wel aangeduid als toewijzing. U wijst elk ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input)) aan de overeenkomstige component van de bibliotheek van derden.

Alle informatie over de toewijzing wordt toegevoegd aan de `mappings.ts` bestand. De `...mappings` in de `mappings.ts` het bestand verwijst naar de standaardtoewijzingen, die de ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) of :type) met [Spectrum Adobe](https://spectrum.adobe.com/page/text-field/) componenten.

Toewijzing toevoegen voor de  `materialtextfield` component, gemaakt in de laatste stap:

1. Open de `mappings.ts` bestand.

1. Voeg de volgende importinstructie toe om de instructie `materialtextfield` aan de component `mappings.ts` bestand:


   ```JavaScript
       import MaterialtextField from "../components/materialtextfield";
   ```

1. Voeg de volgende verklaring toe om in kaart te brengen `text-input` met de component materialtextfield.


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

1. Sla de app op en voer deze uit. De eerste drie velden van het formulier worden weergegeven met [Tekstveld Google Material UI](https://mui.com/material-ui/react-text-field/):

   ![](assets/material-text-field-form-rendetion.png)


   Op dezelfde manier kunt u aangepaste componenten maken voor het bericht (&quot;fieldType&quot;: &quot;multiline-input&quot;) en de velden Service (&quot;fieldType&quot;:&quot;number-input&quot;) beoordelen. U kunt de volgende gegevensopslagplaats van de Git voor douanecomponenten van bericht klonen en de de dienstgebieden schatten:

   [https://github.com/singhkh/react-starter-kit-aem-headless-forms](https://github.com/singhkh/react-starter-kit-aem-headless-forms)

## Volgende stap

U hebt het formulier gegenereerd met aangepaste componenten die gebruikmaken van de gebruikersinterface van Google-materiaal. Hebt u geprobeerd het formulier te verzenden door op de knop Verzenden te klikken (toegewezen aan de overeenkomstige UI-component voor Google-materiaal)? Zo niet, ga dan maar door en probeer het.

Verzendt het formulier de gegevens naar een gegevensbron? Nee? Maak je geen zorgen. Dit komt omdat het formulier niet is geconfigureerd voor communicatie met de runtimebibliotheek.

Hoe kunt u uw formulier configureren om ermee te communiceren? Er komt binnenkort een artikel dat alles in detail zal uitleggen. Blijf op de hoogte!
