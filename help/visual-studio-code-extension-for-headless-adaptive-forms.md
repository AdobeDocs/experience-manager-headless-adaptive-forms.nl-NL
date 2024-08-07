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
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 0%

---

# Microsoft Visual Studio Code-extensie voor adaptieve hoofdformulieren

Als u Microsoft® Visual Studio Code als winde gebruikt, kunt u de Adaptieve uitbreiding van Forms voor de Code van Microsoft Visual Studio gebruiken. De extensie:

* Voegt mogelijkheden IntelliSense voor Adaptive Forms aan de Code van Visual Studio toe
* Helpt de JSON-syntaxis te valideren en automatisch in te vullen voor componenten van Creless adaptieve formulieren
* Biedt een deelvenster waarmee u gemakkelijk door de structuur van een adaptief formulier zonder koptekst kunt navigeren
* Helpt een Headless adaptive-formulier te vertalen

<!-- 

The extension o easily navigate the structure 

Adobe provides an extension for Microsoft&reg; Visual Studio Code to make it easier for you to navigate structure and develop Headless adaptive forms in Visual Studio Code. The extension adds Adaptive Forms related IntelliSense capabilities and helps auto-complete Headless adaptive forms JSON syntax. It also adds a panel, titled Forms Tree, to help navigate structure of Headless adaptive form. 

-->

## Vereisten

* De download en installeert [ Code 1.62.0 van Microsoft Visual Studio of later ](https://code.visualstudio.com/docs/supporting/FAQ#_how-do-i-find-the-version). Als u een oudere versie of geen geïnstalleerde versie hebt, download de recentste versie van [ de Website van Microsoft ](https://code.visualstudio.com/docs/setup/setup-overview). Om Visual Studio van bevellijn op Apple macOS te gebruiken, zie [ Lancering van de bevellijn ](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line).
* Download de [ Adaptieve uitbreiding van de vormenbouwer ](/help/assets/adaptive-form-builder-0.12.0.vsix).

## De extensie installeren

1. Open bevelherinnering en navigeer aan de folder die het gedownloade uitbreidingsdossier, *adaptive-form-builder [ versie ] .vsix* bevat.

1. Voer de volgende opdracht uit om de extensie te installeren:

   `code -–install-extension adaptive-form-builder-0.12.0.vsix`

   <br>

   ![ Installerend uitbreiding ](/help/assets/install-extension.png)


   Voor informatie over .vsix dossiers, zie [ de Hulp van de Code van Microsoft Visual Studio ](https://code.visualstudio.com/docs/editor/extension-marketplace#_install-from-a-vsix).
