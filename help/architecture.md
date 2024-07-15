---
title: Architectuur van niet-adaptieve formulieren
description: Leer meer over de architectuur van AEM Forms Headless Adaptive Forms en hoe u hiermee snel formulieren kunt maken voor verschillende platforms. Dit artikel biedt inzicht in hoe Headless Adaptive Forms werkt en hoe deze kan worden geïntegreerd met verschillende toepassingen om het maken van formulieren te vereenvoudigen.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloze, adaptieve vorm, architectuur
hide: false
exl-id: ee7096d8-89e2-41e0-85e7-b26457df96fb
source-git-commit: 56ad9d8fefc4933847061ba6007ad367984bd2e0
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 0%

---


# Hoe werkt het adaptieve formulier zonder hoofd?

Een Headless adaptief formulier is in feite een JSON-structuur (schema) bestaande uit formuliervelden (Tekstvak, keuzen en nog veel meer velden) en de bijbehorende regels (voorwaardelijke logica) om interactief gedrag aan het formulier toe te voegen. U kunt REST API&#39;s in uw toepassing of website gebruiken om de gehoste JSON-structuur aan te vragen en de JSON-structuur zelf als een formulier in uw app of website weer te geven. Eén hoofdloos adaptief formulier kan meerdere webpagina&#39;s en toepassingen gebruiken zonder dat er toepassingsspecifieke of websitespecifieke wijzigingen in worden aangebracht.

![ hoe de Hoofdloze adaptieve vorm ](/help/assets/how-headless-adaprive-forms-work.png) werkt

## Architectuur {#architecture}

Een standaardarchitectuur voor adaptieve formulieren zonder koptekst vormt een Adobe Experience Manager Forms Server, hulpformulieren zonder koptekst die worden gehost op Adobe Experience Manager Forms Server en uw frontend-apps (website, mobiele toepassing, JavaScript-apps, chattoepassingen en meer) voor kanaalspecifieke formulieruitvoeringen.

De typische architectuur van een Zwaardeloze adaptieve vormenplaatsing kijkt als het volgende:

![Architectuur](/help/assets/headless-af-architecture.png)

<!-- 

You can use the React renderer component shipped with Headless adaptive forms to render an Adaptive Form or build your own custom component to natively render a Headless Form in a website or an application or use any UI framework or programming language to build your own components to render your forms.

A typical Headless adaptive forms architecture constitutes an Adobe Experience Manager Server, JSON structure of forms, various frontend apps for channel-specific form renditions.

![Architecture](/help/assets/headless-af-architecture.png) -->

### Component van een Headless adaptive form-implementatie

**de Server van Adobe Experience Manager**: Samen met het dienen als gastheer voor Zwaardeloze adaptieve vormen, verstrekt Adobe Experience Manager de volgende achterste eindmogelijkheden:

* RESTful-API&#39;s voor het weergeven, ophalen, vooraf invullen, valideren, verzenden, volgen van de verzendstatus van formulieren zonder kop.
* Visuele redacteur om een Headless adaptieve vorm gemakkelijk te ontwikkelen.
* Forms-gegevensmodel voor het ontvangen of verzenden van gegevens naar verschillende gegevensbronnen.
* Workflowengine om complexe taken te automatiseren.

**Koploze adaptieve vormen**: Een Headless adaptieve vorm wordt vertegenwoordigd als .json dossier. De JSON-structuur definieert componenten, beperkingen en structuur van een formulier.

**Voorste-end Apps**: Voorste-end apps zoals, SPA (de Toepassingen van de Enige Pagina), Mobiele Apps, de Apps van JavaScript, verbruiken Zwaardeloze adaptieve vormen (de Vertegenwoordiging van de Vorm JSON) en geven de vorm op een cliënt terug. U kunt de React-rendercomponent die wordt geleverd met Headless adaptive-formulieren, gebruiken om een adaptief formulier te genereren of uw eigen aangepaste component te maken om dynamisch adaptieve formulieren zonder koptekst te genereren.

<!-- ### Understanding Headless adaptive forms definition -->



### Gereedschappen voor ontwikkelaars

In een doorsnee ontwikkelingscyclus begint u met het maken en hosten van adaptieve hoofdformulieren op Adobe Experience Manager Forms Server. In de tweede stap wijst u uw UI-componenten toe of gebruikt u een openbare UI-componentenbibliotheek, zoals Google Material UI of Chakra UI om uw formulieren op te maken. In de laatste stap worden adaptieve formulieren zonder koptekst opgehaald en weergegeven in uw toepassing (website, mobiele toepassing, JavaScript-apps, chattoepassingen of vele andere oppervlakken).

Met de volgende gereedschappen kunt u adaptieve formulieren zonder koptekst maken en integreren in uw toepassingen:

