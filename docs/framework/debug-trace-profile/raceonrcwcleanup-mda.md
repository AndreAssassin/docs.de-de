---
title: raceOnRCWCleanup-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- RCW
- managed debugging assistants (MDAs), RCWs
- race on RCW cleanup
- MDAs (managed debugging assistants), RCWs
- RaceOnRCWCleanup MDA
- runtime callable wrappers
ms.assetid: bee1e9b1-50a8-4c89-9cd9-7dd6b2458187
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628790bb8229dc519589c122235f07a38ba57c1c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59100235"
---
# <a name="raceonrcwcleanup-mda"></a><span data-ttu-id="8f6bd-102">raceOnRCWCleanup-MDA</span><span class="sxs-lookup"><span data-stu-id="8f6bd-102">raceOnRCWCleanup MDA</span></span>
<span data-ttu-id="8f6bd-103">Der `raceOnRCWCleanup`-MDA (Assistent für verwaltetes Debuggen) wird aktiviert, wenn die CLR (Common Language Runtime) ermittelt, dass ein [RWC (Runtime Callable Wrapper)](../../../docs/framework/interop/runtime-callable-wrapper.md) verwendet wird, wenn ein Freigabeaufruf mithilfe eines Befehls wie etwa der <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType>-Methode erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-103">The `raceOnRCWCleanup` managed debugging assistant (MDA) is activated when the common language runtime (CLR) detects that a [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) (RCW) is in use when a call to release it is made using a command such as the <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="8f6bd-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="8f6bd-104">Symptoms</span></span>  
 <span data-ttu-id="8f6bd-105">Zugriffsverletzungen oder Speicherschäden während oder nach dem Freigeben eines RCW mithilfe von <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> oder einer ähnlichen Methode.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-105">Access violations or memory corruption during or after freeing an RCW using <xref:System.Runtime.InteropServices.Marshal.ReleaseComObject%2A> or a similar method.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="8f6bd-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="8f6bd-106">Cause</span></span>  
 <span data-ttu-id="8f6bd-107">Der RCW wird in einem anderen Thread oder für den freigebenden Threadstapel verwendet.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-107">The RCW is in use on another thread or on the freeing thread stack.</span></span>  <span data-ttu-id="8f6bd-108">Ein RCW, der verwendet wird, kann nicht freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-108">An RCW that is in use cannot be released.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="8f6bd-109">Auflösung</span><span class="sxs-lookup"><span data-stu-id="8f6bd-109">Resolution</span></span>  
 <span data-ttu-id="8f6bd-110">Geben Sie einen RCW, der im aktuellen Thread oder in anderen Threads verwendet wird, nicht frei.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-110">Do not free an RCW that could be in use either in the current or in other threads.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="8f6bd-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8f6bd-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="8f6bd-112">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-112">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="8f6bd-113">Output</span><span class="sxs-lookup"><span data-stu-id="8f6bd-113">Output</span></span>  
 <span data-ttu-id="8f6bd-114">Eine Meldung mit einer Beschreibung des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="8f6bd-114">A message describing the error.</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="8f6bd-115">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="8f6bd-115">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <raceOnRCWCleanup/>  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f6bd-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f6bd-116">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="8f6bd-117">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="8f6bd-117">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="8f6bd-118">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="8f6bd-118">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
