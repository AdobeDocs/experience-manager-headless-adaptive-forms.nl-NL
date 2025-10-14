---
title: Veelgestelde vragen over Headless Adaptive Forms
description: Veelgestelde vragen
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloos, adaptief formulier, veelgestelde vragen
hide: false
exl-id: 5bfc307d-96a3-4007-b65f-32176ecdb710
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '431'
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

<!-- ## Do I need an archetype project to develop Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. Later on, you can use the 
archetype project to deploy the finished Headless adaptive forms and corresponding custom code, created using starter app, to Forms as a Cloud Service environment. The Forms as a Cloud Service environment helps you test and productionize the forms. -->

## Waar kan ik een voorvertoning van een Headless adaptive-formulier krijgen? {#storybook-example}

U kunt de starttoepassing gebruiken om een aangepast, hoofdloos adaptief formulier te genereren en voor te vertonen. U kunt a [&#x200B; storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--introduction) voorbeeld ook wijzigen om een Headless adaptieve vorm voor te vertonen.

![](/help/assets/storybook-example.png)

## Is het mogelijk om Zwaardeloze adaptieve vormen met douanekaders te gebruiken?

Hoofdloze adaptieve vormen zijn gebaseerd op [&#x200B; standaardspecificatie &#x200B;](/help/assets/headless-adaptive-forms-specification.pdf). U kunt de specificatie uitbreiden om het te gebruiken om douanecomponenten te bouwen. Bijvoorbeeld, componenten voor Chakra UI, Vue.js, en meer.

## Worden trapsgewijze velden ondersteund door hulpformulieren zonder koptekst?

In trapsgewijze velden hangt de inhoud van het tweede veld af van de inhoud die in het eerste veld is gekozen. Het [&#x200B; Storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behavior—options&args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJS son.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) verstrekt een voorbeeld van het trapsgewijze gebieden.

## Kunnen formulieren zonder koptekst en aanpassingen vooraf worden ingevuld met gepersonaliseerde gegevens?

Met adaptieve formulieren zonder koppen kunnen formulieren vooraf worden ingevuld met gepersonaliseerde gegevens. Het [&#x200B; Storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--prefill-form-with-personalised-data) verstrekt een voorbeeld van hoe te om een Zwaarteloze adaptieve vorm vooraf in te vullen.

<!-- >
## Can I use existing Adaptive Forms editor to create a Headless adaptive form?

At this moment, you use the Adaptive Form Editor to specify the JSON structure and set submit action for the forms. Support for drag-and-drop components, applying rules using editor, and more editor-related options would be available later in the beta phase. Keep a watch on release notes.  -->

## Kan ik Headless adaptieve formulieren gebruiken met Angular SPA?

U kunt de SDK Web gebruiken om Zwaardeloze adaptieve vormen met Angular SPA te integreren. Het staat los van elk kader. U kunt de React SDK als verwijzing gebruiken.

<!-- ## Should the `-r prerelease` switch be used every time to start the AEM SDK instance or only for the first time?

During the limited release program, use the `-r prerelease` switch every time you start the AEM SDK instance. 

## What is AEM Forms add-on (.far file) and how to install it?

Adobe Experience Manager Forms as a Cloud Service feature archive provides tools to create Headless adaptive forms on the local development environment. To install the feature archive, see [Setup development environment](setup-development-environment.md).

<!-- 
## Where do one get the license.properties file from?

You do not require a license.properties file to run AEM Cloud Service SDK. 

-->

## Is er een insteekmodule om de ontwikkeling voor Headless AF te vereenvoudigen?

Ja — een uitbreiding van de Code van Visual Studio laat u manueel auteur koploze adaptieve vormen in JSON.

## Kan een Headless adaptive-formulier verbinding maken met een CRM voor het lezen of schrijven van gegevens?

Met Microsoft Dynamics en Salesforce kunt u een adaptief formulier zonder koptekst verzenden of vooraf invullen. Naast CRM&#39;s bieden Zwaardeloze adaptieve formulieren ondersteuning voor het verzenden of vooraf invullen van REST-eindpunten, e-mail en aangepaste verzendacties.
