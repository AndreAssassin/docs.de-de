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
ms.openlocfilehash: cb7520518497b244be8be3751ca8a3063a02717a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59135862"
---
# <a name="clr-etw-events"></a><span data-ttu-id="0c1db-102">CLR-ETW-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-102">CLR ETW Events</span></span>
<span data-ttu-id="0c1db-103">Die Themen in diesem Abschnitt beschreiben die Ereignisablaufverfolgung für Windows-Ereignisse (ETW).</span><span class="sxs-lookup"><span data-stu-id="0c1db-103">The topics in this section describe event tracing for Windows (ETW) events.</span></span> <span data-ttu-id="0c1db-104">Jedes Ereignis verfügt über ein zugeordnetes Schlüsselwort und die Ebene, die im Thema [CLR-ETW-Schlüsselwörter und-Ebenen](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="0c1db-104">Each event has an associated keyword and level, which are described in the [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md) topic.</span></span> <span data-ttu-id="0c1db-105">Die CLR verfügt über zwei Anbieter für die Ereignisse:</span><span class="sxs-lookup"><span data-stu-id="0c1db-105">The CLR has two providers for the events:</span></span>  
  
-   <span data-ttu-id="0c1db-106">Der Laufzeitanbieter löst Ereignisse in Abhängigkeit von den aktivierten Schlüsselwörtern (Ereigniskategorien) aus.</span><span class="sxs-lookup"><span data-stu-id="0c1db-106">The runtime provider, which raises events depending on which keywords (categories of events) are enabled.</span></span> <span data-ttu-id="0c1db-107">Die GUID des CLR-Laufzeitanbieters ist e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span><span class="sxs-lookup"><span data-stu-id="0c1db-107">The CLR runtime provider GUID is e13c0d23-ccbc-4e12-931b-d9cc2eee27e4.</span></span>  
  
-   <span data-ttu-id="0c1db-108">Der Rundownanbieter, der für spezielle Zwecke genutzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0c1db-108">The rundown provider, which has special-purpose uses.</span></span> <span data-ttu-id="0c1db-109">Die GUID des CLR-Rundownanbieters ist A669021C-C450-4609-A035-5AF59AF4DF18.</span><span class="sxs-lookup"><span data-stu-id="0c1db-109">The CLR rundown provider GUID is a669021c-c450-4609-a035-5af59af4df18.</span></span>  
  
 <span data-ttu-id="0c1db-110">Weitere Informationen zu den Anbietern finden Sie unter [CLR-ETW-Anbieter](../../../docs/framework/performance/clr-etw-providers.md).</span><span class="sxs-lookup"><span data-stu-id="0c1db-110">For more information about the providers, see [CLR ETW Providers](../../../docs/framework/performance/clr-etw-providers.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0c1db-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0c1db-111">In This Section</span></span>  
 [<span data-ttu-id="0c1db-112">Laufzeitinformationsereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-112">Runtime Information Events</span></span>](../../../docs/framework/performance/runtime-information-etw-events.md)  
 <span data-ttu-id="0c1db-113">Erfasst Informationen über die Laufzeit, einschließlich der SKU, der Versionsnummer, der Art der Aktivierung der Laufzeit, der Befehlszeilenparameter, mit denen sie gestartet wurde, der GUID (wenn zutreffend) und weiterer wichtiger Informationen.</span><span class="sxs-lookup"><span data-stu-id="0c1db-113">Captures information about the runtime, including the SKU, version number, the manner in which the runtime was activated, the command-line parameters it was started with, the GUID (if applicable), and other relevant information.</span></span>  
  
 [<span data-ttu-id="0c1db-114">ExceptionThrown_V1-Ereignis</span><span class="sxs-lookup"><span data-stu-id="0c1db-114">Exception Thrown_V1 Event</span></span>](../../../docs/framework/performance/exception-thrown-v1-etw-event.md)  
 <span data-ttu-id="0c1db-115">Erfasst Informationen über Ausnahmen, die ausgelöst wurden.</span><span class="sxs-lookup"><span data-stu-id="0c1db-115">Captures information about exceptions that are thrown.</span></span>  
  
 [<span data-ttu-id="0c1db-116">Konfliktereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-116">Contention Events</span></span>](../../../docs/framework/performance/contention-etw-events.md)  
 <span data-ttu-id="0c1db-117">Erfasst Informationen über Konflikte bezüglich Überwachungssperren oder nativen Sperren, die von der Laufzeit verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c1db-117">Captures information about contention for monitor locks or native locks that the runtime uses.</span></span>  
  
 [<span data-ttu-id="0c1db-118">Threadpoolereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-118">Thread Pool Events</span></span>](../../../docs/framework/performance/thread-pool-etw-events.md)  
 <span data-ttu-id="0c1db-119">Erfasst Informationen zu den Arbeitsthreadpools und den I/O-Threadpools.</span><span class="sxs-lookup"><span data-stu-id="0c1db-119">Captures information about worker thread pools and I/O thread pools.</span></span>  
  
 [<span data-ttu-id="0c1db-120">Ladeprogrammereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-120">Loader Events</span></span>](../../../docs/framework/performance/loader-etw-events.md)  
 <span data-ttu-id="0c1db-121">Erfasst Informationen zum Laden und Entladen von Anwendungsdomänen, Assemblys und Modulen.</span><span class="sxs-lookup"><span data-stu-id="0c1db-121">Captures information about loading and unloading application domains, assemblies, and modules.</span></span>  
  
 [<span data-ttu-id="0c1db-122">Methodenereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-122">Method Events</span></span>](../../../docs/framework/performance/method-etw-events.md)  
 <span data-ttu-id="0c1db-123">Erfasst Informationen über CLR-Methoden für die Symbolauflösung.</span><span class="sxs-lookup"><span data-stu-id="0c1db-123">Captures information about CLR methods for symbol resolution.</span></span>  
  
 [<span data-ttu-id="0c1db-124">Garbage Collection-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-124">Garbage Collection Events</span></span>](../../../docs/framework/performance/garbage-collection-etw-events.md)  
 <span data-ttu-id="0c1db-125">Erfasst Informationen zur Garbage Collection, und hilft Ihnen bei der Diagnose und beim Debuggen.</span><span class="sxs-lookup"><span data-stu-id="0c1db-125">Captures information pertaining to garbage collection, to help in diagnostics and debugging.</span></span>  
  
 [<span data-ttu-id="0c1db-126">JIT-Ablaufverfolgungsereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-126">JIT Tracing Events</span></span>](../../../docs/framework/performance/jit-tracing-etw-events.md)  
 <span data-ttu-id="0c1db-127">Erfasst Informationen über JIT-Inlining und Endeaufrufe.</span><span class="sxs-lookup"><span data-stu-id="0c1db-127">Captures information about just-in-time (JIT) inlining and tail calls.</span></span>  
  
 [<span data-ttu-id="0c1db-128">Interop-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-128">Interop Events</span></span>](../../../docs/framework/performance/interop-etw-events.md)  
 <span data-ttu-id="0c1db-129">Erfasst Informationen über die Stubgenerierung und Zwischenspeicherung der Microsoft Intermediate Language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="0c1db-129">Captures information about Microsoft intermediate language (MSIL) stub generation and caching.</span></span>  
  
 [<span data-ttu-id="0c1db-130">ARM-Ereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-130">ARM Events</span></span>](../../../docs/framework/performance/application-domain-resource-monitoring-arm-etw-events.md)  
 <span data-ttu-id="0c1db-131">Erfasst detaillierte Diagnoseinformationen über den Status einer Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="0c1db-131">Captures detailed diagnostic information about the state of an application domain.</span></span>  
  
 [<span data-ttu-id="0c1db-132">Sicherheitsereignisse</span><span class="sxs-lookup"><span data-stu-id="0c1db-132">Security Events</span></span>](../../../docs/framework/performance/security-etw-events.md)  
 <span data-ttu-id="0c1db-133">Erfasst Informationen über starke Namen und Authenticodeüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="0c1db-133">Captures information about strong name and Authenticode verification.</span></span>  
  
 [<span data-ttu-id="0c1db-134">Stapelereignis</span><span class="sxs-lookup"><span data-stu-id="0c1db-134">Stack Event</span></span>](../../../docs/framework/performance/stack-etw-event.md)  
 <span data-ttu-id="0c1db-135">Erfasst Informationen, die mit anderen Ereignissen zur Generierung von Stackablaufverfolgungen verwendet werden, nachdem ein Ereignis eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="0c1db-135">Captures information that is used with other events to generate stack traces after an event is raised.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c1db-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c1db-136">See also</span></span>

- [<span data-ttu-id="0c1db-137">Verbessertes Debugging und Leistungsoptimierung mit ETW</span><span class="sxs-lookup"><span data-stu-id="0c1db-137">Improve Debugging And Performance Tuning With ETW</span></span>](https://go.microsoft.com/fwlink/?LinkId=179696)
- [<span data-ttu-id="0c1db-138">Windows Performance-Blog</span><span class="sxs-lookup"><span data-stu-id="0c1db-138">Windows Performance Blog</span></span>](https://go.microsoft.com/fwlink/?LinkId=179509)
- [<span data-ttu-id="0c1db-139">Controlling .NET Framework Logging (Steuern der Protokollierung in .NET Framework)</span><span class="sxs-lookup"><span data-stu-id="0c1db-139">Controlling .NET Framework Logging</span></span>](../../../docs/framework/performance/controlling-logging.md)
- [<span data-ttu-id="0c1db-140">CLR ETW Providers (CLR-ETW-Anbieter)</span><span class="sxs-lookup"><span data-stu-id="0c1db-140">CLR ETW Providers</span></span>](../../../docs/framework/performance/clr-etw-providers.md)
- [<span data-ttu-id="0c1db-141">CLR ETW Keywords and Levels (CLR-ETW-Schlüsselwörter und -Ebenen)</span><span class="sxs-lookup"><span data-stu-id="0c1db-141">CLR ETW Keywords and Levels</span></span>](../../../docs/framework/performance/clr-etw-keywords-and-levels.md)
- [<span data-ttu-id="0c1db-142">ETW-Ereignisse in der Common Language Runtime</span><span class="sxs-lookup"><span data-stu-id="0c1db-142">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
