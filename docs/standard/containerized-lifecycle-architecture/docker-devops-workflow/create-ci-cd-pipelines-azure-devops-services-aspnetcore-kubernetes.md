---
title: Schritte im Outer-Loop-DevOps-Workflow für eine Docker-Anwendung
description: Lebenszyklus von Docker-Containeranwendungen mit der Microsoft-Plattform und Tools
ms.date: 02/15/2019
ms.openlocfilehash: 9fdc5acfd375e4f2266859f061ef1c854286b914
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65644984"
---
# <a name="creating-cicd-pipelines-in-azure-devops-services-for-a-net-core-20-application-on-containers-and-deploying-to-a-kubernetes-cluster"></a>Erstellen von CI/CD-Pipelines in Azure DevOps Services für eine .NET Core 2.0-Anwendung auf Containern und anschließendes Bereitstellen für ein Kubernetes-Cluster

In Abbildung 5-12 sehen Sie die End-to-End-DevOps-Szenario für die Verwaltung von Code, Code-Kompilierung, Docker-Images erstellen, Docker-Images per Push übertragen, um eine Docker-Registrierung und schließlich auf die Bereitstellung in einem Kubernetes-Cluster in Azure.

![Workflow: Startet in den Entwicklungscomputer. Mithilfe von Push übertragen, in einem Repository beginnt die Build/CI-Aufgabe, die mithilfe eines benutzerdefinierten Images, das gesendet, um eine Docker-Registrierung, und klicken Sie dann von der CD/deploy-Task, schließlich pushen in AKS.](media/docker-workflow-ci-cd-aks.png)

**Abbildung 5-12**. CI/CD-Szenario erstellen Docker-Images und Bereitstellen eines Kubernetes-Clusters in Azure

Es ist wichtig, hervorzuheben, dass die zwei Pipelines, Build/CI und Release/CD, über die Docker-Registrierung (z. B. Docker Hub oder Azure Container Registry-Instanz) verbunden sind. Die Docker-Registrierung ist eine der wichtigsten Unterschiede im Vergleich zu einem traditionellen CI-/CD-Prozess ohne Docker.

Wie in Abbildung 5-13 dargestellt, ist die erste Phase der Build/CI-Pipeline. In Azure DevOps-Dienste können Sie Build/CI-Pipelines erstellen, die Kompilieren des Codes, die Docker-Images erstellen und per push an eine Docker-Registrierung, wie Docker Hub oder Azure Container Registry-Instanz wird.

![Browseransicht des Azure DevOps, Builddefinition, Prozess-Aufgabe.](media/build-ci-pipeline-azure-devops-push-to-docker-registry.png)

**Abbildung 5-13**. Build/CI-Pipeline in Azure DevOps-Docker-Images erstellen, und Images per Push übertragen, in einem Docker-Registrierung

In der zweite Phase wird zum Erstellen einer Bereitstellung/Release-Pipeline. In Azure DevOps-Dienste können Sie einfach eine Bereitstellungspipeline, die für einen Kubernetes-Cluster mit den Kubernetes-Aufgaben für Azure DevOps-Dienste, wie in Abbildung 5-14 dargestellt erstellen.

![Browseransicht der Azure DevOps, stellen Sie in Kubernetes-Aufgabendefinition.](media/release-cd-pipeline-azure-devops-deploy-to-kubernetes.png)

**Abbildung 5-14**. Release/CD-Pipeline in Azure DevOps-Dienste in einem Kubernetes-Cluster bereitstellen

> [! Exemplarische Vorgehensweise] eShopModernized für Kubernetes bereitstellen:
>
> Eine ausführliche exemplarische Vorgehensweise zur Azure DevOps-CI/CD-Pipelines Bereitstellen in Kubernetes, siehe diesen Beitrag: \
><https://github.com/dotnet-architecture/eShopModernizing/wiki/04.-How-to-deploy-your-Windows-Containers-based-apps-into-Kubernetes-in-Azure-Container-Service-(Including-CI-CD)>

>[!div class="step-by-step"]
>[Zurück](docker-application-outer-loop-devops-workflow.md)
>[Weiter](../run-manage-monitor-docker-environments/index.md)
