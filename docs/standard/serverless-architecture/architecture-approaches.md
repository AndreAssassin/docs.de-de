---
title: Architekturansätze - serverlose apps
description: Eine Einführung in die Architektur Ansätzen für das Erstellen von Cloud-basierte unternehmensanwendungen, von N-schichtige Architekturen für die serverlose.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638841"
---
# <a name="architecture-approaches"></a><span data-ttu-id="6e06f-103">Architekturansätze</span><span class="sxs-lookup"><span data-stu-id="6e06f-103">Architecture approaches</span></span>

<span data-ttu-id="6e06f-104">Grundlegendes zu vorhandenen Ansätze zum Entwerfen von Unternehmens-apps unterstützt, die serverlose Rolle erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="6e06f-105">Es gibt viele Ansätze und Muster, die sich über mehrere Jahrzehnte bei der Softwareentwicklung entwickelt, und alle haben ihre eigenen vor- und Nachteile.</span><span class="sxs-lookup"><span data-stu-id="6e06f-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="6e06f-106">In vielen Fällen die ultimative Lösung kann nicht auf einem einzigen Ansatz entscheiden, umfassen aber möglicherweise mehrere Ansätze integrieren.</span><span class="sxs-lookup"><span data-stu-id="6e06f-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="6e06f-107">Migrationsszenarien ist häufig die Umstellung von einem Architekturkonzept, zu einem anderen über ein Hybridansatz erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e06f-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="6e06f-108">In diesem Kapitel bietet eine Übersicht über beide Muster für die logische und physische Architektur für unternehmensanwendungen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="6e06f-109">Architekturmuster</span><span class="sxs-lookup"><span data-stu-id="6e06f-109">Architecture patterns</span></span>

