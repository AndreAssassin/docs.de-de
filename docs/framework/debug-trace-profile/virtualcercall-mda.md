---
title: VirtualCERCall-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- MDAs (managed debugging assistants), CER calls
- virtualCERCall MDA
- virtual CER calls
- constrained execution regions
- CER calls
- managed debugging assistants (MDAs), CER calls
ms.assetid: 1eb18c7a-f5e0-443f-80fb-67bfbb047da2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e2c8712837dab17f70be32617711c1bad9349508
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086077"
---
# <a name="virtualcercall-mda"></a><span data-ttu-id="f6659-102">VirtualCERCall-MDA</span><span class="sxs-lookup"><span data-stu-id="f6659-102">virtualCERCall MDA</span></span>
<span data-ttu-id="f6659-103">Der `virtualCERCall`-MDA (Assistent für verwaltetes Debuggen) wird als Warnung aktiviert und gibt an, dass eine Aufrufwebsite in einem Aufrufdiagramm eines eingeschränkten Ausführungsbereichs (CER) auf ein virtuelles Ziel verweist, also ein virtueller Aufruf an eine virtuelle, nicht finale Methode oder ein Aufruf, der eine Schnittstelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="f6659-103">The `virtualCERCall` managed debugging assistant (MDA) is activated as a warning indicating that a call site within a constrained execution region (CER) call graph refers to a virtual target, that is, a virtual call to a non-final virtual method or a call using an interface.</span></span> <span data-ttu-id="f6659-104">Die Common Language Runtime (CLR) kann die Zielmethode dieser Aufrufe der Intermediate Language und der Metadatenanalyse nicht allein vorhersagen.</span><span class="sxs-lookup"><span data-stu-id="f6659-104">The common language runtime (CLR) cannot predict the destination method of these calls from the intermediate language and metadata analysis alone.</span></span> <span data-ttu-id="f6659-105">Folglich kann die Aufrufstruktur nicht als Teil des CER-Diagramms vorbereitet und Threadabbrüche in dieser Unterstruktur nicht automatisch blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="f6659-105">As a result, the call tree cannot be prepared as part of the CER graph and thread aborts in that subtree cannot be automatically blocked.</span></span> <span data-ttu-id="f6659-106">Dieser MDA gibt eine Warnung für die Fälle aus, in denen ein CER erweitert werden muss. Dazu werden explizite Aufrufe der <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A>-Methode verwendet, sobald die zusätzlichen Informationen, die zur Berechnung des Aufrufsziels erforderlich sind, zur Laufzeit bekannt sind.</span><span class="sxs-lookup"><span data-stu-id="f6659-106">This MDA warns of cases where a CER might need to be extended by using explicit calls to the <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> method once the additional information required to compute the call target is known at run time.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="f6659-107">Symptome</span><span class="sxs-lookup"><span data-stu-id="f6659-107">Symptoms</span></span>  
 <span data-ttu-id="f6659-108">CERs, die nicht ausgeführt werden, wenn ein Thread abgebrochen oder eine Anwendungsdomäne entladen wird.</span><span class="sxs-lookup"><span data-stu-id="f6659-108">CERs that do not run when a thread is aborted or an application domain is unloaded.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="f6659-109">Ursache</span><span class="sxs-lookup"><span data-stu-id="f6659-109">Cause</span></span>  
 <span data-ttu-id="f6659-110">Ein CER enthält einen Aufruf einer virtuellen Methode, die nicht automatisch vorbereitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f6659-110">A CER contains a call to a virtual method that cannot be prepared automatically.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="f6659-111">Auflösung</span><span class="sxs-lookup"><span data-stu-id="f6659-111">Resolution</span></span>  
 <span data-ttu-id="f6659-112">Rufen Sie <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> für die virtuelle Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f6659-112">Call <xref:System.Runtime.CompilerServices.RuntimeHelpers.PrepareMethod%2A> for the virtual method.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="f6659-113">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="f6659-113">Effect on the Runtime</span></span>  
 <span data-ttu-id="f6659-114">Dieser MDA hat keine Auswirkungen auf die CLR.</span><span class="sxs-lookup"><span data-stu-id="f6659-114">This MDA has no effect on the CLR.</span></span>  
  
## <a name="output"></a><span data-ttu-id="f6659-115">Output</span><span class="sxs-lookup"><span data-stu-id="f6659-115">Output</span></span>  
  
```  
Method 'MethodWithCer', while executing within a constrained execution region, makes a call  
at IL offset 0x0024 to 'VirtualMethod', which is virtual and cannot be prepared automatically  
at compile time. The caller must ensure this method is prepared explicitly at  
runtime before entering the constrained execution region.  
method name="VirtualMethod"  
declaringType name="VirtualCERCall+MyClass"  
  declaringModule name="mda"  
    callsite name="MethodWithCer" offset="0x0024"  
```  
  
## <a name="configuration"></a><span data-ttu-id="f6659-116">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="f6659-116">Configuration</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    < VirtualCERCall />  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="f6659-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6659-117">Example</span></span>  
  
```csharp
class MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    virtual void VirtualMethod()  
    {  
        ...  
    }  
}  
  
class MyDerivedClass : MyClass  
{  
    [ReliabilityContract(Consistency.MayCorruptProcess, CER.None)]  
    override void VirtualMethod()  
    {  
        ...  
    }  
}  
  
void MethodWithCer(MyClass object)  
{  
    RuntimeHelpers.PrepareConstrainedRegions();  
    try  
    {  
        ...  
    }  
    finally  
    {  
        // Start of the CER.  
  
        // Cannot tell at analysis time whether object is a MyClass  
        // or a MyDerivedClass, so we do not know which version of   
        // VirtualMethod we are going to call.  
        object.VirtualMethod();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="f6659-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6659-118">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="f6659-119">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="f6659-119">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="f6659-120">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="f6659-120">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
