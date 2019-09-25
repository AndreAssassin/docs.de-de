---
title: Entwickeln cloudnativer .NET-Anwendungen für Azure
description: Leitfaden zum Erstellen cloudnativer Anwendungen, die Container, Microservices und serverlose Features von Azure nutzen.
author: ardalis
ms.date: 03/07/2019
ms.openlocfilehash: 67e235b051702308d2455b2501bfb59a4317635b
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71214165"
---
# <a name="architecting-cloud-native-net-applications-for-azure"></a><span data-ttu-id="312dc-103">Entwickeln cloudnativer .NET-Anwendungen für Azure</span><span class="sxs-lookup"><span data-stu-id="312dc-103">Architecting Cloud Native .NET Applications for Azure</span></span>

![Titelbild](./media/cover.png)

<span data-ttu-id="312dc-105">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="312dc-105">PUBLISHED BY</span></span>

<span data-ttu-id="312dc-106">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="312dc-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="312dc-107">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="312dc-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="312dc-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="312dc-108">One Microsoft Way</span></span>

<span data-ttu-id="312dc-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="312dc-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="312dc-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="312dc-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="312dc-111">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="312dc-111">All rights reserved.</span></span> <span data-ttu-id="312dc-112">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="312dc-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="312dc-113">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="312dc-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="312dc-114">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="312dc-114">The views, opinions, and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="312dc-115">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="312dc-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="312dc-116">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="312dc-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="312dc-117">Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="312dc-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="312dc-118">Mac und macOS sind Marken von Apple Inc.</span><span class="sxs-lookup"><span data-stu-id="312dc-118">Mac and macOS are trademarks of Apple Inc.</span></span>

<span data-ttu-id="312dc-119">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="312dc-119">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="312dc-120">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="312dc-120">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="312dc-121">Autoren:</span><span class="sxs-lookup"><span data-stu-id="312dc-121">Authors:</span></span>

