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
source-git-commit: 48ba054d7ef3b4e27e0b4d6026dfc2475917723e
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 0%

---


# Hoe werkt het adaptieve formulier zonder hoofd?

Een Headless adaptief formulier is in feite een JSON-structuur (schema) bestaande uit formuliervelden (Tekstvak, keuzen en nog veel meer velden) en de bijbehorende regels (voorwaardelijke logica) om interactief gedrag aan het formulier toe te voegen. U kunt REST API&#39;s in uw toepassing of website gebruiken om de gehoste JSON-structuur aan te vragen en de JSON-structuur zelf als een formulier in uw app of website weer te geven. Eén hoofdloos adaptief formulier kan meerdere webpagina&#39;s en toepassingen gebruiken zonder dat er toepassingsspecifieke of websitespecifieke wijzigingen in worden aangebracht.

![Hoe het Zwaardeloze adaptieve formulier werkt](/help/assets/how-headless-adaprive-forms-work.png)

## Architectuur {#architecture}

Een standaardarchitectuur voor adaptieve formulieren zonder koptekst vormt een Adobe Experience Manager Forms Server, hulpformulieren zonder koptekst die worden gehost op Adobe Experience Manager Forms Server en uw frontend-apps (website, mobiele toepassing, JavaScript-toepassingen, chattoepassingen en meer) voor kanaalspecifieke formulieruitvoeringen.

De typische architectuur van een Zwaardeloze adaptieve vormenplaatsing kijkt als het volgende:

![Architectuur](/help/assets/headless-af-architecture.png)

<!-- 

You can use the React renderer component shipped with Headless adaptive forms to render an Adaptive Form or build your own custom component to natively render a Headless Form in a website or an application or use any UI framework or programming language to build your own components to render your forms.

A typical Headless adaptive forms architecture constitutes an Adobe Experience Manager Server, JSON structure of forms, various frontend apps for channel-specific form renditions.

![Architecture](/help/assets/headless-af-architecture.png) -->

### Component van een Headless adaptive form-implementatie

**Adobe Experience Manager Server**: Adobe Experience Manager biedt niet alleen de host voor adaptieve Headless-formulieren, maar ook de volgende back-endmogelijkheden:

* RESTful-API&#39;s voor het weergeven, ophalen, vooraf invullen, valideren, verzenden, volgen van de verzendstatus van formulieren zonder kop.
* Visuele redacteur om een Headless adaptieve vorm gemakkelijk te ontwikkelen.
* Forms-gegevensmodel voor het ontvangen of verzenden van gegevens naar verschillende gegevensbronnen.
* Workflowengine om complexe taken te automatiseren.

**Hoofdloze adaptieve formulieren**: Een hoofdloos adaptief formulier wordt weergegeven als een .json-bestand. De JSON-structuur definieert componenten, beperkingen en structuur van een formulier.

**front-end apps**: Voor-end toepassingen zoals, SPA (Single Page Applications), Mobile Apps, JavaScript Apps, verbruiken koploze adaptieve formulieren (de JSON-formulierweergave) en genereren het formulier op een client. U kunt de React-rendercomponent die wordt geleverd met Headless adaptive-formulieren, gebruiken om een adaptief formulier te genereren of uw eigen aangepaste component te maken om dynamisch adaptieve formulieren zonder koptekst te genereren.

<!-- ### Understanding Headless adaptive forms definition -->



### Gereedschappen voor ontwikkelaars

In een doorsnee ontwikkelingscyclus begint u met het maken en hosten van adaptieve hoofdformulieren op Adobe Experience Manager Forms Server. In de tweede stap wijst u uw UI-componenten toe of gebruikt u een openbare UI-componentenbibliotheek, zoals Google Material UI of Chakra UI om uw formulieren op te maken. In de laatste stap worden adaptieve formulieren zonder koptekst opgehaald en weergegeven in uw toepassing (website, mobiele toepassing, JavaScript-toepassingen, chattoepassingen of veel andere oppervlakken).

Met de volgende gereedschappen kunt u adaptieve formulieren zonder koptekst maken en integreren in uw toepassingen:

**Forms Web SDK (clientruntime)**: Forms Web SDK is een JavaScript-bibliotheek aan de clientzijde. Hiermee kunt u clientvalidaties toepassen op formuliervelden, de status van het formulier behouden en kunt u koppelingen maken naar formulieren met een UI-laag of een component die adaptieve formulieren weergeeft. Klanten kunnen hiermee beperkingen valideren die zijn toegepast op verschillende velden van een formulier en haken om de JSON-formulierstructuur aan te sluiten op het UI-framework. De Forms Web SDK heeft de volgende componenten:

