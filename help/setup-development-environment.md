---
title: Ontwikkelomgeving instellen voor AEM adaptieve hoofdvormen
description: Ontwikkelomgeving instellen voor AEM adaptieve hoofdvormen
hide: true
exl-id: fd92f057-1217-42f8-a454-1bc7e3827e01
source-git-commit: 41286ff4303e0f4d404deb113fd59d1499768da5
workflow-type: tm+mt
source-wordcount: '758'
ht-degree: 1%

---


# Een lokale ontwikkelomgeving instellen {#headless-adaptive-forms-setup-development-environment}

U kunt een lokale ontwikkelomgeving instellen om adaptieve formulieren zonder koptekst te maken en te testen op uw lokale computer. De ontwikkelomgeving bestaat uit AEM SDK en AEM Forms Feature Archive die op AEM SDK zijn geïnstalleerd.
<!--
 After a Headless adaptive form or related assets are ready on the local development environment, you can deploy the Headless adaptive form application to your publishing environment. -- >

You require knowledge to build application using react, Git, and Maven to use Headless adaptive forms.

<!-- 

### Download the latest version of AEM as a Cloud Service SDK or Forms feature archive (AEM Forms add-on) from Software Distribution {#software-distribution}

To download the supported version of Adobe Experience Manager as a Cloud Service SDK or Forms feature archive (AEM Forms add-on):

