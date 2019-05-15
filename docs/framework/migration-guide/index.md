---
title: 'Migrationshandbuch zu .NET Framework 4.8, 4.7, 4.6 und 4.5 '
ms.custom: updateeachrelease
ms.date: 04/18/2019
helpviewer_keywords:
- .NET Framework, migrating applications to
- migration, .NET Framework
ms.assetid: 02d55147-9b3a-4557-a45f-fa936fadae3b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b1cda82125a2d4a6eb3102b01bea639a4f3e3df
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636087"
---
# <a name="migration-guide-to-the-net-framework-48-47-46-and-45"></a><span data-ttu-id="ffbce-102">Migrationshandbuch zu .NET Framework 4.8, 4.7, 4.6 und 4.5</span><span class="sxs-lookup"><span data-stu-id="ffbce-102">Migration Guide to the .NET Framework 4.8, 4.7, 4.6, and 4.5</span></span>

<span data-ttu-id="ffbce-103">Wenn Sie Ihre App mit einer früheren Version von .NET Framework erstellt haben, können Sie im Allgemeinen problemlos ein Upgrade auf .NET Framework 4.5 und die Nebenversionen (4.5.1 und 4.5.2), .NET Framework 4.6 und die Nebenversionen (4.6.1 und 4.6.2), .NET Framework 4.7 und seine Nebenversionen (4.7.1 und 4.7.2) oder .NET Framework 4.8 ausführen.</span><span class="sxs-lookup"><span data-stu-id="ffbce-103">If you created your app using an earlier version of the .NET Framework, you can generally upgrade it to .NET Framework 4.5 and its point releases (4.5.1 and 4.5.2), .NET Framework 4.6 and its point releases (4.6.1 and 4.6.2), .NET Framework 4.7 and its point releases (4.7.1 and 4.7.2), or .NET Framework 4.8 easily.</span></span> <span data-ttu-id="ffbce-104">Öffnen Sie Ihr Projekt in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ffbce-104">Open your project in Visual Studio.</span></span> <span data-ttu-id="ffbce-105">Wenn das Projekt in einer früheren Version von Visual Studio erstellt wurde, wird automatisch das Dialogfeld **Projektkompatibilität** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="ffbce-105">If your project was created in an earlier version of Visual Studio, the **Project Compatibility** dialog box automatically opens.</span></span> <span data-ttu-id="ffbce-106">Weitere Informationen zum Durchführen von Upgrades für ein Projekt in Visual Studio finden Sie unter [Übertragung, Migration und Upgrade der Visual Studio-Projekte](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) und [Visual Studio 2019 – Zielplattformen und Kompatibilität](/visualstudio/releases/2019/compatibility).</span><span class="sxs-lookup"><span data-stu-id="ffbce-106">For more information about upgrading a project in Visual Studio, see [Port, Migrate, and Upgrade Visual Studio Projects](/visualstudio/porting/port-migrate-and-upgrade-visual-studio-projects) and [Visual Studio 2019 Platform Targeting and Compatibility](/visualstudio/releases/2019/compatibility).</span></span>

 <span data-ttu-id="ffbce-107">Einige Änderungen in .NET Framework erfordern jedoch Änderungen am Code.</span><span class="sxs-lookup"><span data-stu-id="ffbce-107">However, some changes in the .NET Framework require changes to your code.</span></span> <span data-ttu-id="ffbce-108">So möchten Sie möglicherweise die neuen Features von .NET Framework 4.5 und Nebenversionen, von .NET Framework 4.6 und Nebenversionen, von .NET Framework 4.7 und Nebenversionen oder .NET Framework 4.8 nutzen.</span><span class="sxs-lookup"><span data-stu-id="ffbce-108">You may also want to take advantage of functionality that is new in .NET Framework 4.5 and its point releases, in .NET Framework 4.6 and its point releases, in .NET Framework 4.7 and its point releases, or in .NET Framework 4.8.</span></span> <span data-ttu-id="ffbce-109">Diese Art von Änderungen an der App für eine neue Version von .NET Framework wird in der Regel als *Migration* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffbce-109">Making these types of changes to your app for a new version of the .NET Framework is typically referred to as *migration*.</span></span> <span data-ttu-id="ffbce-110">Wenn Ihre Anwendung nicht migriert werden muss, können Sie sie in .NET Framework 4.5 oder einer späteren Version ausführen, ohne sie neu zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="ffbce-110">If your app doesn't have to be migrated, you can run it in the .NET Framework 4.5 or a later version without recompiling it.</span></span>

## <a name="migration-resources"></a><span data-ttu-id="ffbce-111">Migrationsressourcen</span><span class="sxs-lookup"><span data-stu-id="ffbce-111">Migration resources</span></span>

