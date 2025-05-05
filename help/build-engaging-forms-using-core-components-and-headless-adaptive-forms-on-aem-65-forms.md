---
title: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-title: Build Engaging Forms Using Core Components and Headless
description: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-description: Build Engaging Forms Using Core Components and Headless
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
topic-tags: develop
hide: true
exl-id: 07a71aac-de38-4839-b8d6-b47c3f575eb3
source-git-commit: 999c3d092d03d7a82363bc94ce79ceb33bf0df7e
workflow-type: tm+mt
source-wordcount: '2130'
ht-degree: 0%

---

# Forms inschakelen met behulp van Core Components en Headless Adaptive Forms op AEM 6.5 Forms {#build-engaging-forms-using-core-components-and-headless}

## Overzicht van Lab {#lab-overview}

In dit hands-on laboratorium, leert u:

Hoe u AEM Forms kunt gebruiken om Adaptive Forms eenvoudig te maken met de nieuwste Core Components, die consistent zijn met AEM Sites, zodat u alominkanaalgegevens kunt vastleggen door de Adaptive Forms als headless-formulieren voor internet, mobiel en chatten te gebruiken. U leert ook beste praktijken rond het stileren, aanpassingen, en front-end ontwikkeling.

## Toetsen {#key-takeaways}

* **Bedrijfs Agility**: Als bedrijfsgebruiker, kan ik de ervaring van de Vorm voor veelvoudige kanalen gemakkelijk ontwerpen.

* **Macht om ontwikkelaar** vooruit te sturen: Als vooruitstrevende ontwikkelaar, kan ik de eindgebruikerservaring controleren gebruikend hoofdloze vormen.

* **Snelheid van de Ontwikkelaar**: Als ontwikkelaar, kan ik gemakkelijk en constant Plaatsen en de componenten van Forms aanpassen.

## Voordat u begint {#pre-requisites}

Om deze handen op laboratorium te gebruiken:

