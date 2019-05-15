---
title: .NET Framework-Dokumentation
ms.date: 04/02/2019
ms.custom: updateeachrelease
f1_keywords:
- f61f02f2-2f20-483d-8f56-a9c8f3a54986
helpviewer_keywords:
- .NET Framework, documentation
- documentation, .NET Framework
ms.assetid: f61f02f2-2f20-483d-8f56-a9c8f3a54986
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d93dea42dbb854d8d52bd5cf3e54d1ce0d892d6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635531"
---
# <a name="net-framework-guide"></a><span data-ttu-id="e7744-102">.NET Framework – Leitfaden</span><span class="sxs-lookup"><span data-stu-id="e7744-102">.NET Framework Guide</span></span>

> [!NOTE]
> <span data-ttu-id="e7744-103">Dieser .NET Framework-Inhaltssatz enthält Informationen für die .NET Framework-Versionen 4.5 bis 4.8.</span><span class="sxs-lookup"><span data-stu-id="e7744-103">This .NET Framework content set includes information for .NET Framework versions 4.5 through 4.8.</span></span> <span data-ttu-id="e7744-104">Weitere Informationen zum Herunterladen von .NET Framework finden Sie unter [Installieren von .NET Framework](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-104">To download the .NET Framework, see [Installing the .NET Framework](./install/guide-for-developers.md).</span></span> <span data-ttu-id="e7744-105">Eine Liste der neuen Features und Änderungen in .NET Framework finden Sie unter [Neuerungen in .NET Framework](./whats-new/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-105">For a list of new features and changes in the NET Framework, see [What's New in the .NET Framework](./whats-new/index.md).</span></span> <span data-ttu-id="e7744-106">Eine Liste der unterstützten Plattformen finden Sie unter [Systemanforderungen für .NET Framework](./get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-106">For a list of supported platforms, see [.NET Framework System Requirements](./get-started/system-requirements.md).</span></span> <span data-ttu-id="e7744-107">Dokumentation zu früheren Versionen von .NET Framework finden Sie unter [Dokumentation zu vorherigen .NET Framework-Versionen](https://docs.microsoft.com/previous-versions/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="e7744-107">For documentation about older versions of the .NET Framework, see [.NET previous versions documentation](https://docs.microsoft.com/previous-versions/dotnet/).</span></span>

<span data-ttu-id="e7744-108">.NET Framework ist eine Entwicklungsplattform zum Erstellen von Apps für Web, Windows, Windows Phone, Windows Server und Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="e7744-108">The .NET Framework is a development platform for building apps for web, Windows, Windows Phone, Windows Server, and Microsoft Azure.</span></span> <span data-ttu-id="e7744-109">Es besteht aus der Common Language Runtime (CLR) und der .NET Framework-Klassenbibliothek, die eine breite Palette von Funktionen sowie Unterstützung für viele Branchenstandards bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e7744-109">It consists of the common language runtime (CLR) and the .NET Framework class library, which includes a broad range of functionality and support for many industry standards.</span></span>

<span data-ttu-id="e7744-110">.NET Framework stellt viele Dienste bereit, einschließlich der Verwaltung des Arbeitsspeichers, Sicherheit für den Typ und Arbeitsspeicher, Sicherheit sowie Netzwerk- und Anwendungsbereitstellung.</span><span class="sxs-lookup"><span data-stu-id="e7744-110">The .NET Framework provides many services, including memory management, type and memory safety, security, networking, and application deployment.</span></span> <span data-ttu-id="e7744-111">Es bietet einfach zu bedienende Datenstrukturen und APIs, die auf niedrigerer Ebene des Windows-Betriebssystems abstrahieren.</span><span class="sxs-lookup"><span data-stu-id="e7744-111">It provides easy-to-use data structures and APIs that abstract the lower-level Windows operating system.</span></span> <span data-ttu-id="e7744-112">Sie können mit .NET Framework verschiedene Programmiersprachen verwenden, einschließlich C#, F# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="e7744-112">You can use different programming languages with the .NET Framework, including C#, F#, and Visual Basic.</span></span>

<span data-ttu-id="e7744-113">Eine allgemeine Einführung in .NET Framework für Benutzer und Entwickler erhalten Sie unter [Erste Schritte](./get-started/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-113">For a general introduction to the .NET Framework for both users and developers, see [Getting Started](./get-started/index.md).</span></span> <span data-ttu-id="e7744-114">Eine Einführung in die Architektur und die Hauptfunktionen von .NET Framework finden Sie unter [Übersicht](./get-started/overview.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-114">For an introduction to the architecture and key features of the .NET Framework, see the [overview](./get-started/overview.md).</span></span>

<span data-ttu-id="e7744-115">.NET Framework kann mit Docker und mit [Windows-Containern](/virtualization/windowscontainers/about/) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7744-115">The .NET Framework can be used with Docker and with [Windows Containers](/virtualization/windowscontainers/about/).</span></span>

## <a name="installation"></a><span data-ttu-id="e7744-116">Installation</span><span class="sxs-lookup"><span data-stu-id="e7744-116">Installation</span></span>

<span data-ttu-id="e7744-117">.NET Framework ist im Lieferumgang von Windows enthalten; so können Sie .NET Framework-Anwendungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7744-117">The .NET Framework comes with Windows, enabling you to run .NET Framework applications.</span></span> <span data-ttu-id="e7744-118">Sie benötigen möglicherweise eine höhere Version von .NET Framework als die in Ihrer Windows-Version vorhandene.</span><span class="sxs-lookup"><span data-stu-id="e7744-118">You may need a later version of the .NET Framework than the one that comes with your Windows version.</span></span> <span data-ttu-id="e7744-119">Weitere Informationen finden Sie unter [Installieren von .NET Framework unter Windows](./install/index.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-119">For more information, see [Install the .NET Framework on Windows](./install/index.md).</span></span>

<span data-ttu-id="e7744-120">Lesen Sie [Reparieren von .NET Framework](./install/repair.md), um zu erfahren, wie Sie Ihre .NET Framework-Installation reparieren, wenn bei der Installation von .NET Framework Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="e7744-120">See [Repair the .NET Framework](./install/repair.md) to learn how to repair your .NET Framework installation if you're experiencing errors when installing the .NET Framework.</span></span>

<span data-ttu-id="e7744-121">Informationen zum Herunterladen von .NET Framework finden Sie unter [Install the .NET Framework for developers (Installieren von .NET Framework für Entwickler)](./install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="e7744-121">For more detailed information on downloading the .NET Framework, see [Install the .NET Framework for developers](./install/guide-for-developers.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e7744-122">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e7744-122">In this section</span></span>

* [<span data-ttu-id="e7744-123">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="e7744-123">What's New</span></span>](./whats-new/index.md)  
<span data-ttu-id="e7744-124">Beschreibt wichtige Funktionen und Änderungen in den neuesten Versionen von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7744-124">Describes key new features and changes in the latest versions of the .NET Framework.</span></span> <span data-ttu-id="e7744-125">Enthält Listen von veralteten Typen und Membern sowie eine Führungslinie für das Migrieren der Anwendungen aus der früheren Version von .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e7744-125">Includes lists of obsolete types and members, and provides a guide for migrating your applications from the previous version of the .NET Framework.</span></span>

* [<span data-ttu-id="e7744-126">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="e7744-126">Get Started</span></span>](./get-started/index.md)  
<span data-ttu-id="e7744-127">Stellt eine umfassende Übersicht über .NET Framework und Links zu zusätzlichen Ressourcen bereit.</span><span class="sxs-lookup"><span data-stu-id="e7744-127">Provides a comprehensive overview of the .NET Framework and links to additional resources.</span></span>

* [<span data-ttu-id="e7744-128">Installationshandbuch</span><span class="sxs-lookup"><span data-stu-id="e7744-128">Installation Guide</span></span>](./install/index.md)  
<span data-ttu-id="e7744-129">Enthält Ressourcen und Anleitungen zur Installation von .NET Framework und Problembehandlung.</span><span class="sxs-lookup"><span data-stu-id="e7744-129">Provides resources and guidance about .NET Framework installation and troubleshooting.</span></span>

* [<span data-ttu-id="e7744-130">Migrationshandbuch</span><span class="sxs-lookup"><span data-stu-id="e7744-130">Migration Guide</span></span>](./migration-guide/index.md)  
<span data-ttu-id="e7744-131">Stellt Ressourcen und eine Liste der Änderungen bereit, die Sie berücksichtigen müssen, wenn Sie Ihre Anwendung zu einer neuen Version von .NET Framework migrieren.</span><span class="sxs-lookup"><span data-stu-id="e7744-131">Provides resources and a list of changes you need to consider if you're migrating your application to a new version of the .NET Framework.</span></span>

* [<span data-ttu-id="e7744-132">Entwicklungshandbuch</span><span class="sxs-lookup"><span data-stu-id="e7744-132">Development Guide</span></span>](./development-guide.md)  
<span data-ttu-id="e7744-133">Enthält eine Richtlinie für alle wichtigen technologischen Bereiche und Aufgaben für die Anwendungsentwicklung, einschließlich Erstellen, Konfigurieren, Debuggen, Sichern und Bereitstellen der Anwendung, sowie Informationen über dynamische Programmierung, Interoperabilität, Erweiterbarkeit, Speicherverwaltung und Threading.</span><span class="sxs-lookup"><span data-stu-id="e7744-133">Provides a guide to all key technology areas and tasks for application development, including creating, configuring, debugging, securing, and deploying your application, and information about dynamic programming, interoperability, extensibility, memory management, and threading.</span></span>

* [<span data-ttu-id="e7744-134">Extras</span><span class="sxs-lookup"><span data-stu-id="e7744-134">Tools</span></span>](./tools/index.md)  
<span data-ttu-id="e7744-135">Beschreibt die Tools, die Sie beim Entwickeln, Konfigurieren und Bereitstellen von Anwendungen mithilfe der .NET Framework-Technologien unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e7744-135">Describes the tools that help you develop, configure, and deploy applications by using .NET Framework technologies.</span></span>

* [<span data-ttu-id="e7744-136">Zusätzliche Klassenbibliotheken und APIs</span><span class="sxs-lookup"><span data-stu-id="e7744-136">Additional class libraries and APIs</span></span>](./additional-apis/index.md)  
<span data-ttu-id="e7744-137">Stellt Dokumentation für private .NET Framework-APIs bereit, die von Microsoft-Tools verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7744-137">Provides documentation for private .NET Framework APIs used by Microsoft tools.</span></span>

## <a name="see-also"></a><span data-ttu-id="e7744-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7744-138">See also</span></span>

* [<span data-ttu-id="e7744-139">.NET Framework-Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="e7744-139">.NET Framework Class Library</span></span>](/dotnet/api/?view=netframework-4.8)
