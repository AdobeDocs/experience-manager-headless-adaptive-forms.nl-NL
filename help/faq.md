---
title: Veelgestelde vragen
description: Veelgestelde vragen
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloos, adaptief formulier, veelgestelde vragen
hide: false
exl-id: 5bfc307d-96a3-4007-b65f-32176ecdb710
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---

# Veelgestelde vragen (FAQ) {#headless-adaptive-forms-faq}

## Moet ik React.js kennen om Zwaardeloze adaptieve vormen te gebruiken?

U kunt elk framework, elke bibliotheek of elke taal gebruiken om Zzonder koppen adaptieve formulieren te genereren en onze REST API&#39;s gebruiken om de formulieren te valideren en te verzenden. AF-core bibliotheek, geleverd OOTB, is framework-onafhankelijk. React-Render en React-componet bibliotheken, die OTB worden verstrekt, zijn voor uw gemak. U kunt uw eigen componenten ontwikkelen en u kunt deze niet alleen gebruiken.

<!-- 
## Did Adobe release a new AEM Archetype for Headless adaptive forms?

You can use Archetype 37 with flag `includeFormsheadless` or later flag to create an AEM project with Headless adaptive forms functionality. 

-->

## Heb ik Forms as a Cloud Service sandbox nodig om adaptieve formulieren zonder koptekst te kunnen gebruiken?

Met de startapp kunt u beginnen met het ontwikkelen en opmaken van adaptieve formulieren zonder koptekst. U hebt Forms as a Cloud Service nodig om adaptieve formulieren zonder koptekst te hosten en te bedienen, samen met mogelijkheden voor back-end formulieren.

<!-- ## Do I need an archetype project to develop Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. Later on, you can use the 
archetype project to deploy the finished Headless adaptive forms and corresponding custom code, created using starter app, to Forms as a Cloud Service environment. The Forms as a Cloud Service environment helps you test and productionize the forms. -->

## Waar kan ik een voorbeeld van een Zwaardeloze adaptieve vorm krijgen? {#storybook-example}

U kunt de starttoepassing gebruiken om een aangepast, hoofdloos adaptief formulier te genereren en voor te vertonen. U kunt ook een [storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--introduction) Een voorbeeld bekijken van een adaptief formulier zonder koptekst.

![](/help/assets/storybook-example.png)

## Is het mogelijk om Zwaardeloze adaptieve vormen met douanekaders te gebruiken?

Hoofdloze adaptieve formulieren zijn gebaseerd op [standaardspecificatie](/help/assets/Headless-Adaptive-Form-Specification.pdf). U kunt de specificatie uitbreiden om het te gebruiken om douanecomponenten te bouwen. Bijvoorbeeld, componenten voor Chakra UI, Vue.js, en meer.

## Worden trapsgewijze velden ondersteund door hulpformulieren zonder koptekst?

In trapsgewijze velden hangt de inhoud van het tweede veld af van de inhoud die in het eerste veld is gekozen. De [Winkelboek](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behavior—options&amp;args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJS son.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) Hier ziet u een voorbeeld van trapsgewijze velden.

## Kunnen formulieren zonder koptekst en aanpassingen vooraf worden ingevuld met gepersonaliseerde gegevens?

Met adaptieve formulieren zonder koppen kunnen formulieren vooraf worden ingevuld met gepersonaliseerde gegevens. De [Winkelboek](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--prefill-form-with-personalised-data) Hier ziet u een voorbeeld van het vooraf invullen van een adaptief formulier zonder koptekst.

<!-- >
## Can I use existing Adaptive Forms editor to create a Headless adaptive form?

At this moment, you use the Adaptive Form Editor to specify the JSON structure and set submit action for the forms. Support for drag-and-drop components, applying rules using editor, and more editor-related options would be available later in the beta phase. Keep a watch on release notes.  -->

## Kan ik hulpvormen zonder hoofd gebruiken met Angular SPA?

U kunt de SDK van het Web gebruiken om Zwaardeloze adaptieve vormen met de SPA van de Angular te integreren. Het staat los van elk kader. U kunt React SDK als verwijzing gebruiken.

<!-- ## Should the `-r prerelease` switch be used every time to start the AEM SDK instance or only for the first time?

During the limited release program, use the `-r prerelease` switch every time you start the AEM SDK instance. 

## What is AEM Forms add-on (.far file) and how to install it?

Adobe Experience Manager Forms as a Cloud Service feature archive provides tools to create Headless adaptive forms on the local development environment. To install the feature archive, see [Setup development environment](setup-development-environment.md).

<!-- 
## Where do one get the license.properties file from?

You do not require a license.properties file to run AEM Cloud Service SDK. 

-->

## Is er een insteekmodule om de ontwikkeling voor Headless AF te vereenvoudigen?

Ja, is een uitbreiding beschikbaar voor de Code van Microsoft Visual Studio. Hiermee kunt u op een handige manier handmatig de JSON-formulieren zonder koptekst maken.

## Kan een Headless adaptive-formulier verbinding maken met een CRM voor het lezen of schrijven van gegevens?

Met Microsoft Dynamics en Salesforce kunt u een adaptief formulier zonder koptekst verzenden of vooraf invullen. Naast CRM&#39;s bieden Zwaardeloze adaptieve formulieren ondersteuning voor het verzenden of vooraf invullen van REST-eindpunten, e-mail en aangepaste verzendacties.
