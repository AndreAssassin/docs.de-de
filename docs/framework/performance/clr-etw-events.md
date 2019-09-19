---
title: CLR-ETW-Ereignisse
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events
- ETW, common language runtime
- ETW, CLR events
ms.assetid: ef2b31c3-7426-43e7-9924-92339b96556d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6798a83973f94f07a2a215d5208aa55f0f9ae929
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046749"
---
# <a name="clr-etw-events"></a><span data-ttu-id="1bdbf-102">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-102">CLR ETW Events</span></span>
<span data-ttu-id="1bdbf-103">Die Themen in diesem Abschnitt beschreiben die Ereignisablaufverfolgung für Windows-Ereignisse (ETW).</span><span class="sxs-lookup"><span data-stu-id="1bdbf-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="1bdbf-104">Jedes Ereignis verfügt über ein zugeordnetes Schlüsselwort und die Ebene, die im Thema [CLR-ETW-Schlüsselwörter und-Ebenen](clr-etw-keywords-and-levels.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="1bdbf-105">Die CLR verfügt über zwei Anbieter für die Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="1bdbf-105">The CLR has two providers for the events:</span></span>  
  
- <span data-ttu-id="1bdbf-106">Der Laufzeitanbieter löst Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern (Ereigniskategorien) aus.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="1bdbf-107">Die GUID des CLR-Laufzeitanbieters ist e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
- <span data-ttu-id="1bdbf-108">Der Rundownanbieter, der für spezielle Zwecke genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="1bdbf-109">Die GUID des CLR-Rundownanbieters ist A669021C-C450-4609-A035-5AF59AF4DF18.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="1bdbf-110">Weitere Informationen zu den Anbietern finden Sie unter [CLR-ETW-Anbieter](clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="1bdbf-110">For more information about the providers, see [CLR ETW Providers](clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1bdbf-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1bdbf-111">In This Section</span></span>  
 [<span data-ttu-id="1bdbf-112">Laufzeitinformationsereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-112">Runtime Information Events</span></span>](runtime-information-etw-events.md)  
 <span data-ttu-id="1bdbf-113">Erfasst Informationen über die Laufzeit, einschließlich der SKU, der Versionsnummer, der Art der Aktivierung der Laufzeit, der Befehlszeilenparameter, mit denen sie gestartet wurde, der GUID (wenn zutreffend) und weiterer wichtiger Informationen.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="1bdbf-114">ExceptionThrown_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="1bdbf-114">Exception Thrown_V1 Event</span></span>](exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="1bdbf-115">Erfasst Informationen über Ausnahmen, die ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="1bdbf-116">Konfliktereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-116">Contention Events</span></span>](contention-etw-events.md)  
 <span data-ttu-id="1bdbf-117">Erfasst Informationen über Konflikte bezüglich Überwachungssperren oder nativen Sperren, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="1bdbf-118">Threadpoolereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-118">Thread Pool Events</span></span>](thread-pool-etw-events.md)  
 <span data-ttu-id="1bdbf-119">Erfasst Informationen zu den Arbeitsthreadpools und den I/O-Threadpools.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="1bdbf-120">Ladeprogrammereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-120">Loader Events</span></span>](loader-etw-events.md)  
 <span data-ttu-id="1bdbf-121">Erfasst Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="1bdbf-122">Methodenereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-122">Method Events</span></span>](method-etw-events.md)  
 <span data-ttu-id="1bdbf-123">Erfasst Informationen über CLR-Methoden für die Symbolauflösung.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="1bdbf-124">Garbage Collection-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-124">Garbage Collection Events</span></span>](garbage-collection-etw-events.md)  
 <span data-ttu-id="1bdbf-125">Erfasst Informationen zur Garbage Collection, und hilft Ihnen bei der Diagnose und beim Debuggen.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="1bdbf-126">JIT-Ablaufverfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-126">JIT Tracing Events</span></span>](jit-tracing-etw-events.md)  
 <span data-ttu-id="1bdbf-127">Erfasst Informationen über JIT-Inlining und Endeaufrufe.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="1bdbf-128">Interop-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-128">Interop Events</span></span>](interop-etw-events.md)  
 <span data-ttu-id="1bdbf-129">Erfasst Informationen über die Stubgenerierung und Zwischenspeicherung der Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1bdbf-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="1bdbf-130">ARM-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-130">ARM Events</span></span>](application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="1bdbf-131">Erfasst detaillierte Diagnoseinformationen über den Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="1bdbf-132">Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="1bdbf-132">Security Events</span></span>](security-etw-events.md)  
 <span data-ttu-id="1bdbf-133">Erfasst Informationen über starke Namen und Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="1bdbf-134">Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="1bdbf-134">Stack Event</span></span>](stack-etw-event.md)  
 <span data-ttu-id="1bdbf-135">Erfasst Informationen, die mit anderen Ereignissen zur Generierung von Stackablaufverfolgungen verwendet werden, nachdem ein Ereignis eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="1bdbf-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bdbf-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1bdbf-136">See also</span></span>

- [<span data-ttu-id="1bdbf-137">Verbessern der Debuggen und Leistungsoptimierung mit etw</span><span class="sxs-lookup"><span data-stu-id="1bdbf-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="1bdbf-138">Windows Performance-Blog</span><span class="sxs-lookup"><span data-stu-id="1bdbf-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="1bdbf-139">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="1bdbf-139">Controlling .NET Framework Logging</span></span>](controlling-logging.md)
- [<span data-ttu-id="1bdbf-140">CLR ETW Providers (CLR-ETW-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="1bdbf-140">CLR ETW Providers</span></span>](clr-etw-providers.md)
- [<span data-ttu-id="1bdbf-141">CLR ETW Keywords and Levels (CLR-ETW-Schlüsselwörter und -Ebenen)</span><span class="sxs-lookup"><span data-stu-id="1bdbf-141">CLR ETW Keywords and Levels</span></span>](clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="1bdbf-142">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="1bdbf-142">ETW Events in the Common Language Runtime</span></span>](etw-events-in-the-common-language-runtime.md)
