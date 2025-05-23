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
source-wordcount: '1145'
ht-degree: 0%

---

# Een hoofdloos adaptief formulier maken met de Adaptieve Forms-editor {#create-a-headless-adaptive-form-using-adaptive-forms-editor}

AEM Forms as a Cloud Service biedt een gebruiksvriendelijke editor om Headless Adaptive Forms te maken. Als er meer dan 24 basiscomponenten beschikbaar zijn, kunt u eenvoudig een formulier maken door componenten in de editor te slepen en neer te zetten. Daarnaast kunt u in de regeleditor validaties toevoegen aan uw formuliervelden.

>[!NOTE]
>
> 
>Als u aan Hoofdloze Aanpassings Forms nieuw bent, adviseert de Adobe om door [ te gaan creeer en publiceer een vorm zonder kop gebruikend startkit ](create-and-publish-a-headless-form.md) leerprogramma om de grondbeginselen te leren en een headless adaptieve vorm te behandelen alvorens de AanpassingsForms redacteur voor de vormen van de Zwaartepunt te gebruiken.

Voer de volgende stappen uit om een Headless adaptive-formulier te maken met de Adaptive Forms-editor:

## Voordat u begint:

U hebt het volgende nodig om een adaptief formulier te maken met de Adaptive Forms-editor:

**voor AEM 6.5 Forms:**

* Toegang tot een AEM 6.5.16.0 of later Forms-auteurexemplaar.

* Adaptieve Forms Core-componenten

* Adaptive Forms Core Components-sjabloon

* Een adaptief formulierthema voor een op kerncomponenten gebaseerde sjabloon

* Voeg uw gebruikers toe aan de groep [!DNL forms-users] . De leden van de groep [!DNL forms-users] hebben machtigingen om een adaptief formulier te maken.


**voor AEM Forms as a Cloud Service:**

* Toegang tot een [ as a Cloud Service de auteursinstantie van AEM Forms ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-forms-cloud-service.html?lang=nl-NL) of a [ lokale as a Cloud Service SDK van AEM Forms ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/setup-local-development-environment.html?lang=nl-NL) milieu.

* **een Adaptief malplaatje van de Vorm**: Een malplaatje verstrekt een basisstructuur en bepaalt verschijning (lay-outs en stijlen) van een Aangepast Vorm. Het heeft vooraf opgemaakte componenten die bepaalde eigenschappen en inhoudsstructuur bevatten. Het biedt ook de opties om een thema en een verzendactie te definiëren. In het thema wordt de actie look and feel and submit gedefinieerd voor de actie die moet worden ondernomen bij het verzenden van een adaptief formulier. Bijvoorbeeld, verzendend de verzamelde gegevens naar een gegevensbron. De cloudservice biedt een OOTB-sjabloon met de naam blank:

   * De `blank Adaptive Forms (Core Components)` -sjabloon wordt opgenomen in elk nieuw AEM Forms as a Cloud Service programma.
   * U kunt ook [ een nieuw Adaptief malplaatje van Forms (de Componenten van de Kern) ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/template-editor.html?lang=nl-NL) van kras tot stand brengen.

* **een Adaptief thema van de Vorm**: Een thema bevat het stileren details voor de componenten en de panelen. Stijlen omvatten eigenschappen zoals achtergrondkleuren, statuskleuren, transparantie, uitlijning en grootte. Wanneer u een thema toepast, weerspiegelt de opgegeven stijl de corresponderende componenten.  De `Canvas` -sjabloon wordt opgenomen in elk nieuw AEM Forms as a Cloud Service programma.

* **Toestemmingen**: Voeg uw gebruikers aan [!DNL forms-users] groep toe. De leden van de groep [!DNL forms-users] hebben machtigingen om een adaptief formulier te maken. Voor gedetailleerde lijst van vormen specifieke gebruikersgroepen, zie [ Groepen en toestemmingen ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/setup-configure-migrate/forms-groups-privileges-tasks.html?lang=nl-NL).


## Een adaptief formulier maken  {#create-an-adaptive-form-components}

1. Meld u aan bij uw [!DNL Experience Manager Forms] Author-instantie.

1. Ga uw geloofsbrieven op de Experience Manager login pagina in. Tik in de linkerbovenhoek op **[!UICONTROL Adobe Experience Manager]** > **[!UICONTROL Forms]** > **[!UICONTROL Forms & Documents]** nadat u zich hebt aangemeld.

1. Tik op **[!UICONTROL Create]** > **[!UICONTROL Adaptive Forms]** . De wizard wordt geopend. Selecteer op het tabblad Source een sjabloon:

   ![ Malplaatje ](/help/assets/core-components-template.png)

   Wanneer u een sjabloon selecteert, wordt de in de sjabloon opgegeven actie voor het thema en het verzenden automatisch geselecteerd en wordt de knop **[!UICONTROL Create]** ingeschakeld. U kunt naar de tabbladen **[!UICONTROL Style]** of **[!UICONTROL Submission]** gaan om een ander thema te selecteren of een actie te verzenden. Als de geselecteerde sjabloon geen thema opgeeft, blijft de knop Maken uitgeschakeld. U kunt naar het tabblad **[!UICONTROL Styles]** gaan om handmatig een thema te selecteren.

1. Selecteer op het tabblad **[!UICONTROL Style]** een thema:

   * Als de geselecteerde sjabloon een thema opgeeft, wordt het thema automatisch geselecteerd in de wizard. U kunt ook een ander thema kiezen op het tabblad Stijl.

   * Als de geselecteerde sjabloon geen thema opgeeft, kunt u het tabblad Stijl gebruiken om een thema te kiezen. De knop **[!UICONTROL Create]** wordt alleen ingeschakeld nadat een thema is geselecteerd.

