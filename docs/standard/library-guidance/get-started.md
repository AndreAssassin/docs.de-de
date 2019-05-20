---
title: Erste Schritte beim Erstellen hochwertiger .NET-Bibliotheken
description: Erste Schritte beim Erstellen von .NET-Bibliotheken.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 980f0edcee07688935f6d08f3ce1ed812159695e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640744"
---
# <a name="get-started"></a><span data-ttu-id="00c03-103">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="00c03-103">Get started</span></span>

## <a name="cross-platform-targetingcross-platform-targetingmd"></a>[<span data-ttu-id="00c03-104">Plattformübergreifende Ziele</span><span class="sxs-lookup"><span data-stu-id="00c03-104">Cross-platform targeting</span></span>](./cross-platform-targeting.md)

<span data-ttu-id="00c03-105">Verwenden von .NET Standard und dem Festlegen von Zielversionen zum Erstellen plattformübergreifender Bibliotheken.</span><span class="sxs-lookup"><span data-stu-id="00c03-105">How to use .NET Standard and multi-targeting to create cross-platform libraries.</span></span> <span data-ttu-id="00c03-106">.NET läuft an vielen Stellen, und gute .NET-Bibliotheken sollten so viele Plattformen und Entwickler wie möglich unterstützen.</span><span class="sxs-lookup"><span data-stu-id="00c03-106">.NET runs in many places, and good .NET libraries should strive to support as many platforms and developers as possible.</span></span>

## <a name="strong-namingstrong-namingmd"></a>[<span data-ttu-id="00c03-107">Starke Namen</span><span class="sxs-lookup"><span data-stu-id="00c03-107">Strong naming</span></span>](./strong-naming.md)

<span data-ttu-id="00c03-108">Erfahren Sie mehr zu den Vor- und Nachteilen eines starken Namens.</span><span class="sxs-lookup"><span data-stu-id="00c03-108">Learn about strong naming and its advantages and disadvantages.</span></span> <span data-ttu-id="00c03-109">Wenn für eine .NET-Bibliothek ein starker Name verwendet wird, kann diese von den meisten Entwicklern verwendet werden. Außerdem ist dies die empfohlene bewährte Methode.</span><span class="sxs-lookup"><span data-stu-id="00c03-109">Strong naming a .NET library allows the most developers to use it and is a recommended best practice.</span></span>

## <a name="nuget-and-open-source-librariesnugetmd"></a>[<span data-ttu-id="00c03-110">NuGet und Open-Source-Bibliotheken</span><span class="sxs-lookup"><span data-stu-id="00c03-110">NuGet and open-source libraries</span></span>](./nuget.md)

<span data-ttu-id="00c03-111">Der beste Weg, NuGet-Pakete für Open-Source-.NET-Bibliotheken zu erstellen, einschließlich empfohlener Metadaten für alle Pakete, die öffentlich auf NuGet.org veröffentlicht werden.</span><span class="sxs-lookup"><span data-stu-id="00c03-111">The best way to create NuGet packages for open-source .NET libraries, including recommended metadata for all packages published publicly on NuGet.org.</span></span>

### <a name="dependenciesdependenciesmd"></a>[<span data-ttu-id="00c03-112">Abhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="00c03-112">Dependencies</span></span>](./dependencies.md)

<span data-ttu-id="00c03-113">Mit NuGet ist es ganz einfach, vorhandene Pakete beim Erstellen einer.NET-Bibliothek zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="00c03-113">NuGet makes it easy to use existing packages when building a .NET library.</span></span> <span data-ttu-id="00c03-114">Erfahren Sie mehr über die häufigen Problemquellen von NuGet-Abhängigkeiten und wie Sie diese vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="00c03-114">Learn about NuGet dependencies' common sources of friction and how to avoid them.</span></span>

### <a name="source-linksourcelinkmd"></a>[<span data-ttu-id="00c03-115">Quelllink</span><span class="sxs-lookup"><span data-stu-id="00c03-115">Source Link</span></span>](./sourcelink.md)

<span data-ttu-id="00c03-116">SourceLink ist ein großartiges Werkzeug, das es Benutzern Ihrer .NET-Bibliothek ermöglicht, während des Debuggens in den Quellcode zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="00c03-116">Source Link is a great tool that allows users of your .NET library to step into its source code while debugging.</span></span> <span data-ttu-id="00c03-117">Dieser Artikel bietet eine Übersicht darüber, was SourceLink ist, und warum Sie es verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="00c03-117">This article is an overview of what Source Link is and why you should use it.</span></span>

### <a name="publishingpublish-nuget-packagemd"></a>[<span data-ttu-id="00c03-118">Veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="00c03-118">Publishing</span></span>](./publish-nuget-package.md)

<span data-ttu-id="00c03-119">NuGet.org ist zwar das bekannteste und am weitesten verbreitete Repository, es gibt jedoch viele Möglichkeiten, NuGet-Pakete zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="00c03-119">While NuGet.org is the most widely known and used repository, there are many places to publish NuGet packages.</span></span> <span data-ttu-id="00c03-120">Erfahren Sie mehr über die verschiedenen verfügbaren NuGet-Paketrepositorys und bewährte Sicherheitsmethoden für die Veröffentlichung einer .NET-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="00c03-120">Learn about the different NuGet package repositories available, and security best practices for publishing a .NET library.</span></span>

## <a name="versioningversioningmd"></a>[<span data-ttu-id="00c03-121">Versionskontrolle</span><span class="sxs-lookup"><span data-stu-id="00c03-121">Versioning</span></span>](./versioning.md)

<span data-ttu-id="00c03-122">Gute .NET-Bibliotheken entwickeln sich im Laufe der Zeit weiter, indem in späteren Versionen Funktionen hinzugefügt, Fehler behoben und die Leistung verbessert werden.</span><span class="sxs-lookup"><span data-stu-id="00c03-122">Good .NET libraries evolve over time, adding features, fixing bugs, and improving performance in later releases.</span></span> <span data-ttu-id="00c03-123">Erfahren Sie mehr über die verschiedenen Versionsnummern und wie Sie Entwickler über aktuelle Änderungen informieren können.</span><span class="sxs-lookup"><span data-stu-id="00c03-123">Learn about the various version numbers and how to communicate breaking changes to developers.</span></span>

### <a name="breaking-changesbreaking-changesmd"></a>[<span data-ttu-id="00c03-124">Breaking Changes</span><span class="sxs-lookup"><span data-stu-id="00c03-124">Breaking changes</span></span>](./breaking-changes.md)

<span data-ttu-id="00c03-125">Es ist wichtig für eine .NET-Bibliothek, ein Gleichgewicht zwischen Stabilität für bestehende Benutzer und Innovation für die Zukunft zu finden.</span><span class="sxs-lookup"><span data-stu-id="00c03-125">It's important for a .NET library to find a balance between stability for existing users and innovation for the future.</span></span> <span data-ttu-id="00c03-126">Erfahren Sie mehr über die verschiedenen Arten von Änderungen und Strategien zum Hinzufügen neuer Funktionen unter Beibehaltung der Abwärtskompatibilität.</span><span class="sxs-lookup"><span data-stu-id="00c03-126">Learn about the different kinds of breaking changes and strategies for adding new features while maintaining backwards compatibility.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="00c03-127">[Zurück](index.md)
>[Weiter](cross-platform-targeting.md)</span><span class="sxs-lookup"><span data-stu-id="00c03-127">[Previous](index.md)
[Next](cross-platform-targeting.md)</span></span>
