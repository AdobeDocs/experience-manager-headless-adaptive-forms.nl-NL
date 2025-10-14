---
title: AEM Headless Adaptive Forms - Overzicht
description: Overzicht voor adaptieve AEM Headless-formulieren.
hide: true
exl-id: cd7c7972-376c-489f-a684-f479d92c37e7
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 3%

---


# Opmerkingen bij de release

Welkom bij de Experience Manager Headless adaptive-release. Lees verder voor bronnen en instructies om aan de slag te gaan en de release optimaal te maken.

Gebruik adaptieve Adobe Experience Manager-formulieren zonder hoofd om formuliertoepassingen te maken met front-end frameworks, zoals React, Angular en andere. Gebruik de Adaptive Forms Web SDK voor staatsbeheer, bevestiging, en integratie met extra touchpoints.


De vroege adopterversie verleent u toegang om de Zwaarteloze adaptieve vormen in a [&#x200B; lokale ontwikkelomgeving &#x200B;](setup-development-environment.md) te gebruiken. U kunt de lokale ontwikkelomgeving gebruiken om adaptieve formulieren zonder hoofd te maken en te testen.

Hoofdloze adaptieve formulieren worden voortdurend verbeterd. Bezoek deze pagina regelmatig om op de hoogte te blijven van de meest recente ontwikkelingen. Deze pagina biedt u informatie over het volgende:

* vroege toegang
* nieuwste releases
* nieuwe functies
* Verbeteringen
* opgeloste problemen
* verouderde functionaliteit
* speciale instructies
* Geplande wijzigingen

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

### AEM Forms as a Cloud Service SDK

AEM Forms as a Cloud Service SDK helpt u bij het maken, opslaan en ophalen van adaptieve formulieren zonder koptekst. Het helpt ook vooraf ingevulde, server-zijregelbevestiging te verstrekken, en de verzenddiensten voor Zwaarloze aanpassende vormen.

### Forms Web SDK

Forms Web SDK biedt de API&#39;s voor het valideren van beperkingen die zijn toegepast op verschillende velden van een formulier en haken voor het verbinden van de JSON-structuur van het formulier met het UI-framework. Het biedt ook React Renderer-&#x200B; voor Headless adaptive-formulieren om een Headless adaptive-formulier in uw toepassing te integreren. De volgende componenten van het Web SDK zijn beschikbaar:

* **[@aemforms/af-response-components &#x200B;](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer &#x200B;](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core &#x200B;](https://www.npmjs.com/package/@aemforms/af-core)**

<!-- npm i --save @aemforms/af-react-components @aemforms/af-react-renderer @aemforms/af-core -->

#### Winkelboek

Het [&#x200B; Storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) verstrekt een overzicht van de verschillende componenten van Zwaartepunt aanpassende vormen. Het verstrekt ook een lijst van alle gesteunde componenten, hun overeenkomstige eigenschappen, en beperkingen.

### Forms Core-component

<!-- Forms components are the structural elements that constitute the content of the form being authored. These components provide various form fields and ability to customize those fields. -->

De Componenten van de kern zijn een reeks gestandaardiseerde componenten van het Beheer van de Inhoud van het Web (WCM) om u te helpen ontwikkelingstijd versnellen en de onderhoudskosten van uw vormen drukken. De Forms Container-component is een kerncomponent. Met deze functie kunt u een JSON-structuur van Headless adaptive-formulier insluiten en weergeven in de Adaptive Forms Editor van Forms as a Cloud Service SDK.

### Adaptieve Forms V2-specificaties

Specificatie voor hulpformulieren zonder koptekst biedt gedetailleerde informatie over alle componenten, beperkingen en methoden die beschikbaar zijn om adaptieve formulieren zonder koptekst te definiëren. De specificatie is beschikbaar in [&#x200B; PDF &#x200B;](/help/assets/Headless-Adaptive-Form-Specification.pdf) formaat.

### HTTP en JS API

[&#x200B; HTTP APIs &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/api/) staat u toe om van een lijst te maken, te halen, te bevestigen, voor te leggen, en de status van de spoorvoorlegging van hoofdloze vormen. <!-- URL is 404! [JS APIs](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) helps you use Headless adaptive forms with any JavaScript based UI framework. -->

### Visual Studio-extensie

[&#x200B; de uitbreiding van de Code van Visual Studio &#x200B;](visual-studio-code-extension-for-headless-adaptive-forms.md) helpen een geldige structuur tot stand brengen JSON. Het biedt ondersteuning voor IntelliSense en validatie voor JSON-structuur van formulieren en algemene functies zoals het toevoegen, verwijderen of hernoemen van componenten van een JSON-structuur.

<!-- ## What's next

The following features would be available in upcoming releases:

* HTTP APIs to invoke a business logic.
* Server-side capabilities (Prefill, server-side validation, generating Document of Record (DoR), Submitting to a Form Data Model or using Form Data Models for creating rules, and more).
* Continuous improvements to specifications and Headless adaptive form runtime.
* Use  Adaptive Forms editor for easier management and authoring Headless adaptive forms.
-->