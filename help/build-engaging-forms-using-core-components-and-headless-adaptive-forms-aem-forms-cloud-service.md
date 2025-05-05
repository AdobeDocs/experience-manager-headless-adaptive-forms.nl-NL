---
title: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-title: Build Engaging Forms Using Core Components and Headless
description: Forms inschakelen met behulp van kerncomponenten en zonder hoofd
seo-description: Build Engaging Forms Using Core Components and Headless
topic-tags: develop
exl-id: ef99ffe9-4a37-4f0a-a4d3-78976c92220f
source-git-commit: bcc51bcae3b26cf20e7c0b5b75935bf69a991731
workflow-type: tm+mt
source-wordcount: '2452'
ht-degree: 0%

---

# Forms inschakelen met behulp van Core Components en Headless Adaptive Forms op AEM Forms as a Cloud Service {#build-engaging-forms-using-core-components-and-headless}

## Overzicht van Lab {#lab-overview}

In dit hands-on laboratorium, leert u:

Hoe u AEM Forms kunt gebruiken om gemakkelijk adaptieve formulieren te maken met de nieuwste kerncomponenten die consistent zijn met AEM Sites, waardoor het mogelijk wordt om gegevens op te halen door de adaptieve formulieren als headless formulieren aan het web, mobiele apparaten en chatten te leveren. U leert ook beste praktijken rond het stileren, aanpassingen, en front-end ontwikkeling.

## Toetsen {#key-takeaways}

* **Bedrijfs Agility**: Als bedrijfsgebruiker, kan ik de ervaring van de Vorm voor veelvoudige kanalen gemakkelijk ontwerpen.

* **Macht om ontwikkelaar** vooruit te sturen: Als vooruitstrevende ontwikkelaar, kan ik de eindgebruikerservaring controleren gebruikend hoofdloze vormen.

* **Snelheid van de Ontwikkelaar**: Als ontwikkelaar, kan ik gemakkelijk en constant Plaatsen en de componenten van Forms aanpassen.

## Vereisten {#prerequisites}

Om deze handen op laboratorium te gebruiken:

