---
title: Ontwikkelomgeving instellen voor een as a Cloud Service sandbox van Forms
description: Ontwikkelomgeving instellen voor een as a Cloud Service sandbox van Forms
hide: true
exl-id: befac9ad-d2c4-4705-96fc-f0ea0ef823b8
source-git-commit: 41286ff4303e0f4d404deb113fd59d1499768da5
workflow-type: tm+mt
source-wordcount: '1149'
ht-degree: 0%

---

# Ontwikkelomgeving instellen voor hulpformulieren zonder hoofd op Cloud Service

<span class="preview"> dit is a **WERK IN VOORTGANG** artikel.</span>


Klaar om adaptieve formulieren zonder koptekst te maken en te testen op de Cloud Service? Schakel Forms in voor uw Cloud Service-programma en ga aan de slag.

## Voordat u begint

* Installeer [ Laatste versie van Git ](https://git-scm.com/downloads) op uw lokale machine. Als u aan Git nieuw bent, zie [ Installerend Git ](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git). Met de Git-opslagplaats kunt u de formulieren en aangepaste code die in uw lokale ontwikkelomgeving zijn ontwikkeld, naar de ontwikkelomgeving van uw Cloud Service verzenden.

* Installeer [ Node.js 16.13.0 of later ](https://nodejs.org/en/download/) op uw lokale machine. Als u aan Node.js nieuw bent, zie [ hoe te Node.js ](https://nodejs.dev/en/learn/how-to-install-nodejs) installeren.

* Creeer een programma van AEM as a Cloud Service: Volg stap 1-7 van [ creeer programma ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program) artikel om een programma voor uw organisatie tot stand te brengen.

* Laat [ het Kanaal van de preRelease voor uw programma van de Cloud Service ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/release-notes/prerelease.html?lang=nl-NL&cloud-environments) toe.

## Workflow instellen

Als u Headless adaptive-formulieren wilt inschakelen op uw Forms as a Cloud Service sandbox, schakelt u `Forms - Digital enrolment` -oplossing in voor uw AEM Cloud Service-programma, maakt u een project op basis van Archetype 37 of hoger op uw lokale computer en duwt u deze naar uw Forms as a Cloud Service omgeving. Het volledige proces is:

![ Werkschema aan opstellingsontwikkelomgeving voor een as a Cloud Service Sandbox van Forms ](assets/FORMS-HLAF-SANDBOX-PRODUCTION-ENR.png)

### 1. Forms inschakelen voor uw programma

<table style="table-layout:auto">
<tr>
  <td>
  1. Meld u aan bij <a href="https://experience.adobe.com/" > https://experience.adobe.com/ </a> en selecteer de optie <b> Experience Manager </b> .

  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/cloud-manager-experience-manager.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
  &#x200B;2. Voor de optie <b> Cloud Manager </b> klikt u op <b> Starten. </b> Er wordt een lijst met programma's voor uw organisatie weergegeven.
  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/cloud-manager-experience-manager-launch.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
    &#x200B;3. Tik voor uw programma op het pictogram ... en selecteer de optie <b> Programma bewerken </b> . Er wordt een dialoogvenster weergegeven. 
  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/edit-program.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
    &#x200B;4. Ga in het dialoogvenster Programma bewerken naar het tabblad <b> Oplossingen en invoegtoepassingen </b> , selecteer de optie <b> Forms - Digital Enrollment </b> en tik op <b> Bijwerken </b> . 
  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/program-solution-addons.png">
    </a>
    <br>
  </td>
</tr>
</table>

### 2. Kloonopslagplaats van uw programma naar uw lokale computer

Elk AEM as a Cloud Service-programma heeft een git-opslagplaats. Hiermee kunt u aangepaste code en elementen van de lokale computer uploaden naar de omgeving van de Cloud Service. Tijdens de installatie gebruiken we de Git-opslagplaats om code, sjablonen en andere informatie die betrekking hebben op uw Cloud Service, zonder koptekst, van uw lokale computer te voorzien. Het klonen van de Cloud Service git opslagplaats op uw lokale machine is de eerste stap naar het brengen van aangepaste code en inhoud van uw lokale machine aan Cloud Service.

>[!INFO]
>
> U kunt zich altijd vastleggen op een Git-opslagplaats zonder deze te klonen. Maar het heeft zijn eigen eigenaardigheden. We gebruiken dus de klonen-benadering in dit document.


De gegevensopslagruimte klonen:

<table style="table-layout:fixed">
<tr>
  <td>
  1. Tik in het pijplijnvak van uw programma op <b> Toegang tot repo-info. </b> Er verschijnt een dialoogvenster met informatie over opslagplaats 

  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/git-repo.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
  &#x200B;2. Tik op <b> Wachtwoord genereren </b> en kopieer de URL van de <b> gegevensopslagruimte. </b> 
  </td>
  <td>
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/repository-info.png">
    <br>
  </td>
</tr>
<tr>
  <td>
    &#x200B;3. Open op uw lokale computer de opdrachtregel, maak een map en voer de volgende opdracht uit. Geef vervolgens de gewenste gegevens op voor de bewaarplaats:
    </br>
    <code> git clone [Repository URL] </code> </br></br>
    Bijvoorbeeld: </br> 
    <code> git clone https://git.cloudmanager.adobe.com/stage-aemformsdev/khushwantsingh-p45413-uk89613/ </code>

</br> wanneer gevraagd, krijg <b> Gebruikersnaam </b> en <b> Wachtwoord </b> van het <b> scherm van Info van de Bewaarplaats </b>.
</td>
  <td>
     <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/clone-success.png">
  </td>
</tr>
</table>


### 3. Een project op basis van AEM archetype maken

Het archetype-project is een op maven gebaseerde sjabloon. Het leidt tot een minimaal project dat op beste praktijken wordt gebaseerd om met Headless aanpassings vormen te beginnen. Het omvat ook de kernfuncties voor het aanpassen van formulieren zonder koptekst voor Forms as a Cloud Service. Het is verplicht om het archetype 37 of later gebaseerde project tot stand te brengen en op te stellen.
®®
Afhankelijk van het besturingssysteem voert u de opdracht maven uit om een as a Cloud Service Experience Manager Forms-project te maken. Gebruik archetype versie 37 of hoger. Zie {de documentatie van 0} Archetype [&#128279;](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/developing/archetype/overview.html?lang=nl-NL) om de recentste versie van Archetype te vinden.

+++ Microsoft® Windows

1. Open de bevelherinnering met Administratieve voorrechten (de bevelherinnering van de Looppas of bash shell als beheerder).
1. Voer de onderstaande opdracht uit:

   ```shell
     mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate ^
     -D archetypeGroupId=com.adobe.aem ^
     -D archetypeArtifactId=aem-project-archetype ^
     -D archetypeVersion=37 ^
     -D appTitle=myheadlessform ^
     -D appId=myheadlessform ^
     -D groupId=com.myheadlessform ^
     -D includeFormsenrollment="y" ^
     -D includeFormsheadless="y" 
   ```

™™
* Stel `appTitle` in om de titel en de groepen componenten te definiëren.
* Stel `appId` in om de namen van de componenten, config- en inhoudsmappen en de clientbibliotheek te definiëren.
* Stel `groupId` in om de Maven groupId en het Java™ Source-pakket te definiëren.
* Gebruik de optie `includeFormsenrollment=y` om Forms-specifieke configuraties, -thema&#39;s, -sjablonen, -kerncomponenten en -afhankelijkheden op te nemen die vereist zijn om een adaptieve Forms te maken.
* Gebruik de optie `includeFormsheadless=y` om Forms Core-componenten en afhankelijkheden op te nemen die vereist zijn om de functionaliteit voor Zwaardeloze adaptieve formulieren in te bouwen. Als u deze optie inschakelt, worden de volgende opties opgenomen:\
* **Lege met kerncomponenten** malplaatje met [ kerncomponenten ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=nl-NL).
* A frontend React module, `ui.frontend.react.forms.af`. Hiermee kunt u een adaptieve vorm zonder koptekst weergeven in een reactie-app.

+++®®


+++ Apple macOS of Linux®

1. Open terminal als wortelgebruiker. Hiermee kunt u opdrachten uitvoeren met beheerdersrechten. U kunt ook de opdracht `sudo root` gebruiken nadat u het terminalvenster hebt geopend om opdrachten met beheerdersrechten uit te voeren.
1. Voer de onderstaande opdracht uit:

   ```shell
     mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
     -D archetypeGroupId=com.adobe.aem \
     -D archetypeArtifactId=aem-project-archetype \
     -D archetypeVersion=37 \
     -D appTitle=myheadlessform \
     -D appId=myheadlessform \
     -D groupId=com.myheadlessform \
     -D includeFormsenrollment="y" \
     -D includeFormsheadless="y"  
   ```

™™
* Stel `appTitle` in om de titel en de groepen componenten te definiëren.
* Stel `appId` in om de namen van de Maven ArfactId, de component, config, de inhoudsmap en de clientbibliotheek te definiëren.
* Stel `groupId` in om de Maven groupId en het Java™ Source-pakket te definiëren.
* Gebruik de optie `includeFormsenrollment=y` om Forms-specifieke configuraties, -thema&#39;s, -sjablonen, -kerncomponenten en -afhankelijkheden op te nemen die vereist zijn om een adaptieve Forms te maken.
* Gebruik de optie `includeFormsheadless=y` om Forms Core-componenten en afhankelijkheden op te nemen die vereist zijn om de functionaliteit voor Zwaardeloze adaptieve formulieren in te bouwen. Als u deze optie inschakelt, worden de volgende opties opgenomen:\
* **Lege met kerncomponenten** malplaatje met [ kerncomponenten ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=nl-NL).
* Een frontend reageert module, `ui.frontend.react.forms.af` . Hiermee kunt u een adaptieve vorm zonder koptekst weergeven in een reactie-app.

+++

Als de opdracht met succes is voltooid, wordt een projectmap gemaakt met de naam die in `appID` is opgegeven. Als u bijvoorbeeld `appID` met value `myheadlessform` gebruikt, wordt een map met de naam `myheadlessform` gemaakt. Het bevat het op Archetype gebaseerde project.

### 4. Zet het op Archetype-Gebaseerde project van de AEM aan uw Cloud Service milieu

1. Vervang de inhoud van de it-opslagplaats door inhoud van een op Archtype gebaseerd project.

   >[!VIDEO](https://video.tv.adobe.com/v/3409809/)

1. Open opdrachtprompt, navigeer naar de map Git Repository en voer de onderstaande opdrachten in de vermelde volgorde uit om de vervangen inhoud te uploaden naar de omgeving van uw Cloud Service. U kunt ook een visuele editor gebruiken in plaats van de onderstaande opdrachten om inhoud naar de opslagplaats van de Cloud Service te duwen.

   ```
      git add .
      git commit
      git push origin
   ```

### 5. Voer een ontwikkelingspijplijn voor uw programma uit



<table style="table-layout:auto">
<tr>
  <td>
  1. Meld u aan bij <a href="https://experience.adobe.com/" > https://experience.adobe.com/ </a> en selecteer de optie <b> Experience Manager </b> .

  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/cloud-manager-experience-manager.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
  &#x200B;2. Voor de optie <b> Cloud Manager </b> klikt u op <b> Starten. </b> Er wordt een lijst met programma's voor uw organisatie weergegeven. Open uw programma. 
  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/cloud-manager-experience-manager-launch.png">
    </a>
    <br>
  </td>
</tr>
<tr>
  <td>
    &#x200B;3. Tik voor de pijplijn op het pictogram ... en selecteer de optie <b> Uitvoeren </b> . Tik op <b> Uitvoeren </b> en wacht tot de status van de <b> pijplijn </b> verandert in <b> Voltooid </b> als u wordt gevraagd de pijplijn uit te voeren.  
  </td>
  <td>
    <a href="https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/onboarding/demo-add-on/create-program.html?lang=nl-NL&#create-program">
      <img alt="AEM as a Cloud Service-programma&apos;s" src="assets/run-build-pipeline.png">
    </a>
    <br>
  </td>
</tr>
</table>

Nu is uw omgeving klaar voor gebruik van hulpformulieren zonder koptekst. U kunt definitie JSON van een vorm aan uw milieu van de Cloud Service nu uploaden, een Zwaartepunt creëren adaptieve vorm die op het wordt gebaseerd, en [ gebruiken getForm ](https://opensource.adobe.com/aem-forms-af-runtime/api/#tag/Get-Form-Definition/operation/getForm) en andere rest APIs om de Zwaarteloze adaptieve vorm in uw toepassing of dienst te gebruiken.
