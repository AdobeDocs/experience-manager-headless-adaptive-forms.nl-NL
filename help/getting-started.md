---
title: Aan de slag met Headless Adaptive Forms
description: Aan de slag met Headless Adaptive Forms
keywords: koploze, adaptieve vorm, zelfstudie
hide: true
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 0%

---


# Aan de slag met Headless Adaptive Forms

Deze zelfstudie biedt u een end-to-end framework om een Headless adaptive-formulier te maken. De zelfstudie is ingedeeld in een gebruikscase en meerdere hulplijnen. Met elke handleiding kunt u nieuwe functies toevoegen aan het adaptieve formulier zonder koptekst dat in deze zelfstudie wordt gemaakt. U hebt na elke handleiding een functionerend, hoofdloos adaptief formulier. Aan het einde van deze zelfstudie moet u het volgende kunnen doen:

* Een hoofdloos adaptief formulier maken
* Bedrijfsregels toevoegen aan uw formulier
* Gebruikersinterface voor Google-materiaal gebruiken om formulier te stijlëren
* Het formulier vooraf invullen
* Uw formulier insluiten op een webpagina

U gaat ook een beter begrip opbouwen van de architectuur, beschikbare artefacten en JSON-structuur van Headless adaptieve formulieren.

**de reis begint met het leren van het gebruiksgeval**:

Raya Tan, lid van het ministerie van Buitenlandse Zaken van een land dat bekend staat om zijn natuurlijke schoonheid en bloeiende toeristische economie, houdt toezicht op de verspreiding van visumaanvragen onder toeristen. Deze formulieren zijn beschikbaar op de website van de afdeling, in systeemeigen mobiele apps en in PDF-indeling, met verschillende taalopties waaruit toeristen kunnen kiezen. Het kan echter lastig zijn om deze formulieren op verschillende platforms en technologieën te beheren en te schalen.

Om de doeltreffendheid en de flexibiliteit van hun visumaanvraagprocedure te verbeteren, heeft het ministerie van Buitenlandse Zaken besloten een aanpak te hanteren die zich zonder meer aanpast. Deze ontkoppelde architectuur scheidt de voorkant van de achterkant, waardoor u meer aanpassingen en schaalbaarheid kunt maken. De afdeling is van plan om de React componenten van Materiaal UI van Google te gebruiken om de gebruikerservaring van de formulieren te verbeteren. Het zal ook achterste mogelijkheden zoals het volgende gebruiken:

* Digitale handtekeningen
* Gegevensintegratie
* Bedrijfsprocesbeheer
* Document van opname
* Gebruiksanalyse

De populairste vorm onder toeristen is het formulier &quot;Contact opnemen&quot;, dat wordt gebruikt om verschillende vragen en vragen te stellen. Als zodanig heeft het ministerie van Buitenlandse Zaken ervoor gekozen om met dit formulier te beginnen met de aanpak van de Zwaardeloze adaptieve formulieren. Deze zelfstudie begeleidt u door het proces om het formulier Contact met ons maken te maken op basis van deze nieuwe architectuur. Het uiteindelijke resultaat ziet er als volgt uit:

![ Contact de Hoofdloze adaptieve vorm van de V.S. ](assets/contact-us-headless-adaptive-forms.png)