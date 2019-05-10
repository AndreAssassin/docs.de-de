---
title: Modernisieren Ihrer Apps mit Überwachung und Telemetrie
description: Modernisieren vorhandener .NET-Anwendungen mit Azure-Cloud und Windows-Containern | Modernisieren Sie Ihre apps mit Überwachung und Telemetrie
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/30/2018
ms.openlocfilehash: a8135031d2879ff377881d246c532573a2149fe7
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64611660"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="5a501-103">Modernisieren Ihrer Apps mit Überwachung und Telemetrie</span><span class="sxs-lookup"><span data-stu-id="5a501-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="5a501-104">Wenn Sie eine Anwendung in der Produktion ausführen, ist es wichtig, dass Sie Erkenntnisse zur Leistung Ihrer Anwendung haben.</span><span class="sxs-lookup"><span data-stu-id="5a501-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="5a501-105">Wird auf einer hohen Ebene ausgeführt?</span><span class="sxs-lookup"><span data-stu-id="5a501-105">Is it performing at a high level?</span></span> <span data-ttu-id="5a501-106">Erhalten Benutzer Fehler, oder ist die Anwendung, stabil und zuverlässig?</span><span class="sxs-lookup"><span data-stu-id="5a501-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="5a501-107">Sie benötigen die umfassenden Leistungsüberwachungsfunktionen, leistungsstarke Warnungen und Dashboards, um sicherzustellen, dass Ihre Anwendung verfügbar sind und wie erwartet ist.</span><span class="sxs-lookup"><span data-stu-id="5a501-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="5a501-108">Sie müssen auch in der Lage, schnell angezeigt werden, wenn ein Problem vorliegt, stellen Sie fest, wie viele Kunden betroffen sind, und führen eine Analyse der Grundursache und beheben Sie das Problem.</span><span class="sxs-lookup"><span data-stu-id="5a501-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="5a501-109">Überwachen Sie Ihre Anwendung mit Application Insights</span><span class="sxs-lookup"><span data-stu-id="5a501-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="5a501-110">Application Insights ist ein erweiterbarer Application Performance Management (APM), Dienst für Webentwickler, die auf mehreren Plattformen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="5a501-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="5a501-111">Verwenden sie zum Überwachen Ihrer aktiven Webanwendung.</span><span class="sxs-lookup"><span data-stu-id="5a501-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="5a501-112">Application Insights erkennt automatisch leistungsanomalien.</span><span class="sxs-lookup"><span data-stu-id="5a501-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="5a501-113">Sie enthält leistungsstarke Analysetools, denen Probleme diagnostizieren und besser zu verstehen, was Benutzer mit Ihrer app tun.</span><span class="sxs-lookup"><span data-stu-id="5a501-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="5a501-114">Application Insights wurde entwickelt, können Sie kontinuierlich verbessern von Leistung und benutzerfreundlichkeit.</span><span class="sxs-lookup"><span data-stu-id="5a501-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="5a501-115">Dies funktioniert für apps auf einer Vielzahl von Plattformen, einschließlich Node.js, .NET und J2EE, gibt an, ob lokal gehostet oder in der Cloud.</span><span class="sxs-lookup"><span data-stu-id="5a501-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="5a501-116">Application Insights lässt sich in Ihre DevOps-Prozesse integrieren und verfügt über Verbindungspunkte mit einer Vielzahl von Entwicklungstools.</span><span class="sxs-lookup"><span data-stu-id="5a501-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="5a501-117">Abbildung 4-10 zeigt ein Beispiel wie Application Insights für Ihre Anwendung überwacht und wie sie gewinnen Sie wichtige an ein Dashboard angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5a501-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights-Überwachung-dashboard](./media/image10.png)

