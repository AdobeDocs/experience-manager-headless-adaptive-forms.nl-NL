---
title: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-title: Build Engaging Forms Using Core Components and Headless
description: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-description: Build Engaging Forms Using Core Components and Headless
topic-tags: develop
hide: true
hidefromtoc: true
exl-id: d0ca7389-9a7a-421e-ab6b-7845813d860e
source-git-commit: f489a2ba818db44ccd92df80a177f0e9f3a1bc2c
workflow-type: tm+mt
source-wordcount: '2479'
ht-degree: 0%

---

# Forms inschakelen met behulp van Core Components en Headless Adaptive Forms op AEM Forms as a Cloud Service {#build-engaging-forms-using-core-components-and-headless}

## Overzicht van Lab {#lab-overview}

In dit hands-on laboratorium, leert u:

Hoe u AEM Forms kunt gebruiken om gemakkelijk adaptieve formulieren te maken met de nieuwste kerncomponenten die consistent zijn met AEM Sites, waardoor het mogelijk wordt om gegevens op te halen door de adaptieve formulieren als headless formulieren aan het web, mobiele apparaten en chatten te leveren. U leert ook beste praktijken rond het stileren, aanpassingen, en front-end ontwikkeling.

## Toetsen {#key-takeaways}

* **Bedrijfsflexibiliteit**: Als zakelijke gebruiker kan ik gemakkelijk Form Experience voor meerdere kanalen schrijven.

* **Kracht voor ontwikkelaar vooraf**: Als front-end ontwikkelaar kan ik de gebruikerservaring bepalen met behulp van headless formulieren.

* **Snelheid ontwikkelaar**: Als ontwikkelaar kan ik gemakkelijk en consistent Sites en Forms-componenten aanpassen.

## Vereisten {#prerequisites}

Om deze handen op laboratorium te gebruiken:

