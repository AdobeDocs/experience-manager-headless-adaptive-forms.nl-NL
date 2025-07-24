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
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 0%

---

# Problemen oplossen

## Kan het project Archetype niet implementeren in de lokale ontwikkelomgeving

### Probleem

Wanneer u de `mvn -PautoInstallPackage clean install` of gelijkaardige bevelen gebruikt om een project van het Archetype van AEM op te stellen, ontbreekt het project om op te stellen.

### Reden

Dit kan gebeuren door een niet-ondersteunde versie of een beschadigde installatie van `node.js` of `NPM` .

### Oplossing

1. Volledig [ verwijdert huidige installaties van Node.JS ](https://khushwantsehgal.wordpress.com/2022/06/28/how-to-remove-node-js-completely-from-windows-10/) uit uw milieu.

1. Installeer `node.JS 16.13.0` of hoger met `NPM` .

1. Start de computer opnieuw op.


## De opdracht `mvn clean install` kan niet worden uitgevoerd

### Probleem

Wanneer u de opdrachten `mvn clean install` of vergelijkbaar gebruikt om een AEM Archetype-project te implementeren, wordt de opdracht niet uitgevoerd.

### Reden

Dit kan gebeuren als Git niet is geïnstalleerd.

### Oplossing

Download en installeer de [ recentste versie van Git ](https://git-scm.com/downloads). Als u aan Git nieuw bent, zie [ Installerend Git ](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git).