> <span data-ttu-id="312dc-122">**Steve „ardalis“ Smith** – Softwarearchitekt und Trainer – [Ardalis.com](https://ardalis.com)</span><span class="sxs-lookup"><span data-stu-id="312dc-122">**Steve "ardalis" Smith** - Software Architect and Trainer - [Ardalis.com](https://ardalis.com)</span></span>
>
> <span data-ttu-id="312dc-123">**Rob Vettor** – Principal Cloud System Architect und IP Architect bei Microsoft – [RobVettor.com](https://robvettor.com)</span><span class="sxs-lookup"><span data-stu-id="312dc-123">**Rob Vettor** - Microsoft - Principal Cloud System Architect/IP Architect - [RobVettor.com](https://robvettor.com)</span></span>

<span data-ttu-id="312dc-124">Teilnehmer und Prüfer:</span><span class="sxs-lookup"><span data-stu-id="312dc-124">Participants and Reviewers:</span></span>

> <span data-ttu-id="312dc-125">**Cesar De la Torre**, Principal Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="312dc-125">**Cesar De la Torre**, Principal Program Manager, .NET team, Microsoft</span></span>
>
> <span data-ttu-id="312dc-126">**Nish Anil**, Senior Program Manager, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="312dc-126">**Nish Anil**, Sr. Program Manager, .NET team, Microsoft</span></span>

<span data-ttu-id="312dc-127">Editoren:</span><span class="sxs-lookup"><span data-stu-id="312dc-127">Editors:</span></span>

> <span data-ttu-id="312dc-128">**Maira Wenzel**, Sr. Content Developer, .NET-Team, Microsoft</span><span class="sxs-lookup"><span data-stu-id="312dc-128">**Maira Wenzel**, Sr. Content Developer, .NET team, Microsoft</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="312dc-129">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="312dc-129">Who should use this guide</span></span>

<span data-ttu-id="312dc-130">Die Zielgruppe dieses Leitfadens sind hauptsächlich Entwickler, Entwicklungsleiter und Architekten, die lernen möchten, wie Anwendungen für die Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="312dc-130">The audience for this guide is mainly developers, development leads, and architects who are interested in learning how to build applications designed for the cloud.</span></span>

<span data-ttu-id="312dc-131">Technische Entscheidungsträger, die überlegen, ihre Anwendungen mithilfe eines cloudnativen Ansatzes zu erstellen, sind eine sekundäre Zielgruppe.</span><span class="sxs-lookup"><span data-stu-id="312dc-131">A secondary audience is technical decision-makers who plan to choose whether to build their applications using a cloud-native approach.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="312dc-132">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="312dc-132">How you can use this guide</span></span>

<span data-ttu-id="312dc-133">In diesem Leitfaden wird zunächst der Begriff „Cloudnativ“ definiert und eine Referenzanwendung vorgestellt, die mithilfe cloudnativer Prinzipien und Technologien erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="312dc-133">This guide begins by defining cloud native and introducing a reference application built using cloud-native principles and technologies.</span></span> <span data-ttu-id="312dc-134">Nach diesen ersten beiden Kapiteln ist das Buch in spezifische Kapitel unterteilt, die sich mit gängigen Themen im Bezug zu den meisten cloudnativen Anwendungen befassen.</span><span class="sxs-lookup"><span data-stu-id="312dc-134">Beyond these first two chapters, the rest of the book is broken up into specific chapters focused on topics common to most cloud-native applications.</span></span> <span data-ttu-id="312dc-135">Sie können zu einem dieser Kapitel springen, um die folgenden cloudnativen Ansätze kennenzulernen:</span><span class="sxs-lookup"><span data-stu-id="312dc-135">You can jump to any of these chapters to learn about cloud-native approaches to:</span></span>

- <span data-ttu-id="312dc-136">Daten und Datenzugriff</span><span class="sxs-lookup"><span data-stu-id="312dc-136">Data and data access</span></span>
- <span data-ttu-id="312dc-137">Kommunikationsmuster</span><span class="sxs-lookup"><span data-stu-id="312dc-137">Communication patterns</span></span>
- <span data-ttu-id="312dc-138">Skalierung und Skalierbarkeit</span><span class="sxs-lookup"><span data-stu-id="312dc-138">Scaling and scalability</span></span>
- <span data-ttu-id="312dc-139">Anwendungsresilienz</span><span class="sxs-lookup"><span data-stu-id="312dc-139">Application resiliency</span></span>
- <span data-ttu-id="312dc-140">Überwachung und Integrität</span><span class="sxs-lookup"><span data-stu-id="312dc-140">Monitoring and health</span></span>
- <span data-ttu-id="312dc-141">Identität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="312dc-141">Identity and security</span></span>
- <span data-ttu-id="312dc-142">DevOps</span><span class="sxs-lookup"><span data-stu-id="312dc-142">DevOps</span></span>

<span data-ttu-id="312dc-143">Dieser Leitfaden ist sowohl im PDF-Format als auch online verfügbar.</span><span class="sxs-lookup"><span data-stu-id="312dc-143">This guide is available both in PDF form and online.</span></span> <span data-ttu-id="312dc-144">Sie können dieses Dokument oder Links zur Onlineversion an Ihr Team weiterleiten, um ein allgemeines Verständnis dieser Themen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="312dc-144">Feel free to forward this document or links to its online version to your team to help ensure common understanding of these topics.</span></span> <span data-ttu-id="312dc-145">Die meisten dieser Themen profitieren von einem einheitlichen Verständnis der zugrunde liegenden Prinzipien und Muster sowie der Nachteile einiger Entscheidungen, die in Relation zu diesen Entscheidungen stehen.</span><span class="sxs-lookup"><span data-stu-id="312dc-145">Most of these topics benefit from a consistent understanding of the underlying principles and patterns, as well as the trade-offs involved in decisions related to these topics.</span></span> <span data-ttu-id="312dc-146">Das Ziel dieses Dokuments ist es, Teams und Teamleiter mit den Informationen auszustatten, die sie benötigen, um fundierte Entscheidungen bezüglich der Architektur, der Entwicklung und des Hostings ihrer Anwendungen zu treffen.</span><span class="sxs-lookup"><span data-stu-id="312dc-146">Our goal with this document is to equip teams and their leaders with the information they need to make well-informed decisions for their applications' architecture, development, and hosting.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="312dc-147">Nächste</span><span class="sxs-lookup"><span data-stu-id="312dc-147">Next</span></span>](introduction.md)
