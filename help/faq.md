---
title: Veelgestelde vragen over Headless Adaptive Forms
description: Veelgestelde vragen
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloos, adaptief formulier, veelgestelde vragen
index: true
exl-id: 5bfc307d-96a3-4007-b65f-32176ecdb710
source-git-commit: 86129488bec7faed87600a237ac034ca1b601187
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 0%

---

# Veelgestelde vragen (FAQ) {#headless-adaptive-forms-faq}

## Moet ik React.js kennen om Zwaardeloze adaptieve vormen te gebruiken?

U kunt elk framework, elke bibliotheek of elke taal gebruiken om Zzonder koppen adaptieve formulieren te genereren en REST API&#39;s van Adobe te gebruiken voor het valideren en verzenden van de formulieren. De AF-core bibliotheek, die aan u wordt verstrekt uit-van-de-doos, is kaderonafhankelijk. React-Render en React-componet bibliotheken, die ook aan u uit-van-de-doos worden verstrekt, zijn voor uw gemak. U kunt uw eigen componenten maken. U bent niet beperkt tot de beschikbare componenten.


<!-- 
## Did Adobe release a new AEM Archetype for Headless adaptive forms?

You can use Archetype 37 with flag `includeFormsheadless` or later flag to create an AEM project with Headless adaptive forms functionality. 

-->

## Heb ik Forms as a Cloud Service-sandbox nodig om Headless adaptieve formulieren te gebruiken?

Met de startapp kunt u beginnen met het ontwikkelen en opmaken van adaptieve formulieren zonder koptekst. U hebt Forms as a Cloud Service nodig om adaptieve formulieren zonder koptekst te hosten en te bedienen, samen met mogelijkheden voor back-end formulieren.

<!-- 
## Do I need an archetype project to develop Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. Later on, you can use the 
archetype project to deploy the finished Headless adaptive forms and corresponding custom code, created using starter app, to Forms as a Cloud Service environment. The Forms as a Cloud Service environment helps you test and productionize the forms. 
-->

## Waar kan ik een voorvertoning van een Headless adaptive-formulier krijgen? {#storybook-example}

U kunt de starttoepassing gebruiken om een aangepast, hoofdloos adaptief formulier te genereren en voor te vertonen. U kunt a [ storybook ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples—Introductie) voorbeeld ook wijzigen om een Headless adaptieve vorm voor te vertonen.

![](/help/assets/storybook-example.png)

## Is het mogelijk om Zwaardeloze adaptieve vormen met douanekaders te gebruiken?

Hoofdloze adaptieve vormen zijn gebaseerd op [ standaardspecificatie ](/help/assets/headless-adaptive-forms-specification.pdf). U kunt de specificatie uitbreiden om het te gebruiken om douanecomponenten te bouwen. Bijvoorbeeld, componenten voor Chakra UI, Vue.js, en meer.

## Worden trapsgewijze velden ondersteund door hulpformulieren zonder koptekst?

In trapsgewijze velden hangt de inhoud van het tweede veld af van de inhoud die in het eerste veld is gekozen. Het [ Storybook ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behavior—options&args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJS son.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) verstrekt een voorbeeld van het trapsgewijze gebieden.

## Kunnen formulieren zonder koptekst en aanpassingen vooraf worden ingevuld met gepersonaliseerde gegevens?

Met adaptieve formulieren zonder koppen kunnen formulieren vooraf worden ingevuld met gepersonaliseerde gegevens. Het [ Storybook ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples—Prefill-form-with-personalized-data) verstrekt een voorbeeld van hoe te om een Zwaarteloze adaptieve vorm vooraf in te vullen.

<!--
## Can I use existing Adaptive Forms editor to create a Headless adaptive form?

At this moment, you use the Adaptive Form Editor to specify the JSON structure and set submit action for the forms. Support for drag-and-drop components, applying rules using editor, and more editor-related options would be available later in the beta phase. Keep a watch on release notes.  
-->

## Kan ik Headless adaptieve formulieren gebruiken met Angular SPA?

U kunt de SDK Web gebruiken om Zwaardeloze adaptieve vormen met Angular SPA te integreren. Het staat los van elk kader. U kunt de React SDK als verwijzing gebruiken.

<!--
## Should the `-r prerelease` switch be used every time to start the AEM SDK instance or only for the first time?

During the limited release program, use the `-r prerelease` switch every time you start the AEM SDK instance. 