* Installeer de [nieuwste release van Git](https://git-scm.com/downloads). Als u nog geen ervaring hebt met Git, raadpleegt u [Git installeren](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Installeren [Node.js 16.13.0 of hoger](https://nodejs.org/en/download/). Als u nog geen ervaring hebt met Node.js, raadpleegt u [Node.js installeren](https://nodejs.dev/en/learn/how-to-install-nodejs).

* [Hoofdloze adaptieve Forms inschakelen](enable-headless-adaptive-forms-and-core-components-on-forms-cloud-service.md) voor uw as a Cloud Service AEM Forms-omgeving.

* Installeren [Microsoft Visual Studio-code](https://code.visualstudio.com/download) of een teksteditor zonder opmaak. De voorbeelden in document maken gebruik van de Code van Microsoft Visual Studio.



## Les 1 {#lesson-1}

### Doelstelling {#lesson-1-objectives}

Verken uzelf met de as a Cloud Service AEM Forms-omgeving.

### Lessencontext {#lesson-1-context}

In deze les, vertrouwt u zich met het as a Cloud Service milieu van AEM Forms door het gebruikersinterface te navigeren.

### Uitoefening {#lesson-1-excercise}

1. Open uw browser en ga URL van het auteursmilieu van de Cloud Service in. Bijvoorbeeld:
   [https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/start.html](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/start.html)

1. Meld u aan bij de ontwikkelomgeving van de Cloud Service.

1. Als u naar de gebruikersinterface van AEM Forms wilt navigeren, klikt u op **Forms > Forms &amp; Documents**.

   ![](/help/assets/screenshot2028113829.png){width="50%" align="left"}

   ![](/help/assets/screenshot2028113929.png){width="50%" align="left"}

   Pop-ups met betrekking tot voorkeuren of gegevens negeren. Alle beschikbare formulieren worden weergegeven.


## Les 2

### Doelstelling

Ontwerp een adaptief formulier met de nieuwste kerncomponenten, configureer het formulier en verzend het.

### Lessencontext

In deze les zult u als zakelijke gebruiker een adaptief formulier ontwerpen voor meerdere kanalen, zoals web, mobiel en chatten met behulp van adaptieve formulieren die zijn ontworpen met gestandaardiseerde OTB-kerncomponenten voor het vastleggen van gegevens.

### Uitoefening

1. Maak een verzendeindpunt voor het formulier:

   1. Openen <https://requestbin.com/> in een nieuw browsertabblad.
      ![](/help/assets/screenshot2028114329.png){width="50%" align="left"}

   1. Klikken **Een openbare map maken** en kopieer de URL van het eindpunt.
      ![](/help/assets/screenshot202023-03-0120at206.10.0020pm.png){width="50%" align="left"}

1. Ontwerp een adaptief formulier met de wizard-interface:

   1. Navigeer in het browsertabblad dat wordt gebruikt in Les 1 naar AEM Forms als Cloud Service-webinterface en navigeer naar Forms en Documenten.
      ![](/help/assets/screenshot2028114029.png)

   1. Klikken **Maken** en selecteer Adaptief formulier.
      ![](/help/assets/screenshot2028114629.png)

   1. Selecteer de **Leeg met kerncomponenten** sjabloon in het scherm Sjabloonselectie, zoals hieronder wordt weergegeven:
      ![](/help/assets/screenshot202023-03-0120at206.09.1520pm.png)

   1. Klik op de knop **Stijl** en selecteert u de **thema** thema zoals hieronder getoond:
      ![](/help/assets/screenshot202023-03-0120at206.09.2320pm.png)

   1. Klik op de knop **Indiening** en selecteert u de **Verzenden naar REST-eindpunt** en geeft u de openbare map op in het dialoogvenster
      **URL voor het verzoek van de POST** veld zoals hieronder weergegeven:
      ![](/help/assets/screenshot202023-03-0120at206.09.5320pm.png)

   1. Klikken **Maken**. Geef een naam en titel op voor het formulier. Bijvoorbeeld: **registratie**. Klikken **Maken**.

   1. De aangepaste formuliereditor wordt geopend. Pop-ups of dialoogvensters voor voorkeuren of informatie negeren. Klik op de componentenbrowser op de linkerrails en voeg de **Koptekst** en **Voettekst** aan respectievelijk de boven- en onderzijde van het lege formulier.
      ![](/help/assets/screenshot2028121929.png)

   1. Sleep componenten vanuit de browser Components om een formulier te maken, vergelijkbaar met het volgende:

      ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}





1. Validaties toevoegen aan formulier:

   1. Klik op de knop **Telefoonnummer** zodat het pop-upmenu verschijnt. Klik op de knop **Perictogram** in het menu om het veld te configureren.

   1. Open de **validatie, tabblad** markeren **Vereist** en klik op **Gereed**. Het succesbericht wordt weergegeven.
      ![](/help/assets/screenshot2028123529.png){width="50%" align="left"}

      ![](/help/assets/screenshot2028123629.png){width="50%" align="left"}

1. Bekijk een voorbeeld van het formulier en verzend het.

   1. Klikken **Voorvertoning** om een voorbeeld van het formulier te bekijken vanuit het perspectief van de eindgebruiker.

   1. Vul het formulier met dummygegevens.

   1. Verzend het formulier.
      ![](/help/assets/screenshot2028125729.png)

   1. Controleer de verzonden gegevens op het tabblad Aanvraagvak.
      ![](/help/assets/screenshot2028125829.png)

1. Interactiviteit toevoegen aan formulier met regels:

   1. Klik op de knop **Schakel het selectievakje in als u 5% korting wilt ontvangen** component. Klik op het pictogram Regels op de optiewerkbalk. De bewerkingsoptie Regel wordt geopend.

   1. Maak een regel wanneer de **Schakel het selectievakje in als u 5% korting wilt ontvangen** is geselecteerd, zijn de opties voor het toepassen van een creditcard uitgeschakeld.

1. Publiceer het formulier.

   1. Open bijvoorbeeld de AEM Forms-beheerinterface. `https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments`en selecteert u het formulier.

   1. Klikken **Publiceren**.

      ![](/help/assets/screenshot2028115629.png)

      Het succesbericht wordt weergegeven.

      ![](/help/assets/screenshot2028115729.png)

      De publicatie-URL van het formulier lijkt op `https://publish-p105303-e986623.adobeaemcloud.com/content/forms/af/registration.html`.

   1. Als u het gepubliceerde formulier wilt weergeven, vervangt u de programma-id (pXXXXXX) en de milieu-id (eXXXXXX) in de bovenstaande URL door id&#39;s van uw omgeving.

## Les 3

### Doelstelling

Werk stijlen bij met behulp van best practices voor ontwikkeling vooraf.

### Lessencontext

In deze les leert u als front-end ontwikkelaar hoe u de opmaak van het eerder gemaakte adaptieve formulier eenvoudig kunt bijwerken.

### Uitoefening

Stel de lokale opslagruimte van het thema in:

1. Open de Herinnering of shell van het Bevel met beheerderrechten:

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om te navigeren aan **c:\git** map

   ```Shell
   cd c:\git
   ```

1. Gebruik de volgende opdracht om de themafrontend-code te klonen:

   ```Shell
   git clone -b WKND https://github.com/adobe/aem-forms-theme-canvas
   ```


1. Gebruik de volgende opdracht in de vermelde volgorde om naar de **aem-forms-theme-canvas** directory en open de Code van Visual Studio.

   ```Shell
   cd aem-forms-theme-canvas
   code .
   ```

   ![](/help/assets/screenshot2028126029.png)

1. Selecteren **De auteurs van alle bestanden in de bovenliggende map vertrouwen** en klik op **Ja, ik vertrouw de auteurs**.

   ![](/help/assets/screenshot2028116229.png){width="50%" align="left"}

1. Als u het formulier wilt weergeven dat wordt gehost in de publicatieomgeving van uw cloudservice, wijzigt u de naam van de `env_template` bestand.  Als u de naam van het bestand wilt wijzigen, klikt u op de knop **env_template** en selecteert u de **Naam wijzigen** -optie.

   ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}

   </br>

   ![](/help/assets/screenshot2028116529.png){width="50%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand en sla het bestand op:

   * **AEM_URL**: Geef uw publicatieomgeving voor de cloudservice op. Bijvoorbeeld, `https://publish-p105303-e986623.adobeaemcloud.com/`

   * **AEM_ADAPTIVE_FORM**: Geef het pad van het formulier op. Als het formulierpad bijvoorbeeld `/content/forms/af/registration`de waarde van deze variabele `registration`.

     ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}