**SDK van het Web van Forms (Cliënt-Kant Runtime)**: Het Web SDK van Forms is een cliënt-kant bibliotheek van JavaScript. Hiermee kunt u clientvalidaties toepassen op formuliervelden, de status van het formulier behouden en kunt u koppelingen maken naar formulieren met een UI-laag of een component die adaptieve formulieren weergeeft. Klanten kunnen hiermee beperkingen valideren die zijn toegepast op verschillende velden van een formulier en haken om de JSON-formulierstructuur aan te sluiten op het UI-framework. De Forms Web SDK heeft de volgende componenten:

* **Bedrijfs regelverwerker**: De bewerker van de bedrijfsregel keurt de vormJSON structuur als input goed, beheert de staat van de vormgebieden, voert regels uit, en gebeurtenismanagers huidig in JSON.
* **Reageer binder**: Verzekert haken over controlemechanisme om staat aan de Componenten van de Vorm toe te voegen. Het is ook handig om een formulier vooraf in te vullen.
* **de bibliotheek van Componenten**: Het verstrekt de Componenten van het Spectrum Reageren en gebruikt haken in React de module van de Bindder om staat aan die componenten toe te voegen.

De Forms Web SDK beschikt niet alleen over de API&#39;s voor het valideren van beperkingen die zijn toegepast op verschillende velden van een formulier, maar biedt ook haken voor het verbinden van Headless Adaptive-formulieren met het UI-framework. Het biedt ook React Renderer-&#x200B; voor Headless adaptive-formulieren om een Headless adaptive-formulier in uw toepassing te integreren. De volgende componenten van Web SDK zijn beschikbaar:

* **[@aemforms/af-response-components ](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer ](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core ](https://www.npmjs.com/package/@aemforms/af-core)**

Al deze componenten zijn inbegrepen in AEM Archetype. Wanneer u een project met AEM Archetype 37 of hoger maakt voor adaptieve koptekstformulieren, wordt de nieuwste versie van de hierboven vermelde bibliotheken opgenomen in het project.

**Begonnen Toepassing**: de Adobe heeft ook een begonnen toepassing vrijgegeven om u te helpen snel met Zwaarteloze adaptieve vormen beginnen.

<!-- **View Library (UI Layer)**: A custom form application built in a front-end language. You can use react, Angular, Flutter, NPM, Vue.js, Ionic, BootStrap, or any other language to built front end. You can also use the Headless adaptive forms Super Component, provided out-of-the-box, inside a react application to render a Headless adaptive form. Headless adaptive forms super component makes use of OOTB react spectrum -based form components to render the Headless adaptive form. 

Core-Components: It enables use to render an Adaptive Form using JSON structure. It uses rule grammar to help create dynamic field interactions. The rule grammar is based on [JSON formula](http://github.com/adobe/json-formula/). You can develop your own renderer or embed the React based Adaptive Forms renderer, provided OOTB, in your front-end app to render the form. -->

**Storybook**: [ Storybook ](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) verstrekt een overzicht van verschillende componenten van de adaptieve vormen zonder Titel. Het verstrekt ook een lijst van alle gesteunde componenten, hun overeenkomstige eigenschappen, en beperkingen.

**de Uitbreiding van de Code van Visual Studio**: [ de uitbreiding van de Code van Visual Studio ](visual-studio-code-extension-for-headless-adaptive-forms.md) helpen een geldige structuur tot stand brengen JSON. Het biedt ondersteuning voor IntelliSense en validatie voor JSON-structuur van formulieren en algemene functies zoals het toevoegen, verwijderen of hernoemen van componenten van een JSON-structuur.

**Aangepaste Forms versie 2.0 specificaties**: De adaptieve versie 2.0 van Forms specificatie verstrekt gedetailleerde informatie over alle componenten, beperkingen, en methodes beschikbaar om Zwaartepunt te bepalen aanpassende vormen. De specificatie is beschikbaar in [ PDF ](/help/assets/Headless-Adaptive-Form-Specification.pdf) formaat.

**HTTP en JavaScript APIs**: [ HTTP APIs ](https://opensource.adobe.com/aem-forms-af-runtime/api/) staat u toe om van hoofdvormen een lijst te maken, te halen, te bevestigen, voor te leggen, de status van de spoorvoorlegging te volgen. [ JS APIs ](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) helpt u Zwaarloze aanpassingsvormen met om het even welk op JavaScript gebaseerd kader UI gebruiken.

**JSON Formule**: Het is een implementatie van de grammatica van de vormenuitdrukking om u te helpen JSON structuur vragen en regels voor Zwaardeloze adaptieve vormen tot stand brengen. De grammatica is een masker van spreadsheet-als functies en exploitanten en [ JMESPath ](https://jmespath.org/) een JSON vraagtaal. U kunt [ playground ](https://opensource.adobe.com/json-formula/dist/index.html) gebruiken om JSON-formulesyntaxis en mogelijkheden te onderzoeken.