## What is AEM Forms add-on (.far file) and how to install it?

Adobe Experience Manager Forms as a Cloud Service feature archive provides tools to create Headless adaptive forms on the local development environment. To install the feature archive, see [Setup development environment](setup-development-environment.md).

## Where do one get the license.properties file from?

You do not require a license.properties file to run AEM Cloud Service SDK. 
-->

## Is er een insteekmodule om de ontwikkeling voor Headless AF te vereenvoudigen?

Ja — een uitbreiding van de Code van Visual Studio laat u manueel auteur koploze adaptieve vormen in JSON.

## Wat is de aanbevolen aanpak voor mobiele of offline formulieren? {#mobile-offline-forms}

Bouw uw eigen native app en haal formulierdefinities op via de Headless Adaptive Forms API. U kunt desgewenst offline ondersteuning implementeren (bijvoorbeeld lokale opslag en synchronisatie). Zie [ Mobiele vormen beste praktijken ](mobile-forms-best-practices.md) voor de geadviseerde benadering en verbindingen aan APIs.

## Hoe gebruikt u GraphQL of headless APIs met AEM Forms?

AEM Headless Adaptive Forms gebruikt **HTTP/REST APIs**, niet GraphQL. Uw app roept deze API&#39;s aan om formulieren weer te geven, een formulierdefinitie (JSON) op te halen, te valideren, te verzenden en de verzendstatus bij te houden. Gebruik [ Hoofdloze adaptieve vormenHTTP APIs ](https://opensource.adobe.com/aem-forms-af-runtime/api/) voor de volledige verwijzing. Voor hoe de vormen worden opgehaald en teruggegeven, zie [ Architectuur ](architecture.md) en [ Begrip hoofdloze vormen ](understanding-headless-forms.md).

## Hoe kan ik hoofdloze formulieren implementeren en opmaken met React-componenten in Adobe AEM Forms?

U implementeert en maakt koploze formulieren met behulp van uw eigen React-componenten en CSS (of een UI-bibliotheek zoals de materiaalinterface). De formulierlogica (status, validatie en regels) is afkomstig van de Forms Web SDK en het JSON-formulier. Uw app levert de interface die deze weergeeft.

* Om een hoofdloze vorm met een Reactie UI bibliotheek te stileren, zie [ Gebruik een douane reactiebibliotheek om een koploze vorm ](use-google-material-ui-react-components-to-render-a-headless-form.md) terug te geven.
* Om de componenten van het Reageren van de douane aan vormgebieden te bouwen en in kaart te brengen, zie [ de douanecomponenten van het Gebruik om een koploze vorm ](developing-for-headless-forms-using-your-own-components.md) terug te geven.

Voor concepten zoals wanneer om hoofdloze vormen, staatsbeheer, en bevestiging te gebruiken, zie [ Begrip hoofdloze vormen ](understanding-headless-forms.md).

## Hoe kan ik AEM Forms implementeren en aanpassen met aangepaste CSS, thema&#39;s, regeleditors en headless formulieren?

**Koploze vormen:** Stijlvol en blik-en-voelen zijn volledig onder uw controle. U gebruikt uw eigen React (of andere) componenten en uw eigen CSS; er zijn geen ingebouwde thema&#39;s. Zie [ Gebruik een douane reactiebibliotheek om een koploze vorm ](use-google-material-ui-react-components-to-render-a-headless-form.md) terug te geven en [ douanecomponenten van het Gebruik om een koploze vorm ](developing-for-headless-forms-using-your-own-components.md) terug te geven om uit te voeren en stijlen koploze vormen.

**Klassieke AEM Forms (thema&#39;s, regelredacteur, visuele redacteur):** CSS van de Douane, de themaredacteur, en de regelredacteur zijn op de klassieke (niet-hoofdloze) Aangepaste het auteurservaring van Forms van toepassing. Voor die onderwerpen, zie de [ documentatie van AEM Forms ](https://experienceleague.adobe.com/docs/experience-manager-forms.html) op Experience League.

## Kan een Headless adaptive-formulier verbinding maken met een CRM voor het lezen of schrijven van gegevens?

Met Microsoft Dynamics en Salesforce kunt u een adaptief formulier zonder koptekst verzenden of vooraf invullen. Naast CRM&#39;s bieden Zwaardeloze adaptieve formulieren ondersteuning voor het verzenden of vooraf invullen van REST-eindpunten, e-mail en aangepaste verzendacties.
