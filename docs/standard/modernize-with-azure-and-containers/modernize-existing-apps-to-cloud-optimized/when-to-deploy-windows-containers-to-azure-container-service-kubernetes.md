---
title: Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: 0b803b104f905fddac7939d7b070c206aabffeda
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62011969"
---
# <a name="when-to-deploy-windows-containers-to-azure-container-service-that-is-kubernetes"></a>Beim Bereitstellen von Windows-Containern in Azure Container Service (d.h. Kubernetes)

Azure Container Service optimiert die Konfiguration beliebter Open-Source-Tools und Technologien speziell für Azure. Sie erhalten eine offene Lösung, die Portabilität für Ihre Container sowohl für die Anwendungskonfiguration bietet. Sie wählen die Größe, die Anzahl der Hosts und der orchestrationstools. Azure Container Service übernimmt die Infrastruktur für Sie.

Wenn Sie bereits mit Open Source-orchestratoren wie Kubernetes, Docker Swarm oder DC/OS arbeiten, müssen Sie nicht so ändern Sie bestehende Verwaltungspraktiken um containerworkloads in die Cloud zu verschieben. Verwenden Sie die Application-Management-Tools, denen Sie bereits kennen und über die API-Standardendpunkte für den Orchestrator Ihrer Wahl verbinden.

Alle diese orchestratoren sind ausgereifte Umgebungen auf, wenn Sie Linux-Docker-Container verwenden, aber möglicherweise nur in der Vorschauphase für Windows-Container.

Z. B. in Kubernetes Unterstützung für Container systemeigen (Bewohner erster Klasse), also mithilfe von Windows-Containern in Kubernetes eignet sich auch (in der Vorschau in ACS ab Frühjahr 2018).

Wichtiger Hinweis: Die hoch entwickelten und "Weitere PaaS" ACS (Azure Container Service) für Kubernetes-Version befindet sich AKS (Azure Kubernetes Service), Windows-Container werden Q2 2018 weiterhin nicht unterstützt, jedoch in Kürze unterstützt.

>[!div class="step-by-step"]
>[Zurück](when-to-deploy-windows-containers-to-service-fabric.md)
>[Weiter](choosing-azure-compute-options-for-container-based-applications.md)