---
title: Architectuur van niet-adaptieve formulieren
description: Leer meer over de architectuur van de AEM Forms Headless adaptieve Forms en hoe u hiermee snel formulieren kunt maken voor verschillende platforms. Dit artikel biedt inzicht in hoe Headless adaptive Forms werkt en hoe deze kan worden geïntegreerd met verschillende toepassingen om het proces voor het maken van formulieren te vereenvoudigen.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloze, adaptieve vorm, architectuur
hide: false
exl-id: ee7096d8-89e2-41e0-85e7-b26457df96fb
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 0%

---


# Hoe werkt het adaptieve formulier zonder hoofd?

Een Headless adaptief formulier is in wezen een JSON-structuur (schema) bestaande uit formuliervelden (Tekstvak, keuzen en nog veel meer velden) en de bijbehorende regels (voorwaardelijke logica) om interactief gedrag aan het formulier toe te voegen. U kunt REST API&#39;s in uw toepassing of website gebruiken om de gehoste JSON-structuur aan te vragen en de JSON-structuur zelf als een formulier in uw app of website weer te geven. Eén hoofdloos adaptief formulier kan meerdere webpagina&#39;s en toepassingen gebruiken zonder dat er toepassingsspecifieke of websitespecifieke wijzigingen in worden aangebracht.

