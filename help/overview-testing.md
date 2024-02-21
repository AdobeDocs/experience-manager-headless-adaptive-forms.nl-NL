---
title: Overzicht van AEM hulpformulieren zonder koptekst
description: AEM Forms Headless Adaptive Forms biedt een snelle en efficiënte manier om formulieren te maken voor verschillende platformen, zoals headless of Headful CMS, React-toepassingen, Single Page Applications (SPA), Web Apps, Mobile apps, Amazon Alexa, Google Assistant, WhatsApp en meer. Met Headless Adaptive Forms kunt u het proces van het samenstellen van formulieren stroomlijnen, waardoor het eenvoudiger wordt om gegevens van uw gebruikers te verzamelen op verschillende apparaten en platforms.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: CMS zonder kop, adaptieve formulieren, headless UI, Headful CMS, voice assistants, alexa, chatbots, WhatsApp-architectuur
hide: true
hidefromtoc: true
source-git-commit: 78ae6bc3e390d6a8e46d10d3ad3580c4268bf4ed
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Inleiding

Adobe Experience Manager (AEM) Headless Adaptive Forms is een oplossing voor het maken en beheren van webformulieren zonder hoofd binnen het Adobe Experience Manager-platform. Met deze functie kunnen organisaties interactieve formulieren maken, publiceren en beheren die via API&#39;s kunnen worden benaderd en waarmee interactie mogelijk is, in plaats van via een traditionele grafische gebruikersinterface. AEM Headless Adaptive Forms biedt meer flexibiliteit en schaalbaarheid bij de ontwikkeling en implementatie van formulieren en een verbeterde gebruikerservaring doordat het formulierontwerp en de functionaliteit op specifieke behoeften kunnen worden afgestemd. Door gebruik te maken van de mogelijkheden van AEM en technologie zonder kop, biedt deze oplossing een robuust platform voor het maken, beheren en implementeren van webformulieren voor verschillende gebruiksgevallen en -toepassingen.

![Een formulier maken en genereren in een willekeurige website, toepassing of niet-visuele interactie](/help/assets/headless-forms-for-any-device.jpeg)

Met behulp van hoofdloze adaptieve formulieren kunt u:

* multikanaalformulieren van hoge kwaliteit maken in de programmeertaal van uw keuze
* U kunt zelf formulieren integreren in uw bureaublad en mobiele apps, websites en chattoepassingen
* gebruik uw eigen UI-componenten opnieuw met formuliertoepassingen
* de [macht van Adobe Experience Manager Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/getting-started/introduction-aem-forms.html)

Daarnaast hebt u de vrijheid om uw eigen componenten te ontwikkelen om een formulier te genereren met behulp van een willekeurig gebruikersinterface-framework en een door u gekozen programmeertaal. U kunt ook de React-componenten gebruiken die offline beschikbaar zijn om een Headless adaptief formulier te genereren.

## Belangrijkste kenmerken

<!-- 

<table style="width:100%;">
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Responsive Forms</h2>
          <p>The adaptive form feature enables you to create a single source for a form that automatically sizes and re-flows on mobile devices.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Communication API</h2>
          <p>The adaptive form feature enables you to create a single source for a form that automatically sizes and re-flows on mobile devices.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Card Image 2" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Business Process Management</h2>
          <p>Integrate RDBMS, OData, Or Microsoft SOAP services, as well as protocols like Swagger 2.0 to connect to just about anything.</p>
        </div>
      </div>
    </td>
  </tr>
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Card Image 3" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Save and resume forms</h2>
          <p>Allow clients to save in-progress forms and return later to complete them, even on another device.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/04-overview-search.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Forms Search and Discovery</h2>
          <p>Let customers easily find relevant forms based on a simple search query, tags, filters, and even geolocation — on any device through a personalized portal, with or without authentication.
          </p>
        </div>
      </div>
    </td>
      <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/04-overview-search.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Forms Search and Discovery</h2>
          <p>Let customers easily find relevant forms based on a simple search query, tags, filters, and even geolocation — on any device through a personalized portal, with or without authentication.
          </p>
        </div>
      </div>
    </td>
  </tr>
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/05-overview-analytics.jpeg" alt="Card Image 2" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Form analytics and reporting</h2>
          <p>Out-of-the-box, customizable dashboards make it easy to apply analytics to forms to gain insight for actionable areas of improvement.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/06-overview-business-process.jpeg" alt="Card Image 3" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Business Process Management</h2>
          <p>Route application submissions through customized workflows and a centralized dashboard for review, approval, and digital signatures by back-office employees — even when employees are on the go on a mobile device.
          </p>
        </div>
      </div>
    </td>
  </tr>
</table>

-->


<div style="display: flex; flex-wrap: wrap; justify-content: space-between; margin: 20px;">
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Pictogram 1" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 1</h2>
        <p>Beschrijving 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Pictogram 2" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 2</h2>
        <p>Omschrijving 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Pictogram 3" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 3</h2>
        <p>Beschrijving 3</p>
    </div>
        <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/04-overview-search.jpeg" alt="Pictogram 1" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 1</h2>
        <p>Beschrijving 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/05-overview-analytics.jpeg" alt="Pictogram 2" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 2</h2>
        <p>Omschrijving 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/06-overview-business-process.jpeg" alt="Pictogram 3" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Kop 3</h2>
        <p>Beschrijving 3</p>
    </div>
    <!-- Add more cards as needed -->
</div>




<div style="display: flex; flex-wrap: wrap; justify-content: space-between; margin: 20px;">
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Afbeelding 1" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Kop 1</h2>
        <p>Beschrijving 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Afbeelding 2" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Kop 2</h2>
        <p>Omschrijving 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Afbeelding 3" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Kop 3</h2>
        <p>Beschrijving 3</p>
    </div>
    <!-- Add more cards as needed -->
</div>



## Wie kan adaptieve formulieren zonder koptekst gebruiken? {#who-can-use-headless-adaptive-forms}

Elke front-end ontwikkelaar die bekend is met de moderne JavaScript-frameworks kan gebruikmaken van Headless adaptive-formulieren. Ontwikkelaars kunnen hun bestaande expertise in frontendtalen, zoals React, gebruiken om prachtige ervaringen op bedrijfsniveau met het vastleggen van gegevens te creëren.

U hebt geen voorafgaande kennis van Adobe Experience Manager nodig om Zwaardeloze adaptieve formulieren te ontwikkelen.

<!-- 
## How to join the early adopter program? {#how-to-join-early-adopter-forms}

The service is available for AEM Forms as a Cloud Service and AEM 6.5.16.0 Forms or later On-Premise term customers and Adobe-Managed Service enterprise customers. Send an email to [headlessadaptiveforms@adobe.com](mailto:headlessadaptiveforms@adobe.com) from your official email ID to join the early adopter program. 

-->