* Installeer de [ recentste versie van Git ](https://git-scm.com/downloads). Als u aan Git nieuw bent, zie [ Installerend Git ](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Installeer [ Node.js 16.13.0 of later ](https://nodejs.org/en/download/). Als u aan Node.js nieuw bent, zie [ hoe te Node.js ](https://nodejs.dev/en/learn/how-to-install-nodejs) installeren.

* [ laat Hoofdloze Adaptieve Forms ](enable-headless-adaptive-forms-and-core-components.md) op uw AEM 6.5 milieu van Forms toe.

* Installeer [ Code van Microsoft Visual Studio ](https://code.visualstudio.com/download) of om het even welke duidelijke tekstredacteur. De voorbeelden in document maken gebruik van de Code van Microsoft Visual Studio.

## Les 1 {#lesson-1}

### Doelstelling {#lesson-1-objectives}

Verken uzelf met AEM 6.5 Forms-omgeving.

### Lessencontext {#lesson-1-context}

In deze les, vertrouwt u zich met AEM 6.5 Forms door het gebruikersinterface te navigeren.

### Uitoefening {#lesson-1-excercise}

1. Open uw browser en ga URL van het auteursmilieu in. Bijvoorbeeld:
   [ https://localhost:4502 ](https://localhost:4502).

1. Nadat u bent aangemeld, navigeert u naar de gebruikersinterface van AEM Forms. Klik **Forms**.

   ![](/help/assets/screenshot2028113829.png){width="50%" align="left"}

1. Klik **Forms &amp; Documenten**. Pop-ups met betrekking tot voorkeuren of gegevens negeren.

   ![](/help/assets/screenshot2028113929.png){width="50%" align="left"}

   Alle beschikbare formulieren worden weergegeven.

   ![](/help/assets/screenshot2028114029.png){width="50%" align="left"}

## Les 2

### Doelstelling

Maak een adaptief formulier met de nieuwste Core Components, configureer het formulier en verzend het.

### Lessencontext

In deze les ontwerpt u als zakelijke gebruiker een adaptief formulier voor meerdere kanalen, zoals web, mobiel en chatten met de Adaptieve Forms-editor met gestandaardiseerde Out-of-the-box Core Components om gegevens vast te leggen.

### Uitoefening

1. Maak een verzendeindpunt voor het formulier:

   1. Open <https://requestbin.com/> in een nieuw browsertabblad.

      ![](/help/assets/screenshot2028114329.png){width="50%" align="left"}

   1. Klik **creeer een openbare bak** en kopieer het eindpunt URL.

      ![](/help/assets/screenshot202023-03-0120at206.10.0020pm.png){width="50%" align="left"}

   Dit specifieke eindpunt dient als voorbeeld voor het voorleggen en het bekijken van gegevens. In daadwerkelijke productie, gebruikt u uw eigen eindpunt of gegevensbronnen om de gevangen gegevens op te slaan.

1. Auteur een adaptief formulier:

   1. In het browser lusje dat in Les 1 wordt gebruikt, navigeer aan het Webinterface van AEM Forms en navigeer aan **Forms** > **Forms en Documenten**.

   1. Klik **creëren** en selecteer AanpassingsVorm.

      ![](/help/assets/creating-adaptive-form-6-5.png){width="50%" align="left"}

   1. Selecteer **Leeg met het malplaatje van de Componenten van de Kern** van het scherm van de malplaatjeselectie zoals hieronder getoond en klik **daarna**.

      ![](/help/assets/creating-adaptive-form-6-5-select-blank-template.png){width="50%" align="left"}

   1. Specificeer `Contact us` als **Titel** van de vorm. Zorg ervoor dat de **Naam** van de vorm `contact-us` is.

      ![](/help/assets/creating-adaptive-form-65-specify-title.png){width="50%" align="left"}

   1. Klik **creëren**. Er wordt een dialoogvenster weergegeven.

   1. Voor de dialoogdoos, geeft de klik **&#x200B;**&#x200B;uit. Het formulier wordt geopend in de Adaptive Form Editor. Pop-ups of dialoogvensters voor voorkeuren of informatie negeren.

   1. Open de browser Components en sleep de component Panel naar het midden van het scherm.

      ![](/help/assets/lab65-add-panel.png){width="50%" align="left"}

   1. Sleep componenten vanuit de browser Components om een formulier te maken, vergelijkbaar met het volgende:

      ![](/help/assets/contact-us-headless-adaptive-form.png){width="50%" align="left"}


   1. Open Browser van de Inhoud, klik de eigenschappen van de Container van de Gids pictogram, en open de **Verzending** tabel. Selecteer **voorleggen aan REST eindpunt** Actie voorleggen, **POST verzoek** optie toelaten, en REST die eindpunt specificeren in les 2 in **URL voor de tekstvakje van het verzoek van de POST** wordt gecreeerd, en klik het **Gedane** pictogram.

      ![](/help/assets/configure-submit-action.png){width="50%" align="left"}

1. Publish en adaptief formulier:

   1. Open AEM UI, navigeer aan **Forms** > **Forms &amp; Documenten**. Selecteer de vorm die in vorige stap wordt gecreeerd en klik **Publish**.

   1. Voor de dialoog van Publish Assets, klik **Publish**. Het succesbericht wordt weergegeven.

## Les 3

### Doelstelling

Werk stijlen bij met behulp van best practices voor ontwikkeling vooraf.

### Lessencontext

In deze les leert u als front-end ontwikkelaar hoe u de opmaak van het eerder gemaakte adaptieve formulier eenvoudig kunt bijwerken.

### Uitoefening

Stel de lokale opslagruimte van het thema in:

1. Open de Herinnering of shell van het Bevel met beheerderrechten:

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. Gebruik in de opdrachtprompt de volgende opdracht om naar de map `c:\git` te navigeren.

   ```Shell
   cd git
   ```

   Als de map niet bestaat, maakt u deze met de opdracht `md git` .

1. Gebruik de volgende opdracht om de themafrontend-code te klonen:

   ```Shell
   git clone -b WKND https://github.com/adobe/aem-forms-theme-canvas
   ```

1. Gebruik het volgende bevel in de vermelde orde om aan **te navigeren aem-vormen-thema-canvas** folder en open Code van Visual Studio.

   ```Shell
   cd aem-forms-theme-canvas
   code .
   ```

   ![](/help/assets/screenshot2028126029.png){width="50%" align="left"}

1. Selecteer **Vertrouwen de auteurs van alle dossiers in de ouderomslag** en klik **ja, ik vertrouw de auteurs**.

   ![](/help/assets/screenshot2028116229.png){width="50%" align="left"}

1. Wijzig de naam van het `env_template` -bestand in .env.  Om het dossier anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen** optie.

   ![](/help/assets/screenshot2028116429.png){width="30%" align="left"}

   </br>

   ![](/help/assets/screenshot2028116529.png){width="50%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand en sla het bestand op:

   * **AEM_URL**: Specificeer URL van a **publiceren** instantie. Bijvoorbeeld: `https://localhost:4502/`

   * **AEM_ADAPTIVE_FORM**: Specificeer de naam van de vorm. Bijvoorbeeld `contact-us` .

   </br>

   ![](/help/assets/lab65-theme-environment-variable.png)


1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028117029.png)

   >[!NOTE]
   >
   > * Als u een bericht vragend om npm via het `npm notice Run npm nstall -g npm@9.6.0` bevel bij te werken krijgt, negeer het bericht.
   > * Stel geen andere npm bevelen in werking tenzij geïnstrueerd in het werkboek.

1. Voer nu de volgende opdracht uit om een voorbeeld van het formulier te bekijken.

   ```Shell
   npm run live
   ```

   ![](/help/assets/screenshot2028117229.png)

   Wacht tot de bovenstaande opdracht is uitgevoerd op het `webpack compiled` -bericht. Het formulier wordt weergegeven op een browsertabblad.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser na het uitvoeren van het `npm run live` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.


   ![](/help/assets/contact-us-headless-adaptive-form-with-canvas-theme.png){width="50%" align="left"}


1. Open het bestand `PROJECT\src\site\_variables.scss` in Visual Studio Code. De `$error` -kleur is een kleur van het type RED.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. In browser, leg de vorm voor om de Rode kleur op het **Voornaam** gebied te zien.

   ![](/help/assets/error-color-before.png)

1. Plaats de **$error** kleur aan **#5736eb** en bewaar het dossier.

1. Vernieuw de browser en verzend het formulier. De kleur van de foutmelding in het veld Voornaam is dienovereenkomstig gewijzigd.

   ![](/help/assets/error-color-after.png)

1. In de Herinnering van het Bevel, druk **CTRL+C**, ga **Y** in, en druk **ga** sleutel in om het npm proces te eindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.
1. Sluit de Code van Visual Studio en de Snelle vensters van het Bevel.

## Les 4

### Doelstelling

Het formulier weergeven op web/mobiele en andere interfaces als een headless-formulier.

### Lessencontext

In deze les leert u als ontwikkelaar vooraf hoe u het adaptieve formulier dat u eerder hebt gemaakt, kunt weergeven als een vorm zonder kop met behulp van het raamwerk voor het ontwerpen van het spectrum voor reacties.

### Uitoefening

De lokale bewaarplaats van de opstelling gebruikend reactie starter project:

1. Open de Herinnering van het Bevel gebruikend beheerderrechten.

   ![](/help/assets/screenshot2028115829.png){width="30%" align="left"}

1. Gebruik in de opdrachtprompt de volgende opdracht om naar de map `c:\git` te navigeren.

   ```Shell
   cd git
   ```

1. Gebruik de volgende opdracht om het aanzetproject Adaptief formulier te klonen:

   ```Shell
   git clone https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028117329.png)

1. Gebruik de volgende bevelen in de vermelde orde om aan de **te navigeren reactie-starter-kit-a-headless-vormen** folder en open Code van Visual Studio.

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028117529.png)


   Het venster van de Code van Visual Studio opent.

   ![](/help/assets/screenshot2028117429.png){width="50%" align="left"}

Het formulier weergeven dat wordt gehost in uw publicatieomgeving:

1. Wijzig de naam van het env_template-bestand in .env-bestand. Om anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen** optie.

   ![](/help/assets/screenshot2028117629.png){width="30%" align="left"}

   ![](/help/assets/screenshot2028117729.png)

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt.

   * **AEM_URL**: Specificeer URL van het publicatiemilieu. Bijvoorbeeld: `https://localhost:4503/`

   * **AEM_FORM_PATH**: Specificeer de weg van de Aangepaste Vorm die in de vorige les wordt gecreeerd. Bijvoorbeeld: `/content/forms/af/contact-us/`

   </br>

   ![](/help/assets/lab65-starter-kit-environment-variable.png)

1. Open het bevelvenster, zorg ervoor u bij de **reactie-starter-kit-a-headless-vormen** folder bent, en stel het volgende bevel in werking:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028118029.png)


1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm start
   ```

   ![](/help/assets/lab65-starter-kit-start.png)

   Met de bovenstaande opdracht start u een lokale ontwikkelingsserver waarmee de formulierdefinitie die is opgehaald van AEM, zonder kop wordt weergegeven met behulp van de frontend bibliotheek met het spectrum voor reacties.

   >[!NOTE]
   >
   > 
   > Als u een leeg scherm in browser na het uitvoeren van het `npm start` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.

   ![](/help/assets/headless-adaptive-form-lab.png)

We brengen wijzigingen aan in het formulier op de server als een zakelijke gebruiker. Wijzigingen worden dan automatisch doorgevoerd in het formulier zonder kop.

1. Open de AEM Forms-beheerinterface in de browser. Bijvoorbeeld, [ http://localhost:4502/aem/forms.html/content/dam/formsanddocuments ](http://localhost:4502/aem/forms.html/content/dam/formsanddocuments).

1. Selecteer de **vorm van het Contact van ons** en klik **uitgeven.** Het formulier wordt geopend in de Adaptive Forms Editor.


1. Selecteer het **gebied van het Aantal van het Contact** en klik **uitgeven pictogram (het pictogram van het Potlood)** in de toolbar. Als u niet de pop op toolbar kunt zien, schakelaar om wijze uit te geven door **te klikken geeft** knoop in hoogste recht uit, links naar **Voorproef** knoop.

   ![](/help/assets/change-field-title.png){width="50%" align="left"}

1. Verander het etiket in **Mobiel Aantal**. Klik op een lege ruimte in het formulier en de wijzigingen die in het formulier zijn aangebracht, worden opgeslagen.

Laten we het bijgewerkte formulier publiceren om de wijzigingen in de publicatieomgeving door te geven.

1. In het lusje van de het beheersinterface van AEM Forms, selecteer de vorm van het contactgebruik, en klik **unpublish**. Als u niet **ziet unpublish** knoop, overslaan aan stap 3 om de veranderingen direct te publiceren.


1. Klik **unpublish**. Klik **Sluiten** in respectieve dialoog.

1. Na browser verfrist zich, selecteer de vorm van het contactusje en klik **Publish**.


1. Klik **Publish**. Klik **dicht** in de respectieve dialoog.

1. Vernieuw de browsertab met de koploze vorm. Het label Contactnummer is gewijzigd in Mobiel nummer.

   ![](/help/assets/headless-adaptive-form.png)

1. Open het Prompt venster van het Bevel dat wordt gebruikt om **te beginnen reactie-starter-kit-a-headless-vormen** project, druk **CTRL+C**, dan
ga **Y** in en druk Enter sleutel om het npm proces te eindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.

1. Sluit de Code van Visual Studio en de Snelle vensters van het Bevel.


## Les 5

### Doelstelling

Het formulier weergeven als een formulier zonder kop met de gebruikersinterface voor Google-materiaal

### Lessencontext

In deze les leert u als ontwikkelaar aan de voorzijde hoe u het adaptieve formulier dat u eerder hebt gemaakt, kunt weergeven als een formulier zonder kop met de gebruikersinterface van Google-materiaal.

### Uitoefening

Stel lokale opslagruimte in met een project voor het starten van een materiaalinterface:

1. Open de Herinnering van het Bevel gebruikend beheerderrechten.

   ![](/help/assets/screenshot2028115829.png){width="30%" align="left"}

1. Gebruik in de opdrachtprompt de volgende opdracht om naar de map `c:\git` te navigeren.

   ```Shell
   cd git
   ```

1. Voer de volgende opdrachten in de vermelde volgorde uit om een map met de naam mui te maken en naar de map mui te navigeren met de volgende opdrachten:

   ```Shell
   mkdir mui
   
   cd mui
   ```

1. Gebruik de volgende opdracht om het aanzetproject Adaptief formulier te klonen:

   ```Shell
   git clone -b mui-lab https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028126529.png)

1. Gebruik het volgende bevel in de vermelde orde om aan de **te navigeren reactie-starter-kit-a-headless-formulieren** omslag en open de code in de Code van Visual Studio:

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028126829.png)

