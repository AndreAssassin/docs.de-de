---
title: InvalidFunctionPointerInDelegate-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- invalidFunctionPointerInDelegate MDA
- managed debugging assistants (MDAs), invalid function pointer to delegates
- MDAs (managed debugging assistants), invalid function pointer to delegates
- function pointers, invalid
- marshaling, run-time errors
- managed debugging assistants (MDAs), marshaling
- MDAs (managed debugging assistants), marshaling
- invalid function pointers
ms.assetid: 99ae44f1-783e-49a9-9009-24f54bbd0f09
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cbb33d2cddab22ad2072354ba543d2cd6a60a668
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61754569"
---
# <a name="invalidfunctionpointerindelegate-mda"></a><span data-ttu-id="a207e-102">InvalidFunctionPointerInDelegate-MDA</span><span class="sxs-lookup"><span data-stu-id="a207e-102">invalidFunctionPointerInDelegate MDA</span></span>
<span data-ttu-id="a207e-103">Der `invalidFunctionPointerInDelegate` Assistent für verwaltetes Debuggen (MDA) wird aktiviert, wenn ein ungültiger Funktionszeiger übergeben wird, um einen Delegaten über einen systemeigenen Funktionszeiger zu konstruieren.</span><span class="sxs-lookup"><span data-stu-id="a207e-103">The `invalidFunctionPointerInDelegate` managed debugging assistant (MDA) is activated when an invalid function pointer is passed in to construct a delegate over a native function pointer.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="a207e-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="a207e-104">Symptoms</span></span>  
 <span data-ttu-id="a207e-105">Zugriffsverletzungen oder unerwartete Speicherschäden beim Verwenden eines Delegaten über einen Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="a207e-105">Access violations or unexpected memory corruption when using a delegate over a function pointer.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="a207e-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="a207e-106">Cause</span></span>  
 <span data-ttu-id="a207e-107">Es wurde ein ungültiger Funktionszeiger angegeben.</span><span class="sxs-lookup"><span data-stu-id="a207e-107">An invalid function pointer was specified.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="a207e-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="a207e-108">Resolution</span></span>  
 <span data-ttu-id="a207e-109">Geben Sie einen gültigen Funktionszeiger an.</span><span class="sxs-lookup"><span data-stu-id="a207e-109">Specify a valid function pointer</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="a207e-110">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a207e-110">Effect on the Runtime</span></span>  
 <span data-ttu-id="a207e-111">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="a207e-111">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="a207e-112">Output</span><span class="sxs-lookup"><span data-stu-id="a207e-112">Output</span></span>  
 <span data-ttu-id="a207e-113">Der ungültige Funktionszeiger.</span><span class="sxs-lookup"><span data-stu-id="a207e-113">The invalid function pointer.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="a207e-114">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="a207e-114">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <invalidFunctionPointerInDelegate />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a207e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a207e-115">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="a207e-116">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="a207e-116">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="a207e-117">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="a207e-117">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
