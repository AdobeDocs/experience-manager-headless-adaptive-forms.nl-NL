---
title: Aangepaste componenten gebruiken om een koploze vorm te genereren
description: Leer hoe u aangepaste componenten maakt en deze toewijst aan Headless Adaptive Forms-velden. Deze gids verklaart hoe te om componenten door gebiedstype en middeltype in kaart te brengen om douane het teruggeven en gedrag te bereiken.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: 5aba1821-35dc-4da4-b188-d4853d64d5ee
source-git-commit: 780f06a39c75dbf8795ac7a971150410ed7981e9
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 0%

---


# Aangepaste componenten gebruiken om een koploze vorm te genereren {#developing-for-headless-forms-using-your-own-components}

In Headless Adaptive Forms kunt u aangepaste componenten maken en implementeren om de weergave en functionaliteit van uw formulieren te definiëren. Terwijl de standaardcomponenten standaardgedrag verstrekken, zou u specifieke elementen UI of interactie-zoals een douane &quot;Aankondiging&quot;component of een gespecialiseerd gebied van de Handtekening van de Krabbels kunnen nodig hebben.

In dit artikel wordt u door het maken van een aangepaste React-component geleid en wordt deze toegewezen aan uw Headless Adaptive Form.

## &#x200B;1. Een aangepaste reacomponent maken

Maak eerst de component React die het formulierveld weergeeft. Deze component kan elke React-bibliotheek gebruiken (zoals de materiaalinterface, het Ant-ontwerp of uw eigen aangepaste stijlen).

Bijvoorbeeld, creeer een component van de douane **Aankondiging** die een read-only bericht met specifiek het stileren teruggeeft.

1. Navigeer naar de componentenmap van uw React-project (bijvoorbeeld `src/components`).
2. Maak bijvoorbeeld een nieuwe map en een nieuw bestand voor de component `Announcement/index.tsx` .
3. Implementeer de component. De toepassing moet `props` accepteren die compatibel is met de Forms-runtime zonder koptekst (doorgaans de status van het veld ontvangen).

```tsx
import React from 'react';
import { useRuleEngine } from '@aemforms/af-react-renderer';
import { FieldJson, State } from '@aemforms/af-core';

const Announcement = function (props: State<FieldJson>) {
    // The useRuleEngine hook connects the component to the form logic
    const [state, handlers] = useRuleEngine(props);

    if (!state.visible) {
        return null;
    }

    return (
        <div className="custom-announcement" style={{ border: '1px solid #ccc', padding: '10px', backgroundColor: '#f9f9f9' }}>
            <h3>{state?.label?.value}</h3>
            <p>{state?.default}</p>
        </div>
    );
}

export default Announcement;
```

## &#x200B;2. De aangepaste component toewijzen

Als u de aangepaste component wilt gebruiken, moet u deze toewijzen in het `mappings.ts` -bestand. De Forms-runtime zonder koptekst gebruikt deze toewijzing om te bepalen welke React-component moet worden gerenderd voor elk veld in het formulier JSON.

Er zijn twee primaire manieren om componenten in kaart te brengen: door **Type van Gebied** of door **Type van Middel**.

### Toewijzing op veldtype

De standaardtoewijzing is gebaseerd op de eigenschap `fieldType` in het formulier-JSON (bijvoorbeeld `text-input` , `checkbox` , `button` ). Dit is nuttig wanneer u *alle* instanties van een standaardcomponent met uw douaneversie wilt vervangen.

1. Open `src/utils/mappings.ts` (of waar uw toewijzingen zijn gedefinieerd).
2. Importeer uw aangepaste component.
3. Voeg het toe aan het toewijzingsobject met `fieldType` als toets.

```typescript
import { mappings } from "@aemforms/af-react-components";
import Announcement from "../components/Announcement";

const customMappings: any = {
  ...mappings,
  "text-input": Announcement // This would replace ALL text-input fields (use with caution)
};

export default customMappings;
```

### Toewijzing per brontype (aangepaste componenten)

Als u een douanecomponent in AEM (b.v., een &quot;Aankondiging&quot;component die een standaardcomponent van de Tekst uitbreidt) hebt gecreeerd en u *slechts* wilt teruggeven die specifieke component verschillend in uw React app, u het door zijn **Type van Middel** of een uniek herkenningsteken in kaart zou moeten brengen.

Deze benadering staat u toe om standaardcomponenten te hebben van de Tekst die normaal worden teruggegeven, terwijl uw douane &quot;Aankondiging&quot;component uw gespecialiseerde implementatie van het Reageren gebruikt.

1. Identificeer het unieke herkenningsteken voor uw component. In de Headless Form JSON vindt u dit vaak in de eigenschap `:type` of een aangepaste `fieldType` , indien geconfigureerd.
2. Voeg de toewijzing toe gebruikend dit herkenningsteken.

```typescript
import { mappings } from "@aemforms/af-react-components";
import Announcement from "../components/Announcement";

const customMappings: any = {
  ...mappings,
  // Map by resource type or custom identifier
  "my-project/components/announcement": Announcement
};

export default customMappings;
```

> **Nota:** zorg ervoor dat uw model van de Vorm van AEM correcte `:type` of herkenningsteken uitvoert die de sleutel aanpast u in `mappings.ts` gebruikt.

## &#x200B;3. De toewijzingen toepassen

Ten slotte moet u ervoor zorgen dat de instantie Koploos formulier deze aangepaste toewijzingen gebruikt.

```tsx
import React from 'react';
import { AdaptiveForm } from '@aemforms/af-react-renderer';
import customMappings from './utils/mappings';
import formJSON from './form-def.json';

function App() {
  return (
    <AdaptiveForm
      formJson={formJSON}
      mappings={customMappings}
    />
  );
}

export default App;
```

Door deze stappen te volgen kunt u de mogelijkheden van uw Headless Adaptive Forms uitbreiden met onderdelen die voldoen aan uw specifieke ontwerp- en functionele vereisten.
