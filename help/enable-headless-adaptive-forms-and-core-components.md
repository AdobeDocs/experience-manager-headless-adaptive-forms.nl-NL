---
title: Hoofdloze adaptieve Forms inschakelen op AEM 6.5 Forms
seo-title: Step-by-Step Guide for enabling Headless Adaptive Forms on AEM 6.5 Forms
description: Leer hoe u adaptieve formulieren zonder hoofd kunt inschakelen op AEM 6.5 Forms met onze stapsgewijze handleiding. In onze zelfstudie wordt u door het proces geleid, zodat u deze krachtige functie eenvoudig kunt integreren in uw website en uw gebruikerservaring kunt verbeteren.
seo-description: Learn how to enable headless adaptive forms on AEM 6.5 Forms with our step-by-step guide. Our tutorial walks you through the process, making it easy to integrate this powerful feature into your website and improve your user experience.
contentOwner: Khushwant Singh
role: Admin
exl-id: c5a7dee1-b177-4461-b9bd-af40ef59ad80
source-git-commit: f489a2ba818db44ccd92df80a177f0e9f3a1bc2c
workflow-type: tm+mt
source-wordcount: '752'
ht-degree: 0%

---

# Hoofdloze adaptieve Forms inschakelen op AEM 6.5 Forms {#enable-headless-adaptive-forms-on-aem-65-forms}

Als u Headless Adaptive Forms wilt inschakelen voor uw AEM 6.5 Forms-omgeving, stelt u een project op basis van Archetype 41 of hoger in en implementeert u dit project in alle auteur- en publicatieinstanties.

Door het AEM Archetype 41 of later gebaseerde project aan uw AEM 6.5 instanties van Forms op te stellen, kunt u de capaciteit verkrijgen om [op Adaptieve Forms gebaseerde Core Components maken](create-a-headless-adaptive-form.md). Deze formulieren worden weergegeven in de JSON-indeling en worden gebruikt als Headful en Headless Adaptive Forms, waardoor u meer flexibiliteit en aanpassingen kunt bieden voor verschillende kanalen, waaronder mobiele apps, webtoepassingen en native apps.

## Vereisten {#prerequisites}

Voordat u Headless Adaptive Forms op AEM 6.5 Forms-omgeving inschakelt,

* [Upgrade naar AEM 6.5 Forms Service Pack 16 (6.5.16.0) of hoger](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/aem-forms-current-service-pack-installation-instructions.html).