1. (Optioneel) Selecteer op het tabblad Gegevens een gegevensmodel:

   * **het gegevensmodel van de Vorm**: Het Model van de Gegevens van de Vorm van A [&#128279;](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/integrate/use-form-data-model/data-integration.html?lang=nl-NL) laat u entiteiten en de diensten van ongelijksoortige gegevensbronnen aan een Aangepaste Vorm integreren. Kies Formuliergegevensmodel als het adaptieve formulier dat u maakt, bestaat uit het ophalen en schrijven van gegevens van en naar meerdere gegevensbron.

   * **JSON Schema**: [ JSON schema ](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/forms/adaptive-forms-authoring/authoring-adaptive-forms-foundation-components/create-an-adaptive-form-on-forms-cs/adaptive-form-json-schema-form-model.html?lang=nl-NL) de Aangepaste Vorm staat naadloze integratie met het achterste deelsysteem van uw organisatie toe door de capaciteit te verstrekken om een schema te associëren JSON, dat de structuur van de gegevens vertegenwoordigt die worden geproduceerd of worden verbruikt. Met deze koppeling kunnen auteurs dynamisch inhoud toevoegen aan het adaptieve formulier met behulp van de elementen van het schema. De elementen van het schema zijn tijdens het ontwerpproces gemakkelijk toegankelijk op het tabblad Gegevensmodelobjecten van de inhoudbrowser en alle velden worden automatisch toegevoegd aan elk nieuw gemaakt adaptief formulier.

   Standaard worden alle velden van het gekoppelde JSON-schema automatisch geselecteerd en geconverteerd naar de overeenkomstige componenten van het adaptieve formulier, waardoor het ontwerpproces wordt gestroomlijnd. De wizard biedt het extra gebruiksgemak waarmee u via selectievakjes kunt kiezen welke velden in het adaptieve formulier moeten worden opgenomen.

1. Selecteer op het tabblad **[!UICONTROL Submission]** een verzendactie:

   * Wanneer u een sjabloon selecteert, wordt de verzendactie die in de sjabloon is opgegeven automatisch geselecteerd. U kunt een andere verzendactie selecteren op het tabblad Verzending. Op het tabblad **[!UICONTROL &#x200B; Submission]** worden alle beschikbare verzendhandelingen weergegeven.

   * Wanneer de geselecteerde sjabloon geen verzendactie opgeeft, kunt u op het tabblad **[!UICONTROL Submission]** een verzendactie selecteren

1. (Optioneel) Op het tabblad **[!UICONTROL Delivery]** kunt u een publicatiedatum of een publicatiedatum opgeven voor een adaptief formulier.

1. Tik op **[!UICONTROL Create]**. Er wordt een dialoogvenster weergegeven waarin u de titel, naam en locatie voor het opslaan van het adaptieve formulier kunt opgeven:

   * **[!UICONTROL Title]** Hiermee geeft u de weergavenaam van het formulier op. Met de titel kunt u het formulier identificeren in de gebruikersinterface van [!DNL Experience Manager Forms] .
   * **[!UICONTROL Name:]** Hiermee geeft u de naam van het formulier op. Er wordt een knooppunt met de opgegeven naam gemaakt in de repository. Wanneer u een titel begint te typen, wordt automatisch een waarde voor het naamveld gegenereerd. U kunt de voorgestelde waarde wijzigen. Het naamveld mag alleen alfanumerieke tekens, afbreekstreepjes en onderstrepingstekens bevatten. Alle ongeldige invoer wordt vervangen door een afbreekstreepje.
   * **[!UICONTROL Path:]** Hiermee geeft u de locatie op waar het adaptieve formulier moet worden opgeslagen. U kunt het adaptieve formulier rechtstreeks opslaan in `/content/dam/formsanddocuments` of een map maken, zoals `/content/dam/formsanddocuments/adaptiveforms` , om een adaptief formulier op te slaan. Zorg ervoor dat u de map maakt voordat u deze in het pad gebruikt. In het veld **[!UICONTROL Path]** wordt niet automatisch een map gemaakt.

1. Tik op **[!UICONTROL Create]**. Er wordt een adaptief formulier gemaakt en geopend in de Adaptive Forms-editor. De redacteur toont de inhoud beschikbaar in het malplaatje.  Op basis van het type adaptief formulier worden de formulierelementen in het gekoppelde <!--XFA form template, XML schema or --> JSON-schema of formuliergegevensmodel weergegeven op het tabblad **[!UICONTROL Data Model Objects]** van het **[!UICONTROL Content Browser]** -formulier in het zijpaneel. U kunt deze elementen ook slepen en neerzetten om het adaptieve formulier te maken.

Nu kunt u de Adaptive Forms-componenten naar de container van Adaptive Forms slepen om het formulier te ontwerpen en te maken.


## JSON-uitvoering van een adaptief formulier weergeven {#preview-form}

Selecteer de Adaptieve Vorm en tik **Voorproef**. Het voorbeeld van het formulier wordt weergegeven. Als u de formulierdefinitie (JSON) van het formulier wilt weergeven, vervangt u de extensie .html in de URL door .model.json

Bijvoorbeeld, http:// [ auteur-server ]:[ haven ] /editor.html/content/forms/af/contact-us.model.json

U kunt Headless Adaptive Forms [ gebruiken getForm ](https://opensource.adobe.com/aem-forms-af-runtime/api/#tag/Get-Form-Definition) API om de vormdefinitie (JSON) te halen en het in uw toepassing te gebruiken.

![ de vormdefinitie van de Mening (JSOI) ](assets/json-definantion.png)

