---
title: Overzicht van Zwaarloze adaptieve formulieren AEM
description: Overzicht voor AEM hulpformulieren zonder koptekst.
hide: true
exl-id: cd7c7972-376c-489f-a684-f479d92c37e7
source-git-commit: 0127f8ddede38083f0932b0e8d7efdd0dd77c3a6
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 2%

---


# Opmerkingen bij de release

Welkom bij Experience Manager Headless adaptive forms early adopter release. Lees verder voor bronnen en instructies om aan de slag te gaan en de release optimaal te maken.

U kunt adaptieve Adobe Experience Manager Headless-formulieren gebruiken om formuliertoepassingen te maken met behulp van front-end UI-frameworks zoals React, Angular en meer en de Adaptive Forms Web SDK gebruiken voor mogelijkheden zoals staatsbeheer, validatie en integratie met verschillende andere aanraakpunten.

De vroege adopterversie verleent u toegang om de Zwaarteloze adaptieve vormen in a [ lokale ontwikkelomgeving ](setup-development-environment.md) te gebruiken. U kunt de lokale ontwikkelomgeving gebruiken om adaptieve formulieren zonder hoofd te maken en te testen.

Hoofdloze adaptieve formulieren worden voortdurend verbeterd. Bezoek deze pagina regelmatig om op de hoogte te blijven van de meest recente ontwikkelingen. Deze pagina biedt u informatie over vroege toegang, recentste versies, nieuwe eigenschappen, verbeteringen, insectenmoeilijke situaties, vervangen functionaliteit, speciale instructies, en toekomstige plannen voor veranderingen.

<!-- 

## July 2022 (v0.22.1)

### New features

* Introduced the `validateFormData` API. It validates all the components against the rules and constraints an returns the list of errors. The validation takes place on the server.
* Introduced the `FormLoad` event.
* Introduced the `importData` and `exportData`.
* You can now dynamically add or remove items, that expect unqiue values, from a repeatable panel. You can use the `minItems` and `maxitems` constraint to set limit of item.
* You can now use constraint to set maximum file upload size, accepted file types, minimum files, and maximum files to upload.

### Improvements and bug fixes

* The service was executing some event handlers twice. The issue is fixed.
* Fixing Data Generation with different values of dataRef, name and type.

<!-- ### React Renderer component -->

## Artefacten beschikbaar in de release van vroegtijdige adoptie

In de reis om Adobe Experience Manager Headless-adaptieve formulieren naar u te brengen, zijn de volgende artefacten beschikbaar in de release van de eerste adopter:

### AEM FORMS AS A CLOUD SERVICE SDK

AEM Forms as a Cloud Service SDK helpt u bij het maken, opslaan en ophalen van adaptieve formulieren zonder koptekst. Het helpt ook vooraf ingevulde, server-zijregelbevestiging te verstrekken, en de verzenddiensten voor Zwaarloze aanpassende vormen.

### Forms Web SDK

Forms Web SDK biedt de API&#39;s voor het valideren van beperkingen die zijn toegepast op verschillende velden van een formulier en voor het verbinden van JSON-formulierstructuur met het UI-framework. Het biedt ook React Renderer-&#x200B; voor Headless adaptive-formulieren om een Headless adaptive-formulier in uw toepassing te integreren. De volgende componenten van Web SDK zijn beschikbaar:

* **[@aemforms/af-response-components ](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer ](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core ](https://www.npmjs.com/package/@aemforms/af-core)**

<!-- npm i --save @aemforms/af-react-components @aemforms/af-react-renderer @aemforms/af-core -->

#### Winkelboek

[ Storybook ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) verstrekt een overzicht van verschillende componenten van Zwaartepunt aanpassende vormen. Het verstrekt ook een lijst van alle gesteunde componenten, hun overeenkomstige eigenschappen, en beperkingen.

### Forms Core-component

<!-- Forms components are the structural elements that constitute the content of the form being authored. These components provide various form fields and ability to customize those fields. -->

De Componenten van de kern zijn een reeks gestandaardiseerde componenten van het Beheer van de Inhoud van het Web (WCM) om u te helpen ontwikkelingstijd versnellen en onderhoudskosten van uw vormen drukken. De Forms Container-component is een kerncomponent. Hiermee kunt u een JSON-structuur van Headless adaptive-formulier insluiten en weergeven in de Adaptive Forms Editor van Forms as a Cloud Service SDK.

### Adaptieve Forms V2-specificaties

Specificatie voor hulpformulieren zonder koptekst biedt gedetailleerde informatie over alle componenten, beperkingen en methoden die beschikbaar zijn om adaptieve formulieren zonder koptekst te definiëren. De specificatie is beschikbaar in [ PDF ](/help/assets/Headless-Adaptive-Form-Specification.pdf) formaat.

### HTTP en JS API

[ HTTP APIs ](https://opensource.adobe.com/aem-forms-af-runtime/api/) staat u toe om van een lijst te maken, te halen, te bevestigen, voor te leggen, verzendstatus van headless vormen te volgen. [ JS APIs ](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) helpt u Zwaarloze aanpassingsvormen met om het even welk op JavaScript gebaseerd kader UI gebruiken.

### Visual Studio-extensie

[ de uitbreiding van de Code van Visual Studio ](visual-studio-code-extension-for-headless-adaptive-forms.md) helpen een geldige structuur tot stand brengen JSON. Het biedt ondersteuning voor IntelliSense en validatie voor JSON-structuur van formulieren, samen met algemene functies zoals het toevoegen, verwijderen of hernoemen van componenten van een JSON-structuur.

<!-- ## What's next

The following features would be available in upcoming releases:

* HTTP APIs to invoke a business logic.
* Server-side capabilities (Prefill, server-side validation, generating Document of Record (DoR), Submitting to a Form Data Model or using Form Data Models for creating rules, and more).
* Continuous improvements to specifications and Headless adaptive form runtime.
* Use  Adaptive Forms editor for easier management and authoring Headless adaptive forms.
-->