<span data-ttu-id="6e06f-110">Moderne Geschäftsanwendungen führen Sie eine Vielzahl von Architekturmuster.</span><span class="sxs-lookup"><span data-stu-id="6e06f-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="6e06f-111">Dieser Abschnitt stellt eine Umfrage für allgemeine Muster dar.</span><span class="sxs-lookup"><span data-stu-id="6e06f-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="6e06f-112">Die Muster, die hier aufgeführten werden nicht unbedingt alle bewährten Methoden, aber unterschiedliche Ansätze zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="6e06f-113">Weitere Informationen finden Sie unter [Azure-anwendungsarchitekturleitfaden](https://docs.microsoft.com/azure/architecture/guide/).</span><span class="sxs-lookup"><span data-stu-id="6e06f-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="6e06f-114">Mehr als Monolithen entwickelt</span><span class="sxs-lookup"><span data-stu-id="6e06f-114">Monoliths</span></span>

<span data-ttu-id="6e06f-115">Viele Geschäftsanwendungen folgen einem Muster für die monolithische Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6e06f-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="6e06f-116">Legacy-Anwendungen werden häufig als "Monolithen" implementiert.</span><span class="sxs-lookup"><span data-stu-id="6e06f-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="6e06f-117">In der monolithischen Anwendung-Muster sind alle Aspekte der Anwendung in einer einzelnen Bereitstellung enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="6e06f-118">Angefangen bei der Benutzeroberfläche für die Datenbankaufrufe ist in der gleichen Codebasis enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Architektur der monolithischen Anwendung](./media/monolith-architecture.png)

<span data-ttu-id="6e06f-120">Es gibt mehrere Vorteile, die mit dem monolithischen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="6e06f-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="6e06f-121">Häufig ist es einfach zu einer einzigen Codebasis abrufen und mit der Arbeit beginnen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="6e06f-122">Zeit kann geringer sein, und Erstellen von testumgebungen ist so einfach wie eine neue Kopie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="6e06f-123">Sollen mehrere Komponenten und Anwendungen, kann die monolithische Anwendung entworfen werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="6e06f-124">Leider die monolithische Anwendung Muster nach Maß zu unterteilen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="6e06f-125">Gravierenden Nachteile des monolithischen Ansatzes gehören:</span><span class="sxs-lookup"><span data-stu-id="6e06f-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="6e06f-126">Schwierige parallel in derselben Codebasis arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="6e06f-127">Alle Änderungen, unabhängig davon, wie einfach ist, muss eine neue Version der gesamten Anwendung bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="6e06f-128">Refactoring potenziell wirkt sich auf die gesamte Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="6e06f-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="6e06f-129">Die einzige Lösung für die Skalierung häufig ist die Erstellung mehrerer mit großem Ressourcenaufwand Kopien auf die monolithische Anwendung.</span><span class="sxs-lookup"><span data-stu-id="6e06f-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="6e06f-130">Integration kann schwierig sein, wie Systeme erweitern oder zu anderen Systemen werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="6e06f-131">Es kann schwierig zu testen aufgrund müssen so konfigurieren Sie die gesamte monolithische Anwendung sein.</span><span class="sxs-lookup"><span data-stu-id="6e06f-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="6e06f-132">Wiederverwendung von Code ist eine Herausforderung darstellen, und andere apps dem mitunter wieder müssen ihre eigenen Kopien von Code.</span><span class="sxs-lookup"><span data-stu-id="6e06f-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="6e06f-133">Viele Unternehmen suchen Sie in der Cloud als eine Möglichkeit zum Migrieren von monolithischen Anwendungen, und wandeln Sie sie gleichzeitig auf mehrere-Muster, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="6e06f-134">Es ist üblich, die sich die einzelnen Anwendungen und Komponenten, um verwaltet, bereitgestellt und separat skaliert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="6e06f-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="6e06f-135">N-Schicht-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6e06f-135">N-Layer applications</span></span>

<span data-ttu-id="6e06f-136">Anwendung Partition Anwendungslogik in bestimmten Ebenen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="6e06f-137">Die am häufigsten verwendeten Ebenen sind:</span><span class="sxs-lookup"><span data-stu-id="6e06f-137">The most common layers include:</span></span>

* <span data-ttu-id="6e06f-138">Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="6e06f-138">User interface</span></span>
* <span data-ttu-id="6e06f-139">Geschäftslogik</span><span class="sxs-lookup"><span data-stu-id="6e06f-139">Business logic</span></span>
* <span data-ttu-id="6e06f-140">Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="6e06f-140">Data access</span></span>

<span data-ttu-id="6e06f-141">Andere Ebenen können Middleware, Batchverarbeitung und API enthalten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="6e06f-142">Es ist wichtig zu beachten, dass die Schichten logisch sind.</span><span class="sxs-lookup"><span data-stu-id="6e06f-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="6e06f-143">Obwohl sie isoliert entwickelt haben, können sie alle der gleichen Zielplattform bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N-Schichten-Architektur](./media/n-layer-architecture.png)

<span data-ttu-id="6e06f-145">Es gibt mehrere Vorteile, die mit dem Ansatz mit N-Ebene, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="6e06f-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="6e06f-146">Refactoring wird isoliert auf einer Ebene.</span><span class="sxs-lookup"><span data-stu-id="6e06f-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="6e06f-147">Teams können unabhängig voneinander erstellen, testen, bereitstellen und Verwalten der verschiedenen Schichten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="6e06f-148">Ebenen können ausgelagert werden, z. B. möglicherweise die Datenschicht mehrere Datenbanken zugreifen, ohne dass Änderungen an der UI-Ebene.</span><span class="sxs-lookup"><span data-stu-id="6e06f-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="6e06f-149">Serverless kann verwendet werden, um eine oder mehrere Ebenen zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6e06f-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="6e06f-150">Microservices</span><span class="sxs-lookup"><span data-stu-id="6e06f-150">Microservices</span></span>

<span data-ttu-id="6e06f-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  Architekturen enthalten die allgemeinen Merkmale, die enthalten:</span><span class="sxs-lookup"><span data-stu-id="6e06f-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="6e06f-152">Anwendungen bestehen aus mehreren kleinen Diensten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="6e06f-153">Jeder Dienst wird in einem eigenen Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="6e06f-154">Dienste werden rund um Geschäftsbereichen ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="6e06f-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="6e06f-155">Dienste kommunizieren über einfache APIs, die in der Regel mithilfe von HTTP als Transport.</span><span class="sxs-lookup"><span data-stu-id="6e06f-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="6e06f-156">Dienste können bereitgestellt und unabhängig voneinander aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="6e06f-157">Dienste stehen keinen einzigen Datenspeicher abhängt.</span><span class="sxs-lookup"><span data-stu-id="6e06f-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="6e06f-158">Das System wurde entworfen, mit einem Fehler, denken Sie daran, und die app kann weiterhin ausgeführt, selbst wenn bestimmte Dienste nicht.</span><span class="sxs-lookup"><span data-stu-id="6e06f-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="6e06f-159">Microservices müssen nicht mit anderen Ansätzen Architektur sich gegenseitig ausschließende sein.</span><span class="sxs-lookup"><span data-stu-id="6e06f-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="6e06f-160">Beispielsweise kann eine N-schichtige Architektur Microservices für die mittlere Ebene verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="6e06f-161">Es ist auch möglich, in einer Vielzahl von Möglichkeiten, von der virtuellen Verzeichnisse auf dem IIS-Hosts für Container Microservices zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6e06f-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="6e06f-162">Merkmale von Microservices stellen sie vor allem ideal für serverlose Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![Microservicearchitektur](./media/microservices-architecture.png)

<span data-ttu-id="6e06f-164">Vorteile der Microservices-Architekturen umfassen:</span><span class="sxs-lookup"><span data-stu-id="6e06f-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="6e06f-165">Refactoring ist häufig auf einen einzelnen Dienst.</span><span class="sxs-lookup"><span data-stu-id="6e06f-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="6e06f-166">Dienste können unabhängig voneinander aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="6e06f-167">Flexibilität und Elastizität können die Anforderungen der einzelnen Dienste optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="6e06f-168">Entwicklung möglich parallel auf verschiedenen Teams und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="6e06f-169">Es ist einfacher, umfassende Tests für isolierte Dienste zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="6e06f-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="6e06f-170">Microservices verfügen über eigene Herausforderungen, darunter:</span><span class="sxs-lookup"><span data-stu-id="6e06f-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="6e06f-171">Bestimmen, welche Dienste verfügbar sind und wie sie aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="6e06f-172">Der Lebenszyklus der Dienste zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6e06f-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="6e06f-173">Verstehen, wie Dienste in der gesamten Anwendung miteinander verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="6e06f-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="6e06f-174">Vollständige systemüberprüfung der Aufrufe für verschiedene Dienste zu testen.</span><span class="sxs-lookup"><span data-stu-id="6e06f-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="6e06f-175">Letzten Endes sind Lösungen, behandeln all diese Herausforderungen, einschließlich der auf der die Vorteile des serverlosen, die weiter unten erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="6e06f-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="6e06f-176">[Zurück](index.md)
>[Weiter](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="6e06f-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