1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028117029.png)

   >[!NOTE]
   >
   > * Als u een bericht ontvangt waarin u wordt gevraagd om Npm bij te werken via het dialoogvenster `npm notice Run npm nstall -g npm@9.6.0`, negeert u het bericht.
   > * Stel geen andere npm bevelen in werking tenzij geïnstrueerd in het werkboek.

1. Voer nu de volgende opdracht uit om een voorbeeld van het formulier te bekijken.

   ```Shell
   npm run live
   ```

   ![](/help/assets/screenshot2028117229.png)

   Zodra het bovenstaande bevel wordt uitgevoerd, wacht op `webpack compiled` bericht. Het formulier wordt weergegeven op een browsertabblad.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser ervaart nadat u de opdracht `npm run live` gebruiken voor meer dan 3-4 minuten, wijzigen `localhost` in browser URL naar 127.0.0.1 en druk op **Enter**.


   ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}


1. In de Code van Visual Studio, open `PROJECT\src\site\_variables.scss` bestand. Let op: `$error` kleur is een kleur van RED.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. Verstuur het formulier in de browser om de rode kleur in het dialoogvenster **Voornaam** veld.

   ![](/help/assets/screenshot2028120829.png)

1. Stel de **$error** kleur naar **#5736eb** en sla het bestand op.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. Vernieuw de browser en verzend het formulier. De kleur van de foutmelding in het veld Voornaam is dienovereenkomstig gewijzigd.

   ![](/help/assets/screenshot2028121129.png)

1. Druk in de opdrachtprompt op **CTRL+C**, enter **Y** en drukken op **Enter** sleutel om het npm proces te beëindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.
1. Sluit de Code van Visual Studio en de Snelle vensters van het Bevel.

## Les 4

### Doelstelling

Het formulier weergeven op web/mobiele en andere interfaces als een headless-formulier.

### Lessencontext

In deze les leert u als ontwikkelaar vooraf hoe u het adaptieve formulier dat u eerder hebt gemaakt, kunt weergeven als een vorm zonder kop met behulp van het raamwerk voor het ontwerpen van het spectrum met reacties.

### Uitoefening

