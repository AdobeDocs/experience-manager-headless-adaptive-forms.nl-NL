---
title: Een hoofdloos adaptief formulier maken met de Adaptieve Forms-editor
description: Een hoofdloos adaptief formulier maken met de Adaptieve Forms-editor
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: 0214dc2e-52ce-40e9-bef3-f4f4a7ff266f
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '1200'
ht-degree: 0%

---

# Een hoofdloos adaptief formulier maken met de Adaptieve Forms-editor {#create-a-headless-adaptive-form-using-adaptive-forms-editor}

AEM Forms as a Cloud Service biedt een gebruiksvriendelijke editor om Headless Adaptive Forms te maken. Als er meer dan 24 basiscomponenten beschikbaar zijn, kunt u eenvoudig een formulier maken door componenten in de editor te slepen en neer te zetten. Daarnaast kunt u in de regeleditor validaties toevoegen aan uw formuliervelden.

>[!NOTE]
>
> 
>Als u nog geen ervaring hebt met Headless Adaptive Forms, raadt de Adobe u aan door de [Een formulier zonder kop maken en publiceren met de startkit](create-and-publish-a-headless-form.md) zelfstudie om de basisbeginselen te leren en een adaptief formulier zonder kop te gebruiken voordat u de Adaptieve Forms-editor voor Headless-formulieren gebruikt.

Voer de volgende stappen uit om een Headless adaptive-formulier te maken met de Adaptive Forms-editor:

## Voordat u begint:

U hebt het volgende nodig om een adaptief formulier te maken met de Adaptive Forms-editor:

**Voor AEM 6.5 Forms:**

* Toegang tot een AEM 6.5.16.0 of later Forms-auteurexemplaar.

* Adaptieve Forms Core-componenten

* Adaptive Forms Core Components-sjabloon

* Een adaptief formulierthema voor een op kerncomponenten gebaseerde sjabloon

* Gebruikers toevoegen aan [!DNL forms-users] groep. De leden van de [!DNL forms-users] groep heeft machtigingen om een adaptief formulier te maken.


**Voor AEM Forms as a Cloud Service:**

* Toegang tot een [AEM Forms as a Cloud Service-auteurinstantie](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-forms-cloud-service.html?lang=en) of [lokale as a Cloud Service SDK van AEM Forms](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=en) milieu.

* **Een adaptieve formuliersjabloon**: Een sjabloon biedt een basisstructuur en definieert de vormgeving (lay-outs en stijlen) van een adaptief formulier. Het heeft vooraf opgemaakte componenten die bepaalde eigenschappen en inhoudsstructuur bevatten. Het biedt ook de opties om een thema en een verzendactie te definiëren. In het thema wordt de actie look and feel and submit gedefinieerd voor de actie die moet worden ondernomen bij het verzenden van een adaptief formulier. Bijvoorbeeld, verzendend de verzamelde gegevens naar een gegevensbron. De cloudservice biedt een OOTB-sjabloon met de naam blank:

   * De `blank Adaptive Forms (Core Components)` De sjabloon wordt bij elk nieuw as a Cloud Service AEM Forms-programma geleverd.
   * U kunt [een nieuwe adaptieve Forms-sjabloon (Core Components) maken](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/template-editor.html) helemaal niet.

* **Een adaptief formulierthema**: Een thema bevat opmaakgegevens voor de componenten en deelvensters. Stijlen omvatten eigenschappen zoals achtergrondkleuren, statuskleuren, transparantie, uitlijning en grootte. Wanneer u een thema toepast, weerspiegelt de opgegeven stijl de corresponderende componenten.  De `Canvas` De sjabloon wordt bij elk nieuw as a Cloud Service AEM Forms-programma geleverd.

* **Machtigingen**: Voeg uw gebruikers toe aan [!DNL forms-users] groep. De leden van de [!DNL forms-users] groep heeft machtigingen om een adaptief formulier te maken. Zie voor een gedetailleerde lijst met formulierspecifieke gebruikersgroepen [Groepen en machtigingen](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/forms-groups-privileges-tasks.html).


## Een adaptief formulier maken  {#create-an-adaptive-form-components}

1. Aanmelden bij uw [!DNL Experience Manager Forms] Auteur-instantie.

1. Ga uw geloofsbrieven op de Experience Manager login pagina in. Tik in de linkerbovenhoek nadat u bent aangemeld op **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]**.

1. Tik op **[!UICONTROL Create]**  > **[!UICONTROL Adaptive Forms]**. De wizard wordt geopend. Selecteer een sjabloon op het tabblad Bron:

   ![Sjabloon](/help/assets/core-components-template.png)

   Wanneer u een sjabloon selecteert, wordt de actie voor het thema en het verzenden die in de sjabloon is opgegeven automatisch geselecteerd en wordt de opdracht **[!UICONTROL Create]** wordt ingeschakeld. Je kunt naar de **[!UICONTROL Style]** of **[!UICONTROL Submission]** tabs om een ander thema te selecteren of actie te verzenden. Als de geselecteerde sjabloon geen thema opgeeft, blijft de knop Maken uitgeschakeld. Je kunt naar de **[!UICONTROL Styles]** om handmatig een thema te selecteren.

1. In de **[!UICONTROL Style]** selecteert u een thema:

   * Als de geselecteerde sjabloon een thema opgeeft, wordt het thema automatisch geselecteerd in de wizard. U kunt ook een ander thema kiezen op het tabblad Stijl.

   * Als de geselecteerde sjabloon geen thema opgeeft, kunt u het tabblad Stijl gebruiken om een thema te kiezen. De **[!UICONTROL Create]** De knop wordt alleen ingeschakeld nadat een thema is geselecteerd.

