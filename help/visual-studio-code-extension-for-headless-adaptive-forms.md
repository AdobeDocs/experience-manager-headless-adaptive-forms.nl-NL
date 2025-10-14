---
title: Visual Studio Code-extensie voor adaptieve formulieren zonder koptekst
description: Visual Studio Code-extensie voor adaptieve formulieren zonder koptekst
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: hoofdloze, adaptieve vormen, de uitbreiding van de Code van Visual Studio
hide: false
exl-id: 11960e91-6c09-48d4-9d57-37537f808cd4
source-git-commit: 28792fe1690e68cd301a0de2ce8bff53fae1605f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 0%

---

# Microsoft Visual Studio Code-extensie voor adaptieve hoofdformulieren

Als u de Code van Microsoft® Visual Studio als winde (Geïntegreerde Ontwikkelomgeving) gebruikt, kunt u de Adaptieve uitbreiding van Forms voor de Code van Microsoft Visual Studio gebruiken. De extensie:

* Voegt mogelijkheden IntelliSense voor Adaptive Forms aan de Code van Visual Studio toe.
* Hiermee kunt u de JSON-syntaxis valideren en automatisch aanvullen voor componenten van Creative Cloud-adaptieve formulieren.
* Met dit deelvenster kunt u eenvoudig door een deelvenster navigeren in de structuur van een adaptief formulier zonder kop.
* Hiermee kunt u een Headless adaptive-formulier vertalen.

<!-- 

The extension o easily navigate the structure 

Adobe provides an extension for Microsoft&reg; Visual Studio Code to make it easier for you to navigate structure and develop Headless adaptive forms in Visual Studio Code. The extension adds Adaptive Forms related IntelliSense capabilities and helps auto-complete Headless adaptive forms JSON syntax. It also adds a panel, titled Forms Tree, to help navigate structure of Headless adaptive form. 

-->

## Vereisten

* De download en installeert [&#x200B; Code 1.62.0 van Microsoft Visual Studio of later &#x200B;](https://code.visualstudio.com/docs/supporting/FAQ#_how-do-i-find-the-version). Als u een oudere versie of geen geïnstalleerde versie hebt, download de recentste versie van de [&#x200B; Website van Microsoft &#x200B;](https://code.visualstudio.com/docs/setup/setup-overview). Om Visual Studio van de bevellijn op Apple macOS te gebruiken, zie [&#x200B; Lancering van de bevellijn &#x200B;](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).
* Download de [&#x200B; Adaptieve uitbreiding van de vormenbouwer &#x200B;](/help/assets/adaptive-form-builder-0.12.0.vsix).

## De extensie installeren

1. Open de bevelherinnering en navigeer aan de folder die het gedownloade uitbreidingsdossier, *adaptive-form-builder [ versie ] .vsix* bevat.

1. Voer de volgende opdracht uit om de extensie te installeren:

   `code -–install-extension adaptive-form-builder-0.12.0.vsix`

   <br>

   ![&#x200B; Installerend uitbreiding &#x200B;](/help/assets/install-extension.png)


   Voor informatie over .vsix dossiers, zie [&#x200B; de Hulp van de Code van Microsoft Visual Studio &#x200B;](https://code.visualstudio.com/docs/configure/extensions/extension-marketplace#_install-from-a-vsix).