De lokale bewaarplaats van de opstelling gebruikend reactie starter project:

1. Open de Herinnering van het Bevel gebruikend beheerderrechten.

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om te navigeren aan **c:\git** map

   ```Shell
   cd c:\git
   ```

1. Gebruik de volgende opdracht om het aanpasbare formulier te klonen om te starten:

   ```Shell
   git clone https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028117329.png)

1. Gebruik de volgende opdrachten in de vermelde volgorde om naar de **response-starter-kit-aem-headless-forms** directory en open de Code van Visual Studio.

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028117529.png)


   Het venster van de Code van Visual Studio opent.

   ![](/help/assets/screenshot2028117429.png){width="50%" align="left"}

U kunt als volgt het formulier weergeven dat wordt gehost op uw cloudservice-publicatieomgeving:

1. Wijzig de naam van het env_template-bestand in .env-bestand. Klik met de rechtermuisknop op de knop **env_template** en selecteert u de **Naam wijzigen** -optie.

   ![](/help/assets/screenshot2028117629.png){width="50%" align="left"}

   ![](/help/assets/screenshot2028117729.png)

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt.

   * **AEM_URL**: Geef de URL van de publicatieomgeving van de cloudservice op. Bijvoorbeeld, `https://publish-p105303-e986623.adobeaemcloud.com`

   * **AEM_FORM_PATH**: Geef het pad op van het adaptieve formulier dat in de vorige les is gemaakt. Bijvoorbeeld, `/content/forms/af/registration/`

     ![](/help/assets/screenshot202023-03-0820at202.49.1820pm.png)

1. Open het opdrachtvenster, controleer of u zich in de map met formulieren zonder hoofdletter en hoofdletter bevindt voor de reactie en voer de volgende opdracht uit:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028118029.png)


