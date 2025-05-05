---
title: Hoofdloze adaptieve Forms inschakelen op AEM 6.5 Forms
seo-title: Step-by-Step Guide for enabling Headless Adaptive Forms on AEM 6.5 Forms
description: Leer hoe u adaptieve formulieren zonder hoofd kunt inschakelen op AEM 6.5 Forms met onze stapsgewijze handleiding. In onze zelfstudie wordt u door het proces geleid, zodat u deze krachtige functie eenvoudig kunt integreren in uw website en uw gebruikerservaring kunt verbeteren.
seo-description: Learn how to enable headless adaptive forms on AEM 6.5 Forms with our step-by-step guide. Our tutorial walks you through the process, making it easy to integrate this powerful feature into your website and improve your user experience.
contentOwner: Khushwant Singh
role: Admin
exl-id: e1a5e7e0-d445-4cca-b8d7-693d9531f075
source-git-commit: 999c3d092d03d7a82363bc94ce79ceb33bf0df7e
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 0%

---

# Hoofdloze adaptieve Forms inschakelen op AEM 6.5 Forms {#enable-headless-adaptive-forms-on-aem-65-forms}

Als u Headless Adaptive Forms wilt inschakelen voor uw AEM 6.5 Forms-omgeving, stelt u een project op basis van Archetype 41 of hoger in en implementeert u dit project in al uw Auteur- en Publish-instanties.

Door het AEM Archetype 41 op te stellen of later gebaseerd project aan uw AEM 6.5 instanties van Forms, krijgt u de capaciteit om [ de Componenten van de Kern te creëren die Aangepaste Forms ](create-a-headless-adaptive-form.md) worden gebaseerd. Deze formulieren worden weergegeven in de JSON-indeling en worden gebruikt als Headful en Headless Adaptive Forms, waardoor u meer flexibiliteit en aanpassingen kunt bieden voor verschillende kanalen, waaronder mobiele apps, webtoepassingen en native apps.

## Vereisten {#prerequisites}

Voordat u Headless Adaptive Forms op AEM 6.5 Forms-omgeving inschakelt,