* **Zakelijke regelprocessor**: De verwerker voor bedrijfsregels accepteert de JSON-formulierstructuur als invoer, beheert de status van de formuliervelden, voert de regels uit en gebeurtenishandlers in de JSON.
* **React binder**: Biedt koppelingen over controller om status toe te voegen aan formuliercomponenten. Het is ook handig om een formulier vooraf in te vullen.
* **Componentenbibliotheek**: Het verstrekt de Componenten van het Spectrum van het Reageren en gebruikt haken in de module van de Bindder van het Reageren om staat aan die componenten toe te voegen.

De Forms Web SDK beschikt niet alleen over de API&#39;s voor het valideren van beperkingen die zijn toegepast op verschillende velden van een formulier, maar biedt ook haken voor het verbinden van Headless Adaptive-formulieren met het UI-framework. Het biedt ook React Renderer-&#x200B; voor Headless adaptive-formulieren om een Headless adaptive-formulier in uw toepassing te integreren. De volgende componenten van Web SDK zijn beschikbaar:

* **[@aemforms/af-response-components](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core](https://www.npmjs.com/package/@aemforms/af-core)**

Al deze componenten zijn inbegrepen in AEM Archetype. Wanneer u een project met AEM Archetype 37 of hoger maakt voor adaptieve koptekstformulieren, wordt de nieuwste versie van de hierboven vermelde bibliotheken opgenomen in het project.

**Gestart toepassing**: Adobe heeft ook een gestarte toepassing uitgebracht waarmee u snel kunt beginnen met hulpformulieren zonder koptekst.

<!-- **View Library (UI Layer)**: A custom form application built in a front-end language. You can use react, Angular, Flutter, NPM, Vue.js, Ionic, BootStrap, or any other language to built front end. You can also use the Headless adaptive forms Super Component, provided out-of-the-box, inside a react application to render a Headless adaptive form. Headless adaptive forms super component makes use of OOTB react spectrum -based form components to render the Headless adaptive form. 

Core-Components: It enables use to render an Adaptive Form using JSON structure. It uses rule grammar to help create dynamic field interactions. The rule grammar is based on [JSON formula](http://github.com/adobe/json-formula/). You can develop your own renderer or embed the React based Adaptive Forms renderer, provided OOTB, in your front-end app to render the form. -->

**Winkelboek**: [Winkelboek](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) biedt een overzicht van de verschillende componenten van Headless adaptieve formulieren. Het verstrekt ook een lijst van alle gesteunde componenten, hun overeenkomstige eigenschappen, en beperkingen.

**Visual Studio-extensie**: [Visual Studio Code-extensie](visual-studio-code-extension-for-headless-adaptive-forms.md) om een geldige JSON-structuur te helpen maken. Het biedt ondersteuning voor IntelliSense en validatie voor JSON-structuur van formulieren en algemene functies zoals het toevoegen, verwijderen of hernoemen van componenten van een JSON-structuur.

**Aangepaste Forms versie 2.0-specificaties**: De adaptieve Forms versie 2.0-specificatie biedt gedetailleerde informatie over alle componenten, beperkingen en methoden die beschikbaar zijn om adaptieve formulieren zonder koptekst te definiëren. De specificatie is beschikbaar in [PDF](/help/assets/Headless-Adaptive-Form-Specification.pdf) gebruiken.

**HTTP- en JavaScript-API&#39;s**: [HTTP-API&#39;s](https://opensource.adobe.com/aem-forms-af-runtime/api/) Hiermee kunt u de verzendstatus van formulieren zonder kop weergeven, ophalen, valideren, verzenden en volgen. [JS API&#39;s](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) Hiermee kunt u op basis van JavaScript aangepaste formulieren zonder koptekst gebruiken.

**JSON Formula**: Het is een implementatie van de grammatica van formulierexpressies waarmee u JSON-structuur kunt opvragen en regels kunt maken voor hulpformulieren zonder koptekst. De grammatica is een mengelmoes van spreadsheetfuncties en -operatoren en [JMESPath](https://jmespath.org/) een JSON-querytaal. U kunt de [speelplaats](https://opensource.adobe.com/json-formula/dist/index.html) om de syntaxis en mogelijkheden van JSON-formules te verkennen.