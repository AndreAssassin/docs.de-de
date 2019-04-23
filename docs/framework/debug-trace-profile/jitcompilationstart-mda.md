---
title: jitCompilationStart-MDA
ms.date: 03/30/2017
helpviewer_keywords:
- JIT compilation
- MDAs (managed debugging assistants), JIT compilation
- JitCompilationStart MDA
- managed debugging assistants (MDAs), JIT compilation
ms.assetid: 5ffd2857-d0ba-4342-9824-9ffe04ec135d
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62064286fecc4736f39ad790f0fd7f0e6d84b149
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162344"
---
# <a name="jitcompilationstart-mda"></a><span data-ttu-id="30faa-102">jitCompilationStart-MDA</span><span class="sxs-lookup"><span data-stu-id="30faa-102">jitCompilationStart MDA</span></span>
<span data-ttu-id="30faa-103">Der Assistent für verwaltetes Debuggen (MDA) `jitCompilationStart` berichtet, wann der JIT-Compiler mit der Kompilierung einer Funktion beginnt.</span><span class="sxs-lookup"><span data-stu-id="30faa-103">The `jitCompilationStart` managed debugging assistant (MDA) is activated to report when the just-in-time (JIT) compiler starts to compile a function.</span></span>  
  
## <a name="symptoms"></a><span data-ttu-id="30faa-104">Symptome</span><span class="sxs-lookup"><span data-stu-id="30faa-104">Symptoms</span></span>  
 <span data-ttu-id="30faa-105">Die Größe der Arbeitssätze vergrößert sich für ein Programm, das bereits im nativen Bildformat vorhanden ist, da „mscorjit.dll“ in den Prozess geladen wird.</span><span class="sxs-lookup"><span data-stu-id="30faa-105">The working set size increases for a program that is already in native image format because mscorjit.dll is loaded into the process.</span></span>  
  
## <a name="cause"></a><span data-ttu-id="30faa-106">Ursache</span><span class="sxs-lookup"><span data-stu-id="30faa-106">Cause</span></span>  
 <span data-ttu-id="30faa-107">Nicht alle Assemblys, von denen die Anwendung abhängt, wurden im nativen Format generiert, oder die, für die das der Fall ist, wurden nicht korrekt registriert.</span><span class="sxs-lookup"><span data-stu-id="30faa-107">Not all the assemblies the program depends on have been generated into native format, or those that have are not registered correctly.</span></span>  
  
## <a name="resolution"></a><span data-ttu-id="30faa-108">Auflösung</span><span class="sxs-lookup"><span data-stu-id="30faa-108">Resolution</span></span>  
 <span data-ttu-id="30faa-109">Durch die Aktivierung dieses MDA können Sie bestimmen, welche Funktion JIT-kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="30faa-109">Enabling this MDA allows you to determine which function is being JIT-compiled.</span></span> <span data-ttu-id="30faa-110">Bestimmen Sie, ob die Assembly mit der Funktion im nativen Format generiert und ordnungsgemäß registriert wird.</span><span class="sxs-lookup"><span data-stu-id="30faa-110">Determine whether the assembly that contains the function is generated to native format and properly registered.</span></span>  
  
## <a name="effect-on-the-runtime"></a><span data-ttu-id="30faa-111">Auswirkungen auf die Laufzeit</span><span class="sxs-lookup"><span data-stu-id="30faa-111">Effect on the Runtime</span></span>  
 <span data-ttu-id="30faa-112">Dieser MDA protokolliert eine Meldung, kurz bevor eine Methode JIT-kompiliert wird. Deshalb hat die Aktivierung dieses MDA erhebliche Auswirkungen auf die Leistung.</span><span class="sxs-lookup"><span data-stu-id="30faa-112">This MDA logs a message just before a method is JIT-compiled, so enabling this MDA has significant impact on performance.</span></span> <span data-ttu-id="30faa-113">Beachten Sie, dass dieser MDA keine separate Nachricht generiert, wenn eine Methode inline ist.</span><span class="sxs-lookup"><span data-stu-id="30faa-113">Note that if a method is inline, this MDA will not generate a separate message.</span></span>  
  
