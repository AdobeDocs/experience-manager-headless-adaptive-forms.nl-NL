---
title: Hoofdloze adaptieve Forms inschakelen op AEM Forms as a Cloud Service
seo-title: Step-by-Step Guide for enabling Headless Adaptive Forms on AEM Forms as a Cloud Service
description: Leer hoe u adaptieve formulieren zonder hoofd kunt inschakelen op AEM Forms as a Cloud Service met onze stapsgewijze handleiding. In onze zelfstudie wordt u door het proces geleid, zodat u deze krachtige functie eenvoudig kunt inschakelen voor uw AEM Forms-omgeving.
seo-description: Learn how to enable headless adaptive forms on AEM Forms as a Cloud Service with our step-by-step guide. Our tutorial walks you through the process, making it easy to enable this powerful feature for your AEM Forms environment.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin
level: Beginner, Intermediate
contentOwner: Khushwant Singh
docset: CloudService
hide: true
hidefromtoc: true
exl-id: 7afff771-1296-4162-84c5-c8266b94af2f
source-git-commit: 999c3d092d03d7a82363bc94ce79ceb33bf0df7e
workflow-type: tm+mt
source-wordcount: '914'
ht-degree: 0%

---

# Hoofdloze adaptieve Forms inschakelen op AEM Forms as a Cloud Service {#enable-headless-adaptive-forms-on-aem-forms-cloud-service}

Als u Headless Adaptive Forms inschakelt op AEM Forms as a Cloud Service, kunt u uw Forms zonder koppen maken, publiceren en leveren via uw AEM Forms Cloud Service-instanties naar meerdere kanalen. Voor het gebruik van Headless Adaptive Forms hebt u de omgeving geschikt voor Adaptive Forms Core Components nodig.

## Overwegingen