Het formulier weergeven dat wordt gehost in uw publicatieomgeving:

1. Wijzig de naam van het **env_template** dossier aan **.env** dossier. Om anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen**.

   ![](/help/assets/screenshot2028126629.png){width="30%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt. Gebruik **CTRL + S** schakelaarcombinatie om het dossier te bewaren.

   * **AEM_URL**: Specificeer URL van het publicatiemilieu. Bijvoorbeeld, [ https://localhost:4503](https://localhost:4503)

   * **AEM_FORM_PATH**: Specificeer de weg van de Aangepaste Vorm die in de vorige les wordt gecreeerd. Bijvoorbeeld /content/forms/af/contact-us/


1. Open het bevelvenster, zorg ervoor u bij de **reactie-starter-kit-a-headless-vormen** folder bent, en stel het volgende bevel in werking:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028127029.png)

1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm start
   ```

   ![](/help/assets/lab65-mui-starter-kit-start.png)

   Met de opdracht wordt een lokale ontwikkelingsserver gestart en wordt de formulierdefinitie zonder kop opgehaald van AEM met behulp van de Google Material UI frontend-bibliotheek.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser na het uitvoeren van het `npm start` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.

   ![](/help/assets/google-mui-form.png)

## Les 6

### Doelstelling

Een ander uiterlijk van de vorm zonder kop maken met behulp van variaties in de materiaalinterface

### Lessencontext

In deze les, als front-end ontwikkelaar, leert u hoe te om een afwisselende vertegenwoordiging van verschillende componenten tot stand te brengen gebruikend Materiële UI voor de AanpassingsVorm die eerder door de bedrijfsgebruiker wordt gecreeerd.

### Uitoefening

Werk de variatie van componenten in het hoofdloze project bij. U kunt als volgt de variant van de materiaalUI-tekstinvoercomponent wijzigen in `OutlinedInput` :

1. Navigeer in Visuele code naar de tekstinvoercomponent door het `index.tsx` -bestand op `src/components/textinput/index.tsx` te openen.

1. Voeg `//` toe aan het begin van coderegel 104. De regel wordt omgezet in een opmerking.

   ```Shell
   //const Cmp = \'outlined\' === appliedCssClassNames ? OutlinedInput: Input;
   ```

1. Voeg het volgende toe op regel 105 om een andere variant van component te gebruiken en het dossier op te slaan. Gebruik **CTRL + S** schakelaarcombinatie om het dossier te bewaren.

   ```Shell
   const Cmp = OutlinedInput;
   ```

   ![](/help/assets/aem65-lab-code-update.png)

   Het is essentieel om correcte kapitalisatie voor &quot;OutlinedInput&quot;variant anders te gebruiken zou compilatie ontbreken. De lokale compilatie van de ontwikkelomgeving begint automatisch in Bevel. Wacht tot u het volgende bericht ziet

   `webpack 5.75.0 compiled with 3 warnings in 6659 ms`
   `inside proxy req`
   `setting new origin header`

1. Vernieuw de browser als deze niet automatisch wordt vernieuwd om te zien hoe de component voor tekstinvoer een andere variant gebruikt.

   ![](/help/assets/screenshot2028127729.png){width="50%" align="left"}


   Deze wijziging vindt plaats voor eindgebruikers zonder dat de formulierdefinitie wordt gewijzigd op AEM Forms Server en is specifiek voor de headless
betrokken kanaal. Bijvoorbeeld, Webkanaal in dit laboratorium.

   ![](/help/assets/aem65-lab-mui-style-update.png)


1. Sluit de Code van Visual Studio en de Snelle Vensters van het Bevel.

## Veelgestelde vragen

+++ Zijn de Componenten van de Kern openbaar?

Ja, Adaptive Forms Core Components zijn verkrijgbaar met AEM 6.5 Forms en Forms als Cloud Service. U hebt AEM Forms 6.5 Service Pack 16 of hoger nodig om Adaptive Forms Core Components te kunnen gebruiken.

+++

+++ Vereisen de Hoofdloze vormen een afzonderlijke vergunning?

Nee, voor Headless-formulieren wordt dezelfde licentiewaarde gebruikt, uitgedrukt in het aantal verzonden formulieren.

+++




## Volgende stappen

Nu u hebt geleerd hoe u Adaptive Forms kunt bouwen en op meerdere kanalen kunt aanbieden met behulp van headless-formulieren, moet u proberen uw nieuwe vaardigheden in werking te stellen. Maak plezier en ga door met het creëren en leveren van uitzonderlijke ervaringen voor het vastleggen van gegevens aan uw eindgebruikers, waar ze zich bevinden, op schaal!

## Bronnen

* [ Aangepaste Inleiding van de Componenten van de Kern van de Vorm ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)

* [ creeer Aangepast Vorm gebruikend de Componenten van de Kern ](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

* [ stileren van de Update voor kern op component-gebaseerde AF ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=en)

* [ Zwaarloze Adaptieve Forms ](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/overview.html?lang=en)

* [ Gebruikend Hoofdloze Reageer starterkit ](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/get-started/create-and-publish-a-headless-form.html?lang=en)
