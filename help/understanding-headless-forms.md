---
title: Werken met headless formulieren - Concepten en veelgestelde vragen
description: Antwoorden op veelvoorkomende vragen over de soorten zonder kop, hoe deze verschillen van traditionele formulierbibliotheken, implementatiedetails, UI-controle, prestaties en integratie met frameworks en backends.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: koploze formulieren, headless form library, adaptieve formulieren, state management, validation, design system, SSR, CMS
index: true
exl-id: 539da3e9-25c5-4e26-ba4e-f68cf849bca4
source-git-commit: 86129488bec7faed87600a237ac034ca1b601187
workflow-type: tm+mt
source-wordcount: '2605'
ht-degree: 0%

---

# Werken met headless formulieren - Concepten en veelgestelde vragen {#understanding-headless-forms}

Deze handleiding beantwoordt algemene vragen over hoofdloze formulieren in het algemeen en hoe deze van toepassing zijn op AEM Headless Adaptive Forms. Gebruik deze optie om te bepalen wanneer u een headless-aanpak gebruikt en hoe u formulieren in uw stapel implementeert, opmaakt en integreert.

## Basisbeginselen en begrip {#basics-understanding}

### Wat is een eindeloze formulierbibliotheek?

A **hoofdloze vormbibliotheek** is een vormoplossing die **vormlogica** (staat, bevestiging, regels, voorlegging) van **presentatie** scheidt (UI componenten en het stileren). De &#39;head&#39; is de zichtbare vorm-UI; &#39;headless&#39; betekent dat de bibliotheek geen vaste interface dicteert of verzendt. In plaats daarvan wordt het volgende getoond:

* A **vormmodel** (vaak JSON): structuur, gebieden, beperkingen, en regels.
* **APIs of haken** om vormstaat te lezen en bij te werken, bevestiging in werking te stellen, en voorlegging te behandelen.
* **Gebeurtenissen en levenscyclus** zodat kan uw UI op veranderingen reageren.