* Wanneer u een vers as a Cloud Service programma van AEM Forms creeert, [ Koploze Adaptieve Forms wordt reeds toegelaten voor uw milieu&#39;s ](#are-adaptive-forms-core-components-enabled-for-my-environment).

* Als u een ouder as a Cloud Service programma van Forms hebt waar de Componenten van de Kern [ niet ](#enable-components) worden toegelaten, kunt u [ de Aangepaste gebiedsdelen van de Componenten van de Kern van Forms ](#enable-headless-adaptive-forms-for-an-aem-forms-as-a-cloud-service-environment) toevoegen aan uw bewaarplaats van AEM as a Cloud Service en de bewaarplaats opstellen aan uw milieu&#39;s van de Cloud Service om Zwaardeloze Aanpassings Forms toe te laten.

* Als uw bestaand milieu van de Cloud Service optie [ verstrekt om op kern-componenten-Gebaseerde Aangepaste Forms ](create-a-headless-adaptive-form.md) tot stand te brengen, zijn de Zwaardeloze Aanpassings Forms reeds toegelaten voor uw milieu en u kunt op de Component gebaseerde Aangepaste Forms van de Kern als hoofdloze vormen aan kanalen zoals mobiel, Web, inheemse apps, en de diensten dienen die een headless vertegenwoordiging van Aanpassings Forms vereisen.


>[!NOTE]
>
>
> De Adobe verstrekt Aangepaste Forms [ starter uitrusting (React App) ](create-and-publish-a-headless-form.md) om ontwikkelaars te helpen snel met de Zwaardeloze Aanpassings ontwikkeling van Forms beginnen, zonder Zwaardeloze Aanpassings Forms op het as a Cloud Service milieu van AEM Forms toe te laten. U kunt de Zwaardeloze Aanpassings Forms op een as a Cloud Service milieu van Forms later na a [ snelle hands-on met het ontwikkelen van kransloze vormen ](create-and-publish-a-headless-form.md) toelaten.

## Hoofdloze adaptieve Forms inschakelen voor een as a Cloud Service AEM Forms-omgeving

Voer de volgende stappen uit, in de vermelde volgorde, om Headless Adaptive Forms voor een AEM Forms as a Cloud Service omgeving in te schakelen


![](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service.png)


## 1. Clone your AEM Forms as a Cloud Service Git Repository {#clone-git-repository}

1. Login aan [ Cloud Manager ](https://my.cloudmanager.adobe.com/) en selecteer uw organisatie en programma.

1. Navigeer aan de **Pipelines** kaart van uw **pagina van het Overzicht van het Programma**, klik de **Info van de Reactie van de Toegang** knoop om tot uw Bewaarplaats van het Bezit van het Bezit toegang te hebben en te beheren. De pagina bevat de volgende informatie:

   * URL naar de Cloud Manager Git Repository.
   * Referenties van de Git Repository (Gebruikersnaam en Wachtwoord) Gebruikersnaam.

   Klik **produceer Wachtwoord** om het wachtwoord te bekijken of te produceren.

1. Open terminal of bevelherinnering op uw lokale computer en stel het volgende bevel in werking:

   ```Shell
   git clone [Git Repository URL]
   ```

   Geef de gegevens op wanneer u hierom wordt gevraagd. De opslagplaats is gekloond op uw lokale computer.


## 2. Voeg adaptieve Forms Core Components-afhankelijkheden toe aan uw Git Repository {#add-adaptive-forms-core-components-dependencies}

1. Open de map Git Repository in een tekstcode-editor zonder opmaak. Bijvoorbeeld, de Code van VS.
1. Open het `[AEM Repository Folder]\pom.xml` -bestand om het te bewerken.
1. Vervang versies van `core.forms.components.version`, `core.forms.components.af.version` en `core.wcm.components.version` componenten met versies die in [ worden gespecificeerd kerncomponentendocumentatie ](https://github.com/adobe/aem-core-forms-components). Als de component niet bestaat, voegt u deze componenten toe.

   ```XML
   <!-- Replace the version with the latest released version at https://github.com/adobe/aem-core-forms-components/tags -->
   
   <properties>
       <core.forms.components.version>2.0.14</core.formscomponents.version>
       <core.forms.components.af.version>2.0.14</core.forms.components.af.version>  
       <core.wcm.components.version>2.21.2</core.wcmcomponents.version>
   </properties>
   ```

   ![ de recentste versie van de Verwijzing van de Componenten van de Kern van Forms ](/help/assets/latest-forms-component-version.png)

1. Voeg in de sectie Afhankelijkheden van het `[AEM Repository Folder]\pom.xml` -bestand de volgende afhankelijkheden toe en sla het bestand op.

   ```XML
       <!-- WCM Core Component Examples Dependencies -->
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.apps</artifactId>
               <type>zip</type>
               <version>${core.wcm.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.content</artifactId>
               <type>zip</type>
               <version>${core.wcm.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.config</artifactId>
               <version>${core.wcm.components.version}</version>
               <type>zip</type>
           </dependency>    
           <!-- End of WCM Core Component Examples Dependencies -->
           <!-- Forms Core Component Dependencies -->
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-core</artifactId>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-apps</artifactId>
               <version>${core.forms.components.version}</version>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-core</artifactId>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-apps</artifactId>
               <version>${core.forms.components.version}</version>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-apps</artifactId>
               <type>zip</type>
               <version>${core.forms.components.version}</version>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-content</artifactId>
               <type>zip</type>
               <version>${core.forms.components.version}</version>
           </dependency>
   <!-- End of AEM Forms Core Component Dependencies -->
   ```

1. Open het `[AEM Repository Folder]/all/pom.xml` -bestand om het te bewerken. Voeg de volgende afhankelijkheden toe aan de sectie `<embeddeds>` en sla het bestand op.

   ```XML
   <!-- WCM Core Component Examples Dependencies -->
   
   <!-- inside plugin config of filevault-package-maven-plugin -->  
   <!-- embed wcm core components examples artifacts -->
   
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.content</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.cq</groupId>
       <artifactId>core.wcm.components.examples.ui.config</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <!-- embed forms core components artifacts -->
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/application/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-core</artifactId>
       <target>/apps/${appId}-vendor-packages/application/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-examples-apps</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   <embedded>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-examples-content</artifactId>
       <type>zip</type>
       <target>/apps/${appId}-vendor-packages/content/install</target>
   </embedded>
   ```

   >[!NOTE]
   >
   >
   >  Vervang `${appId}` door uw appId.
   >
   >  Zoek in het `[AEM Repository Folder]/all/pom.xml` -bestand naar de term `-packages/application/install` om de term `${appId}` te zoeken. De tekst voor de term `-packages/application/install` is de `${appId}` . De volgende code, `myheadlessform` is bijvoorbeeld `${appId}` .
   >
   >   ```
   >             <embedded>
   >                     <groupId>com.myheadlessform</groupId>
   >                     <artifactId>myheadlessform.ui.apps<artifactId>
   >                     <type>zip</type>
   >                   <target>/apps/myheadlessform-packages/application install</target>
   >             </embedded>
   >   ```

1. Voeg in de sectie `<dependencies>` van het `[AEM Repository Folder]/all/pom.xml` -bestand de volgende afhankelijkheden toe en sla het bestand op:

   ```XML
           <!-- Other existing dependencies -->
           <!-- wcm core components examples dependencies -->
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.apps</artifactId>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.config</artifactId>
               <type>zip</type>
               </dependency>
           <dependency>
               <groupId>com.adobe.cq</groupId>
               <artifactId>core.wcm.components.examples.ui.content</artifactId>
               <type>zip</type>
           </dependency>
               <!-- forms core components dependencies -->
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-af-apps</artifactId>
               <type>zip</type>
           </dependency>
           <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-apps</artifactId>
               <type>zip</type>
           </dependency>
               <dependency>
               <groupId>com.adobe.aem</groupId>
               <artifactId>core-forms-components-examples-content</artifactId>
               <type>zip</type>
           </dependency>
   ```

1. Open de `[AEM Repository Folder]/ui.apps/pom.xml` voor bewerking. Voeg de `af-core bundle` afhankelijkheid toe en sla het bestand op.

   ```XML
       <dependency>
       <groupId>com.adobe.aem</groupId>
       <artifactId>core-forms-components-af-core</artifactId>
       </dependency>
   ```

   >[!NOTE]
   >
   >Zorg ervoor dat de volgende Adaptive Forms Core Components-artefacten niet in uw project zijn opgenomen.
   >
   > `<dependency>`
   >
   >   `<groupId>com.adobe.aem</groupId>`
   >   `<artifactId>core-forms-components-apps</artifactId>`
   >
   > `</dependency>`
   >
   > en
   >
   > `<dependency>`
   >
   >   `<groupId>com.adobe.aem</groupId>`
   >   `<artifactId>core-forms-components-core</artifactId>`
   >
   > `</dependency>`


1. Sla het bestand op en sluit het.

## 3. Werk het project bij met de nieuwste versie van Forms Core Components:

1. Open de [ AEM Archetype Omslag van het Project ] /pom.xml voor het uitgeven.


1. Sla het bestand op en sluit het.

## 4. Leg de updates vast aan uw Git Repository en voer pijpleiding uit om de repository te implementeren {#Commit-the-updates-to-your-git-repository}

1. U kunt als volgt code toewijzen aan uw Git Repository:
   1. Open de terminal of opdrachtprompt.
   1. Navigeer naar uw `[AEM Repository Folder]` en voer de volgende opdrachten in de vermelde volgorde uit

      ```Shell
      git add pom.xml
      git add all/pom.xml
      git add ui.apps/pom.xml
      git commit -m "Added dependencies for Adaptive Forms Core Components"
      git push origin
      ```

1. Nadat de dossiers aan de Bewaarplaats van de Bewaarplaats van het Git worden geëngageerd, [ stel de pijpleiding ](https://experienceleague.adobe.com/docs/experience-manager-cloud-manager/using/how-to-use/deploying-code.html) in werking.

   Nadat de pijpleidingslooppas succesvol is, worden de Adaptieve Componenten van de Kern van Forms toegelaten voor het overeenkomstige milieu. Bovendien worden een Adaptive Forms (Core Components)-sjabloon en een Canvas 3.0-thema toegevoegd aan uw Forms as a Cloud Service omgeving, zodat u opties kunt kiezen om de op Core Components gebaseerde Adaptive Forms aan te passen en te maken.


## Veelgestelde vragen {#faq}

### Wat zijn kerncomponenten? {#core-components}

De [ Componenten van de Kern ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) zijn een reeks gestandaardiseerde componenten van het Beheer van de Inhoud van het Web (WCM) voor AEM om ontwikkelingstijd te versnellen en onderhoudskosten van uw websites te drukken.

### Welke mogelijkheden worden toegevoegd aan het toelaten van kerncomponenten? {#core-components-capabilities}

Wanneer de Adaptive Forms Core Components voor uw omgeving is ingeschakeld, worden een leeg, op Core Components gebaseerd adaptief formulier sjabloon en Canvas 3.0 thema toegevoegd aan uw omgeving. Nadat u Adaptive Forms Core Components voor uw omgeving hebt ingeschakeld, kunt u:

* Creëer op basis van adaptieve Forms Core Components.
* Op kerncomponenten gebaseerde adaptieve formuliersjablonen maken.
* Aangepaste thema&#39;s maken voor adaptieve formuliersjablonen die zijn gebaseerd op kerncomponenten.
* De JSON-representaties van de Serve Core Component gebaseerd op adaptieve formulieren naar kanalen zoals mobiel, web, native apps en services waarvoor een weergave zonder kop nodig is.

### Zijn Adaptive Forms Core Components ingeschakeld voor mijn omgeving? {#enable-components}

Om te controleren of Adaptive Forms Core Components geschikt zijn voor uw omgeving:

1. [ Kloon uw as a Cloud Service bewaarplaats van AEM Forms ](#1-clone-your-aem-forms-as-a-cloud-service-git-repository).

1. Open het `[AEM Repository Folder]/all/pom.xml` -bestand van de AEM Forms Cloud Service Git Repository.

1. Zoek naar de volgende gebiedsdelen:

   * core-forms-components-af-core
   * core-forms-components-core
   * core-forms-components-apps
   * core-forms-components-af-apps
   * core-forms-components-examples-apps
   * core-forms-components-examples-content


   ![ bepaal de plaats van het kern-vormen-componenten-af-kern artefact in all/pom.xml ](/help/assets/enable-headless-adaptive-forms-on-aem-forms-cloud-service-locate-core-af-artifact.png)

   Als de afhankelijkheden bestaan, worden Adaptive Forms Core Components ingeschakeld voor uw omgeving.