1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm start
   ```

   ![](/help/assets/screenshot2028118129.png)

   Met de bovenstaande opdracht start u een lokale ontwikkelingsserver waarmee de formulierdefinitie die is opgehaald van AEM, zonder kop wordt weergegeven met behulp van de frontend bibliotheek met het spectrum voor reacties.

   >[!NOTE]
   >
   > 
   > Als u een leeg scherm in browser ervaart nadat u de opdracht `npm start` gebruiken voor meer dan 3-4 minuten, wijzigen `localhost` in browser URL naar 127.0.0.1 en druk op **Enter**.

   ![](/help/assets/screenshot2028118229.png)

Laten we de uitvoering van regels in deze vorm zonder kop controleren:

1. Selecteer de **Schakel het selectievakje in als u 5% korting wilt ontvangen** -optie. De volgende optie voor het toepassen van een creditcard is uitgeschakeld.

   ![](/help/assets/screenshot2028126229.png)

1. Uitschakelen **Schakel het selectievakje in als u 5% korting wilt ontvangen** om de optie creditcard in te schakelen.

   ![](/help/assets/screenshot2028126329.png)

We brengen wijzigingen aan in het formulier op de server als een zakelijke gebruiker. Wijzigingen worden dan automatisch doorgevoerd in het formulier zonder kop.

1. Open de AEM Forms-beheerinterface in de browser. Bijvoorbeeld: [https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/forms.html/content/dam/formsanddocuments](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments).

1. Selecteer de **contactus** formulier en klik op **Bewerken.** Het formulier wordt geopend in de editor voor adaptieve formulieren.


1. Selecteer de **Telefoonnummer** en klik op de knop **Bewerkingspictogram (potloodpictogram)** in de werkbalk. Als u de pop-upwerkbalk niet kunt zien, schakelt u over naar de modus Bewerken door op **Bewerken** knop rechtsboven, links naar **Voorvertoning** knop.

   ![](/help/assets/screenshot2028119629.png)

1. Wijzig het label in Mobiel nummer. Klik op een lege ruimte in het formulier en de wijzigingen die in het formulier zijn aangebracht, worden opgeslagen.

   ![](/help/assets/screenshot2028119729.png)

Laten we het bijgewerkte formulier publiceren om de wijzigingen in de publicatieomgeving door te geven.

1. Selecteer het registratieformulier op het tabblad AEM Forms-beheerinterface en klik op **Publiceren ongedaan maken**. Als u het geneesmiddel niet ziet **Publiceren ongedaan maken** gaat u naar stap 3 om de wijzigingen rechtstreeks te publiceren.

1. Klikken **Publiceren ongedaan maken**. Klikken **Sluiten** in de respectieve dialoog.

1. Selecteer het registratieformulier nadat de browser is vernieuwd en klik op **Publiceren**.

1. Klikken **Publiceren**. Klikken **Sluiten** in de respectieve dialoog.

1. Vernieuw de browsertab met de koploze vorm. Het label Telefoonnummer is gewijzigd in Mobiel nummer.

   ![](/help/assets/screenshot2028120529.png)

1. Open het venster Opdrachtprompt waarmee het dialoogvenster **response-starter-kit-aem-headless-forms** project, pers **CTRL+C** en vervolgens voert u **Y** en druk op Enter om het npm-proces te beëindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.

1. Sluit de Code van Visual Studio en de Snelle vensters van het Bevel.


## Les 5

### Doelstelling

Het formulier weergeven als een formulier zonder kop met de gebruikersinterface voor Google-materiaal

### Lessencontext

In deze les leert u als ontwikkelaar aan de voorzijde hoe u het adaptieve formulier dat u eerder hebt gemaakt, kunt weergeven als een formulier zonder kop met de gebruikersinterface van Google Material.

### Uitoefening

Stel lokale opslagruimte in met een project voor het starten van een materiaalinterface:

1. Open de Herinnering van het Bevel gebruikend beheerderrechten.

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}


1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om te navigeren aan **c:\git** map:

   ```Shell
   cd c:\git
   ```

1. Voer de volgende opdrachten in de vermelde volgorde uit om een map met de naam mui te maken en naar de map mui te navigeren met de volgende opdrachten:

   ```Shell
   mkdir mui
   
   cd mui
   ```

1. Gebruik de volgende opdracht om het aanpasbare formulier te klonen om te starten:

   ```Shell
   git clone -b mui-lab https://github.com/adobe/react-starter-kit-aem-headless-forms
   ```

   ![](/help/assets/screenshot2028126529.png)

1. Gebruik de volgende opdracht in de vermelde volgorde om naar de **response-starter-kit-aem-headless-forms** omslag en open de code in de Code van Visual Studio:

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028126829.png)

U kunt als volgt het formulier weergeven dat wordt gehost op uw cloudservice-publicatieomgeving:

1. De naam van de **env_template** bestand naar **.env** bestand. Klik met de rechtermuisknop op de knop **env_template** bestand en selecteer **Naam wijzigen**.

   ![](/help/assets/screenshot2028126629.png){width="50%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt. Gebruik de **CTRL + S** overschakelen op een andere combinatie om het bestand op te slaan.

   * **AEM_URL**: Geef de URL van de publicatieomgeving van de cloudservice op. Bijvoorbeeld: [https://publish-p105303-e986623.adobeaemcloud.com](https://publish-p105303-e986623.adobeaemcloud.com/)

   * **AEM_FORM_PATH**: Geef het pad op van het adaptieve formulier dat in de vorige les is gemaakt. Bijvoorbeeld: /content/forms/af/registration/

     ![](/help/assets/screenshot2028126929.png)

1. Open het opdrachtvenster en zorg dat u zich bij de **response-starter-kit-aem-headless-forms** en voer de volgende opdracht uit:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028127029.png)

1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm start
   ```

   ![](/help/assets/screenshot2028127129.png)

   Met de opdracht wordt een lokale ontwikkelingsserver gestart en wordt de formulierdefinitie zonder kop opgehaald van AEM met behulp van de Google Material UI frontend-bibliotheek.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser ervaart nadat u de opdracht `npm start` gebruiken voor meer dan 3-4 minuten, wijzigen `localhost` in browser URL naar 127.0.0.1 en druk op **Enter**.

   ![](/help/assets/screenshot2028127229.png)

1. U kunt als volgt de uitvoering van dezelfde bedrijfslogica in deze formulieruitvoering evalueren:

   Selecteren **Schakel het selectievakje in als u 5% korting wilt ontvangen**. De volgende optie **Wilt u een aanvraag indienen voor het formulier voor eBay-creditcard?** wordt uitgeschakeld.

   ![](/help/assets/screenshot2028127329.png){width="50%" align="left"}

