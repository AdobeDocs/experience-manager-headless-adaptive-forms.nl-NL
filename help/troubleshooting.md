---
title: Problemen oplossen met Forms zonder hoofdfunctie
description: Problemen oplossen met Forms zonder hoofdfunctie
keywords: hoofdloos, adaptief formulier, probleemoplossing
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: bfb7e688-d2be-4aaa-ac9b-147cbd74b516
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 0%

---

# Problemen oplossen

## Kan het project Archetype niet implementeren in de lokale ontwikkelomgeving

### Probleem

Wanneer u de opdracht `mvn -PautoInstallPackage clean install` of gelijkaardige bevelen om een AEM project op te stellen Archeype, ontbreekt het project om op te stellen.

### Reden

Dit kan gebeuren door een niet-ondersteunde versie of beschadigde installatie van node.js of NPM.

### Oplossing

1. Volledig [bestaande installaties van Node.JS verwijderen](https://khushwantsehgal.wordpress.com/2022/06/28/how-to-remove-node-js-completely-from-windows-10/) uit uw omgeving.

1. Installeer Node.JS 16.13.0 of later met NPM.

1. Start de computer opnieuw op.


## De `mvn clean install` command mislukt

### Probleem

Wanneer u de opdracht `mvn clean install` of gelijkaardige bevelen om een AEM project op te stellen Archeype, ontbreekt het bevel om te lopen.

### Reden

Dit kan gebeuren als Git niet is geïnstalleerd.

### Oplossing

Download en installeer de [nieuwste release van Git](https://git-scm.com/downloads). Als u nog geen ervaring hebt met Git, raadpleegt u [Git installeren](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
