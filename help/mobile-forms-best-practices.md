---
title: Aanbevolen werkwijzen voor mobiele formulieren
description: Voor gebruik van mobiele en offline formulieren maakt u uw eigen native app en haalt u formulierdefinities op via de Headless Adaptive Forms API. Aanbevolen aanpak voor systeemeigen mobiele toepassingen.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: mobiele formulieren, native app, offline formulieren, headless API
index: true
exl-id: 6f25039f-61fc-4366-9e17-6b2809162c58
source-git-commit: 86129488bec7faed87600a237ac034ca1b601187
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Aanbevolen werkwijzen voor mobiele formulieren {#mobile-forms-best-practices}

Bij gebruik van mobiele en offline formulieren kunt u het beste uw eigen native app ontwikkelen en formulierdefinities ophalen via de Headless Adaptive Forms API. Dit geeft u volledige controle over de mobiele ervaring en zorgt voor doorlopende ondersteuning naarmate mobiele platforms zich ontwikkelen.

## Aanbevolen aanpak {#recommended-approach}

Bouw een inheemse mobiele toepassing (iOS of Android) die:

1. **Vetst de hoofdloze vormdefinitie** - gebruik [&#x200B; Zwaarloze Adaptieve Forms APIs &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/api/) om de vorm JSON op bestelling terug te winnen (bijvoorbeeld, wanneer de gebruiker een vorm opent of aan het in uw app navigeert). U kunt beschikbare formulieren weergeven en vervolgens de formulierdefinitie ophalen met de id.

2. **geeft de vorm in uw app** terug - gebruik uw aangewezen kader UI (bijvoorbeeld, React Native, of inheemse meningen) om de vorm van JSON terug te geven. U kunt de Forms Web SDK en de bestaande Aangepaste formulieren zonder koptekst gebruiken Reageer componenten waar ze in uw stapel passen, of uw eigen renderer maken die dezelfde JSON-structuur gebruikt.

3. **naar keuze steunt off-line** - voer lokale opslag en synchronisatie in uw app uit. Stel bijvoorbeeld dat u formulierdefinities in de cache plaatst als u online bent, concepten lokaal opslaat en gegevens verzendt of synchroniseert wanneer het apparaat weer online is.

Deze benadering zorgt ervoor dat uw app behouden blijft terwijl Android en iOS veranderen en gebruikt het ondersteunde Headless Adaptive Forms-platform voor het schrijven, valideren en verzenden van formulieren.

## Aan de slag {#getting-started}

* [&#x200B; AEM Headless adaptieve vormen overzicht &#x200B;](overview.md) - Mogelijkheden en concepten.
* [&#x200B; Koploze adaptieve vormen APIs &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/api/) - Lijst, haal, bevestigt, en verzend vormen programmatically.
* [&#x200B; Architectuur &#x200B;](architecture.md) - hoe de Koploze adaptieve vormen werken en hoe front-end toepassingen hen verbruiken.

Voor geleidelijke integratie, zie [&#x200B; creeer en publiceer een headless vorm &#x200B;](create-and-publish-a-headless-form.md) en het [&#x200B; portaal van de Ontwikkelaar &#x200B;](https://experienceleague.adobe.com/landing/aem-headless-forms/developer.html?lang=nl-NL).