<span data-ttu-id="ffbce-112">Lesen Sie die folgenden Dokumente, bevor Sie die App aus früheren Versionen von .NET Framework zu Version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2 oder 4.8 migrieren:</span><span class="sxs-lookup"><span data-stu-id="ffbce-112">Review the following documents before you migrate your app from earlier versions of the .NET Framework to version 4.5, 4.5.1, 4.5.2, 4.6, 4.6.1, 4.6.2, 4.7, 4.7.1, 4.7.2, or 4.8:</span></span>

- <span data-ttu-id="ffbce-113">Lesen Sie [Versionen und Abhängigkeiten](versions-and-dependencies.md), damit Sie die CLR-Version kennen, die den einzelnen Versionen von .NET Framework zugrunde liegt, und um Richtlinien zur erfolgreichen Ausrichtung für Apps auf das gewünschte Ziel zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="ffbce-113">See [Versions and Dependencies](versions-and-dependencies.md) to understand the CLR version underlying each version of the .NET Framework and to review guidelines for targeting your apps successfully.</span></span>

- <span data-ttu-id="ffbce-114">Lesen Sie [Anwendungskompatibilität](application-compatibility.md), um Informationen zu Laufzeit- und Neuausrichtungsänderungen zu erhalten, die sich auf die App auswirken können, und zu entsprechenden Maßnahmen.</span><span class="sxs-lookup"><span data-stu-id="ffbce-114">Review [Application Compatibility](application-compatibility.md) to find out about runtime and retargeting changes that might affect your app and how to handle them.</span></span>

- <span data-ttu-id="ffbce-115">Überprüfen Sie [Veraltete Elemente in der Klassenbibliothek](../whats-new/whats-obsolete.md), um veraltete Typen oder Member im Code und die empfohlenen Alternativen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ffbce-115">Review [What's Obsolete in the Class Library](../whats-new/whats-obsolete.md) to determine any types or members in your code that have been made obsolete, and the recommended alternatives.</span></span>

- <span data-ttu-id="ffbce-116">Unter [Neuigkeiten](../whats-new/index.md) finden Sie Beschreibungen von neuen Funktionen, die Sie Ihrer App hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ffbce-116">See [What's New](../whats-new/index.md) for descriptions of new features that you may want to add to your app.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffbce-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffbce-117">See also</span></span>

- [<span data-ttu-id="ffbce-118">Anwendungskompatibilität</span><span class="sxs-lookup"><span data-stu-id="ffbce-118">Application Compatibility</span></span>](application-compatibility.md)
- [<span data-ttu-id="ffbce-119">Migrieren von .NET Framework 1.1</span><span class="sxs-lookup"><span data-stu-id="ffbce-119">Migrating from the .NET Framework 1.1</span></span>](migrating-from-the-net-framework-1-1.md)
- [<span data-ttu-id="ffbce-120">Versionskompatibilität</span><span class="sxs-lookup"><span data-stu-id="ffbce-120">Version Compatibility</span></span>](version-compatibility.md)
- [<span data-ttu-id="ffbce-121">Versionen und Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="ffbce-121">Versions and Dependencies</span></span>](versions-and-dependencies.md)
- [<span data-ttu-id="ffbce-122">Vorgehensweise: Konfigurieren einer App zur Unterstützung von .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="ffbce-122">How to: Configure an app to support .NET Framework 4 or later versions</span></span>](how-to-configure-an-app-to-support-net-framework-4-or-4-5.md)
- [<span data-ttu-id="ffbce-123">Neuigkeiten</span><span class="sxs-lookup"><span data-stu-id="ffbce-123">What's New</span></span>](../whats-new/index.md)
- [<span data-ttu-id="ffbce-124">Veraltete Elemente in der Klassenbibliothek</span><span class="sxs-lookup"><span data-stu-id="ffbce-124">What's Obsolete in the Class Library</span></span>](../whats-new/whats-obsolete.md)
- [<span data-ttu-id="ffbce-125">Versions- und Assemblyinformationen zu .NET Framework</span><span class="sxs-lookup"><span data-stu-id="ffbce-125">.NET Framework Version and Assembly Information</span></span>](https://go.microsoft.com/fwlink/?LinkId=201701)
- [<span data-ttu-id="ffbce-126">Microsoft .NET Framework Support Lifecycle-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="ffbce-126">Microsoft .NET Framework Support Lifecycle Policy</span></span>](https://go.microsoft.com/fwlink/?LinkId=196607)
- [<span data-ttu-id="ffbce-127">.NET Framework 4 migration issues (Migrationsprobleme in .NET Framework 4)</span><span class="sxs-lookup"><span data-stu-id="ffbce-127">.NET Framework 4 migration issues</span></span>](net-framework-4-migration-issues.md)
