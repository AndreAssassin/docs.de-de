---
title: ASP.NET Core gRPC für WCF-Entwickler – gRPC für WCF-Entwickler
description: ZU SCHREIBEND
author: markrendle
ms.date: 09/02/2019
ms.openlocfilehash: dc39fc96e7154fb50acd0b65a58586b3fa12ab50
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696919"
---
# <a name="aspnet-core-grpc-for-wcf-developers"></a><span data-ttu-id="86830-103">ASP.NET Core gRPC für WCF-Entwickler</span><span class="sxs-lookup"><span data-stu-id="86830-103">ASP.NET Core gRPC for WCF Developers</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

![Titelbild](./media/cover.png)

<span data-ttu-id="86830-105">VERÖFFENTLICHT VON</span><span class="sxs-lookup"><span data-stu-id="86830-105">PUBLISHED BY</span></span>

<span data-ttu-id="86830-106">Microsoft Developer Division, .NET- und Visual Studio-Produktteams</span><span class="sxs-lookup"><span data-stu-id="86830-106">Microsoft Developer Division, .NET, and Visual Studio product teams</span></span>

<span data-ttu-id="86830-107">Eine Abteilung der Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="86830-107">A division of Microsoft Corporation</span></span>

<span data-ttu-id="86830-108">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="86830-108">One Microsoft Way</span></span>

<span data-ttu-id="86830-109">Redmond, Washington 98052-6399</span><span class="sxs-lookup"><span data-stu-id="86830-109">Redmond, Washington 98052-6399</span></span>

<span data-ttu-id="86830-110">Copyright © 2019 Microsoft Corporation</span><span class="sxs-lookup"><span data-stu-id="86830-110">Copyright © 2019 by Microsoft Corporation</span></span>

<span data-ttu-id="86830-111">Alle Rechte vorbehalten.</span><span class="sxs-lookup"><span data-stu-id="86830-111">All rights reserved.</span></span> <span data-ttu-id="86830-112">Die Inhalte dieses Buchs dürfen in keiner Form und für keinen Zweck ohne die schriftliche Genehmigung des Herausgebers reproduziert oder übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="86830-112">No part of the contents of this book may be reproduced or transmitted in any form or by any means without the written permission of the publisher.</span></span>

<span data-ttu-id="86830-113">Dieses Buch wird unverändert bereitgestellt und drückt die Ansichten und Meinungen des Autors aus.</span><span class="sxs-lookup"><span data-stu-id="86830-113">This book is provided “as-is” and expresses the author’s views and opinions.</span></span> <span data-ttu-id="86830-114">Die Ansichten, Meinungen und Informationen, die in diesem Buch zum Ausdruck gebracht werden, einschließlich URLs und anderer Verweise auf Internetwebsites, können ohne vorherige Ankündigung geändert werden.</span><span class="sxs-lookup"><span data-stu-id="86830-114">The views, opinions and information expressed in this book, including URL and other Internet website references, may change without notice.</span></span>

<span data-ttu-id="86830-115">Einige der hier dargestellten Beispiele dienen nur zu Illustrationszwecken und sind fiktiv.</span><span class="sxs-lookup"><span data-stu-id="86830-115">Some examples depicted herein are provided for illustration only and are fictitious.</span></span> <span data-ttu-id="86830-116">Keinerlei Zuordnung oder Verbindung zu realen Gegebenheiten ist beabsichtigt oder sollte gefolgert werden.</span><span class="sxs-lookup"><span data-stu-id="86830-116">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="86830-117">Microsoft und die auf der Webseite „Marken“ unter https://www.microsoft.com aufgelisteten Marken sind Marken der Microsoft-Unternehmensgruppe.</span><span class="sxs-lookup"><span data-stu-id="86830-117">Microsoft and the trademarks listed at https://www.microsoft.com on the “Trademarks” webpage are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="86830-118">Das Logo des Docker-Wals ist eine registrierte Marke von Docker, Inc. Verwendet mit Genehmigung.</span><span class="sxs-lookup"><span data-stu-id="86830-118">The Docker whale logo is a registered trademark of Docker, Inc. Used by permission.</span></span>

<span data-ttu-id="86830-119">Alle anderen Marken und Logos sind Eigentum der jeweiligen Besitzer.</span><span class="sxs-lookup"><span data-stu-id="86830-119">All other marks and logos are property of their respective owners.</span></span>

<span data-ttu-id="86830-120">Autor:</span><span class="sxs-lookup"><span data-stu-id="86830-120">Author:</span></span>