In AEM Headless Adaptive Forms, is de vorm a [&#x200B; structuur JSON &#x200B;](architecture.md) die op Adobe Experience Manager wordt ontvangen. Het [&#x200B; Web SDK van Forms &#x200B;](architecture.md#developer-tools) (cliënt-zijruntime) verstrekt de logica laag-zaken regelbewerker, staatsbeheer, bevestiging-terwijl uw app UI levert die die structuur teruggeeft.

### Hoe verschilt een vorm zonder kop van een traditionele formulierbibliotheek?

| Verhouding | Traditionele formulierbibliotheek | Formulierbibliotheek zonder hoofd |
|--------|---------------------------|------------------------|
| **UI** | Wordt geleverd met ingebouwde componenten en stijlen | Geen voorgeschreven interface; u brengt uw eigen componenten |
| **het Stijlen** | Thema&#39;s of overschrijvingen op bibliotheekonderdelen | Volledige controle; gebruik uw ontwerpsysteem ongewijzigd |
| **de definitie van de Vorm** | Vaak alleen-code (componenten in JSX/HTML) | Vaak gegevensgestuurd (JSON/schema van CMS of API) |
| **Staat &amp; bevestiging** | Aan bibliotheekcomponenten gekoppeld | Blootgesteld via API&#39;s/haken; elke interface kan eraan binden |
| **Kanalen** | Meestal web (soms één framework) | Dezelfde formulierdefinitie kan leiden tot web, mobiel, chatten, enzovoort. |

Met AEM Headless Aanpassings Forms, creeert u [&#x200B; en publiceert één keer een vorm &#x200B;](create-and-publish-a-headless-form.md) in AEM; om het even welke cliënt (React, Angular, inheemse mobiele, praatbot) kan [&#x200B; de vorm JSON &#x200B;](architecture.md) halen en het met aangewezen UI voor dat kanaal teruggeven.

### Waarom zou ik koploze vormen in plaats van een op UI-Gebaseerde vormoplossing moeten gebruiken?

Koploze formulieren passen bij uw wensen:

* **het systeemconsistentie van het Ontwerp** - gebruik uw bestaande componenten en merk zonder bibliotheekgebreken te vechten.
* **Multikanaal** - één vormdefinitie voor Web, mobiel, en andere touchpoints (zie [&#x200B; Overzicht &#x200B;](overview.md)).
* **CMS- of backend-gedreven vormen** - de auteurs veranderen vormstructuur en regels zonder code opstellen; uw app verbruikt enkel JSON.
* {de flexibiliteit van het 0} Kader **- de [&#x200B; af-kern &#x200B;](https://www.npmjs.com/package/@aemforms/af-core) bibliotheek is kader-onafhankelijk; De banden van het antwoord worden verstrekt voor gemak, maar u kunt banden voor andere kaders bouwen.**
* **Achterste mogelijkheden** - hefboomwerking AEM Forms voor vooraf ingevulde, bevestiging, voorlegt, werkschema&#39;s, en het Model van Gegevens van Forms zonder het sluiten in een specifieke stapel UI.

### Wanneer heeft het zin een krantenloze aanpak te gebruiken?

Koploze formulieren gebruiken als:

* U hebt een sterk ontwerpsysteem of componentenbibliotheek of u wilt deze ook gebruiken.
* Forms is ontworpen door niet-ontwikkelaars (bijvoorbeeld in een CMS) en moet werken in verschillende apps of kanalen.
* U hebt dezelfde formulierlogica (validatie, regels) nodig voor alle clients van het web, mobiele apparaten of andere clients.
* U wilt rerenderingen minimaliseren en de logica van het formulier onafhankelijk van de gebruikersinterface testen.

Bekijk een traditionele, UI-include-formulierbibliotheek wanneer:

* U hebt snel een werkformulier in één webtoepassing nodig en u hebt geen belang bij een aangepaste UI of een multikanaal.
* Uw team geeft er de voorkeur aan formulieren alleen in code in één framework te definiëren.

### Is &quot;zonder kop&quot; slechts een modewoord of lost het echte problemen op?

Het lost echte architecturale problemen op:

* **Scheiding van zorgen** - de structuur van de vorm, de regels, en de bevestiging leven in gegevens en een logische laag; de laag UI geeft slechts gebruikersacties terug en verzendt. Dit verbetert de testbaarheid en het hergebruik.
* **onafhankelijkheid van het Kanaal** - één vormdefinitie kan verschillende UIs (b.v., Reageer Web, React Native, Angular, of stem) drijven. AEM Headless Adaptive Forms wordt voor dit gebouwd: [&#x200B; bouwt eens, levert over React, SPAs, Web, mobiel, en meer &#x200B;](overview.md).
* **Authoring zonder code** - De zakelijke gebruikers kunnen velden en regels in de [&#x200B; Adaptieve redacteur van de Vorm &#x200B;](create-a-headless-adaptive-form.md) veranderen; de ontwikkelaars hoeven niet voor inhoudveranderingen opnieuw op te stellen.
* **Integratie met bestaande stapels** - u houdt uw ontwerpsysteem, staatsbeheer, en het verpletteren; de koploze laag behandelt slechts vormstaat, bevestiging, en voorlegging.

## Uitvoering en technische vraagstukken {#implementation-technical}

### Hoe beheren headless-formulieren de status?

In AEM Headless Adaptive Forms, wordt de staat beheerd door de **SDK van het Web van Forms**:

* **Bedrijfs regelbewerker** - keurt de vorm JSON goed, beheert gebiedsstaat, en voert regels en gebeurtenismanagers uit die in JSON worden bepaald.
* **Reageren binder** - verstrekt haken (b.v., `useRuleEngine`) over het controlemechanisme zodat ontvangen de componenten React huidige staat en managers; de zelfde staat kan door niet-Reageren UIs via kern APIs worden verbruikt.
* **Staat** omvat gebiedswaarden, zicht, geldigheid, en om het even welke douaneeigenschappen die in het vormmodel worden bepaald.

Uw UI-componenten ontvangen status en handlers (bijvoorbeeld `[state, handlers] = useRuleEngine(props)`); u rendert vanuit `state` en roept `handlers` aan wanneer de gebruiker communiceert. De status van de runtime blijft gelijk aan de definitie en regels van het formulier. Zie [&#x200B; Architectuur &#x200B;](architecture.md) en [&#x200B; de douanecomponenten van het Gebruik om een koploze vorm &#x200B;](developing-for-headless-forms-using-your-own-components.md) terug te geven.

### Hoe werkt validatie in een headless vorm-instelling?

Validatie maakt deel uit van de formulierlogische laag:

* **Beperkingen** worden bepaald in de vormJSON (b.v., vereist, min/max, patroon). Forms Web SDK past deze beperkingen toe en stelt bevestigingsstaat (b.v., geldig/ongeldig, foutenmeldingen) aan uw componenten bloot.
* **cliënt-zijbevestiging** wordt toegepast door SDK die op de vormstructuur wordt gebaseerd; uw UI toont fouten van staat.
* **server-zijbevestiging** is beschikbaar via AEM APIs (b.v., bevestigt eindpunt); u kunt vóór of tijdens voorleggen bevestigen.

U implementeert geen validatielogica in de gebruikersinterface. U geeft alleen de validatiestatus en berichten weer die door de runtime worden geleverd.

### Kan ik vormen zonder kop integreren met schemabevestiging (Yup, Zod, Joi)?

De ingebouwde validatie wordt aangestuurd door de JSON-beperkingen van het formulier. U kunt als volgt Yup, Zod, Joi en dergelijke gebruiken:

* U kunt **&#x200B;**&#x200B;leiden of produceren de Zwaartepunt Aangepaste Vorm JSON van uw schema (b.v., zet JSON- Schema in vorm JSON) om zodat één bron van waarheid zowel schemaverbevestiging als vormstructuur drijft.
* Voor **douanebevestiging** voorbij de vorm JSON, kunt u uw eigen validators (Yup/Zod/Joi) in gebeurtenismanagers in werking stellen of alvorens voor te leggen, en resultaten in de vormstaat of blokvoorlegging duwen. De punten van de integratie zijn de zelfde haken/APIs u voor staat gebruikt en voorlegt.

De [&#x200B; Aangepaste specificatie van Forms &#x200B;](/help/assets/headless-adaptive-forms-specification.pdf) en [&#x200B; Formule JSON &#x200B;](architecture.md) bepalen het regel en beperkingsmodel dat door runtime wordt gebruikt.

### Hoe kan ik async valideren (bijvoorbeeld beschikbaarheid van gebruikersnaam)?

U kunt een synchronisatie-validatie implementeren in uw toepassingslaag:

* Gebruik **regels of gebeurtenismanagers** in de vormJSON (waar gesteund) om logica teweeg te brengen wanneer een gebied verandert.
* In uw **douanecomponenten**, gebruik de zelfde staat/manager haken om uw achtereind (b.v., gebruikersnaadbeschikbaarheid API) te roepen, dan de geldigheid van het gebied bijwerken of een fout via runtime APIs of lokale staat tonen die u in UI oppervlakte.
* Alternatief, voer de controle **op onduidelijk beeld uit of alvorens** voor te leggen en plaats de gebiedsstaat aan ongeldig met een douanebericht als de asynchrone controle ontbreekt.

Het nauwkeurige patroon hangt van hoe uw app met de [&#x200B; bewerker van de bedrijfsregel &#x200B;](architecture.md) en douanecomponenten integreert.

### Hoe kan ik gegevens naar API&#39;s verzenden met behulp van headless-formulieren?

De verzending is losgekoppeld van de interface:

* **AEM legt acties** voor - u vormt de vorm in AEM om aan REST eindpunten, e-mail, of integratie (b.v., Microsoft Dynamics, Salesforce) voor te leggen. Het formulier wordt verzonden via AEM, dat de werkelijke HTTP/backend-aanroep afhandelt. Zie [&#x200B; gebeurtenissen van het Gebruik om vormgegevens &#x200B;](use-events-to-handle-and-submit-form-data.md) te behandelen en voor te leggen.
* **Cliënt-kant legt** voor - Uw app kan naar voorleggen luisteren of vormgegevens van runtime staat verzamelen en het verzenden naar uw eigen APIs. De [&#x200B; het documentlijst van HTTP APIs &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/api/), haalt, bevestigt, voorlegt, en volgt voorleggingsstatus.
* **vooraf ingevulde** - de Gegevens kunnen via REST eindpunten of server-kant worden voorgevuld zodat wanneer de vorm laadt, de staat reeds bevolkt is. Zie [&#x200B; Storybook - vooraf ingevulde voorbeeld &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples—Prefill-form-with-personalized-data).

## UI- en ontwerpcontrole {#ui-design-control}

### Kan ik mijn eigen ontwerpsysteem of componentenbibliotheek gebruiken met headless vormen?

Ja. Dit is een fundamenteel voordeel van eindeloze vormen. Met AEM Headless Adaptive Forms:

* U **kaart** uw eigen componenten aan het vormmodel (door gebiedstype of middeltype). Zie [&#x200B; de douanecomponenten van het Gebruik om een hoofdloze vorm &#x200B;](developing-for-headless-forms-using-your-own-components.md) terug te geven en [&#x200B; het Materiaal UI van Google gebruiken Reageert componenten om een hoofdloze vorm &#x200B;](use-google-material-ui-react-components-to-render-a-headless-form.md) terug te geven.
* Runtime verstrekt **staat en managers**; uw componenten geven terug gebruikend uw ontwerpsysteem en roepen de managers zodat de vormlogica synchroon blijft.
* U kunt **gebruiken Reageer Spectrum**, Materiaal UI, Chakra UI, of om het even welke bibliotheek van de douanecomponent; de [&#x200B; specificatie &#x200B;](/help/assets/headless-adaptive-forms-specification.pdf) kan voor douanecomponenten (b.v., Chakra UI, Vue.js) worden uitgebreid. Zie [&#x200B; Veelgestelde vragen - douanekaders &#x200B;](faq.md#is-it-possible-to-use-headless-adaptive-forms-with-custom-frameworks).

### Biedt headless formulieren toegankelijkheidsondersteuning (ARIA, toetsenbordafhandeling)?

De toegankelijkheid wordt uitgevoerd in de **laag UI** u verstrekt. De koploze laag rendert DOM niet en voegt dus op zichzelf geen ARIA- of toetsenbordgedrag toe. U krijgt toegankelijkheid door:

* Het gebruiken van **toegankelijke componenten** van uw ontwerpsysteem of bibliotheek (vele omvatten ARIA en toetsenbordsteun).
* Na **toegankelijkheid beste praktijken** op uw componenten van het douanegebied (etiketten, foutenmeldingen, nadrukbeheer, toetsenbordnavigatie).
* De ARIA-kenmerken en het gedrag van uw componenten weerspiegelen de formulierstructuur en de status die u ontvangt (bijvoorbeeld vereist, ongeldig, zichtbaar).

Als u de uit-van-de-doos Reageer op spectrum-Gebaseerde componenten gebruikt, profiteert u van hun ingebouwde toegankelijkheid.

### Hoe kan ik complexe UI-componenten verwerken (datumkiezers, aangepaste vervolgkeuzelijsten)?

Behandel hen als **douanecomponenten** in kaart gebracht aan de overeenkomstige gebiedstypes of types van douanemiddel in de vorm JSON:

* Voer uw component uit om de zelfde **steunen/staat/managers** als andere gebiedscomponenten (b.v., via `useRuleEngine`) goed te keuren.
* De staat van het gebruik **voor waarde, zicht, en geldigheid; gebruik** handlers **om waarde bij te werken en bevestiging teweeg te brengen.**
* Render de datumkiezer of het aangepaste vervolgkeuzemenu met de gekozen UI-bibliotheek. Roep bij wijziging de handler aan met de nieuwe waarde, zodat de formulierstatus correct blijft.

Zie [&#x200B; de douanecomponenten van het Gebruik om een headless vorm &#x200B;](developing-for-headless-forms-using-your-own-components.md) voor afbeelding door gebiedstype en middeltype terug te geven.

### Kan ik dynamisch velden (dynamische formulieren) toevoegen of verwijderen?

De vormstructuur wordt bepaald door **vorm JSON** teruggekeerd van de server. Dynamisch gedrag wordt bereikt door:

* **Regels in de vorm JSON** - tonen/verbergen, toelaten/onbruikbaar maken, of vastgestelde waarden die op uitdrukkingen worden gebaseerd. De [&#x200B; bewerker van de bedrijfsregel &#x200B;](architecture.md) voert deze regels uit; uw componenten reageren op `state.visible` en gelijkaardig.
* **server-gedreven structuur** - de Verschillende gebruikers of de contexten kunnen verschillende vorm JSON (b.v., verschillende stappen of secties) ontvangen, zodat &quot;dynamisch&quot;kan &quot;verschillende vormdefinitie per verzoek betekenen.&quot;
* **cliënt-kant verandert** - als uw app het vormmodel (b.v., voeg/verwijder punten in een herhaalbare structuur toe) kan, runtime op dat wijzen; het nauwkeurige vermogen hangt van het vormschema en runtime APIs af.

[&#x200B; Storybook &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) omvat voorbeelden van dynamisch gedrag.

### Hoe kan ik voorwaardelijke velden verwerken (weergeven/verbergen op basis van invoer)?

Voorwaardelijk zicht wordt gedreven door **regels** in de vorm JSON, die door de bewerker van de bedrijfsregel wordt geëvalueerd. U definieert voorwaarden (bijvoorbeeld &quot;als veld A gelijk is aan X, veld B tonen&quot;); de status van de runtime wordt bijgewerkt (bijvoorbeeld `state.visible`). Uw componenten moeten slechts **respecteren staat** (b.v., `if (!state.visible) return null;`). Geen extra logica UI wordt vereist voor tonen/verbergen voorbij het teruggeven van staat. Het draperen en voorwaardelijk gedrag worden gedocumenteerd in de [&#x200B; Aangepaste specificatie van Forms &#x200B;](/help/assets/headless-adaptive-forms-specification.pdf) en in [&#x200B; Storybook - het cascading gebieden &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behavior—options&args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJS son.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) aangetoond. Zie ook [&#x200B; Veelgestelde vragen - het trapsgewijze gebieden &#x200B;](faq.md#do-headless-adaptive-forms-support-cascading-fields).

## Prestaties en schaalbaarheid {#performance-scalability}

### Zijn headless-formulieren krachtiger dan traditionele formulierbibliotheken?

Dat kan, maar het hangt af van de implementatie:

* **gerichte updates** - Een goed ontworpen headless runtime werkt slechts de staat bij die veranderde en slechts de componenten meldt die van het afhangen, die onnodige re-renders in vergelijking met een monolithische vormcomponent kan verminderen.
* **Kleinere bundel UI** - u verzendt slechts de componenten UI u gebruikt (uw ontwerpsysteem), niet een volledige reeks bibliotheekcomponenten.
* **Late lading** - de Vorm JSON kan worden gehaald wanneer nodig; de aanvankelijke bundel kan kleiner blijven.

De prestaties zijn ook afhankelijk van de manier waarop u uw componenten implementeert (bijvoorbeeld het vermijden van onnodige renderingen, memoalisatie).

### Hoe minimaliseren ze opnieuw renderen?

* **vorm van de Staat** - runtime houdt vormstaat in een structuur die verfijnde updates zo slechts beïnvloede delen van de boom toe om opnieuw terug te geven.
* **het ontwerp van Hooks** - Hooks als `useRuleEngine` kan worden uitgevoerd om componenten slechts aan de staat in te tekenen zij gebruiken, zodat de ouder of het sibling veranderingen niet elk gebied dwingen om opnieuw terug te geven.
* **Uw verantwoordelijkheid** - u kunt re-renders verder minimaliseren door React beste praktijken (b.v., `React.memo`, stabiele callbacks) in uw douanecomponenten te gebruiken.

### Kunnen vormen zonder kop goed worden geschaald voor grote formulieren met meerdere stappen?

Ja, indien geschikt ontworpen:

* **de definitie van de Vorm** - de grote vormen kunnen in stappen of secties in JSON worden gesplitst; slechts kan de zichtbare stap/de sectie volledig actief in UI, met luie evaluatie van regels voor verborgen secties moeten zijn indien gesteund.
* **Staat** - runtime houdt één coherente vormstaat; de stapnavigatie toont/verbergt enkel secties of het bijwerken &quot;huidige stap&quot;zonder het dupliceren van gegevens.
* **het Knipperen en luie lading** - u kunt vormJSON in koeken halen of extra secties laden op stapvooruitgang om aanvankelijke nuttige lading en het ontleden kosten laag te houden.

Houd bij zeer grote formulieren rekening met de structuur (bijvoorbeeld wizardstappen), servergestuurde formuliervarianten en het meten van de renderbewerking en regeluitvoering met werkelijke ladingen.

## Integratie en ecosysteem {#integration-ecosystem}

### Kunnen headless vormen met de Acties van Next.js/SSR/van de Server werken?

* **Next.js/React** - ja. Renderer Reageren en haken werken in een React milieu. Gebruik Forms Web SDK in clientcomponenten; haal JSON-formulier zo nodig op de server of client op.
* **SSR** - U kunt de vormJSON op de server halen en het tot de cliënt overgaan zodat loopt de vorm met gegevens. De interactiviteit van het formulier (status, validatie, regels) wordt uitgevoerd op de client waar de SDK is geladen. Vermijd het renderen van formuliervelden die tijdens de SSR afhankelijk zijn van de status Alleen client, of gebruik een tijdelijke aanduiding die op de client hydrateert.
* **de Acties van de Server (Next.js)** - u kunt de Acties van de Server van uw voorleggen manager roepen: wanneer de gebruiker voorlegt, verzamelt uw cliëntcode vormgegevens (van de headless staat) en roept een Actie van de Server in plaats van of naast AEM voorlegt eindpunten voor.

### Hoe integreren headless vormen met CMS, headless handel, of backend systemen?

* **CMS** - AEM is CMS voor de vormdefinitie: de auteurs creëren en publiceren de vorm JSON. Andere CMS&#39;s kunnen verwijzen naar of een koppeling naar de URL/API van het formulier maken. Uw app haalt het formulier op van AEM (of een CDN) en haalt optioneel een kopie of lay-out op van een andere CMS.
* **vooraf invullen en voorleggen** - [&#x200B; vooraf invult &#x200B;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples—Prefill-form-with-personalized-data) en voorlegt kan de eindpunten van REST raken, zodat kunt u van CRM, DAM, of handel achterste vooraf invullen en voorleggen aan het zelfde of verschillende systemen. AEM Forms steunt ook [&#x200B; Microsoft Dynamics en Salesforce &#x200B;](faq.md), REST, e-mail, en douane voorlegt acties voor.
* **het Model van Gegevens van Forms** - AEM Forms verstrekt een Model van Gegevens van Forms om met ongelijksoortige gegevensbronnen te verbinden; de vormen zonder kop kunnen deze mogelijkheden voor vooraf ingevulde, bevestiging gebruiken, en voorleggen zonder u elke integratie zelf bouwt.

Voor mobiele en off-line scenario&#39;s, is de geadviseerde benadering uw eigen app te bouwen en vormdefinities via de Zwaardeloze Aanpassings Forms API [&#128279;](mobile-forms-best-practices.md) te halen.

## Zie ook {#see-also}

* [Overzicht](overview.md)
* [Architectuur](architecture.md)
* [Veelgestelde vragen](faq.md)
* [Een formulier zonder kop maken en publiceren](create-and-publish-a-headless-form.md)
* [API&#39;s voor hulpformulieren zonder hoofd](https://opensource.adobe.com/aem-forms-af-runtime/api/)
* [Codespeelplaats](https://experienceleague.adobe.com/landing/aem-headless-forms/developer/code.html?lang=nl-NL)
* [Winkelboek](https://opensource.adobe.com/aem-forms-af-runtime/storybook/)