> <span data-ttu-id="5a501-119">**Abbildung 4-10.**</span><span class="sxs-lookup"><span data-stu-id="5a501-119">**Figure 4-10.**</span></span> <span data-ttu-id="5a501-120">Application Insights-Überwachung-dashboard</span><span class="sxs-lookup"><span data-stu-id="5a501-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="5a501-121">Überwachen Sie Ihre Docker-Infrastruktur mit Log Analytics und der containerüberwachungslösung</span><span class="sxs-lookup"><span data-stu-id="5a501-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="5a501-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) ist Teil der [Microsoft Azure insgesamt überwachungslösung](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span><span class="sxs-lookup"><span data-stu-id="5a501-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="5a501-123">Es gibt auch einen Dienst [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span><span class="sxs-lookup"><span data-stu-id="5a501-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="5a501-124">Log Analytics überwacht Cloud und lokalen Umgebungen (für lokale OMS) zur Gewährleistung der Verfügbarkeit und Leistung.</span><span class="sxs-lookup"><span data-stu-id="5a501-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="5a501-125">Er sammelt Daten, die von Ressourcen in Ihren cloudbasierten und lokalen Umgebungen sowie von anderen Überwachungstools, um Analysen für mehrere Datenquellen ermöglichen generiert.</span><span class="sxs-lookup"><span data-stu-id="5a501-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="5a501-126">In Bezug auf Azure-Infrastrukturprotokolle, Log Analytics, als Azure-Dienst erfasst Protokoll- und Metrikdaten Daten aus anderen Azure-Diensten (über [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure-VMs, Docker-Containern und lokalen oder anderen cloudinfrastrukturen.</span><span class="sxs-lookup"><span data-stu-id="5a501-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="5a501-127">Log Analytics bietet flexible protokollsuche sowie außerhalb der Box-Analyse auf diesen Daten.</span><span class="sxs-lookup"><span data-stu-id="5a501-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="5a501-128">Es bietet umfassende Tools können Sie quellenübergreifenden Datenanalyse, es erlaubt komplexe Abfragen in allen Protokollen und sie können proaktiv Warnungen ausgeben auf festgelegten Bedingungen basieren.</span><span class="sxs-lookup"><span data-stu-id="5a501-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="5a501-129">Sie können sogar benutzerdefinierte Daten in das zentrale Repository für Log Analytics sammeln, können Sie Abfragen und visualisieren.</span><span class="sxs-lookup"><span data-stu-id="5a501-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="5a501-130">Sie können auch Log Analytics integrierten Lösungen sofort Einblicke in die Sicherheit und Funktionalität Ihrer Infrastruktur nutzen.</span><span class="sxs-lookup"><span data-stu-id="5a501-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="5a501-131">Sie können Zugriff auf Log Analytics über das OMS-Portal oder Azure-Portal, der in einem beliebigen Browser ausgeführt wird, und geben Sie den Zugriff auf Konfigurationseinstellungen und verschiedene Tools zum Analysieren und über die gesammelten Daten dienen.</span><span class="sxs-lookup"><span data-stu-id="5a501-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="5a501-132">Die [containerüberwachungslösung](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) im Log Analytics können Sie anzeigen und Verwalten Ihrer Docker- und Windows-Container-Hosts an einem zentralen Ort.</span><span class="sxs-lookup"><span data-stu-id="5a501-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="5a501-133">Die Lösung zeigt, welche Container ausgeführt wird, welches containerimage sie ausgeführt, und wo Container ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5a501-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="5a501-134">Sie können ausführliche Überwachungsinformationen, einschließlich der Befehle, die mit Containern verwendet werden, anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a501-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="5a501-135">Sie können Container auch beheben, indem anzeigen und Durchsuchen zentralisierte Protokolle, ohne eine Remoteanzeige der Docker- oder Windows-Hosts.</span><span class="sxs-lookup"><span data-stu-id="5a501-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="5a501-136">Sie können Container suchen, die Störungen verursachen und übermäßig viele Ressourcen, die auf einem Host sein können.</span><span class="sxs-lookup"><span data-stu-id="5a501-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="5a501-137">Darüber hinaus können Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen, für Container anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a501-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="5a501-138">Auf Computern unter Windows können Sie zu zentralisieren und vergleichen Sie Protokolle von Windows Server-, Hyper-V und Docker-Containern.</span><span class="sxs-lookup"><span data-stu-id="5a501-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="5a501-139">Die Lösung unterstützt die folgenden containerorchestratoren:</span><span class="sxs-lookup"><span data-stu-id="5a501-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="5a501-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="5a501-140">Docker Swarm</span></span>

- <span data-ttu-id="5a501-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="5a501-141">DC/OS</span></span>

- <span data-ttu-id="5a501-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="5a501-142">Kubernetes</span></span>

- <span data-ttu-id="5a501-143">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="5a501-143">Service Fabric</span></span>

- <span data-ttu-id="5a501-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="5a501-144">Red Hat OpenShift</span></span>

<span data-ttu-id="5a501-145">Abbildung 4-11 zeigt die Beziehungen zwischen verschiedenen containerhosts und Agents und OMS.</span><span class="sxs-lookup"><span data-stu-id="5a501-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics containerüberwachungslösung](./media/image11.png)

> <span data-ttu-id="5a501-147">**Abbildung 4-11.**</span><span class="sxs-lookup"><span data-stu-id="5a501-147">**Figure 4-11.**</span></span> <span data-ttu-id="5a501-148">Log Analytics containerüberwachungslösung</span><span class="sxs-lookup"><span data-stu-id="5a501-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="5a501-149">Sie können die Log Analytics containerüberwachungslösung zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="5a501-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="5a501-150">Informationen über alle containerhosts an einem zentralen Ort anzeigen.</span><span class="sxs-lookup"><span data-stu-id="5a501-150">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="5a501-151">Wissen, welche Container ausgeführt wird, welches Bild sie ausgeführt, und, in dem sie ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5a501-151">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="5a501-152">Finden Sie in einen Audit-Trail für Aktionen in Containern.</span><span class="sxs-lookup"><span data-stu-id="5a501-152">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="5a501-153">Problembehandlung bei anzeigen und Durchsuchen zentralisierter Protokolle ohne Remoteanmeldung auf den Docker-Hosts.</span><span class="sxs-lookup"><span data-stu-id="5a501-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="5a501-154">Container, die möglicherweise "noisy Neighbors", und nutzen übermäßig viele Ressourcen auf einem Host zu finden.</span><span class="sxs-lookup"><span data-stu-id="5a501-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="5a501-155">Zeigen Sie die zentrale CPU, Arbeitsspeicher, Speicher und Netzwerkauslastung und Leistungsinformationen, für Container.</span><span class="sxs-lookup"><span data-stu-id="5a501-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="5a501-156">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="5a501-156">Additional resources</span></span>

- <span data-ttu-id="5a501-157">**Übersicht über die Überwachung in Microsoft Azure**</span><span class="sxs-lookup"><span data-stu-id="5a501-157">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="5a501-158">**Was ist Application Insights?**</span><span class="sxs-lookup"><span data-stu-id="5a501-158">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="5a501-159">**Was ist Log Analytics?**</span><span class="sxs-lookup"><span data-stu-id="5a501-159">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="5a501-160">**Containerüberwachungslösung in Azure Monitor**</span><span class="sxs-lookup"><span data-stu-id="5a501-160">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="5a501-161">**Übersicht über Azure Monitor**</span><span class="sxs-lookup"><span data-stu-id="5a501-161">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="5a501-162">**Was ist die Operations Management Suite (OMS)?**</span><span class="sxs-lookup"><span data-stu-id="5a501-162">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- <span data-ttu-id="5a501-163">**Überwachung von Windows Server-Containern in Service Fabric mit OMS**</span><span class="sxs-lookup"><span data-stu-id="5a501-163">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
><span data-ttu-id="5a501-164">[Zurück](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[Weiter](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="5a501-164">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
