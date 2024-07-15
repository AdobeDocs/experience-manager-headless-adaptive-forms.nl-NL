---
title: Aan de slag met Headless Adaptive Forms
description: Aan de slag met Headless Adaptive Forms
keywords: koploze, adaptieve vorm, zelfstudie
hide: true
source-git-commit: 0127f8ddede38083f0932b0e8d7efdd0dd77c3a6
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 0%

---


# Aan de slag met Headless Adaptive Forms

Deze zelfstudie biedt u een end-to-end framework om een Headless adaptive-formulier te maken. De zelfstudie is ingedeeld in een gebruikscase en meerdere hulplijnen. Met elke handleiding kunt u nieuwe functies toevoegen aan het adaptieve formulier zonder koptekst dat in deze zelfstudie wordt gemaakt. U hebt na elke handleiding een functionerend, hoofdloos adaptief formulier. Aan het einde van deze zelfstudie kunt u het volgende doen:

* Een hoofdloos adaptief formulier maken
* Bedrijfsregels toevoegen aan uw formulier
* Gebruikersinterface voor Google-materiaal gebruiken om formulier te stijlëren
* Het formulier vooraf invullen 
* Uw formulier insluiten op een webpagina

U zult ook een beter begrip van architectuur, beschikbare artefacten, en structuur JSON van de Zwaardeloze adaptieve vormen bouwen.

**de reis begint met het leren van het gebruiksgeval**:

Raya Tan, lid van de buitenlandse afdeling van een land dat bekend staat om zijn natuurlijke schoonheid en bloeiende toeristische economie, houdt toezicht op de verspreiding van visumaanvragen onder toeristen. Deze formulieren zijn beschikbaar op de website van de afdeling, in systeemeigen mobiele apps en in PDF-indeling, met verschillende taalopties waaruit toeristen kunnen kiezen. Het kan echter lastig zijn om deze formulieren op verschillende platforms en technologieën te beheren en te schalen.

Om de doeltreffendheid en de flexibiliteit van hun visumaanvraagprocedure te verbeteren, heeft de buitenlandse afdeling besloten een aanpak te volgen die gericht is op het aanpassen van de formulieren zonder hoofdletters. Deze ontkoppelde architectuur scheidt de voorkant van de achterkant, waardoor u meer aanpassingen en schaalbaarheid kunt maken. De afdeling is van plan om de React componenten van Materiaal UI van Google te gebruiken om de gebruikerservaring van de formulieren te verbeteren, terwijl het gebruiken van achterste mogelijkheden zoals digitale handtekeningen, gegevensintegratie, bedrijfsprocesbeheer, document van verslag, en gebruiksanalyses.

De populairste vorm onder toeristen is het formulier &quot;Contact opnemen&quot;, dat wordt gebruikt om verschillende vragen en vragen te stellen. Als zodanig heeft de buitenlandse afdeling ervoor gekozen om met dit formulier te beginnen met het implementeren van de Headless Adaptive Form-benadering. Deze zelfstudie begeleidt u bij het maken van het formulier Contact opnemen met deze nieuwe architectuur. Het uiteindelijke resultaat zal er als volgt uitzien:

![ Contact de Hoofdloze adaptieve vorm van de V.S. ](assets/contact-us-headless-adaptive-forms.png)