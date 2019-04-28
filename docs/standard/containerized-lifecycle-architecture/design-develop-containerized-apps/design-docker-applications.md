---
title: Entwerfen von Docker-Anwendungen
description: Hier der einen Verweis auf eine ausführliche Anleitung zur Microservices-Architektur, da dies ein Thema ist, die sie nicht in diesem Handbuch beschrieben wird.
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 1d49f7509c0a12edfe375486429147e8fd240b2d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61799345"
---
# <a name="design-docker-applications"></a><span data-ttu-id="e6a1a-103">Entwerfen von Docker-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="e6a1a-103">Design Docker applications</span></span>

<span data-ttu-id="e6a1a-104">Die grundlegenden Konzepte in Bezug auf Container und Docker, Kapitel 1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-104">Chapter 1 introduced the fundamental concepts regarding containers and Docker.</span></span> <span data-ttu-id="e6a1a-105">Diese Informationen ist die grundlegende Informationen, die Sie benötigen, um zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-105">That information is the basic level of information you need to get started.</span></span> <span data-ttu-id="e6a1a-106">Allerdings unternehmensanwendungen können komplex sein und besteht aus mehreren Diensten statt aus einem einzelnen Dienst oder Container.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-106">But, enterprise applications can be complex and composed of multiple services instead of a single service or container.</span></span> <span data-ttu-id="e6a1a-107">Für diese Fälle optionale Verwendung müssen Sie zusätzliche Ansätze zum Entwerfen, wie z. B. serviceorientierter Architektur (SOA) und erweiterte Konzepte von Microservices und Container orchestrierungskonzepte kennen.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-107">For those optional use cases, you need to know additional approaches to design, such as Service-Oriented Architecture (SOA) and the more advanced microservices concepts and container orchestration concepts.</span></span> <span data-ttu-id="e6a1a-108">Der Umfang dieses Dokuments ist nicht beschränkt auf Microservices, aber auf alle Docker-Anwendungslebenszyklus aus diesem Grund wird nicht untersuchen Microservices-Architektur im Detail, da Sie auch können Container und Docker mit regulären SOA, Hintergrundaufgaben oder Aufträge, oder sogar mit monolithischen Anwendung Bereitstellungskonzept vorgehen.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-108">The scope of this document is not limited to microservices but to any Docker application life cycle, therefore, it does not explore microservices architecture in depth because you also can use containers and Docker with regular SOA, background tasks or jobs, or even with monolithic application deployment approaches.</span></span>

<span data-ttu-id="e6a1a-109">**Weitere Informationen** lesen Sie den Leitfaden, um weitere Informationen zum Enterprise-Anwendungen und Microservices-Architektur im Detail [NET-Microservices: Architektur für .NET-containeranwendungen](../../microservices-architecture/index.md) , die Sie können auch von <https://aka.ms/MicroservicesEbook>.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-109">**More info** To learn more about enterprise applications and microservices architecture in depth, read the guide [NET Microservices: Architecture for Containerized .NET Applications](../../microservices-architecture/index.md) that you can also download from <https://aka.ms/MicroservicesEbook>.</span></span>

<span data-ttu-id="e6a1a-110">Bevor wir auf die Anwendung während des Lebenszyklus und DevOps eingehen, ist es jedoch wichtig zu wissen, wie Sie auf das Erstellen Ihrer Anwendung und welche Auswahl für den Entwurf.</span><span class="sxs-lookup"><span data-stu-id="e6a1a-110">However, before we get into the application life cycle and DevOps, it's important to know how you're going to design and construct your application and what are your design choices.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e6a1a-111">[Zurück](index.md)
>[Weiter](common-container-design-principles.md)</span><span class="sxs-lookup"><span data-stu-id="e6a1a-111">[Previous](index.md)
[Next](common-container-design-principles.md)</span></span>