## Les 6

### Doelstelling

Een ander uiterlijk van de vorm zonder kop maken met behulp van variaties in de materiaalinterface

### Lessencontext

In deze les leert u als front-end ontwikkelaar hoe u een alternatieve representatie van verschillende componenten kunt maken met behulp van materiaalinterface voor het adaptieve formulier dat eerder door de zakelijke gebruiker is gemaakt.

### Uitoefening

Werk de variatie van componenten in het hoofdloze project bij. De variant van de materiaalinterface-tekstinvoercomponent wijzigen in `OutlinedInput`:

1. In Visuele Code, navigeer aan de component van de tekstinput door te openen `index.tsx` bestand bij `src/components/textinput/index.tsx`.

1. Toevoegen `//` aan het begin van coderegel 103. De regel wordt omgezet in een opmerking.

   ```Shell
   //const Cmp = \'outlined\' === appliedCssClassNames ? OutlinedInput: Input;
   ```

1. Voeg het volgende toe op regel 104 om een andere variant van component te gebruiken en het dossier op te slaan. Gebruik de **CTRL + S** overschakelen op een andere combinatie om het bestand op te slaan.

   ```Shell
   const Cmp = OutlinedInput;
   ```

   ![](/help/assets/screenshot2028127629.png)

   Het is essentieel om correcte kapitalisatie voor &quot;OutlinedInput&quot;variant anders te gebruiken zou compilatie ontbreken. De lokale compilatie van de ontwikkelomgeving begint automatisch in Bevel. Wacht tot u het volgende bericht ziet

   `webpack 5.75.0 compiled with 3 warnings in 6659 ms`
   `inside proxy req`
   `setting new origin header`

1. Vernieuw de browser als deze niet automatisch wordt vernieuwd om te zien hoe de component voor tekstinvoer een andere variant gebruikt.

   ![](/help/assets/screenshot2028127729.png)


   Deze wijziging vindt plaats voor eindgebruikers zonder dat de formulierdefinitie wordt gewijzigd op AEM Forms Server en is specifiek voor het kanaal zonder kop in kwestie. Bijvoorbeeld, Webkanaal in dit laboratorium.

   ![](/help/assets/screenshot2028127529.png){width="50%" align="left"}


1. Sluit de Code van Visual Studio en de Snelle Vensters van het Bevel.

## Veelgestelde vragen

+++ Is de wizard Adaptief formulier openbaar?

Ja, het is beschikbaar bij AEM Forms als Cloud Service.

+++


+++ Zijn de kerncomponenten openbaar?

Ja, Adaptive Forms core-componenten zijn beschikbaar met AEM Forms als Cloud Service.

+++

+++ Zijn krantenloze formulieren openbaar?

Ja, koploze formulieren zijn beschikbaar met AEM Forms als Cloud Service.

+++

+++ Vereisen de Hoofdloze vormen een afzonderlijke vergunning?

Nee, voor Headless-formulieren wordt dezelfde licentiewaarde gebruikt, uitgedrukt in het aantal verzonden formulieren.

+++

+++ Zijn de componenten van de Kern en Zwaarloze vormen beschikbaar met AEM 6.5 Forms?

Ja, beide adaptieve formulieren bevatten kerncomponenten en headless formulieren die beschikbaar zijn met AEM Forms 6.5 Service Pack 16 en hoger.

+++


## Volgende stappen

Nu u hebt geleerd hoe u adaptieve formulieren kunt maken en deze op meerdere kanalen kunt aanbieden met behulp van headless-formulieren, moet u proberen uw nieuwe vaardigheden in werking te stellen. Maak plezier en ga door met het creëren en leveren van uitzonderlijke ervaringen voor het vastleggen van gegevens aan uw eindgebruikers, waar ze zich bevinden, op schaal!

## Bronnen

* [Inleiding van de kerncomponenten van Adaptive Form](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html)

* [Adaptief formulier maken met behulp van kerncomponenten](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

* [Update styling voor kern op component-gebaseerde AF](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=en)

* [Hoofdloze adaptieve formulieren](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/overview.html?lang=en)

* [Startkit voor Headless React gebruiken](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/get-started/create-and-publish-a-headless-form.html?lang=en)