* Installeer de nieuwste versie van [Apache Maven](https://maven.apache.org/download.cgi).

* Installeer een teksteditor zonder opmaak. Bijvoorbeeld, de Code van Microsoft Visual Studio.

## Maak en implementeer de nieuwste AEM archetype-project

Een AEM Archetype 41 of [later](https://github.com/adobe/aem-project-archetype) gebaseerd project en stel het aan elk van uw Auteur en Publish instanties op:

1. Meld u aan bij uw computer, waarbij u als beheerder uw AEM 6.5 Forms-exemplaar host en uitvoert.
1. Open de opdrachtprompt of terminal.
1. Voer de volgende opdracht uit om op Archetype 41 gebaseerd project te maken:

   * Microsoft Windows

   ```Shell
      mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate ^
      -D archetypeGroupId=com.adobe.aem ^
      -D archetypeArtifactId=aem-project-archetype ^
      -D archetypeVersion=41 ^
      -D appTitle="My Form" ^
      -D appId="myform" ^
      -D groupId="com.myform" ^
      -D includeFormsenrollment="y" ^
      -D aemVersion="6.5.15" 
   ```

   * Linux of Apple macOS

   ```Shell
      mvn -B org.apache.maven.plugins:maven-archetype-plugin:3.2.1:generate \
      -D archetypeGroupId=com.adobe.aem \
      -D archetypeArtifactId=aem-project-archetype \
      -D archetypeVersion=41 \
      -D appTitle="My Form" \
      -D appId="myform" \
      -D groupId="com.myform" \
      -D includeFormsenrollment="y" \
      -D aemVersion="6.5.15" 
   ```

   Houd rekening met de volgende punten wanneer u de bovenstaande opdracht uitvoert:

   * Werk de opdracht bij om de specifieke waarden voor uw omgeving weer te geven, inclusief appTitle, appId en groupId. Stel ook de waarden voor includeFormsenrollment in op &#39;y&#39;. Als u Forms Portal gebruikt, stelt u de optie _includeExamples=y_ om Forms Portal Core-componenten in uw project op te nemen.

   * Wijzig de &#39;aemVersion&#39; niet van 6.5.15.0 in iets anders.

1. (Alleen voor projecten die zijn gebaseerd op Archetype versie 41) Nadat het project Archetype AEM is gemaakt, schakelt u thema&#39;s in voor op Core Components gebaseerde Adaptive Forms. Thema&#39;s inschakelen:

   1. Open de [Projectmap Archetype AEM]/ui.apps/src/main/content/jcr_root/apps/__appId__/components/adaptiveForm/page/customheaderlibs.html voor bewerking:

   1. Voeg de volgende code toe op regel 21:

      ```XML
      <sly data-sly-use.clientlib="core/wcm/components/commons/v1/templates/clientlib.html"
      data-sly-use.formstructparser="com.adobe.cq.forms.core.components.models.form.FormStructureParser"
      data-sly-test.themeClientLibRef="${formstructparser.themeClientLibRefFromFormContainer}">
      <sly data-sly-test="${themeClientLibRef}" data-sly-call="${clientlib.css @ categories=themeClientLibRef}"/>
      </sly>
      ```

      ![Bovengenoemde code toevoegen op regel 21](/help/assets/code-to-enable-themes.png)

   1. Sla het bestand op en sluit het.

1. Project bijwerken met de nieuwste versie van Forms Core Components:

   1. Open de [Projectmap Archetype AEM]/pom.xml voor bewerken.
   1. Versie instellen van `core.forms.components.version` en `core.forms.components.af.version` tot [nieuwste Forms Core-componenten](https://github.com/adobe/aem-core-forms-components/tree/release/650) versie.

      ![Opname van de nieuwste versie van Forms Core Components](/help/assets/latest-forms-component-version.png)

   1. Sla het bestand op en sluit het.


1. Nadat het project van Archetype van de AEM met succes wordt gecreeerd, bouw het plaatsingspakket voor uw milieu. Het pakket maken:

   1. Navigeer naar de hoofdmap van het project Archetype van uw AEM.


   1. Voer de volgende opdracht uit om het project Archetype AEM voor uw omgeving te maken:

      ```Shell
      mvn clean install
      ```

      ![archetypebuild-success](assets/corecomponent-build-successful.png)


   Nadat het project van Archetype van de AEM met succes wordt gebouwd, wordt een AEM Pakket geproduceerd. U kunt het pakket vinden op [Projectmap Archetype AEM]\all\target\[appid].all-[versie].zip

1. Gebruik de [Pakketbeheer](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=en) om [Projectmap Archetype AEM]\all\target\[appid].all-[versie].zip-pakket op alle instanties Auteur en Publiceren.

>[!NOTE]
>
>
>
>Meld u aan via de volgende URL als u problemen ondervindt bij het openen van het aanmeldingsvenster op een publicatieexemplaar om het pakket te installeren via Package Manager: http://[URL van publicatieserver]:[POORT]/system/console. Hierdoor hebt u toegang tot aanmeldingsgegevens voor de instantie Publiceren, zodat u verder kunt gaan met het installatieproces.


De Core Components zijn ingeschakeld voor uw omgeving. Een lege, op componenten gebaseerde adaptieve formuliersjabloon en Canvas 3.0-thema worden geïmplementeerd in uw omgeving, zodat u [op Adaptieve Forms gebaseerde Core Components maken](create-a-headless-adaptive-form.md).

## Veelgestelde vragen

### Wat zijn kerncomponenten?

De [Kernonderdelen](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html) zijn een reeks gestandaardiseerde WCM-componenten (Web Content Management) voor AEM om de ontwikkelingstijd te versnellen en de onderhoudskosten van uw websites te verlagen.

### Wat zijn alle mogelijkheden toegevoegd aan het toelaten van kerncomponenten?


Wanneer de Adaptive Forms Core Components voor uw omgeving is ingeschakeld, worden een leeg, op Core Components gebaseerd adaptief formulier sjabloon en Canvas 3.0 thema toegevoegd aan uw omgeving. Nadat u Adaptive Forms Core Components voor uw omgeving hebt ingeschakeld, kunt u:

* Creëer op basis van adaptieve Forms Core Components.
* Op kerncomponenten gebaseerde adaptieve formuliersjablonen maken.
* Aangepaste thema&#39;s maken voor adaptieve formuliersjablonen die zijn gebaseerd op kerncomponenten.
* De JSON-representaties van de Serve Core Component gebaseerd op adaptieve formulieren naar kanalen zoals mobiel, web, native apps en services waarvoor een weergave zonder kop nodig is.
