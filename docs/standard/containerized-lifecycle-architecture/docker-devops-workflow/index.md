---
title: Docker DevOps-Anwendungsworkflow mit Microsoft-Tools
description: Containerisierten Docker-Anwendungslebenszyklus mit Microsoft Platform und Tools, DevOps-Workflow mit Microsoft-tools
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 80acd58d08900da8e79f6b7388da3b10f9e4e566
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/17/2019
ms.locfileid: "59672302"
---
# <a name="docker-application-devops-workflow-with-microsoft-tools"></a>Docker DevOps-Anwendungsworkflow mit Microsoft-Tools

*Microsoft Visual Studio, Azure DevOps-Services, Team Foundation Server und Azure Monitor angeben, dass ein umfassendes Ökosystem für Entwicklungs- und IT-Betrieb, mit denen dem Team die Tools zum Verwalten von Projekten und schnell zu erstellen, testen und Bereitstellen von Containern Anwendungen.*

Mit Visual Studio und Azure DevOps-Dienste in der Cloud, zusammen mit Team Foundation Server lokal können Entwicklungsteams produktiv erstellen, testen und Freigeben von Anwendungen in Containern, die entweder Windows oder Linux als Ziel.

Microsoft-Tools können die Pipeline für spezifische Implementierungen von containeranwendungen automatisieren, Docker, .NET Core oder eine beliebige Kombination mit anderen Plattformen – von globalen Builds und fortlaufende Integration (CI) und Tests mit Azure DevOps-Services oder Team Foundation-Server, um Continuous Deployment (CD) für Docker-Umgebungen (Entwicklung, Staging, Produktion), und zum Übertragen von Analyseinformationen zu den Diensten an das Entwicklungsteam über Azure Monitor. Jeder Codecommit kann einen Build (CI) initiieren und die Dienste automatisch in bestimmten Containerumgebungen (CD) bereitstellen.

Entwickler und Tester können einfach und schnell produktionsähnliche Entwicklungs- und Testumgebungen basierend auf Docker bereitstellen, indem sie Vorlagen in Microsoft Azure verwenden.

Die Komplexität der Entwicklung von Containanwendungen nimmt abhängig von der Komplexität und Skalierbarkeit des Unternehmens stetig zu. Ein gutes Beispiel Teil dieser Komplexität sind Anwendungen, die basierend auf Microservices-Architekturen. Um in einer solchen Umgebung erfolgreich ausgeführt werden, muss das Projekt den gesamten Lebenszyklus automatisieren – nicht nur die Erstellung und Bereitstellung, sondern auch müssen Versionen verwalten und die Erfassung von Telemetriedaten. Azure DevOps-Dienste und Azure bieten die folgenden Funktionen:

- Azure DevOps-Services-Team Foundation Server quellcodeverwaltung (basierend auf Git oder Team Foundation Version Control), Agile Planung (Agile, Scrum und CMMI werden unterstützt), CI, Release Management und andere Tools für Agile-Teams.

- Azure DevOps-Services und Team Foundation Server umfassen ein leistungsstarkes und wachsendes Ökosystem der ersten und Drittanbieter-Erweiterungen mit denen Sie ganz einfach Erstellen einer CI, im Build, Test, Bereitstellung und release Management-Pipeline für Microservices.

- Ausführen von automatisierten Tests als Teil Ihrer Buildpipeline in Azure DevOps-Dienste.

- Azure DevOps-Dienste können ziehen Sie den Lebenszyklus von DevOps mit der Bereitstellung in Umgebungen mit mehreren, nicht nur für produktionsumgebungen, sondern auch für Tests, einschließlich A / B-Experimente, [Canary-Releases](https://martinfowler.com/bliki/CanaryRelease.html)und so weiter.

- Organisationen können einfach Docker-Container aus privaten Images, die in Azure Container Registry gespeichert sind, zusammen mit allen Abhängigkeiten von Azure-Komponenten (Daten, PaaS usw.) bereitstellen mithilfe von Azure Resource Manager-Vorlagen mit Tools, die sie bereits mit vertraut sind.

>[!div class="step-by-step"]
>[Zurück](../design-develop-containerized-apps/build-aspnet-core-applications-linux-containers-aks-kubernetes.md)
>[Weiter](docker-application-outer-loop-devops-workflow.md)