> <span data-ttu-id="86830-121">**Mark Rendle** – Chief Technical Officer – [Visual ReCode](https://visualrecode.com)</span><span class="sxs-lookup"><span data-stu-id="86830-121">**Mark Rendle** - Chief Technical Officer - [Visual Recode](https://visualrecode.com)</span></span>
>
> <span data-ttu-id="86830-122">**Miranda Steiner** – Technical Author</span><span class="sxs-lookup"><span data-stu-id="86830-122">**Miranda Steiner** - Technical Author</span></span>

<span data-ttu-id="86830-123">Editoren:</span><span class="sxs-lookup"><span data-stu-id="86830-123">Editors:</span></span>

> <span data-ttu-id="86830-124">**Maira Wenzel** – Senior Content Developer – Microsoft</span><span class="sxs-lookup"><span data-stu-id="86830-124">**Maira Wenzel** - Sr Content Developer - Microsoft</span></span>

## <a name="introduction"></a><span data-ttu-id="86830-125">Einführung</span><span class="sxs-lookup"><span data-stu-id="86830-125">Introduction</span></span>

<span data-ttu-id="86830-126">TODO</span><span class="sxs-lookup"><span data-stu-id="86830-126">TODO</span></span>

## <a name="purpose"></a><span data-ttu-id="86830-127">Zweck</span><span class="sxs-lookup"><span data-stu-id="86830-127">Purpose</span></span>

<span data-ttu-id="86830-128">TODO</span><span class="sxs-lookup"><span data-stu-id="86830-128">TODO</span></span>

## <a name="who-should-use-this-guide"></a><span data-ttu-id="86830-129">Zielgruppe dieses Leitfadens</span><span class="sxs-lookup"><span data-stu-id="86830-129">Who should use this guide</span></span>

<span data-ttu-id="86830-130">**AKTUALISIEREN**</span><span class="sxs-lookup"><span data-stu-id="86830-130">**UPDATE THIS**</span></span>

<span data-ttu-id="86830-131">Die Zielgruppe für diesen Leitfaden sind WCF-Entwickler, Entwicklungsleiter und Architekten, die an der Migration von WCF-Lösungen auf .NET 4 und früheren Versionen zu ASP.NET Core 3.0 mithilfe von gRPC-Diensten interessiert sind.</span><span class="sxs-lookup"><span data-stu-id="86830-131">The audience for this guide is WCF developers, development leads, and architects who are interested in migrating WCF solutions on .NET 4 and earlier to ASP.NET Core 3.0 using gRPC services.</span></span>

## <a name="how-you-can-use-this-guide"></a><span data-ttu-id="86830-132">Wie Sie diesen Leitfaden verwenden können</span><span class="sxs-lookup"><span data-stu-id="86830-132">How you can use this guide</span></span>

<span data-ttu-id="86830-133">**AKTUALISIEREN**</span><span class="sxs-lookup"><span data-stu-id="86830-133">**UPDATE THIS**</span></span>

<span data-ttu-id="86830-134">Dies ist eine kurze Einführung in das Erstellen von gRPC-Diensten in ASP.NET Core 3.0 mit einem bestimmten Verweis auf die WCF als analoge Plattform.</span><span class="sxs-lookup"><span data-stu-id="86830-134">This is a short introduction to building gRPC Services in ASP.NET Core 3.0 with particular reference to WCF as an analogous platform.</span></span> <span data-ttu-id="86830-135">Darin werden die Prinzipien von gRPC erläutert, indem die einzelnen Konzepte den entsprechenden Features von WCF zugeordnet werden, und es wird ein Leitfaden zum Migrieren einer vorhandenen WCF-Anwendung zu gRPC geboten.</span><span class="sxs-lookup"><span data-stu-id="86830-135">It explains the principles of gRPC, relating each concept to the equivalent features of WCF, and offers guidance for migrating an existing WCF application to gRPC.</span></span> <span data-ttu-id="86830-136">Sie ist auch für Entwickler nützlich, die WCF-Kenntnisse haben und gRPC erlernen möchten, um neue Dienste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86830-136">It is also useful for developers who have experience of WCF and are looking to learn gRPC to build new services.</span></span> <span data-ttu-id="86830-137">Die Beispielanwendung kann als Vorlage oder Verweis für Ihre eigenen Projekte verwendet werden, und Sie können Code aus dem Buch oder seinen Beispielen kopieren und erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="86830-137">The sample application can be used as a template or reference for your own projects, and you are free to copy and reuse code from the book or its samples.</span></span>

<span data-ttu-id="86830-138">Sie können diesen Leitfaden gerne an Ihr Team weiterleiten, um ein gemeinsames Verständnis dieser Überlegungen und Möglichkeiten zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="86830-138">Feel free to forward this guide to your team to help ensure a common understanding of these considerations and opportunities.</span></span> <span data-ttu-id="86830-139">Wenn alle Beteiligten mit einer gemeinsamen Terminologie und den zugrunde liegenden Prinzipien arbeiten, kann eine konsistente Anwendung von Architekturmustern und -praktiken gewährleistet werden.</span><span class="sxs-lookup"><span data-stu-id="86830-139">Having everybody working from a common set of terminology and underlying principles helps ensure consistent application of architectural patterns and practices.</span></span>

## <a name="references"></a><span data-ttu-id="86830-140">Verweise</span><span class="sxs-lookup"><span data-stu-id="86830-140">References</span></span>

- <span data-ttu-id="86830-141">**gRPC-Website**</span><span class="sxs-lookup"><span data-stu-id="86830-141">**gRPC web site**</span></span>  
  <https://grpc.io>
- <span data-ttu-id="86830-142">**Wahl zwischen .NET Core und .NET Framework für Server-Apps**</span><span class="sxs-lookup"><span data-stu-id="86830-142">**Choosing between .NET Core and .NET Framework for server apps**</span></span>  
  <https://docs.microsoft.com/dotnet/standard/choosing-core-framework-server>

>[!div class="step-by-step"]
>[<span data-ttu-id="86830-143">Nächste</span><span class="sxs-lookup"><span data-stu-id="86830-143">Next</span></span>](introduction.md)