* [ Verbetering aan AEM 6.5 Forms Service Pack 16 (6.5.16.0) of later ](https://experienceleague.adobe.com/docs/experience-manager-65/release-notes/aem-forms-current-service-pack-installation-instructions.html?lang=nl-NL).

* Installeer de recentste versie van [ Apache Maven ](https://maven.apache.org/download.cgi).

* Installeer een teksteditor zonder opmaak. Bijvoorbeeld, de Code van Microsoft Visual Studio.

## Maak en implementeer de nieuwste AEM archetype-project

Om een AEM Archetype 41 tot stand te brengen of [ later ](https://github.com/adobe/aem-project-archetype) gebaseerd project en het op elk van uw Instanties van de Auteur en van Publish op te stellen:

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

   * Werk de opdracht bij om de specifieke waarden voor uw omgeving weer te geven, inclusief appTitle, appId en groupId. Stel ook de waarden voor includeFormsenrollment in op &#39;y&#39;. Als u het Portaal van Forms gebruikt, plaats _includeExamples=y_ optie om de Componenten van de Kern van Forms Portal in uw project te omvatten.

   * Wijzig de &#39;aemVersion&#39; niet van 6.5.15.0 in iets anders.

1. (Alleen voor projecten die zijn gebaseerd op Archetype versie 41) Nadat het project Archetype AEM is gemaakt, schakelt u thema&#39;s in voor op Core Components gebaseerde Adaptive Forms. Thema&#39;s inschakelen:

   1. Open de [ AEM Archetype Omslag van het Project ] /ui.apps/src/main/content/jcr_root/apps/__appId__ /components/adaptiveForm/page/customheaderlibs.html voor het uitgeven:

   1. Voeg de volgende code toe op regel 21:

      ```XML
      <sly data-sly-use.clientlib="core/wcm/components/commons/v1/templates/clientlib.html"
      data-sly-use.formstructparser="com.adobe.cq.forms.core.components.models.form.FormStructureParser"
      data-sly-test.themeClientLibRef="${formstructparser.themeClientLibRefFromFormContainer}">
      <sly data-sly-test="${themeClientLibRef}" data-sly-call="${clientlib.css @ categories=themeClientLibRef}"/>
      </sly>
      ```

      ![ voeg bovengenoemde code op lijn 21 toe ](/help/assets/code-to-enable-themes.png)

   1. Sla het bestand op en sluit het.

1. Project bijwerken met de nieuwste versie van Forms Core Components:

   1. Open de [ AEM Archetype Omslag van het Project ] /pom.xml voor het uitgeven.
   1. Plaats versie van `core.forms.components.version` en `core.forms.components.af.version` aan [ recentste versie van de Componenten van de Kern van Forms ](https://github.com/adobe/aem-core-forms-components/tree/release/650).

      ![ de recentste versie van de Verwijzing van de Componenten van de Kern van Forms ](/help/assets/latest-forms-component-version.png)

   1. Sla het bestand op en sluit het.


1. Nadat het project van Archetype van de AEM met succes wordt gecreeerd, bouw het plaatsingspakket voor uw milieu. Het pakket maken:

   1. Navigeer naar de hoofdmap van het project Archetype van uw AEM.


   1. Voer de volgende opdracht uit om het project Archetype AEM voor uw omgeving te maken:

      ```Shell
      mvn clean install
      ```

      ![ archetypebuild-success ](assets/corecomponent-build-successful.png)


   Nadat het project van Archetype van de AEM met succes wordt gebouwd, wordt een AEM Pakket geproduceerd. U kunt het pakket bij [ AEM Archetype de Omslag van het Project ] \all\target\ [appid].all- [ versie ] .zip vinden

1. Gebruik de [ Manager van het Pakket ](https://experienceleague.adobe.com/docs/experience-manager-65/administering/contentmanagement/package-manager.html?lang=nl-NL) om het [ AEM Archetype Omslag van het Project ] \all\target\[appid].all- [ versie ] .zip pakket op alle Instanties van Auteur en van Publish op te stellen.

>[!NOTE]
>
>
>
>In het geval dat u moeilijkheden tegenkomt die tot de login dialoog op publiceren instantie toegang hebben om het pakket door de Manager van het Pakket te installeren, probeer het programma openen door volgende URL: http://[ Server URL van Publish ]:[ HAVEN ]/systeem/console. Hierdoor hebt u toegang tot aanmelding bij een Publish-instantie, zodat u verder kunt gaan met het installatieproces.


De Core Components zijn ingeschakeld voor uw omgeving. Een lege die Componenten van de Kern op het Adaptieve malplaatje van de Vorm en het thema van Canvas 3.0 worden opgesteld aan uw milieu, toelatend u om [ tot de Componenten van de Kern te leiden die Adaptieve Forms ](create-a-headless-adaptive-form.md) worden gebaseerd.

## Veelgestelde vragen

### Wat zijn kerncomponenten?

De [ Componenten van de Kern ](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html?lang=nl-NL) zijn een reeks gestandaardiseerde componenten van het Beheer van de Inhoud van het Web (WCM) voor AEM om ontwikkelingstijd te versnellen en onderhoudskosten van uw websites te drukken.

### Wat zijn alle mogelijkheden toegevoegd aan het toelaten van kerncomponenten?


Wanneer de Adaptive Forms Core Components voor uw omgeving is ingeschakeld, worden een leeg, op Core Components gebaseerd adaptief formulier sjabloon en Canvas 3.0 thema toegevoegd aan uw omgeving. Nadat u Adaptive Forms Core Components voor uw omgeving hebt ingeschakeld, kunt u:

* Creëer op basis van adaptieve Forms Core Components.
* Op kerncomponenten gebaseerde adaptieve formuliersjablonen maken.
* Aangepaste thema&#39;s maken voor adaptieve formuliersjablonen die zijn gebaseerd op kerncomponenten.
* De JSON-representaties van de Serve Core Component gebaseerd op adaptieve formulieren naar kanalen zoals mobiel, web, native apps en services waarvoor een weergave zonder kop nodig is.
