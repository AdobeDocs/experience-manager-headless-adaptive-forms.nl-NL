---
title: Een headless Form maken en Publish met Adobe Experience Manager Adaptive Forms | Step-by-Step Guide
description: In deze stapsgewijze handleiding leert u hoe u een headless-formulier maakt en publiceert met behulp van adaptieve Adobe Experience Manager-formulieren. Ontdek de voordelen van het zonder kop gaan en stroomlijnt vandaag het proces voor het maken van formulieren. Begin dynamische, responsieve formulieren te maken die naadloos werken op verschillende apparaten met Adobe Experience Manager Headless Adaptive Forms.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: cd7c7972-376c-489f-a684-f479d92c37e7
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---



# Een headless-formulier maken en voorvertonen met een React-app {#introduction}

Met de startkit kunt u snel aan de slag met een React-app. U hebt de vrijheid om Zwaardeloze adaptieve vormen in een Angular, Vanilla JS, en andere ontwikkelomgevingen van uw keus te ontwikkelen en te gebruiken.

Begin met de adaptieve vorm zonder koptekst. Dit is heel eenvoudig en snel. Kloon het kant-en-klare React project, installeer de gebiedsdelen, en stel het project in werking. U hebt een Headless adaptive-formulier dat in een React-app is geïntegreerd. U kunt het voorbeeldreactieproject gebruiken om adaptieve formulieren zonder koppen te maken en te testen voordat u het in een productieomgeving implementeert.

Laten we beginnen:

>[!NOTE]
>
>
> Deze gids Aan de slag gebruikt een React-app. Het staat u vrij om technologie of programmeertaal van uw keuze te gebruiken om adaptieve formulieren zonder koptekst te gebruiken.

## Voordat u begint {#pre-requisites}

Als u een React-app wilt maken en uitvoeren, moet het volgende op uw computer zijn geïnstalleerd:

* Installeer de [ recentste versie van Git ](https://git-scm.com/downloads). Als u aan Git nieuw bent, zie [ Installerend Git ](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Installeer [ Node.js 16.13.0 of later ](https://nodejs.org/en/download/). Als u aan Node.js nieuw bent, zie [ hoe te Node.js ](https://nodejs.dev/en/learn/how-to-install-nodejs) installeren.

## Aan de slag

Wanneer u aan de vereisten voldoet, voert u de volgende stappen uit om aan de slag te gaan:

1. [Startkit voor hulpformulieren zonder koptekst instellen](#setup)

1. [Geef een voorvertoning weer van het adaptieve formulier zonder koptekst dat in de startkit is opgenomen](#preview)

1. [Maak en maak uw eigen, hoofdloze adaptieve formulier](#custom)



## 1. Startkit voor het instellen van hulpformulieren zonder koptelefoon {#install}

De startkit is een React-app met een voorbeeld van een hoofdloos adaptief formulier en de bijbehorende bibliotheken. Gebruik de kit om uw Headless adaptieve formulieren en bijbehorende React-componenten te ontwikkelen en te testen. Voer de volgende opdrachten uit om Hoofdloze adaptieve formulieren in te stellen, startkit:

1. Opdrachtprompt openen en de volgende opdracht uitvoeren:

   ```shell
   git clone https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   Het bevel leidt tot een folder genoemd **reactie-starter-kit-a-headless-vormen** in uw huidige plaats en klonen de Zwaardeloze adaptieve vormen Reageren starter app in het. Naast de configuraties en de lijst met afhankelijkheden die zijn vereist om het formulier te genereren, bevat de map de volgende belangrijke inhoud:

   * **Vorm van de Steekproef**: De starteruitrusting omvat een vorm van de de toepassingstoepassing van de steekproeflening. Open het bestand `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` als u het formulier (formulierdefinitie) dat bij de app is opgenomen, wilt weergeven.
   * **de reactiecomponenten van de Steekproef**: De starteruitrusting omvat steekproefreactiecomponenten voor RTF- en Slider. Deze gids helpt u uw eigen douanecomponenten tot stand brengen gebruikend deze Rijke tekst en componenten van de Schuifregelaar.
   * **Mappings.ts**: Het mappings.ts- dossier helpt u douanecomponenten met vormgebieden in kaart brengen. Wijs bijvoorbeeld een numeriek staperveld toe met de classificatiecomponent.
   * **configuraties van het Milieu**: De configuraties van het milieu laten u verkiezen om een vorm terug te geven inbegrepen in de starterkit of een vorm van een Server van AEM Forms te halen.

   ![](/help/assets/getting-started-starter-kit-content.png)

   >[!NOTE]
   >
   > 
   > De voorbeelden in documenten zijn gebaseerd op VSCode. U kunt geen code-editor voor normale tekst gebruiken.


1. Navigeer aan de **reactie-starter-kit-a-headless-vormen** folder en stel het volgende bevel in werking om de gebiedsdelen te installeren:

   ```shell
   npm install
   ```

   Met deze opdracht downloadt u alle benodigde pakketten en bibliotheken die nodig zijn om de app uit te voeren en samen te stellen, zoals hulpformulieren zonder koptekst
in bibliotheken (@aemforms/af-response-renderer, @aemforms/af-response-components, @adobe/response-spectrum) worden validaties uitgevoerd en blijven gegevens voor exemplaren van het formulier behouden.

   ![](/help/assets/install-react-app-starter-kit.png)


## 2. Voorbeeld van het adaptieve formulier zonder koptekst {#preview}

Nadat u de startkit hebt ingesteld, kunt u een voorbeeld bekijken van het hulpformulier Koploos, en dit vervangen door uw eigen aangepaste formulier. U kunt ook de startkit configureren om een formulier op te halen van een AEM Forms-server. Een voorbeeld van het formulier bekijken

1. Wijzig de naam van het bestand `env_template` in `.env` . Zorg er ook voor dat de optie USE_LOCAL_JSON is ingesteld op true.

   ![](/help/assets/rename-env-file.png)

   <!-- The options in the .env file help you configure source of the forms definantion (.JSON):
    *  To source forms definantion (.JSON) from an AEM Server, set USE_LOCAL_JSON option to false, use the AEM_URL option to specify URL  of your AEM Server, and set the AEM_FORM_PATH option to path of your adaptive form.
    *  To source forms definantion (.JSON) form-model.json file included in the starter-kit, set USE_LOCAL_JSON option to false. -->

1. Gebruik de volgende opdracht om de app uit te voeren:

   ```shell
     npm start
   ```


   Met deze opdracht start u een lokale ontwikkelingsserver en opent u het standaardformulier Headless adaptive dat in de startapp is opgenomen in uw standaardwebbrowser.

   ![ Vorm zonder hoofd van de steekproef ](assets/sample-headless-adaptive-form.png)

   Voilà! U bent allen klaar om een aangepaste, hoofdloze versie te ontwikkelen.

   <!--  As you know, in a headless form the form data and logic are separate from the presentation layer and can be used by any client that can make HTTP requests, such as a mobile app, a static site, or a different web application. The form is often managed and stored on a server, which serves as the backend for the form. The client sends requests to the server to retrieve the form, submit data, and receive updated form data. This allows for greater flexibility and integration with different technologies. You can store and retrive a Headless adaptive form on an AEM Server  -->

## 3. Maak en geef uw eigen, blokloze adaptieve vorm{#custom}

Een Headless adaptief formulier vertegenwoordigt het formulier en de componenten ervan, zoals velden en knoppen, in JSON-indeling (JavaScript Object Notation). Het voordeel van JSON-indeling is dat deze eenvoudig kan worden geparseerd en gebruikt door verschillende programmeertalen, waardoor het een handige manier is om formuliergegevens uit te wisselen tussen systemen. Open het `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` -bestand als u het voorbeeldformulier wilt bekijken dat zich zonder koptekst bij de app bevindt.

Maak een contactformulier met vier velden: &quot;Naam&quot;, &quot;E-mail&quot;, &quot;Contactnummer&quot; en &quot;Bericht&quot;. De velden worden gedefinieerd als objecten (items) in de JSON, waarbij elk object (item) eigenschappen heeft zoals type, label, naam en vereiste waarden. Het formulier heeft ook een knop van het type &quot;submit&quot;. Hier is JSON voor het formulier.


```JSON
{
  "afModelDefinition": {
    "adaptiveform": "0.10.0",
    "items": [
      {
        "fieldType": "text-input",
        "label": {
          "value": "Name"
        },
        "name": "name"
      },
      {
        "fieldType": "text-input",
        "format": "email",
        "label": {
          "value": "Email"
        },
        "name": "email"
      },
      {
        "fieldType": "text-input",
        "format": "phone",
        "pattern": "[0-9]{10}",
        "label": {
          "value": "Contact Number"
        },
        "name": "Phone"
      },
      {
        "fieldType": "multiline-input",
        "label": {
          "value":"Message"
        },
        "name": "message"
      },
      {
        "fieldType": "button",
        "label":{
          "value": "Submit"
        },
        "name":"submit",
        "events":{
          "click": "submitForm()"
        }
      }
    ],
    "action": "https://eozrmb1rwsmofct.m.pipedream.net",
    "description": "Contact Us",
    "title": "Contact Us",
    "metadata": {
      "grammar": "json-formula-1.0.0",
      "version": "1.0.0"
    }
  }
}
```

>[!NOTE]
>
> * Het kenmerk &quot;afModelDefinition&quot; is alleen nodig voor React-toepassingen en maakt geen deel uit van de formulierdefinitie.
> * U kunt de vormJSON manueel-ambachtelijk of de [ AEM adaptieve vormenredacteur (de adaptieve redacteur van WYSIWYG) gebruiken ](create-a-headless-adaptive-form.md) om vormJSON tot stand te brengen en te leveren. In een productieomgeving gebruikt u AEM Forms om het formulier JSON later meer te leveren.
> * De zelfstudie gebruikt de map https://pipedream.com/ om formulierverzendingen te testen. U gebruikt uw eigen eindpunten of eindpunten van derden die door uw organisatie zijn goedgekeurd om de gegevens van een Zwaartepunt - adaptief Vorm te ontvangen.


Als u het formulier wilt weergeven, vervangt u het als voorbeeld aanpasbare formulier JSON zonder koptekst `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` door de bovenstaande JSON, slaat u het bestand op, wacht u tot de startkit het formulier heeft gecompileerd en vernieuwt u het.

![ vervang de steekproefZwaardeloze adaptieve vorm JSON `/react-starter-kit-aem-headless-forms/form-definations/form-model.json` met de aangepaste Zwaarteloze adaptieve vorm JSON ](assets/render-custom-headless-adaptive-form.png)

<!-- Your form is ready. Let's add some validations and make "Name", "Email", and "Message" fields mandatory. -->

U hebt met succes het Zwaarloze Aangepaste Vorm teruggegeven.


## Bonus

Stel de titel van de webpagina waarop het formulier zich bevindt in op `Contact Us | WKND Adventures and Travel` . Om de titel te veranderen, open het _react-starter-kit-aem-headless-forms/public/index.html_ dossier voor het uitgeven en plaats de titel.

![](assets/contact-us-headless-adaptive-forms-updated-title.png)


## Volgende stap

Door gebrek, gebruikt de aanzetuitrusting ](https://spectrum.adobe.com/) componenten van het Spectrum van de Adobe [ om de vorm terug te geven. U kunt uw eigen componenten of componenten van derden maken en gebruiken. Bijvoorbeeld met Google Material UI of Chakra UI.

Laten wij [ materiaal UI van Google ](use-google-material-ui-react-components-to-render-a-headless-form.md) gebruiken om onze vorm van het Contact van ons terug te geven.