* Installeer de [ recentste versie van Git ](https://git-scm.com/downloads). Als u aan Git nieuw bent, zie [ Installerend Git ](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).

* Installeer [ Node.js 16.13.0 of later ](https://nodejs.org/en/download/). Als u aan Node.js nieuw bent, zie [ hoe te Node.js ](https://nodejs.org/en/learn/getting-started/how-to-install-nodejs) installeren.

* [ laat de Aangepaste Componenten van de Kern van Forms ](enable-headless-adaptive-forms-and-core-components-on-forms-cloud-service.md) voor uw as a Cloud Service milieu van AEM Forms toe.

* Installeer [ Code van Microsoft Visual Studio ](https://code.visualstudio.com/download) of om het even welke duidelijke tekstredacteur. De voorbeelden in document maken gebruik van de Code van Microsoft Visual Studio.



## Les 1 {#lesson-1}

### Doelstelling {#lesson-1-objectives}

Verken uzelf met de as a Cloud Service AEM Forms-omgeving.

### Lessencontext {#lesson-1-context}

In deze les, vertrouwt u zich met het as a Cloud Service milieu van AEM Forms door het gebruikersinterface te navigeren.

### Uitoefening {#lesson-1-excercise}

1. Open uw browser en ga URL van het auteursmilieu van de Cloud Service in. Bijvoorbeeld:
   [ https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/start.html](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/start.html)

1. Meld u aan bij de ontwikkelomgeving van de Cloud Service.
   ![](/help/assets/screenshot2028113829.png){width="50%" align="left"}

1. Om aan AEM Forms UI te navigeren, klik **Forms > Forms &amp; Documenten**.



   ![](/help/assets/screenshot2028113929.png){width="50%" align="left"}

   Pop-ups met betrekking tot voorkeuren of gegevens negeren. Alle beschikbare formulieren worden weergegeven.


## Les 2

### Doelstelling

Ontwerp een adaptief formulier met de nieuwste kerncomponenten, configureer het formulier en verzend het.

### Lessencontext

In deze les zult u als zakelijke gebruiker een adaptief formulier ontwerpen voor meerdere kanalen, zoals web, mobiel en chatten met behulp van adaptieve formulieren die zijn ontworpen met gestandaardiseerde OTB-kerncomponenten voor het vastleggen van gegevens.

### Uitoefening

1. Maak een verzendeindpunt voor het formulier:

   1. Open <https://requestbin.com/> in een nieuw browsertabblad.
   1. Klik **creeer een openbare bak** en kopieer het eindpunt URL.

      ![](/help/assets/screenshot2028114329.png){width="50%" align="left"}

      ![](/help/assets/screenshot202023-03-0120at206.10.0020pm.png){width="50%" align="left"}

1. Ontwerp een adaptief formulier met de wizard-interface:

   1. Navigeer in het browsertabblad dat wordt gebruikt in Les 1 naar AEM Forms als Cloud Service-webinterface en navigeer naar Forms en Documenten.

      ![](/help/assets/screenshot2028114029.png)

   1. Klik **creëren** en selecteer AanpassingsVorm.

      ![](/help/assets/screenshot2028114629.png)

   1. Selecteer **Leeg met het malplaatje van de Componenten van de Kern** van het scherm van de malplaatjeselectie zoals hieronder getoond:

      ![](/help/assets/screenshot202023-03-0120at206.09.1520pm.png)

   1. Klik het **lusje van de Stijl** en selecteer het **wknd-thema** thema zoals hieronder getoond:

      ![](/help/assets/screenshot202023-03-0120at206.09.2320pm.png)

   1. Klik het **lusje van de Verzending** en selecteer **voorleggen aan REST eind-punt** kaart en specificeer de openbare bak in **URL voor het gebied van het verzoek van de POST** zoals hieronder getoond:

      ![](/help/assets/screenshot202023-03-0120at206.09.5320pm.png)

   1. Klik **creëren**. Geef een naam en titel op voor het formulier. Bijvoorbeeld, **registratie**. Klik **creëren**.

   1. De aangepaste formuliereditor wordt geopend. Pop-ups of dialoogvensters voor voorkeuren of informatie negeren. Klik componenten browser op linkerspoor en voeg de **Kopbal** toe en **Voettekst** componenten respectievelijk aan de bovenkant en de bodem van de lege vorm.

      ![](/help/assets/screenshot2028121929.png)

   1. Sleep componenten vanuit de browser Components om een formulier te maken, vergelijkbaar met het volgende:

      ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}

1. Validaties toevoegen aan formulier:

   1. Klik de **component van het aantal van de Telefoon** zodat pop-up menu wordt getoond. Klik het **pictogram van de Sleutel** in het menu om het gebied te vormen.

   1. Open het **bevestigingslusje**, merk het gebied **Vereiste**, en klik **Gedaan**. Het succesbericht wordt weergegeven.

      ![](/help/assets/screenshot2028123529.png){width="50%" align="left"}

      ![](/help/assets/screenshot2028123629.png){width="50%" align="left"}

1. Bekijk een voorbeeld van het formulier en verzend het.

   1. Klik **Voorproef** aan voorproef de vorm van een eindgebruikerperspectief.

   1. Vul het formulier met dummygegevens.

   1. Verzend het formulier.

      ![](/help/assets/screenshot2028125729.png)

   1. Controleer de verzonden gegevens op het tabblad Aanvraagvak.

      ![](/help/assets/screenshot2028125829.png)

1. Interactiviteit toevoegen aan formulier met regels:

   1. Klik de **Controle de doos om 5% van** component te ontvangen. Klik op het pictogram Regels op de optiewerkbalk. De bewerkingsoptie Regel wordt geopend.

   1. Creeer een regel, wanneer de **Controle de doos om 5% van** optie te ontvangen wordt geselecteerd, worden de opties om creditcard toe te passen onbruikbaar gemaakt.

1. Publish het formulier.

   1. Open bijvoorbeeld de AEM Forms-beheerinterface `https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments` en selecteer het formulier.

   1. Klik **Publish**.

      ![](/help/assets/screenshot2028115629.png)

      Het succesbericht wordt weergegeven.

      ![](/help/assets/screenshot2028115729.png)

      De publicatie-URL van het formulier komt overeen met `https://publish-p105303-e986623.adobeaemcloud.com/content/forms/af/registration.html` .

   1. Als u het gepubliceerde formulier wilt weergeven, vervangt u de programma-id (pXXXXXX) en de milieu-id (eXXXXXX) in de bovenstaande URL door de id&#39;s van uw
milieu.

## Les 3

### Doelstelling

Werk stijlen bij met behulp van best practices voor ontwikkeling vooraf.

### Lessencontext

In deze les leert u als front-end ontwikkelaar hoe u de opmaak van het eerder gemaakte adaptieve formulier eenvoudig kunt bijwerken.

### Uitoefening

Stel de lokale opslagruimte van het thema in:

1. Open de Herinnering of shell van het Bevel met beheerderrechten:

   ![](/help/assets/screenshot2028115829.png){width="50%" align="left"}

1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om aan **c te navigeren:\ git** omslag

   ```Shell
   cd c:\git
   ```

1. Gebruik de volgende opdracht om de themafrontend-code te klonen:

   ```Shell
   git clone -b WKND https://github.com/adobe/aem-forms-theme-canvas
   ```


1. Gebruik het volgende bevel in de vermelde orde om aan **te navigeren aem-vormen-thema-canvas** folder en open Code van Visual Studio.

   ```Shell
   cd aem-forms-theme-canvas
   code .
   ```

   ![](/help/assets/screenshot2028126029.png)

1. Selecteer **Vertrouwen de auteurs van alle dossiers in de ouderomslag** en klik **ja, ik vertrouw de auteurs**.

   ![](/help/assets/screenshot2028116229.png){width="50%" align="left"}

1. Als u het formulier wilt weergeven dat wordt gehost in de publicatieomgeving van uw cloudservice, wijzigt u de naam van het `env_template` -bestand.  Om het dossier anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen** optie.

   ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}

   </br>

   ![](/help/assets/screenshot2028116529.png){width="50%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand en sla het bestand op:

   * **AEM_URL**: Specificeer uw de dienstpublicatiemilieu van de wolk. Bijvoorbeeld: `https://publish-p105303-e986623.adobeaemcloud.com/`

   * **AEM_ADAPTIVE_FORM**: Specificeer de weg van de vorm. Als het formulierpad bijvoorbeeld `/content/forms/af/registration` is, is de waarde van deze variabele `registration` .

     ![](/help/assets/screenshot2028116429.png){width="50%" align="left"}

1. Maak een lokale gebruiker in AEM omgeving.

   >[!NOTE]
   > Een lokale gebruiker maken:
   > Ga naar `AEM Home` > `Tools` > `Security` > `Users`
   > Zorg ervoor dat de gebruiker lid is van de groep met gebruikers van formulieren.


1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028117029.png)

   >[!NOTE]
   >
   > * Als u een bericht krijgt waarin u wordt gevraagd om npm bij te werken via de opdracht `npm notice Run npm nstall -g npm@9.6.0` , negeert u het bericht.
   > * Stel geen andere npm bevelen in werking tenzij geïnstrueerd in het werkboek.

1. Voer nu de volgende opdracht uit om een voorbeeld van het formulier te bekijken.

   ```Shell
   npm run live
   ```

   ![](/help/assets/screenshot2028117229.png)

   Nadat de bovenstaande opdracht is uitgevoerd, wacht u op het `webpack compiled` -bericht en wordt u omgeleid naar een AEM aanmeldingspagina.

1. Klik **binnen Teken Lokaal (slechts Taken Admin)** op de AEM login pagina.
1. Voer de referenties in voor de lokale gebruiker die is gemaakt en het formulier wordt weergegeven op een browsertabblad.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser na het uitvoeren van het `npm run live` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.


   ![](/help/assets/screenshot2028115129.png){width="50%" align="left"}


1. Open het bestand `PROJECT\src\site\_variables.scss` in Visual Studio Code. De `$error` -kleur is een kleur van het type RED.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. In browser, leg de vorm voor om de Rode kleur op het **Voornaam** gebied te zien.

   ![](/help/assets/screenshot2028120829.png)

1. Plaats de **$error** kleur aan **#5736eb** en bewaar het dossier.

   ![](/help/assets/screenshot2028120729.png){width="50%" align="left"}

1. Vernieuw de browser en verzend het formulier. De kleur van de foutmelding in het veld Voornaam is dienovereenkomstig gewijzigd.

   ![](/help/assets/screenshot2028121129.png)

1. In de Herinnering van het Bevel, druk **CTRL+C**, ga **Y** in, en druk **ga** sleutel in om het npm proces te eindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.
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

1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om aan **c te navigeren:\ git** omslag

   ```Shell
   cd c:\git
   ```

1. Gebruik de volgende opdracht om het aanpasbare formulier te klonen om te starten:

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

U kunt als volgt het formulier weergeven dat wordt gehost op uw cloudservice-publicatieomgeving:

1. Wijzig de naam van het env_template-bestand in .env-bestand. Om anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen** optie.

   ![](/help/assets/screenshot2028117629.png){width="50%" align="left"}

   ![](/help/assets/screenshot2028117729.png)

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt.

   * **AEM_URL**: Specificeer URL van de wolkendienst publiceert milieu. Bijvoorbeeld: `https://publish-p105303-e986623.adobeaemcloud.com`

   * **AEM_FORM_PATH**: Specificeer de weg van de adaptieve vorm die in de vorige les wordt gecreeerd. Bijvoorbeeld: `/content/forms/af/registration/`

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
   > Als u een leeg scherm in browser na het uitvoeren van het `npm start` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.

   ![](/help/assets/screenshot2028118229.png)

Laten we de uitvoering van regels in deze vorm zonder kop controleren:

1. Selecteer de **Controle de doos om 5% van** optie te ontvangen. De volgende optie voor het toepassen van een creditcard is uitgeschakeld.

   ![](/help/assets/screenshot2028126229.png)

1. Schakel **Controle de doos uit om 5% van** te ontvangen om de creditcardoptie toe te laten.

   ![](/help/assets/screenshot2028126329.png)

We brengen wijzigingen aan in het formulier op de server als een zakelijke gebruiker. Wijzigingen worden dan automatisch doorgevoerd in het formulier zonder kop.

1. Open de AEM Forms-beheerinterface in de browser. Bijvoorbeeld, [ https://author-p105303-e986623.adobeaemcloud.com/ui#/aem/aem/forms.html/content/dam/formsanddocuments ](https://author-p105303-e986623.adobeaemcloud.com/ui%23/aem/aem/forms.html/content/dam/formsanddocuments).

1. Selecteer de **contactus** vorm en klik **uitgeven.** Hiermee opent u het formulier in de editor voor adaptieve formulieren.


1. Selecteer het **aantal van de Telefoon** gebied en klik **uitgeven pictogram (het pictogram van het Potlood)** in de toolbar. Als u niet de pop op toolbar kunt zien, schakelaar om wijze uit te geven door **te klikken geeft** knoop in hoogste recht uit, links naar **Voorproef** knoop.

   ![](/help/assets/screenshot2028119629.png)

1. Wijzig het label in Mobiel nummer. Klik op een lege ruimte in het formulier en de wijzigingen die in het formulier zijn aangebracht, worden opgeslagen.

   ![](/help/assets/screenshot2028119729.png)

Laten we het bijgewerkte formulier publiceren om de wijzigingen in de publicatieomgeving door te geven.

1. In het lusje van de het beheersinterface van AEM Forms, selecteer de registratieformulier, en klik **unpublish**. Als u niet **ziet unpublish** knoop, overslaan aan stap 3 om de veranderingen direct te publiceren.

1. Klik **unpublish**. Klik **Sluiten** in respectieve dialoog.

1. Nadat browser verfrist, selecteer de registratieformulier en klik **Publish**.

1. Klik **Publish**. Klik **dicht** in de respectieve dialoog.

1. Vernieuw de browsertab met de koploze vorm. Het label Telefoonnummer is gewijzigd in Mobiel nummer.

   ![](/help/assets/screenshot2028120529.png)

1. Open het Prompt venster van het Bevel dat wordt gebruikt om **te beginnen reactie-starter-kit-a-headless-vormen** project, druk **CTRL+C**, dan
ga **Y** in en druk Enter sleutel om het npm proces te eindigen. Het is belangrijk om de npm server tegen te houden zodat strijdt het niet met de volgende reeks oefeningen.

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


1. Voor de Herinnering van het Bevel, gebruik het volgende bevel om aan **c te navigeren:\ git** omslag:

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

1. Gebruik het volgende bevel in de vermelde orde om aan de **te navigeren reactie-starter-kit-a-headless-formulieren** omslag en open de code in de Code van Visual Studio:

   ```Shell
   cd react-starter-kit-aem-headless-forms
   
   code .
   ```

   ![](/help/assets/screenshot2028126829.png)

U kunt als volgt het formulier weergeven dat wordt gehost op uw cloudservice-publicatieomgeving:

1. Wijzig de naam van het **env_template** dossier aan **.env** dossier. Om anders te noemen, klik het **env_template** dossier met de rechtermuisknop aan en selecteer **anders noemen**.

   ![](/help/assets/screenshot2028126629.png){width="50%" align="left"}

1. Stel de volgende waarden in voor de variabelen in het .env-bestand. Sla het bestand op nadat u de variabelen hebt bijgewerkt. Gebruik **CTRL + S** schakelaarcombinatie om het dossier te bewaren.

   * **AEM_URL**: Specificeer URL van de wolkendienst publiceert milieu. Bijvoorbeeld, [ https://publish-p105303-e986623.adobeaemcloud.com](https://publish-p105303-e986623.adobeaemcloud.com/)

   * **AEM_FORM_PATH**: Specificeer de weg van de adaptieve vorm die in de vorige les wordt gecreeerd. Bijvoorbeeld: /content/forms/af/registration/

     ![](/help/assets/screenshot2028126929.png)

1. Open het bevelvenster, zorg ervoor u bij de **reactie-starter-kit-a-headless-vormen** folder bent, en stel het volgende bevel in werking:

   ```Shell
   npm install
   ```

   ![](/help/assets/screenshot2028127029.png)

1. Voer in het venster Opdrachtprompt de volgende opdracht uit:

   ```Shell
   npm start
   ```

   ![](/help/assets/screenshot2028127129.png)

   Met de opdracht wordt een lokale ontwikkelingsserver gestart en wordt de formulierdefinitie zonder kop opgehaald van AEM met de Google
Materiële UI-frontendbibliotheek.

   >[!NOTE]
   >
   >Als u een leeg scherm in browser na het uitvoeren van het `npm start` bevel meer dan 3-4 minuten ervaart, verander `localhost` in browser URL in 127.0.0.1 en druk **binnengaan**.

   ![](/help/assets/screenshot2028127229.png)

1. U kunt als volgt de uitvoering van dezelfde bedrijfslogica in deze formulieruitvoering evalueren:

   Selecteer **Controle de doos om 5% van** te ontvangen. De verdere optie **zou u voor het Vorm van de BedrijfsCreditcard van Wij.Financiën willen toepassen?** wordt uitgeschakeld.

   ![](/help/assets/screenshot2028127329.png){width="50%" align="left"}

## Les 6

### Doelstelling

Een ander uiterlijk van de vorm zonder kop maken met behulp van variaties in de materiaalinterface

### Lessencontext

In deze les leert u als front-end ontwikkelaar hoe u een alternatieve representatie van verschillende componenten kunt maken met behulp van materiaalinterface voor het adaptieve formulier dat eerder door de zakelijke gebruiker is gemaakt.

### Uitoefening

Werk de variatie van componenten in het hoofdloze project bij. U kunt als volgt de variant van de materiaalUI-tekstinvoercomponent wijzigen in `OutlinedInput` :

1. Navigeer in Visuele code naar de tekstinvoercomponent door het `index.tsx` -bestand op `src/components/textinput/index.tsx` te openen.

1. Voeg `//` toe aan het begin van coderegel 103. De regel wordt omgezet in een opmerking.

   ```Shell
   //const Cmp = \'outlined\' === appliedCssClassNames ? OutlinedInput: Input;
   ```

1. Voeg het volgende toe op regel 104 om een andere variant van component te gebruiken en het dossier op te slaan. Gebruik **CTRL + S** schakelaarcombinatie om het dossier te bewaren.

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


   Deze wijziging vindt plaats voor eindgebruikers zonder dat de formulierdefinitie wordt gewijzigd op AEM Forms Server en is specifiek voor de headless
betrokken kanaal. Bijvoorbeeld, Webkanaal in dit laboratorium.

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

* [ Aangepaste de kerncomponenten van de Vorm inleiding ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/adaptive-forms/introduction.html?lang=nl-NL)

* [ creeer adaptieve vorm gebruikend kerncomponenten ](https://experienceleague.corp.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/creating-adaptive-form-core-components.html)

* [ stileren van de Update voor kern op component-gebaseerde AF ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-core-components/create-an-adaptive-form-on-forms-cs/using-themes-in-core-components.html?lang=nl-NL)

* [ Hoofdloze adaptieve vormen ](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/overview.html?lang=nl-NL)

* [ Gebruikend Hoofdloze Reageer starterkit ](https://experienceleague.adobe.com/docs/experience-manager-headless-adaptive-forms/using/get-started/create-and-publish-a-headless-form.html?lang=nl-NL)