1. Log in to [Software Distribution](https://experience.adobe.com/#/downloads) portal with your Adobe ID.

    >[!NOTE]
    >
    > Your Adobe Organization must be provisioned for AEM as a Cloud Service to download the AEM as a Cloud Service SDK.

1. Navigate to the **[!UICONTROL AEM as a Cloud Service]** tab.
1. Sort by published date in descending order.
1. Click on the latest Adobe Experience Manager as a Cloud Service SDK or Forms feature archive (AEM Forms add-on).
1. Review and accept the EULA. Tap the **[!UICONTROL Download]** button. -->

## Systeemvereisten {#headless-adaptive-forms-system-requirements}

Als u AEM SDK wilt installeren, moet uw lokale computer aan de volgende minimale vereisten voldoen:

* [Java Development Kit 11](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html?1_group.propertyvalues.property=.%2Fjcr%3Acontent%2Fmetadata%2Fdc%3AsoftwareType&amp;1_group.propertyvalues.operation=equals&amp;1_group.propertyvalues.0_values=software-type%3Atooling&amp;fulltext=Oracle%7E+JDK%7E+11%7E&amp;orderby=%40jcr%3Acontent%2 Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=14)
* [Laatste release van Git](https://git-scm.com/downloads). Als u nog geen ervaring hebt met Git, raadpleegt u [Git installeren](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
* [Node.js 16.13.0 of hoger](https://nodejs.org/en/download/). Als u nog geen ervaring hebt met Node.js, raadpleegt u [Node.js installeren](https://nodejs.dev/en/learn/how-to-install-nodejs).
* [Maven 3.6 of hoger](https://maven.apache.org/download.cgi). Als u nog geen ervaring hebt met Maven, zie [Apache Maven installeren](https://maven.apache.org/install.html).

## Ontwikkelomgeving instellen {#headless-adaptive-forms-procedure-to-setup-development-environment}

Een nieuwe lokale ontwikkelomgeving instellen en deze gebruiken voor het ontwikkelen en testen van hulpformulieren zonder hoofd:

1. [AEM as a Cloud Service SDK instellen](#setup-author-instance).
1. [AEM Forms-archief (invoegtoepassing AEM Forms Cloud Service) toevoegen aan AEM SDK](#add-forms-archive).

<!--

1. (Optional) [Add Forms-specific users to your local Author instance](#configure-users-and-permissions).
1. (Optional) Install [Adaptive forms builder extension for Microsoft Visual Studio Code](#microsoft-visual-studio-code-extension-for-headless-adaptive-forms). 

-->

### 1. Instellen AEM as a Cloud Service SDK {#setup-author-instance}

AEM as a Cloud Service SDK (AEM SDK) biedt ontwikkelaars een lokale ervaring om adaptieve formulieren zonder koppen te maken en te testen. U kunt de AEM as a Cloud Service SDK gebruiken om adaptieve formulieren zonder koptekst te maken en voor te vertonen, zodat u de meeste validaties die betrekking hebben op ontwikkeling lokaal kunt uitvoeren. Een instantie van een lokale auteur instellen:

1. [Downloaden](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html) de meest recente [!DNL Adobe Experience Manager] as a Cloud Service SDK. Met de kolom Datum gepubliceerd kunt u de nieuwste SDK sorteren en gemakkelijk vinden.
De indeling is .zip. De ondersteunde versie is aem-sdk-2022.7.8085.20220725T140323Z-220700.zip en hoger.

   ![AEM Cloud Service SDK downloaden van Software Distribution Portal](assets/software-distribution.png)


1. Pak het gedownloade .zip-bestand uit naar een map op uw lokale computer.
1. Maak een map op uw lokale computer die fungeert als installatielocatie voor de auteurinstantie. Bijvoorbeeld, `~/aem-sdk/author`.
1. Kopieer het .jar-bestand uit geëxtraheerde SDK-bestanden naar de installatielocatie en wijzig de naam van het bestand in `aem-author-p4502.jar`. De `p4502` tekenreeks in de bestandsnaam het poortnummer dat moet worden gebruikt. U kunt ook een ander poortnummer opgeven.

   >[!NOTE]
   >
   > Dubbelklik niet op het .jar-bestand om het te starten. Het leidt tot een [fout](https://experienceleague.adobe.com/docs/experience-manager-learn/cloud-service/local-development-environment-set-up/aem-runtime.html?lang=en#troubleshooting-double-click).

1. Open de opdrachtprompt:
   * In Windows kunt u de opdracht **Uitvoeren als beheerder** optie om bevelherinnering op opgeheven wijze te openen.
   * In Linux, zorg ervoor u het eindvenster als wortelgebruiker opent.

1. Navigeer naar de installatielocatie die het gekopieerde .jar-bestand bevat en voer de volgende opdracht uit:

   `java -jar aem-author-p4502.jar -r prerelease`

   ![AEM Cloud Service SDK downloaden van Software Distribution Portal](assets/install-sdk.png)

   * De `-r prerelease` switch schakelt de functies in die alleen beschikbaar zijn in het kader van de prerelease- en beperkte releaseprogramma&#39;s.
   * U kunt `admin` als gebruikersnaam en wachtwoord voor lokale ontwikkeling om de cognitieve belasting te verminderen.

   Nadat AEM begint, opent de login pagina in Webbrowser. U kunt ook de aanmeldingspagina voor AEM SDK-instantie openen op het adres `http://localhost:<port>` in uw webbrowser. Bijvoorbeeld: [http://localhost:4502](http://localhost:4502).

1. Meld u aan bij de instantie Auteur. Tik op de knop ![help](/help/assets/Help-icon.svg) tikken op Info over Adobe Experience Manager en controleren of het versienummer de postfix van PRERELEASE bevat.

   ![help](/help/assets/prerelease.png)

Als u de PRERELEASE-postfix niet ziet, stopt u de server en verwijdert u de `[AEM SDK installation]/crx-quickstart folder`en start het AEM SDK .jar-bestand opnieuw met `-r prerelease` switch. Zie voor meer opties [Problemen oplossen](/help/troubleshooting.md).

### 2. Voeg AEM Forms-archief (invoegtoepassing AEM Forms Cloud Service) toe aan AEM SDK {#add-forms-archive}

Het as a Cloud Service functiearchief van AEM Forms (invoegtoepassing AEM Forms Cloud Service) biedt hulpprogramma&#39;s om adaptieve formulieren zonder koptekst te maken in een lokale ontwikkelomgeving. Het functiearchief installeren:

1. Download en extraheer de nieuwste [!DNL AEM Forms] functiearchief (AEM Forms-invoegtoepassing) van [Softwaredistributie](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?fulltext=AEM*+Forms*+add*+on*&amp;orderby=%40jcr%3Acontent%2Fjcr%3AlastModified&amp;orderby.sort=desc&amp;layout=list&amp;p.offset=0&amp;p.limit=20). Met de kolom Datum gepubliceerd kunt u de nieuwste SDK sorteren en gemakkelijk vinden. De ondersteunde versie is aem-forms-addon-2022.07.06.02-220600 en hoger.

1. Navigeer naar de map crx-quickstart/install. Als de map niet bestaat, maakt u deze.
1. Stop uw AEM SDK-instantie. U kunt uw opdrachtpromptvenster beëindigen waarop AEM SDK-instantie wordt uitgevoerd om AEM te stoppen.
1. De [!DNL AEM Forms] add-on functiearchief van bestand, `aem-forms-addon-<version>.far`, uitgepakt in stap 1 naar de installatiemap.
1. Gebruik de volgende opdracht om de AEM SDK-instantie opnieuw te starten:

   `java -jar aem-author-p4502.jar -r prerelease`

<!-- 

### 3. (Optional) Configure users and permissions {#configure-users-and-permissions}

Create seperate user accounts for Form Developer, Form Practitioner, and end users. These account help you test Headless adaptive forms for various types of users. To create a user account and add roles to the account:

1. Login to your AEM SDK instance.
1. Go to Tools > Security > Users and tap Create. The Create New User wizard opens.
1. In the details tab, specify an ID and Password. All other fields are optional. It is recommended to provide name and an email address.
1. In the Groups tab, search and select user-groups for a user depending on their role. The table below lists all types of users and pre-defined groups for each type of forms users based on their role:
  
    | User Type | AEM Group |
    |---|---|
    | Form developer | [!DNL forms-users] (AEM Forms Users), [!DNL template-authors], [!DNL workflow-users], [!DNL workflow-editors], and [!DNL fdm-authors]  |
    | Customer Experience Lead or UX Designer| [!DNL forms-users], [!DNL template-authors]|
    | AEM administrator | [!DNL aem-administrators], [!DNL fd-administrators] |
    | End user| When a user must log in to view and submit an Adaptive Form, add such users to [!DNL forms-users] group. </br> When no user authentication is required to access Adaptive Forms, do not assign any group to such users.|

<!-- ### 4. (Optional) Install Visual Studio Code extension for Headless adaptive forms {#microsoft-visual-studio-code-extension-for-headless-adaptive-forms}

You can use any IDE for developing Headless adaptive forms. Adobe provides an extension for Microsoft&reg;reg; Visual Studio Code to make it easier for you to navigate structure and develop Headless adaptive forms. The extension adds adaptive forms related IntelliSense capabilities and helps auto-complete Headless adaptive forms JSON syntax. It also adds a panel, titled Forms Tree, to help navigate structure of Headless adaptive form. To use the extension: 

1. Ensure [Microsoft Visual Studio Code 1.62.0 or later](https://code.visualstudio.com/docs/supporting/FAQ#_how-do-i-find-the-version) is installed. If you have an older version or no version installed, download the latest version from [Microsoft Website](https://code.visualstudio.com/docs/setup/setup-overview)
   >[!NOTE]
   >
   >
   > To use Visual Studio from command line on macOS, see [Launching from the command line](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).

1. Download the [Adaptive forms builder extension](/help/assets/adaptive-form-builder-0.12.0.vsix).

1. Navigate the directory containing the *adaptive-form-builder-[version].vsix* file.

1. Run the following command or see [Install from a VSIX](https://code.visualstudio.com/docs/editor/extension-marketplace#_install-from-a-vsix) article for detailed instructions to install a Visual Studio Code extension from a VSIX file:

    `code -–install-extension adaptive-form-builder-[version].vsix`

    </br> Replace the [version] with actual version of the extension. For example, `code -–install-extension adaptive-form-builder-0.12.0.vsix`

    </br> 

    ![Installing extension](/help/assets/install-extension.png)

<!-- ## Create and setup a react app

Adaptive forms renderer component is a react based component. It requires a react app to run and render a Headless adaptive form. To create and setup react app:

1. Open terminal in Visual Studio code and run the following command to create a react app and installs all related dependencies:

    ```shell
    npx create-react-app [react-app-name] --scripts-version 4.0.3 --template typescript
    ```

    Where [react-app-name] represents name of the project, script version is 4.0.3, and template of type typescript. For example, the following command creates a react app named *headless-forms-demo*.

    ```shell
    npx create-react-app headless-forms-demo --scripts-version 4.0.3 --template typescript
    ```

    It may take some time to create the react app and install all the dependencies. The command creates an empty react app with latest version of react and react-dom dependencies. It does not have any artifacts related to adaptive forms renderer component.

1. Adaptive forms renderer component is based on react spectrum and requires react 16.0.0 and react-dom 16.0.0. To install react 16.0.0 and related dependencies:
    1. Open the Visual Studio code terminal Window or command prompt.
    1. Navigate to the directory of react project.  
    1. Run the following command:

        ```shell
        npm install --save react@16.0.0 react-dom@16.14.0 -force
        ```

1. Run the following command to install adaptive forms renderer component related dependencies:

    ```shell
    npm i --save @aemforms/forms-super-component @aemforms/forms-react-core-components @aemforms/forms-super-component @adobe/react-spectrum @react/react-spectrum
    ```

<!-- 1. Install dependencies for adaptive forms renderer component. Packages for these dependencies are available in Adobe Artifactory. To authenticate with Adobe Artifactory and install dependencies for adaptive forms renderer component:

    1. Create environment variables ARTIFACTORY_USER and ARTIFACTORY_API_TOKEN. The ARTIFACTORY_USER stores Adobe LDAP username and ARTIFACTORY_API_TOKEN stores your [Adobe Artifactory token](https://wiki.corp.adobe.com/display/Artifactory/API+Keys)

    1. Run the following command to set NPM_TOKEN and NPM_EMAIL tokens:

        ```shell

        auth=$(curl -s -u${ARTIFACTORY_USER}:${ARTIFACTORY_API_TOKEN} https://artifactory.corp.adobe.com/artifactory/api/npm/auth)
        export NPM_TOKEN=$(echo "${auth}" | grep "_auth" | awk -F " " '{ print $3 }')
        export NPM_EMAIL=$(echo "${auth}" | grep "email" | awk -F " " '{ print $3 }')
        ```

        These tokens are required to communicated with Adobe Artifactory.

    1. Create a .npmrc file in the react project.

        ![.npmrc file](/help/assets/npmrc.png)

    1. Add the following code to the file:

        ```shell
        @aemforms:registry=https://artifactory.corp.adobe.com/artifactory/api/npm/npm-aem-release/
        @react:registry=https://artifactory.corp.adobe.com/artifactory/api/npm/npm-react-release/
        @quarry:registry=https://artifactory.corp.adobe.com/artifactory/api/npm/npm-adobe-release-local/
        //artifactory.corp.adobe.com/artifactory/api/npm/npm-adobe-release-loca/:_auth=${NPM_TOKEN}
        //artifactory.corp.adobe.com/artifactory/api/npm/npm-aem-release/:_auth=${NPM_TOKEN}
        //artifactory.corp.adobe.com/artifactory/api/npm/npm-react-release/:_auth=${NPM_TOKEN}
        _auth=${NPM_TOKEN}
        email=${NPM_EMAIL}
        always-auth=true
        ```

        It defines the antifactory repositories to use for Headless adaptive forms, react, and quarry related scope.
    1. Run the following command to install adaptive forms renderer component related dependencies:

    ```shell
    npm i --save @aemforms/crispr-react-bindings @aemforms/crispr-react-core-components @adobe/react-spectrum @react/react-spectrum
    ```
 
-->
Uw lokale omgeving is klaar. U kunt doorgaan met het maken van een hoofdloos adaptief formulier.