## <a name="output"></a><span data-ttu-id="30faa-114">Output</span><span class="sxs-lookup"><span data-stu-id="30faa-114">Output</span></span>  
 <span data-ttu-id="30faa-115">Das folgende Codebeispiel zeigt eine Beispielausgabe.</span><span class="sxs-lookup"><span data-stu-id="30faa-115">The following code sample shows sample output.</span></span> <span data-ttu-id="30faa-116">In diesem Fall zeigt die Ausgabe an, dass in der Assembly „Die M-Methode testen“ der Klasse „ns2.CO“ JIT-kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="30faa-116">In this case the output shows that in assembly Test the method "m" on class "ns2.CO" was JIT-compiled.</span></span>  
  
```  
method name="Test!ns2.C0::m"  
```  
  
## <a name="configuration"></a><span data-ttu-id="30faa-117">Konfiguration</span><span class="sxs-lookup"><span data-stu-id="30faa-117">Configuration</span></span>  
 <span data-ttu-id="30faa-118">Die folgende Konfigurationsdatei zeigt eine Reihe von Filtern, die filtern können, welche Methoden gemeldet werden, wenn sie zuerst JIT-kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="30faa-118">The following configuration file shows a variety of filters that can be employed to filter out which methods are reported when they are first JIT-compiled.</span></span> <span data-ttu-id="30faa-119">Sie können angeben, dass alle Methoden gemeldet werden, indem der Wert des Attributs "Name", \*.</span><span class="sxs-lookup"><span data-stu-id="30faa-119">You can specify that all methods be reported by setting the value of the name attribute to \*.</span></span>  
  
```xml  
<mdaConfig>  
  <assistants>  
    <jitCompilationStart>  
      <methods>  
        <match name="C0::m" />  
        <match name="MyMethod" />  
        <match name="C2::*" />  
        <match name="ns0::*" />  
        <match name="ns1.C0::*" />  
        <match name="ns2.C0::m" />  
        <match name="ns2.C0+N0::m" />  
      </methods>  
    </jitCompilationStart >  
  </assistants>  
</mdaConfig>  
```  
  
## <a name="example"></a><span data-ttu-id="30faa-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30faa-120">Example</span></span>  
 <span data-ttu-id="30faa-121">Das folgende Codebeispiel ist dazu vorgesehen, mit der vorangegangenen Konfigurationsdatei verwendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="30faa-121">The following code sample is intended to be used with the preceding configuration file.</span></span>  
  
```csharp
using System;  
using System.Reflection;  
using System.Runtime.CompilerServices;  
using System.Runtime.InteropServices;  
  
public class Entry  
{  
    public static void Main(string[] args)  
    {  
        C0.m();  
        C1.MyMethod();  
        C2.m();  
  
        ns0.C0.m();  
        ns0.C0.N0.m();  
        ns0.C1.m();  
  
        ns1.C0.m();  
        ns1.C0.N0.m();  
  
        ns2.C0.m();  
        ns2.C0.N0.m();  
    }  
}  
  
public class C0  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
public class C1  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void MyMethod() { }  
}  
  
public class C2  
{  
    [MethodImpl(MethodImplOptions.NoInlining)]  
    public static void m() { }  
}  
  
namespace ns0  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
  
    public class C1  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
    }  
}  
  
namespace ns1  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
  
namespace ns2  
{  
    public class C0  
    {  
        [MethodImpl(MethodImplOptions.NoInlining)]  
        public static void m() { }  
  
        public class N0  
        {  
            [MethodImpl(MethodImplOptions.NoInlining)]  
            public static void m() { }  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="30faa-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30faa-122">See also</span></span>

- <xref:System.Runtime.InteropServices.MarshalAsAttribute>
- [<span data-ttu-id="30faa-123">Diagnosing Errors with Managed Debugging Assistants (Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen)</span><span class="sxs-lookup"><span data-stu-id="30faa-123">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="30faa-124">Interop Marshaling (Interop-Marshalling)</span><span class="sxs-lookup"><span data-stu-id="30faa-124">Interop Marshaling</span></span>](../../../docs/framework/interop/interop-marshaling.md)