![&#x200B; hoe de Hoofdloze adaptieve vorm &#x200B;](/help/assets/how-headless-adaprive-forms-work.png) werkt

## Architectuur {#architecture}

Een typische Headless adaptive-vormarchitectuur centreert zich op een Adobe Experience Manager Forms-server die als host fungeert voor adaptieve, hoofdloze formulieren. Voor-end apps—web, mobiel, JavaScript, chatbots en meer—genereren de formulieren voor elk kanaal.

De typische architectuur van een Zwaardeloze adaptieve vormenplaatsing kijkt als het volgende:

![Architectuur](/help/assets/headless-af-architecture.png)

<!-- 

You can use the React renderer component shipped with Headless adaptive forms to render an Adaptive Form or build your own custom component to natively render a Headless Form in a website or an application or use any UI framework or programming language to build your own components to render your forms.

A typical Headless adaptive forms architecture constitutes an Adobe Experience Manager Server, JSON structure of forms, various frontend apps for channel-specific form renditions.

![Architecture](/help/assets/headless-af-architecture.png) -->

### Component van een Headless adaptive form-implementatie

**de Server van Adobe Experience Manager**: Samen met het dienen als gastheer voor Zwaardeloze adaptieve vormen, verstrekt Adobe Experience Manager de volgende achterste eindmogelijkheden:

* RESTful-API&#39;s voor het weergeven, ophalen, vooraf invullen, valideren, verzenden en volgen van de verzendstatus van formulieren zonder kop.
* Visuele redacteur om een Headless adaptieve vorm gemakkelijk te ontwikkelen.
* Forms-gegevensmodel voor het ontvangen of verzenden van gegevens naar verschillende gegevensbronnen.
* Een workflow-engine voor het automatiseren van complexe taken.

**Koploze adaptieve vormen**: Een Headless adaptieve vorm wordt vertegenwoordigd als .json dossier. De JSON-structuur definieert componenten, beperkingen en structuur van een formulier.

**Voorste-end Apps**: Voorste-end apps zoals, KUUROORD (de Toepassingen van de Enige Pagina), Mobiele Apps, de Apps van JavaScript, gebruiken Zwaardeloze adaptieve vormen (de Vertegenwoordiging van de Vorm JSON) en geven de vorm op een cliënt terug. U kunt de React-rendercomponent die wordt geleverd met Headless adaptive-formulieren, gebruiken om een adaptief formulier te genereren of uw eigen aangepaste component te maken om Headless adaptieve formulieren native te genereren.

<!-- ### Understanding Headless adaptive forms definition -->



### Gereedschappen voor ontwikkelaars

In een doorsnee ontwikkelingscyclus begint u met het maken en hosten van adaptieve hoofdformulieren op Adobe Experience Manager Forms Server. In de tweede stap wijst u uw UI-componenten toe of gebruikt u een openbare UI-componentenbibliotheek, zoals Google Material UI of Chakra UI om uw formulieren op te maken. In de laatste stap worden adaptieve formulieren zonder koptekst opgehaald en weergegeven in uw toepassing (website, mobiele toepassing, JavaScript-apps, chattoepassingen of vele andere oppervlakken).

Met de volgende gereedschappen kunt u adaptieve formulieren zonder koptekst maken en integreren in uw toepassingen:

**Forms Web SDK (Cliënt-Kant Runtime)**: SDK van het Web van Forms is een cliënt-kant JavaScript bibliotheek. Hiermee kunt u clientvalidaties toepassen op formuliervelden, de status van het formulier behouden en kunt u koppelingen maken naar formulieren met een UI-laag of een component die adaptieve formulieren weergeeft. Klanten kunnen hiermee beperkingen valideren die zijn toegepast op verschillende velden van een formulier en haken om de JSON-structuur van het formulier aan te sluiten op het UI-framework. Forms Web SDK heeft de volgende componenten:

* **Bedrijfs regelverwerker**: De bewerker van de bedrijfsregel keurt de vormJSON structuur als input goed, beheert de staat van de vormgebieden, voert regels uit, en gebeurtenismanagers huidig in JSON.
* **Reageer binder**: Verzekert haken over controlemechanisme om staat aan de Componenten van de Vorm toe te voegen. Het is ook handig om een formulier vooraf in te vullen.
* **de bibliotheek van Componenten**: Het verstrekt de Componenten van het Spectrum Reageren en gebruikt haken in de React module van de Bindder om staat aan die componenten toe te voegen.

Naast het verschaffen van de API&#39;s voor het valideren van beperkingen die zijn toegepast op verschillende velden van een formulier, biedt Forms Web SDK haken om Zwaardeloze adaptieve formulieren aan te sluiten op het UI-framework. Het biedt ook een React-renderer voor Headless adaptieve formulieren waarmee een Headless adaptief formulier kan worden geïntegreerd in uw toepassing. De volgende componenten van het Web SDK zijn beschikbaar:

* **[@aemforms/af-response-components &#x200B;](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer &#x200B;](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core &#x200B;](https://www.npmjs.com/package/@aemforms/af-core)**

Al deze componenten zijn inbegrepen in Archetype van AEM. Wanneer u een AEM Archetype 37 of hoger project voor Zwaardeloze adaptieve formulieren maakt, wordt de nieuwste versie van de hierboven vermelde bibliotheken opgenomen in het project.

* **playground van de Code**: [&#x200B; playground van de Code &#x200B;](https://experienceleague.adobe.com/landing/aem-headless-forms/developer/code.html?lang=nl-NL) is een interactief milieu dat voor ontwikkelaars wordt ontworpen om met te experimenteren, over te leren, en de mogelijkheden van Hoofdloze adaptieve Forms te testen.

**Begonnen Toepassing**: Adobe heeft ook een begonnen toepassing vrijgegeven om u te helpen snel met Hoofdloze adaptieve vormen beginnen.

<!-- **View Library (UI Layer)**: A custom form application built in a front-end language. You can use react, Angular, Flutter, NPM, Vue.js, Ionic, BootStrap, or any other language to built front end. You can also use the Headless adaptive forms Super Component, provided out-of-the-box, inside a react application to render a Headless adaptive form. Headless adaptive forms super component makes use of OOTB react spectrum -based form components to render the Headless adaptive form. 

Core-Components: It enables use to render an Adaptive Form using JSON structure. It uses rule grammar to help create dynamic field interactions. The rule grammar is based on [JSON formula](http://github.com/adobe/json-formula/). You can develop your own renderer or embed the React based Adaptive Forms renderer, provided OOTB, in your front-end app to render the form. -->

**Storybook**: [&#x200B; Storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) verstrekt een overzicht van verschillende componenten van de adaptieve vormen zonder Titel. Het verstrekt ook een lijst van alle gesteunde componenten, hun overeenkomstige eigenschappen, en beperkingen.

**de Uitbreiding van de Code van Visual Studio**: [&#x200B; de uitbreiding van de Code van Visual Studio &#x200B;](visual-studio-code-extension-for-headless-adaptive-forms.md) helpen een geldige structuur tot stand brengen JSON. Het biedt ondersteuning voor IntelliSense en validatie voor JSON-structuur van formulieren en algemene functies zoals het toevoegen, verwijderen of hernoemen van componenten van een JSON-structuur.

**HTTP en JavaScript APIs**: [&#x200B; HTTP APIs &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/api/) laat u een lijst maken, vinden, bevestigen, voorleggen en volgen voorleggingsstatus van hoofdloze vormen. <!-- URL is 404!! [JS APIs](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) helps you use Headless adaptive forms with any JavaScript based UI framework. -->

**JSON Formule**: Het is een implementatie van de grammatica van de vormenuitdrukking om u te helpen JSON structuur vragen en regels voor Zwaardeloze adaptieve vormen tot stand brengen. De grammatica is een masker van spreadsheet-als functies en exploitanten en [&#x200B; JMESPath &#x200B;](https://jmespath.org/) een JSON vraagtaal. U kunt [&#x200B; playground &#x200B;](https://opensource.adobe.com/json-formula/dist/index.html) gebruiken om JSON-formulesyntaxis en mogelijkheden te onderzoeken.

**Aangepaste Forms versie 2.0 specificaties**: De adaptieve versie 2.0 van Forms specificatie verstrekt gedetailleerde informatie over alle componenten, beperkingen, en methodes beschikbaar om Zwaartepunt te bepalen aanpassende vormen. De specificatie is beschikbaar in [&#x200B; PDF &#x200B;](/help/assets/headless-adaptive-forms-specification.pdf) formaat.

