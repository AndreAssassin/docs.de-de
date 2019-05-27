---
title: Entwicklungshandbuch für .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- .NET Framework, development guide
ms.assetid: 26e3d285-24c3-435c-a797-9fe5affb8525
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cc7a0991ae308f1c61026e946021d22da9a4bc3b
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65583532"
---
# <a name="net-framework-development-guide"></a><span data-ttu-id="166a9-102">Entwicklungshandbuch für .NET Framework</span><span class="sxs-lookup"><span data-stu-id="166a9-102">.NET Framework Development Guide</span></span>
<span data-ttu-id="166a9-103">In diesem Abschnitt werden das Erstellen, Konfigurieren, Debuggen, Speichern und Bereitstellen von .NET Framework-Apps beschrieben.</span><span class="sxs-lookup"><span data-stu-id="166a9-103">This section explains how to create, configure, debug, secure, and deploy your .NET Framework apps.</span></span> <span data-ttu-id="166a9-104">Der Abschnitt enthält auch Informationen über Technologiebereiche, wie dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="166a9-104">The section also provides information about technology areas such as dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="166a9-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="166a9-105">In This Section</span></span>  
 [<span data-ttu-id="166a9-106">Grundlagen der Anwendung</span><span class="sxs-lookup"><span data-stu-id="166a9-106">Application Essentials</span></span>](../../docs/standard/application-essentials.md)  
 <span data-ttu-id="166a9-107">Bietet Informationen über grundlegende App-Entwicklungsaufgaben, wie z. B. Programmieren mit App-Domänen und Assemblys, Verwenden von Attributen, Formatieren und Analysieren von Basistypen, Verwenden von Auflistungen, Behandeln von Ereignissen und Ausnahmen, Verwenden von Dateien und Datenstreams und Verwenden von Generics.</span><span class="sxs-lookup"><span data-stu-id="166a9-107">Provides information about basic app development tasks, such as programming with app domains and assemblies, using attributes, formatting and parsing base types, using collections, handling events and exceptions, using files and data streams, and using generics.</span></span>  
  
 [<span data-ttu-id="166a9-108">Daten und Modellierung</span><span class="sxs-lookup"><span data-stu-id="166a9-108">Data and Modeling</span></span>](../../docs/framework/data/index.md)  
 <span data-ttu-id="166a9-109">Enthält Informationen zum Zugreifen auf Daten mit ADO.NET, Language Integrated Query (LINQ), WCF-Datendienste und XML.</span><span class="sxs-lookup"><span data-stu-id="166a9-109">Provides information about how to access data using ADO.NET, Language Integrated Query (LINQ), WCF Data Services, and XML.</span></span>  
  
 [<span data-ttu-id="166a9-110">Clientanwendungen</span><span class="sxs-lookup"><span data-stu-id="166a9-110">Client Applications</span></span>](../../docs/framework/develop-client-apps.md)  
 <span data-ttu-id="166a9-111">Erläutert das Erstellen von Windows-basierten Apps mit Windows Presentation Foundation (WPF) oder mit Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="166a9-111">Explains how to create Windows-based apps by using Windows Presentation Foundation (WPF) or Windows Forms.</span></span>  
  
 [<span data-ttu-id="166a9-112">Webanwendungen mit ASP.NET</span><span class="sxs-lookup"><span data-stu-id="166a9-112">Web Applications with ASP.NET</span></span>](../../docs/framework/develop-web-apps-with-aspnet.md)  
 <span data-ttu-id="166a9-113">Enthält Links zu Informationen über die Verwendung von ASP.NET zum Erstellen von Web Apps für Unternehmen mit minimalem Programmieraufwand.</span><span class="sxs-lookup"><span data-stu-id="166a9-113">Provides links to information about using ASP.NET to build enterprise-class web apps with a minimum of coding.</span></span>  
  
 [<span data-ttu-id="166a9-114">Dienstorientierte Anwendungen mit WCF</span><span class="sxs-lookup"><span data-stu-id="166a9-114">Service-Oriented Applications with WCF</span></span>](../../docs/framework/wcf/index.md)  
 <span data-ttu-id="166a9-115">Erläutert die Verwendung von Windows Communication Foundation (WCF) zum Erstellen dienstorientierter Apps, die sicher und zuverlässig sind.</span><span class="sxs-lookup"><span data-stu-id="166a9-115">Describes how to use Windows Communication Foundation (WCF) to build service-oriented apps that are secure and reliable.</span></span>  
  
 <span data-ttu-id="166a9-116">[Erstellen von Workflows mit Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span><span class="sxs-lookup"><span data-stu-id="166a9-116">[Building workflows with Windows Workflow Foundation](windows-workflow-foundation/index.md)   </span></span>  
 <span data-ttu-id="166a9-117">Enthält Informationen zum Programmiermodell, zu Beispielen und Tools für die Verwendung von Windows Workflow Foundation (WF).</span><span class="sxs-lookup"><span data-stu-id="166a9-117">Provides information about the programming model, samples, and tools for using Windows Workflow Foundation (WF).</span></span>  

 [<span data-ttu-id="166a9-118">Windows-Dienstanwendungen</span><span class="sxs-lookup"><span data-stu-id="166a9-118">Windows Service Applications</span></span>](../../docs/framework/windows-services/index.md)  
 <span data-ttu-id="166a9-119">Erläutert die Verwendung von Visual Studio und .NET Framework zum Erstellen einer App, die als Dienst installiert wird, und zum Starten, Beenden und Steuern ihres Verhaltens.</span><span class="sxs-lookup"><span data-stu-id="166a9-119">Explains how you can use Visual Studio and the .NET Framework to create an app that is installed as a service, and start, stop, and otherwise control its behavior.</span></span>  
  
 [<span data-ttu-id="166a9-120">Parallel Processing, Concurrency, and Async Programming in .NET (Parallelverarbeitung, Parallelität und asynchrone Programmierung in .NET)</span><span class="sxs-lookup"><span data-stu-id="166a9-120">Parallel Processing, Concurrency, and Async Programming in .NET</span></span>](../../docs/standard/parallel-processing-and-concurrency.md)  
 <span data-ttu-id="166a9-121">Enthält Informationen über verwaltetes Threading, parallele Programmierung und Entwurfsmuster für die asynchrone Programmierung.</span><span class="sxs-lookup"><span data-stu-id="166a9-121">Provides information about managed threading, parallel programming, and asynchronous programming design patterns.</span></span>  
  
 [<span data-ttu-id="166a9-122">Netzwerkprogrammierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="166a9-122">Network Programming in the .NET Framework</span></span>](../../docs/framework/network-programming/index.md)  
 <span data-ttu-id="166a9-123">Beschreibt die erweiterbare und verwaltete Implementierung mit mehreren Ebenen für Internetdienste, die schnell und auf einfache Weise in Apps integriert werden können.</span><span class="sxs-lookup"><span data-stu-id="166a9-123">Describes the layered, extensible, and managed implementation of Internet services that you can quickly and easily integrate into your apps.</span></span>  
  
 <span data-ttu-id="166a9-124">[Konfigurieren von .NET Framework-Apps](configure-apps/index.md)  </span><span class="sxs-lookup"><span data-stu-id="166a9-124">[Configuring .NET Framework Apps](configure-apps/index.md)  </span></span>  
 <span data-ttu-id="166a9-125">Erläutert die Verwendung von Konfigurationsdateien zum Ändern von Einstellungen, ohne die .NET Framework-Apps neu kompilieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="166a9-125">Explains how you can use configuration files to change settings without having to recompile your .NET Framework apps.</span></span>  
  
 [<span data-ttu-id="166a9-126">Kompilieren von Apps mit .NET Native</span><span class="sxs-lookup"><span data-stu-id="166a9-126">Compiling Apps with .NET Native</span></span>](../../docs/framework/net-native/index.md)  
 <span data-ttu-id="166a9-127">Erläutert, wie Sie die [!INCLUDE[net_native](../../includes/net-native-md.md)]-Vorkompilierungstechnologie verwenden können, um Windows Store-Apps zu erstellen und bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="166a9-127">Explains how you can use the [!INCLUDE[net_native](../../includes/net-native-md.md)] precompilation technology to build and deploy Windows Store apps.</span></span> [!INCLUDE[net_native](../../includes/net-native-md.md)]<span data-ttu-id="166a9-128">kompiliert Apps, die in verwaltetem Code (C#) geschrieben sind und deren Ziel .NET Framework und dann die Umwandlung zu systemeigenem Code ist.</span><span class="sxs-lookup"><span data-stu-id="166a9-128">compiles apps that are written in managed code (C#) and that target the .NET Framework to native code.</span></span>  
  
 [<span data-ttu-id="166a9-129">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="166a9-129">Security</span></span>](../../docs/standard/security/index.md)  
 <span data-ttu-id="166a9-130">Enthält Informationen über die Klassen und Dienste in .NET Framework, die die sichere Appentwicklung erleichtern.</span><span class="sxs-lookup"><span data-stu-id="166a9-130">Provides information about the classes and services in the .NET Framework that facilitate secure app development.</span></span>  
  
 [<span data-ttu-id="166a9-131">Debuggen, Ablaufverfolgung und Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="166a9-131">Debugging, Tracing, and Profiling</span></span>](../../docs/framework/debug-trace-profile/index.md)  
 <span data-ttu-id="166a9-132">Erläutert, wie .NET Framework-Apps und die Appumgebung getestet und optimiert und wie Profile davon erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="166a9-132">Explains how to test, optimize, and profile .NET Framework apps and the app environment.</span></span> <span data-ttu-id="166a9-133">Dieser Abschnitt enthält Informationen für Administratoren und Entwickler.</span><span class="sxs-lookup"><span data-stu-id="166a9-133">This section includes information for administrators as well as developers.</span></span>  
  
 [<span data-ttu-id="166a9-134">Entwickeln für mehrere Plattformen</span><span class="sxs-lookup"><span data-stu-id="166a9-134">Developing for Multiple Platforms</span></span>](../../docs/standard/cross-platform/index.md)  
 <span data-ttu-id="166a9-135">Bietet Informationen zur Verwendung von .NET Framework zum Erstellen von Assemblys, die über mehrere Plattformen auf mehreren Geräten wie Telefone, Desktopcomputer und über das Internet freigegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="166a9-135">Provides information about how you can use the .NET Framework to build assemblies that can be shared across multiple platforms and multiple devices such as phones, desktop, and web.</span></span>  
  
 [<span data-ttu-id="166a9-136">Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="166a9-136">Deployment</span></span>](../../docs/framework/deployment/index.md)  
 <span data-ttu-id="166a9-137">Erläutert das Verpacken und Verteilen von .NET Framework-Apps und enthält Bereitstellungshandbücher für Entwickler und für Administratoren.</span><span class="sxs-lookup"><span data-stu-id="166a9-137">Explains how to package and distribute your .NET Framework app, and includes deployment guides for both developers and administrators.</span></span>  
  
 [<span data-ttu-id="166a9-138">Leistung</span><span class="sxs-lookup"><span data-stu-id="166a9-138">Performance</span></span>](../../docs/framework/performance/index.md)  
 <span data-ttu-id="166a9-139">Enthält Informationen über die Zwischenspeicherung, die verzögerte Initialisierung, Zuverlässigkeit und ETW-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="166a9-139">Provides information about caching, lazy initialization, reliability, and ETW events.</span></span>  
 
## <a name="reference"></a><span data-ttu-id="166a9-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="166a9-140">Reference</span></span>  
 [<span data-ttu-id="166a9-141">.NET Framework-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="166a9-141">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.7)  
 <span data-ttu-id="166a9-142">Stellt Syntax, Codebeispiele und Informationen zur Verwendung zu den einzelnen Klassen zur Verfügung, die in den .NET Framework-Namespaces enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="166a9-142">Supplies syntax, code examples, and usage information for each class that is contained in the .NET Framework namespaces.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="166a9-143">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="166a9-143">Related Sections</span></span>  
 [<span data-ttu-id="166a9-144">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="166a9-144">Getting Started</span></span>](../../docs/framework/get-started/index.md)  
 <span data-ttu-id="166a9-145">Stellt eine umfassende Übersicht über .NET Framework und Links zu zusätzlichen Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="166a9-145">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>  
  
 [<span data-ttu-id="166a9-146">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="166a9-146">What's New</span></span>](../../docs/framework/whats-new/index.md)  
 <span data-ttu-id="166a9-147">Beschreibt wichtige Funktionen und Änderungen in der neuesten Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="166a9-147">Describes key new features and changes in the latest version of the .NET Framework.</span></span> <span data-ttu-id="166a9-148">Enthält Listen von neuen und veralteten Typen und Membern sowie eine Anleitung für das Migrieren der Apps aus der früheren Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="166a9-148">Includes lists of new and obsolete types and members, and provides a guide for migrating your apps from the previous version of the .NET Framework.</span></span>  
  
 [<span data-ttu-id="166a9-149">Extras</span><span class="sxs-lookup"><span data-stu-id="166a9-149">Tools</span></span>](../../docs/framework/tools/index.md)  
 <span data-ttu-id="166a9-150">Beschreibt die Tools, die Sie beim Entwickeln, Konfigurieren und Bereitstellen von Apps mithilfe der .NET Framework-Technologien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="166a9-150">Describes the tools that help you develop, configure, and deploy apps by using .NET Framework technologies.</span></span>  
  
 [<span data-ttu-id="166a9-151">Beispiele und Tutorials</span><span class="sxs-lookup"><span data-stu-id="166a9-151">.NET samples and tutorials</span></span>](../samples-and-tutorials/index.md)  
 <span data-ttu-id="166a9-152">Hier finden Sie Links zu Beispielen und Tutorials, mit denen Sie mehr über .NET erfahren können.</span><span class="sxs-lookup"><span data-stu-id="166a9-152">Provides links to samples and tutorials that help you learn about .NET.</span></span>