1. (Optioneel) Selecteer op het tabblad Gegevens een gegevensmodel:

   * **Formuliergegevensmodel**: A [Formuliergegevensmodel](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html) Hiermee kunt u entiteiten en services integreren van verschillende gegevensbronnen tot een adaptief formulier. Kies Formuliergegevensmodel als het adaptieve formulier dat u maakt, bestaat uit het ophalen en schrijven van gegevens van en naar meerdere gegevensbron.

   * **JSON Schema**: [JSON-schema](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/adaptive-form-json-schema-form-model.html?lang=en) De adaptieve Vorm staat naadloze integratie met het achterste deelsysteem van uw organisatie toe door de capaciteit te verstrekken om een schema te associëren JSON, dat de structuur van de gegevens vertegenwoordigt die worden geproduceerd of worden verbruikt. Met deze koppeling kunnen auteurs dynamisch inhoud toevoegen aan het adaptieve formulier met behulp van de elementen van het schema. De elementen van het schema zijn tijdens het ontwerpproces gemakkelijk toegankelijk op het tabblad Gegevensmodelobjecten van de inhoudbrowser en alle velden worden automatisch toegevoegd aan elk nieuw gemaakt adaptief formulier.

   Standaard worden alle velden van het gekoppelde JSON-schema automatisch geselecteerd en geconverteerd naar de overeenkomstige componenten van het adaptieve formulier, waardoor het ontwerpproces wordt gestroomlijnd. De wizard biedt het extra gebruiksgemak waarmee u via selectievakjes kunt kiezen welke velden in het adaptieve formulier moeten worden opgenomen.

1. In de **[!UICONTROL Submission]** selecteert u een verzendactie:

   * Wanneer u een sjabloon selecteert, wordt de verzendactie die in de sjabloon is opgegeven automatisch geselecteerd. U kunt een andere verzendactie selecteren op het tabblad Verzending. De **[!UICONTROL  Submission]** worden alle beschikbare verzendhandelingen weergegeven.

   * Als de geselecteerde sjabloon geen verzendactie opgeeft, kunt u de opdracht **[!UICONTROL Submission]** tabblad om een verzendactie te selecteren

1. (Optioneel) In het dialoogvenster **[!UICONTROL Delivery]** kunt u een publicatiedatum of een publicatiedatum opgeven voor een adaptief formulier.

1. Tik op **[!UICONTROL Create]**. Er wordt een dialoogvenster weergegeven waarin u de titel, naam en locatie voor het opslaan van het adaptieve formulier kunt opgeven:

   * **[!UICONTROL Title]** Hier geeft u de weergavenaam van het formulier op. Met de titel kunt u het formulier identificeren in het dialoogvenster [!DNL Experience Manager Forms] gebruikersinterface.
   * **[!UICONTROL Name:]** Hier geeft u de naam van het formulier op. Er wordt een knooppunt met de opgegeven naam gemaakt in de repository. Wanneer u een titel begint te typen, wordt automatisch een waarde voor het naamveld gegenereerd. U kunt de voorgestelde waarde wijzigen. Het naamveld mag alleen alfanumerieke tekens, afbreekstreepjes en onderstrepingstekens bevatten. Alle ongeldige invoer wordt vervangen door een afbreekstreepje.
   * **[!UICONTROL Path:]** Hier geeft u de locatie op waar het adaptieve formulier moet worden opgeslagen. U kunt het adaptieve formulier rechtstreeks opslaan op `/content/dam/formsanddocuments` of maak een map, zoals `/content/dam/formsanddocuments/adaptiveforms` een adaptief formulier opslaan. Zorg ervoor dat u de map maakt voordat u deze in het pad gebruikt. De **[!UICONTROL Path]** wordt niet automatisch een map gemaakt.

1. Tik op **[!UICONTROL Create]**. Er wordt een adaptief formulier gemaakt en geopend in de Adaptive Forms-editor. De redacteur toont de inhoud beschikbaar in het malplaatje.  Op basis van het type adaptief formulier worden de formulierelementen in het bijbehorende formulier <!--XFA form template, XML schema or --> Het JSON-schema of het formuliergegevensmodel worden weergegeven in het **[!UICONTROL Data Model Objects]** tabblad van het **[!UICONTROL Content Browser]** in de zijbalk. U kunt deze elementen ook slepen en neerzetten om het adaptieve formulier te maken.

Nu kunt u de Adaptive Forms-componenten naar de container van Adaptive Forms slepen om het formulier te ontwerpen en te maken.


## JSON-uitvoering van een adaptief formulier weergeven {#preview-form}

Selecteer het adaptieve formulier en tik op **Voorvertoning**. Het voorbeeld van het formulier wordt weergegeven. Als u de formulierdefinitie (JSON) van het formulier wilt weergeven, vervangt u de extensie .html in de URL door .model.json

Bijvoorbeeld http://[auteur-server]:[poort]/editor.html/content/forms/af/contact-us.model.json

U kunt de Forms zonder koptekst (Headless Adaptive) gebruiken [getForm](https://opensource.adobe.com/aem-forms-af-runtime/api/#tag/Get-Form-Definition) API om de formulierdefinitie (JSON) op te halen en te gebruiken in uw toepassing.

![Formulierdefinitie weergeven (JSOI)](assets/json-definantion.png)

