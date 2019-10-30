---
title: Debugschnittstellen
ms.date: 02/07/2019
helpviewer_keywords:
- unmanaged interfaces [.NET Framework], debugging
- debugging interfaces [.NET Framework]
- interfaces [.NET Framework debugging]
ms.assetid: b6297c26-7624-4431-8af4-14112d07bcd5
ms.openlocfilehash: 07b39666637628102e9ffafd2c059ba0d4b51b92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097195"
---
# <a name="debugging-interfaces"></a><span data-ttu-id="1dfc7-102">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1dfc7-102">Debugging Interfaces</span></span>
<span data-ttu-id="1dfc7-103">In diesem Abschnitt werden die unverwalteten Schnittstellen beschrieben, die das Debuggen eines Programms behandeln, das in der Common Language Runtime (CLR) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-103">This section describes the unmanaged interfaces that handle the debugging of a program that is executing in the common language runtime (CLR).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1dfc7-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1dfc7-104">In This Section</span></span>  
 <span data-ttu-id="1dfc7-105">[ICLRDataEnumMemoryRegions-Schnittstelle](iclrdataenummemoryregions-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-105">[ICLRDataEnumMemoryRegions Interface](iclrdataenummemoryregions-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-106">Stellt eine Methode bereit, um Speicherbereiche aufzulisten, die von Aufrufern angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-106">Provides a method to enumerate regions of memory that are specified by callers.</span></span>  
  
 <span data-ttu-id="1dfc7-107">[ICLRDataEnumMemoryRegionsCallback-Schnittstelle](iclrdataenummemoryregionscallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-107">[ICLRDataEnumMemoryRegionsCallback Interface](iclrdataenummemoryregionscallback-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-108">Stellt eine Rückrufmethode für `EnumMemoryRegions` bereit, um an den Debugger das Ergebnis eines Versuchs zu melden, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-108">Provides a callback method for `EnumMemoryRegions` to report to the debugger, the result of an attempt to enumerate a specified region of memory.</span></span>  
  
 <span data-ttu-id="1dfc7-109">[ICLRDataTarget-Schnittstelle](iclrdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-109">[ICLRDataTarget Interface](iclrdatatarget-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-110">Stellt Methoden für die Interaktion mit einem Ziel-CLR-Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-110">Provides methods for interaction with a target CLR process.</span></span>  
  
 <span data-ttu-id="1dfc7-111">[ICLRDataTarget2-Schnittstelle](iclrdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-111">[ICLRDataTarget2 Interface](iclrdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-112">Eine Unterklasse von `ICLRDataTarget`, wird von der Datenzugriffsdienstebene zum Bearbeiten virtueller Speicherbereiche im Zielprozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-112">A subclass of `ICLRDataTarget` that is used by the data access services layer to manipulate virtual memory regions in the target process.</span></span>  
  
 <span data-ttu-id="1dfc7-113">[ICLRDataTarget3-Schnittstelle](iclrdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-113">[ICLRDataTarget3 Interface](iclrdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-114">Eine Unterklasse von [ICLRDataTarget2](iclrdatatarget2-interface.md) , die Zugriff auf Ausnahme Informationen bietet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-114">A subclass of [ICLRDataTarget2](iclrdatatarget2-interface.md) that provides access to exception information.</span></span>  
  
 <span data-ttu-id="1dfc7-115">[ICLRDebugging-Schnittstelle](iclrdebugging-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-115">[ICLRDebugging Interface](iclrdebugging-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-116">Stellt Methoden bereit, die das Laden und Entladen von Modulen für Debuggingzwecke behandeln.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-116">Provides methods that handle loading and unloading modules for debugging.</span></span>  
  
 <span data-ttu-id="1dfc7-117">[Iclrbinbugginglibraryprovider-Schnittstelle](iclrdebugginglibraryprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-117">[ICLRDebuggingLibraryProvider Interface](iclrdebugginglibraryprovider-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-118">Schließt die [Methode der ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md) ein, die eine Bibliotheks Anbieter-Rückruf Schnittstelle abruft, die es ermöglicht, Common Language Runtime versionsspezifische Debugbibliotheken bei Bedarf zu finden und zu laden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-118">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
 <span data-ttu-id="1dfc7-119">[ICLRMetadataLocator-Schnittstelle](iclrmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-119">[ICLRMetadataLocator Interface](iclrmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-120">Schnittstelle, mit der die Datenzugriffsdienstebene Metadaten von Assemblys in einem Zielprozess sucht.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-120">Interface used by the data access services layer to locate metadata of assemblies in a target process.</span></span>  
  
 <span data-ttu-id="1dfc7-121">[ICorDebug-Schnittstelle](icordebug-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-121">[ICorDebug Interface](icordebug-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-122">Stellt Methoden bereit, mit denen Entwickler Anwendungen in der CLR-Umgebung debuggen können.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-122">Provides methods that allow developers to debug applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="1dfc7-123">[ICorDebugAppDomain-Schnittstelle](icordebugappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-123">[ICorDebugAppDomain Interface](icordebugappdomain-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-124">Stellt Methoden zum Debuggen von Anwendungsdomänen bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-124">Provides methods for debugging application domains.</span></span>  
  
 <span data-ttu-id="1dfc7-125">[ICorDebugAppDomain2-Schnittstelle](icordebugappdomain2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-125">[ICorDebugAppDomain2 Interface](icordebugappdomain2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-126">Stellt Methoden bereit, um mit Arrays, Zeigern, Funktionszeigern und ByRef-Typen zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-126">Provides methods to work with arrays, pointers, function pointers, and ByRef types.</span></span> <span data-ttu-id="1dfc7-127">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-127">This interface is an extension of the `ICorDebugAppDomain` interface.</span></span>  
  
 <span data-ttu-id="1dfc7-128">[ICorDebugAppDomain3-Schnittstelle](icordebugappdomain3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-128">[ICorDebugAppDomain3 Interface](icordebugappdomain3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-129">Stellt Methoden bereit, um mit den Windows-Runtime Typen in einer Anwendungsdomäne zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-129">Provides methods to work with the Windows Runtime types in an application domain.</span></span> <span data-ttu-id="1dfc7-130">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAppDomain`- und `ICorDebugAppDomain2`-Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-130">This interface is an extension of the `ICorDebugAppDomain` and `ICorDebugAppDomain2` interfaces.</span></span>  
  
 <span data-ttu-id="1dfc7-131">[ICorDebugAppDomain4-Schnittstelle](icordebugappdomain4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-131">[ICorDebugAppDomain4 Interface](icordebugappdomain4-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-132">Erweitert die [ICorDebugAppDomain](icordebugappdomain-interface.md) -Schnittstelle logisch, um ein verwaltetes Objekt aus einer COM Callable Wrapper zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-132">Logically extends the [ICorDebugAppDomain](icordebugappdomain-interface.md) interface to get a managed object from a COM callable wrapper.</span></span>  
  
 <span data-ttu-id="1dfc7-133">[ICorDebug appdomainerum-Schnittstelle](icordebugappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-133">[ICorDebugAppDomainEnum Interface](icordebugappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-134">Stellt eine Methode bereit, die eine angegebene Anzahl von `ICorDebugAppDomain`-Werten zurückgibt, beginnend mit der nächsten Position in der Enumeration.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-134">Provides a method that returns a specified number of `ICorDebugAppDomain` values starting at the next location in the enumeration.</span></span>  
  
 <span data-ttu-id="1dfc7-135">[ICorDebugArrayValue-Schnittstelle](icordebugarrayvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-135">[ICorDebugArrayValue Interface](icordebugarrayvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-136">Eine Unterklasse von `ICorDebugHeapValue`, die ein eindimensionales oder mehrdimensionales Array darstellt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-136">A subclass of `ICorDebugHeapValue` that represents a single-dimensional or multi-dimensional array.</span></span>  
  
 <span data-ttu-id="1dfc7-137">[ICorDebug-Schnittstelle](icordebugassembly-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-137">[ICorDebugAssembly Interface](icordebugassembly-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-138">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-138">Represents an assembly.</span></span>  
  
 <span data-ttu-id="1dfc7-139">[ICorDebugAssembly2-Schnittstelle](icordebugassembly2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-139">[ICorDebugAssembly2 Interface](icordebugassembly2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-140">Stellt eine Assembly dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-140">Represents an assembly.</span></span> <span data-ttu-id="1dfc7-141">Diese Schnittstelle ist eine Erweiterung der `ICorDebugAssembly`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-141">This interface is an extension of the `ICorDebugAssembly` interface.</span></span>  
  
 <span data-ttu-id="1dfc7-142">[ICorDebugAssembly3-Schnittstelle](icordebugassembly3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-142">[ICorDebugAssembly3 Interface](icordebugassembly3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-143">Erweitert die [ICorDebugAssembly](icordebugassembly-interface.md) -Schnittstelle logisch, um die Unterstützung für containerassemblys und ihre enthaltenen Assemblys</span><span class="sxs-lookup"><span data-stu-id="1dfc7-143">Logically extends the [ICorDebugAssembly](icordebugassembly-interface.md) interface to provide support for container assemblies and their contained assemblies.</span></span> <span data-ttu-id="1dfc7-144">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-144">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-145">[Icorentbugassemblyenum-Schnittstelle](icordebugassemblyenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-145">[ICorDebugAssemblyEnum Interface](icordebugassemblyenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-146">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugAssembly`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-146">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugAssembly` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-147">[Icorentbugblockingobjectenum-Schnittstelle](icordebugblockingobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-147">[ICorDebugBlockingObjectEnum Interface](icordebugblockingobjectenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-148">Stellt einen Enumerator für eine Liste von [Cordebug-blockingobject](cordebugblockingobject-structure.md) -Strukturen bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-148">Provides an enumerator for a list of [CorDebugBlockingObject](cordebugblockingobject-structure.md) structures.</span></span>  
  
 <span data-ttu-id="1dfc7-149">[Icorentbugboxvalue-Schnittstelle](icordebugboxvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-149">[ICorDebugBoxValue Interface](icordebugboxvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-150">Eine Unterklasse von `ICorDebugHeapValue`, die ein geschachteltes Wertklassenobjekt darstellt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-150">A subclass of `ICorDebugHeapValue` that represents a boxed value class object.</span></span>  
  
 <span data-ttu-id="1dfc7-151">[Icordebubugbreakpoint-Schnittstelle](icordebugbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-151">[ICorDebugBreakpoint Interface](icordebugbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-152">Stellt einen Haltepunkt in einer Funktion oder einen Beobachtungspunkt für einen Wert dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-152">Represents a breakpoint in a function or a watch point on a value.</span></span>  
  
 <span data-ttu-id="1dfc7-153">[Icordebubugbreakpointenum-Schnittstelle](icordebugbreakpointenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-153">[ICorDebugBreakpointEnum Interface](icordebugbreakpointenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-154">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugBreakpoint`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-154">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugBreakpoint` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-155">[ICorDebug Chain-Schnittstelle](icordebugchain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-155">[ICorDebugChain Interface](icordebugchain-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-156">Stellt ein Segment einer physikalischen oder logischen Aufrufliste dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-156">Represents a segment of a physical or logical call stack.</span></span>  
  
 <span data-ttu-id="1dfc7-157">[ICorDebug-chainenum-Schnittstelle](icordebugchainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-157">[ICorDebugChainEnum Interface](icordebugchainenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-158">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugChain`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-158">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugChain` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-159">[ICorDebugClass-Schnittstelle](icordebugclass-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-159">[ICorDebugClass Interface](icordebugclass-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-160">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-160">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1dfc7-161">Wenn der Typ generisch ist, stellt `ICorDebugClass` den nicht instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-161">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
 <span data-ttu-id="1dfc7-162">[ICorDebugClass2-Schnittstelle](icordebugclass2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-162">[ICorDebugClass2 Interface](icordebugclass2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-163">Stellt eine generische Klasse oder eine Klasse mit einem Methodenparameter des Typs <xref:System.Type> dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-163">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="1dfc7-164">Diese Schnittstelle erweitert `ICorDebugClass`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-164">This interface extends `ICorDebugClass`.</span></span>  
  
 <span data-ttu-id="1dfc7-165">[ICorDebugCode-Schnittstelle](icordebugcode-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-165">[ICorDebugCode Interface](icordebugcode-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-166">Stellt ein Segment von Microsoft Intermediate Language (MSIL)-Code oder nativem Code dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-166">Represents a segment of either Microsoft intermediate language (MSIL) code or native code.</span></span>  
  
 <span data-ttu-id="1dfc7-167">[ICorDebugCode2-Schnittstelle](icordebugcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-167">[ICorDebugCode2 Interface](icordebugcode2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-168">Stellt Methoden bereit, die die Fähigkeiten von `ICorDebugCode` erweitern.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-168">Provides methods that extend the capabilities of `ICorDebugCode`.</span></span>  
  
 <span data-ttu-id="1dfc7-169">[ICorDebugCode3-Schnittstelle](icordebugcode3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-169">[ICorDebugCode3 Interface](icordebugcode3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-170">Stellt eine Methode bereit, die [ICorDebugCode](icordebugcode-interface1.md) und [ICorDebugCode2](icordebugcode2-interface.md) erweitert, um Informationen über einen verwalteten Rückgabewert bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-170">Provides a method that extends [ICorDebugCode](icordebugcode-interface1.md) and [ICorDebugCode2](icordebugcode2-interface.md) to provide information about a managed return value.</span></span>  
  
 <span data-ttu-id="1dfc7-171">[ICorDebugCode4-Schnittstelle](icordebugcode4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-171">[ICorDebugCode4 Interface](icordebugcode4-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-172">Stellt eine Methode bereit, die einem Debugger das Auflisten der lokalen Variablen und Argumente in einer Funktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-172">Provides a method that enables a debugger to enumerate the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="1dfc7-173">[Icordebugcodeumum-Schnittstelle](icordebugcodeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-173">[ICorDebugCodeEnum Interface](icordebugcodeenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-174">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugCode`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-174">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugCode` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-175">[Icorentbugcomobjectvalue-Schnittstelle](icordebugcomobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-175">[ICorDebugComObjectValue Interface](icordebugcomobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-176">Stellt Methoden bereit, um zwischengespeicherte Schnittstellenobjekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-176">Provides methods to retrieve cached interface objects.</span></span>  
  
 <span data-ttu-id="1dfc7-177">[ICorDebugContext-Schnittstelle](icordebugcontext-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-177">[ICorDebugContext Interface](icordebugcontext-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-178">Stellt ein Kontextobjekt dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-178">Represents a context object.</span></span> <span data-ttu-id="1dfc7-179">Diese Schnittstelle wurde noch nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-179">This interface has not been implemented yet.</span></span>  
  
 <span data-ttu-id="1dfc7-180">[ICorDebug Controller-Schnittstelle](icordebugcontroller-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-180">[ICorDebugController Interface](icordebugcontroller-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-181">Stellt einen Bereich dar, in dem der Kontext der Codeausführung gesteuert werden kann. Dabei handelt es sich entweder um einen <xref:System.Diagnostics.Process> oder eine <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-181">Represents a scope, either a <xref:System.Diagnostics.Process> or an <xref:System.AppDomain>, in which code execution context can be controlled.</span></span>  
  
 <span data-ttu-id="1dfc7-182">[Icorentbugdatatarget-Schnittstelle](icordebugdatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-182">[ICorDebugDataTarget Interface](icordebugdatatarget-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-183">Stellt eine Rückrufschnittstelle bereit, die Zugriff auf einen bestimmten Zielprozess bietet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-183">Provides a callback interface that provides access to a particular target process.</span></span>  
  
 <span data-ttu-id="1dfc7-184">[ICorDebugDataTarget2-Schnittstelle](icordebugdatatarget2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-184">[ICorDebugDataTarget2 Interface](icordebugdatatarget2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-185">Erweitert logisch die [ICorDebug DataTarget](icordebugdatatarget-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-185">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface.</span></span> <span data-ttu-id="1dfc7-186">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-186">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-187">[ICorDebugDataTarget3-Schnittstelle](icordebugdatatarget3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-187">[ICorDebugDataTarget3 Interface](icordebugdatatarget3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-188">Erweitert logisch die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um Informationen über geladene Module bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-188">Logically extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to provide information about loaded modules.</span></span> <span data-ttu-id="1dfc7-189">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-189">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-190">[Icordebugdebugevent-Schnittstelle](icordebugdebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-190">[ICorDebugDebugEvent Interface](icordebugdebugevent-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-191">Definiert die Basisschnittstelle, von der alle `ICorDebug` Debug-Ereignisse abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-191">Defines the base interface from which all `ICorDebug` debug events derive.</span></span> <span data-ttu-id="1dfc7-192">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-192">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-193">[ICorDebugEditAndContinueErrorInfo-Schnittstelle](icordebugeditandcontinueerrorinfo-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-193">[ICorDebugEditAndContinueErrorInfo Interface](icordebugeditandcontinueerrorinfo-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-194">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-194">Obsolete.</span></span> <span data-ttu-id="1dfc7-195">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-195">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1dfc7-196">[ICorDebugEditAndContinueSnapshot-Schnittstelle](icordebugeditandcontinuesnapshot-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-196">[ICorDebugEditAndContinueSnapshot Interface](icordebugeditandcontinuesnapshot-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-197">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-197">Obsolete.</span></span> <span data-ttu-id="1dfc7-198">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-198">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1dfc7-199">[ICorDebugEnum-Schnittstelle](icordebugenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-199">[ICorDebugEnum Interface](icordebugenum-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-200">Dient als abstrakte Basisschnittstelle für das Debuggen von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-200">Serves as the abstract base interface for debugging enumerators.</span></span>  
  
 <span data-ttu-id="1dfc7-201">[Icordebugerrorinfoerum-Schnittstelle](icordebugerrorinfoenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-201">[ICorDebugErrorInfoEnum Interface](icordebugerrorinfoenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-202">Veraltet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-202">Obsolete.</span></span> <span data-ttu-id="1dfc7-203">Verwenden Sie diese Schnittstelle nicht.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-203">Do not use this interface.</span></span>  
  
 <span data-ttu-id="1dfc7-204">[ICorDebugEval-Schnittstelle](icordebugeval-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-204">[ICorDebugEval Interface](icordebugeval-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-205">Stellt Methoden bereit, mit denen der Debugger Code innerhalb des Kontexts des gedebuggten Codes ausführen kann.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-205">Provides methods to enable the debugger to execute code within the context of the code being debugged.</span></span>  
  
 <span data-ttu-id="1dfc7-206">[ICorDebugEval2-Schnittstelle](icordebugeval2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-206">[ICorDebugEval2 Interface](icordebugeval2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-207">Erweitert `ICorDebugEval`, um generische Typen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-207">Extends `ICorDebugEval` to provide support for generic types.</span></span>  
  
 <span data-ttu-id="1dfc7-208">[Icordebugexceptiondebugevent-Schnittstelle](icordebugexceptiondebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-208">[ICorDebugExceptionDebugEvent Interface](icordebugexceptiondebugevent-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-209">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle zur Unterstützung von Ausnahme Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-209">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support exception events.</span></span> <span data-ttu-id="1dfc7-210">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-210">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-211">[Icordebugexceptionobjectcallstackenum-Schnittstelle](icordebugexceptionobjectcallstackenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-211">[ICorDebugExceptionObjectCallStackEnum Interface](icordebugexceptionobjectcallstackenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-212">Stellt einen Enumerator für Aufruflisteninformationen bereit, die in einem Ausnahmeobjekt eingebettet sind.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-212">Provides an enumerator for call stack information that is embedded in an exception object.</span></span>  
  
 <span data-ttu-id="1dfc7-213">[Icordebugexceptionobjectvalue-Schnittstelle](icordebugexceptionobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-213">[ICorDebugExceptionObjectValue Interface](icordebugexceptionobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-214">Erweitert die [ICorDebugObjectValue](icordebugobjectvalue-interface.md) -Schnittstelle, um Stapel Verfolgungs Informationen von einem verwalteten Ausnahme Objekt bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-214">Extends the [ICorDebugObjectValue](icordebugobjectvalue-interface.md) interface to provide stack trace information from a managed exception object.</span></span>  
  
 <span data-ttu-id="1dfc7-215">[Icorentbugframe-Schnittstelle](icordebugframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-215">[ICorDebugFrame Interface](icordebugframe-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-216">Stellt einen Rahmen auf dem aktuellen Stapel dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-216">Represents a frame on the current stack.</span></span>  
  
 <span data-ttu-id="1dfc7-217">[ICorDebug-Schnittstelle](icordebugframeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-217">[ICorDebugFrameEnum Interface](icordebugframeenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-218">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugFrame`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-218">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugFrame` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-219">[ICorDebug Function-Schnittstelle](icordebugfunction-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-219">[ICorDebugFunction Interface](icordebugfunction-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-220">Stellt eine verwaltete Funktion oder Methode dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-220">Represents a managed function or method.</span></span>  
  
 <span data-ttu-id="1dfc7-221">[ICorDebugFunction2-Schnittstelle](icordebugfunction2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-221">[ICorDebugFunction2 Interface](icordebugfunction2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-222">Erweitert `ICorDebugFunction` logisch, um schrittweises Nur mein Code-Debuggen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-222">Logically extends `ICorDebugFunction` to provide support for Just My Code step-through debugging.</span></span>  
  
 <span data-ttu-id="1dfc7-223">[ICorDebugFunction3-Schnittstelle](icordebugfunction3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-223">[ICorDebugFunction3 Interface](icordebugfunction3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-224">Erweitert die [ICorDebugFunction](icordebugfunction-interface1.md) -Schnittstelle logisch, um den Zugriff auf Code über eine ReJIT-Anforderung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-224">Logically extends the [ICorDebugFunction](icordebugfunction-interface1.md) interface to provide access to code from a ReJIT request.</span></span>  
  
 <span data-ttu-id="1dfc7-225">[Icordebubugfunctionbreakpoint-Schnittstelle](icordebugfunctionbreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-225">[ICorDebugFunctionBreakpoint Interface](icordebugfunctionbreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-226">Erweitert `ICorDebugBreakpoint`, um Haltepunkte innerhalb von Funktionen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-226">Extends `ICorDebugBreakpoint` to support breakpoints within functions.</span></span>  
  
 <span data-ttu-id="1dfc7-227">[ICorDebug-Schnittstelle](icordebuggcreferenceenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-227">[ICorDebugGCReferenceEnum Interface](icordebuggcreferenceenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-228">Stellt einen Enumerator für Objekte bereit, die der Garbage Collection übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-228">Provides an enumerator for objects that will be garbage-collected.</span></span>  
  
 <span data-ttu-id="1dfc7-229">[ICorDebugGenericValue-Schnittstelle](icordebuggenericvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-229">[ICorDebugGenericValue Interface](icordebuggenericvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-230">Eine Unterklasse von `ICorDebugValue`, die für alle Werte gilt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-230">A subclass of `ICorDebugValue` that applies to all values.</span></span> <span data-ttu-id="1dfc7-231">Diese Schnittstelle stellt die Get-Methode und die Set-Methode für den Wert bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-231">This interface provides Get and Set methods for the value.</span></span>  
  
 <span data-ttu-id="1dfc7-232">[ICorDebug-Schnittstelle](icordebugguidtotypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-232">[ICorDebugGuidToTypeEnum Interface](icordebugguidtotypeenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-233">Stellt einen Enumerator für ein Objekt bereit, das GUIDs und die entsprechenden `ICorDebugType`-Objekte zuordnet.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-233">Provides an enumerator for an object that maps GUIDs and their corresponding `ICorDebugType` objects.</span></span>  
  
 <span data-ttu-id="1dfc7-234">[ICorDebugHandleValue-Schnittstelle](icordebughandlevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-234">[ICorDebugHandleValue Interface](icordebughandlevalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-235">Eine Unterklasse von `ICorDebugReferenceValue`, die einen Verweiswert darstellt, für den der Debugger einen Handle zur Garbage Collection erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-235">A subclass of `ICorDebugReferenceValue` that represents a reference value to which the debugger has created a handle for garbage collection.</span></span>  
  
 <span data-ttu-id="1dfc7-236">[Icordebugheaperum-Schnittstelle](icordebugheapenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-236">[ICorDebugHeapEnum Interface](icordebugheapenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-237">Stellt einen Enumerator für Objekte auf dem verwalteten Heap bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-237">Provides an enumerator for objects on the managed heap.</span></span>  
  
 <span data-ttu-id="1dfc7-238">[Icordebugheapsegmenterum-Schnittstelle](icordebugheapsegmentenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-238">[ICorDebugHeapSegmentEnum Interface](icordebugheapsegmentenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-239">Stellt einen Enumerator für die Speicherbereiche des verwalteten Heaps bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-239">Provides an enumerator for the memory regions of the managed heap.</span></span>  
  
 <span data-ttu-id="1dfc7-240">[ICorDebugHeapValue-Schnittstelle](icordebugheapvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-240">[ICorDebugHeapValue Interface](icordebugheapvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-241">Eine Unterklasse von `ICorDebugValue`, die ein Objekt darstellt, das vom Garbage Collector der CLR gesammelt wurde.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-241">A subclass of `ICorDebugValue` that represents an object that has been collected by the CLR garbage collector.</span></span>  
  
 <span data-ttu-id="1dfc7-242">[ICorDebugHeapValue2-Schnittstelle](icordebugheapvalue2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-242">[ICorDebugHeapValue2 Interface](icordebugheapvalue2-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-243">Eine Erweiterung von `ICorDebugHeapValue`, die Laufzeithandles unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-243">An extension of `ICorDebugHeapValue` that provides support for runtime handles.</span></span>  
  
 <span data-ttu-id="1dfc7-244">[ICorDebugHeapValue3-Schnittstelle](icordebugheapvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-244">[ICorDebugHeapValue3 Interface](icordebugheapvalue3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-245">Macht die Bildschirmsperreigenschaften von Objekten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-245">Exposes the monitor lock properties of objects.</span></span>  
  
 <span data-ttu-id="1dfc7-246">[Icordebugilcode-Schnittstelle](icordebugilcode-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-246">[ICorDebugILCode Interface](icordebugilcode-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-247">Stellt ein Segment aus Intermediate Language (IL)-Code dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-247">Represents a segment of intermediate language (IL) code.</span></span>  
  
 <span data-ttu-id="1dfc7-248">[ICorDebugILCode2-Schnittstelle](icordebugilcode2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-248">[ICorDebugILCode2 Interface](icordebugilcode2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-249">Erweitert logisch die [icordebugilcode](icordebugilcode-interface.md) -Schnittstelle so, dass Methoden bereitgestellt werden, die das Token für die Signatur der lokalen Variablen einer Funktion zurückgeben und die instrumentierten Intermediate Language (IL)-Offsets eines Profilers den ursprünglichen Methoden-IL-Offsets zuordnen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-249">Logically extends the [ICorDebugILCode](icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
 <span data-ttu-id="1dfc7-250">[ICorDebugILFrame-Schnittstelle](icordebugilframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-250">[ICorDebugILFrame Interface](icordebugilframe-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-251">Stellt einen Stapelrahmen des MSIL-Codes dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-251">Represents a stack frame of MSIL code.</span></span>  
  
 <span data-ttu-id="1dfc7-252">[ICorDebugILFrame2-Schnittstelle](icordebugilframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-252">[ICorDebugILFrame2 Interface](icordebugilframe2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-253">Eine logische Erweiterung von `ICorDebugILFrame`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-253">A logical extension of `ICorDebugILFrame`.</span></span>  
  
 <span data-ttu-id="1dfc7-254">[ICorDebugILFrame3-Schnittstelle](icordebugilframe3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-254">[ICorDebugILFrame3 Interface](icordebugilframe3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-255">Stellt eine Methode bereit, die den Rückgabewert einer Funktion kapselt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-255">Provides a method that encapsulates the return value of a function.</span></span>  
  
 <span data-ttu-id="1dfc7-256">[ICorDebugILFrame4-Schnittstelle](icordebugilframe4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-256">[ICorDebugILFrame4 Interface](icordebugilframe4-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-257">Bietet Methoden, mit denen Sie auf lokale Variablen und Code in einem Stapelrahmen aus Intermediate Language (IL)-Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-257">Provides methods that allow you to access the local variables and code in a stack frame of intermediate language (IL) code.</span></span> <span data-ttu-id="1dfc7-258">Ein Parameter legt fest, ob der Debugger Zugang zu Variablen und Code erhält, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-258">A parameter specifies whether the debugger has access to variables and code added in profiler ReJIT instrumentation.</span></span>  
  
 <span data-ttu-id="1dfc7-259">[Icordebuginstancefieldsymbol-Schnittstelle](icordebuginstancefieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-259">[ICorDebugInstanceFieldSymbol Interface](icordebuginstancefieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-260">Stellt die Debugsymbolinformationen für ein Instanzfeld dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-260">Represents the debug symbol information for an instance field.</span></span> <span data-ttu-id="1dfc7-261">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-261">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-262">[Icorentbuginternalframe-Schnittstelle](icordebuginternalframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-262">[ICorDebugInternalFrame Interface](icordebuginternalframe-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-263">Identifiziert Rahmentypen für den Debugger.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-263">Identifies frame types for the debugger.</span></span>  
  
 <span data-ttu-id="1dfc7-264">[ICorDebugInternalFrame2-Schnittstelle](icordebuginternalframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-264">[ICorDebugInternalFrame2 Interface](icordebuginternalframe2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-265">Stellt Informationen zu internen Frames bereit, einschließlich Stapel Adresse und Position in Bezug auf [ICorDebugFrame](icordebugframe-interface.md) -Objekte.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-265">Provides information about internal frames, including stack address and position in relation to [ICorDebugFrame](icordebugframe-interface.md) objects.</span></span>  
  
 <span data-ttu-id="1dfc7-266">[Icordebugloadedmodule-Schnittstelle](icordebugloadedmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-266">[ICorDebugLoadedModule Interface](icordebugloadedmodule-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-267">Stellt Informationen zu einem geladenen Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-267">Provides information about a loaded module.</span></span> <span data-ttu-id="1dfc7-268">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-268">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-269">[Icorentbugmanagedcallback-Schnittstelle](icordebugmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-269">[ICorDebugManagedCallback Interface](icordebugmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-270">Stellt Methoden zum Verarbeiten von Debuggerrückrufen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-270">Provides methods to process debugger callbacks.</span></span>  
  
 <span data-ttu-id="1dfc7-271">[ICorDebugManagedCallback2-Schnittstelle](icordebugmanagedcallback2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-271">[ICorDebugManagedCallback2 Interface](icordebugmanagedcallback2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-272">Stellt Methoden bereit, um Debugger-Ausnahmebehandlung und Assistenten für verwaltetes Debuggen (MDA) zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-272">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="1dfc7-273">`ICorDebugManagedCallback2` ist eine logische Erweiterung von `ICorDebugManagedCallback`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-273">`ICorDebugManagedCallback2` is a logical extension of `ICorDebugManagedCallback`.</span></span>  
  
 <span data-ttu-id="1dfc7-274">[ICorDebugManagedCallback3-Schnittstelle](icordebugmanagedcallback3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-274">[ICorDebugManagedCallback3 Interface](icordebugmanagedcallback3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-275">Stellt eine Rückrufmethode bereit, die angibt, dass eine aktivierte benutzerdefinierte Debuggerbenachrichtigung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-275">Provides a callback method that indicates that an enabled custom debugger notification has been raised.</span></span>  
  
 <span data-ttu-id="1dfc7-276">[ICorDebug-MDA-Schnittstelle](icordebugmda-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-276">[ICorDebugMDA Interface](icordebugmda-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-277">Stellt eine Nachricht des Assistenten für verwaltetes Debuggen (MDA) dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-277">Represents a managed debugging assistant (MDA) message.</span></span>  
  
 <span data-ttu-id="1dfc7-278">[Icorentbugmemorybuffer-Schnittstelle](icordebugmemorybuffer-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-278">[ICorDebugMemoryBuffer Interface](icordebugmemorybuffer-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-279">Stellt einen In-Memory-Puffer dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-279">Represents an in-memory buffer.</span></span> <span data-ttu-id="1dfc7-280">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-280">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-281">[Icorentbugmergedassemblyrecord-Schnittstelle](icordebugmergedassemblyrecord-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-281">[ICorDebugMergedAssemblyRecord Interface](icordebugmergedassemblyrecord-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-282">Enthält Informationen zu einer zusammengeführten Assembly.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-282">Provides information about a merged assembly.</span></span> <span data-ttu-id="1dfc7-283">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-283">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-284">[ICorDebugMetaDataLocator-Schnittstelle](icordebugmetadatalocator-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-284">[ICorDebugMetaDataLocator Interface](icordebugmetadatalocator-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-285">Stellt Metadateninformationen für den Debugger bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-285">Provides metadata information to the debugger.</span></span>  
  
 <span data-ttu-id="1dfc7-286">[ICorDebug Module-Schnittstelle](icordebugmodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-286">[ICorDebugModule Interface](icordebugmodule-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-287">Stellt ein CLR-Modul dar, das entweder eine ausführbare Datei oder eine Dynamic-Link Library (DLL) ist.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-287">Represents a CLR module, which is either an executable or a dynamic-link library (DLL).</span></span>  
  
 <span data-ttu-id="1dfc7-288">[ICorDebugModule2-Schnittstelle](icordebugmodule2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-288">[ICorDebugModule2 Interface](icordebugmodule2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-289">Fungiert als logische Erweiterung von `ICorDebugModule`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-289">Serves as a logical extension to `ICorDebugModule`.</span></span>  
  
 <span data-ttu-id="1dfc7-290">[ICorDebugModule3-Schnittstelle](icordebugmodule3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-290">[ICorDebugModule3 Interface](icordebugmodule3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-291">Erstellt einen Symbolreader für ein dynamisches Modul.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-291">Creates a symbol reader for a dynamic module.</span></span>  
  
 <span data-ttu-id="1dfc7-292">[Icordebutbugmodulebreakpoint-Schnittstelle](icordebugmodulebreakpoint-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-292">[ICorDebugModuleBreakpoint Interface](icordebugmodulebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-293">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Module zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-293">Extends `ICorDebugBreakpoint` to provide access to specific modules.</span></span>  
  
 <span data-ttu-id="1dfc7-294">[Icordebugmoduledebugevent-Schnittstelle](icordebugmoduledebugevent-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-294">[ICorDebugModuleDebugEvent Interface](icordebugmoduledebugevent-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-295">Erweitert die [icordebugdebugevent](icordebugdebugevent-interface.md) -Schnittstelle, um Ereignisse auf Modulebene zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-295">Extends the [ICorDebugDebugEvent](icordebugdebugevent-interface.md) interface to support module-level events.</span></span> <span data-ttu-id="1dfc7-296">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-296">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-297">[Icorentbugmoduleerumum-Schnittstelle](icordebugmoduleenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-297">[ICorDebugModuleEnum Interface](icordebugmoduleenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-298">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugModule`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-298">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugModule` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-299">[Icorentbugmutabledatatarget-Schnittstelle](icordebugmutabledatatarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-299">[ICorDebugMutableDataTarget Interface](icordebugmutabledatatarget-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-300">Erweitert die [ICorDebugDataTarget](icordebugdatatarget-interface.md) -Schnittstelle, um änderbare Datenziele zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-300">Extends the [ICorDebugDataTarget](icordebugdatatarget-interface.md) interface to support mutable data targets.</span></span>  
  
 <span data-ttu-id="1dfc7-301">[ICorDebugNativeFrame-Schnittstelle](icordebugnativeframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-301">[ICorDebugNativeFrame Interface](icordebugnativeframe-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-302">Eine spezielle Implementierung von `ICorDebugFrame`, die für systemeigene Rahmen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-302">A specialized implementation of `ICorDebugFrame` used for native frames.</span></span>  
  
 <span data-ttu-id="1dfc7-303">[ICorDebugNativeFrame2-Schnittstelle](icordebugnativeframe2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-303">[ICorDebugNativeFrame2 Interface](icordebugnativeframe2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-304">Stellt Methoden bereit, die auf Beziehungen zwischen untergeordneten und übergeordneten Frames überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-304">Provides methods that test for child and parent frame relationships.</span></span>  
  
 <span data-ttu-id="1dfc7-305">[ICorDebugObjectEnum-Schnittstelle](icordebugobjectenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-305">[ICorDebugObjectEnum Interface](icordebugobjectenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-306">Implementiert `ICorDebugEnum`-Methoden und listet Objektarrays anhand ihrer relativen virtuellen Adresse (RVA) auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-306">Implements `ICorDebugEnum` methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
 <span data-ttu-id="1dfc7-307">[ICorDebugObjectValue-Schnittstelle](icordebugobjectvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-307">[ICorDebugObjectValue Interface](icordebugobjectvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-308">Eine Unterklasse von `ICorDebugValue`, die einen Wert darstellt, der ein Objekt enthält.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-308">A subclass of `ICorDebugValue` that represents a value that contains an object.</span></span>  
  
 <span data-ttu-id="1dfc7-309">[ICorDebugObjectValue2-Schnittstelle](icordebugobjectvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-309">[ICorDebugObjectValue2 Interface](icordebugobjectvalue2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-310">Erweitert `ICorDebugObjectValue`, um Vererbung und Überschreibungen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-310">Extends `ICorDebugObjectValue` to support inheritance and overrides.</span></span>  
  
 <span data-ttu-id="1dfc7-311">[ICorDebugProcess-Schnittstelle](icordebugprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-311">[ICorDebugProcess Interface](icordebugprocess-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-312">Stellt einen Prozess dar, der verwalteten Code ausführt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-312">Represents a process that is executing managed code.</span></span>  
  
 <span data-ttu-id="1dfc7-313">[ICorDebugProcess2-Schnittstelle](icordebugprocess2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-313">[ICorDebugProcess2 Interface](icordebugprocess2-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-314">Eine logische Erweiterung von `ICorDebugProcess`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-314">A logical extension of `ICorDebugProcess`.</span></span>  
  
 <span data-ttu-id="1dfc7-315">[ICorDebugProcess3-Schnittstelle](icordebugprocess3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-315">[ICorDebugProcess3 Interface](icordebugprocess3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-316">Steuert benutzerdefinierte Debuggerbenachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-316">Controls custom debugger notifications.</span></span>

 <span data-ttu-id="1dfc7-317">[ICorDebugProcess4-Schnittstelle](icordebugprocess4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-317">[ICorDebugProcess4 Interface](icordebugprocess4-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-318">Bietet Unterstützung für die Out-of-Process-Ausführungs Steuerung.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-318">Provides support for out of process execution control.</span></span>
  
 <span data-ttu-id="1dfc7-319">[ICorDebugProcess5-Schnittstelle](icordebugprocess5-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-319">[ICorDebugProcess5 Interface](icordebugprocess5-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-320">Erweitert die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle, um den Zugriff auf den verwalteten Heap zu unterstützen, um Informationen über Garbage Collection verwalteter Objekte bereitzustellen und um zu bestimmen, ob ein Debugger Bilder aus dem lokalen systemeigenen Image Cache der Anwendung lädt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-320">Extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to support access to the managed heap, to provide information about garbage collection of managed objects, and to determine whether a debugger loads images from the application's local native image cache.</span></span>  
  
 <span data-ttu-id="1dfc7-321">[ICorDebugProcess6-Schnittstelle](icordebugprocess6-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-321">[ICorDebugProcess6 Interface](icordebugprocess6-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-322">Erweitert logisch die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle, um Funktionen wie das Decodieren verwalteter Debugereignisse zu ermöglichen, die in nativen Ausnahme-Debugereignissen und der Aufteilung virtueller Module</span><span class="sxs-lookup"><span data-stu-id="1dfc7-322">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable features such as decoding managed debug events that are encoded in native exception debug events and virtual module splitting.</span></span> <span data-ttu-id="1dfc7-323">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-323">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-324">[ICorDebugProcess7-Schnittstelle](icordebugprocess7-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-324">[ICorDebugProcess7 Interface](icordebugprocess7-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-325">Bietet eine Methode, die den Debugger so konfiguriert, dass speicherinterne Metadatenaktualisierungen im Zielprozess behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-325">Provides a method that configures the debugger to handle in-memory metadata updates in the target process.</span></span>  
  
 <span data-ttu-id="1dfc7-326">[ICorDebugProcess8-Schnittstelle](icordebugprocess8-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-326">[ICorDebugProcess8 Interface](icordebugprocess8-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-327">Erweitert die [ICorDebugProcess](icordebugprocess-interface.md) -Schnittstelle logisch, um bestimmte Typen von [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) -Ausnahme Rückrufen zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-327">Logically extends the [ICorDebugProcess](icordebugprocess-interface.md) interface to enable or disable certain types of [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) exception callbacks.</span></span>  
  
 <span data-ttu-id="1dfc7-328">[Icorentbugprocessenum-Schnittstelle](icordebugprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-328">[ICorDebugProcessEnum Interface](icordebugprocessenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-329">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugProcess`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-329">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugProcess` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-330">[ICorDebugReferenceValue-Schnittstelle](icordebugreferencevalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-330">[ICorDebugReferenceValue Interface](icordebugreferencevalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-331">Eine Unterklasse von `ICorDebugValue`, die Verweistypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-331">A subclass of `ICorDebugValue` that supports reference types.</span></span>  
  
 <span data-ttu-id="1dfc7-332">[Icorentbugregisterset-Schnittstelle](icordebugregisterset-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-332">[ICorDebugRegisterSet Interface](icordebugregisterset-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-333">Stellt die Register dar, die auf dem Computer verfügbar sind, auf dem der Code derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-333">Represents the set of registers available on the machine that is currently executing code.</span></span>  
  
 <span data-ttu-id="1dfc7-334">[ICorDebugRegisterSet2-Schnittstelle](icordebugregisterset2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-334">[ICorDebugRegisterSet2 Interface](icordebugregisterset2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-335">Erweitert die Fähigkeiten von `ICorDebugRegisterSet` für Hardwareplattformen mit mehr als 64 Registern.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-335">Extends the capabilities of `ICorDebugRegisterSet` for hardware platforms that have more than 64 registers.</span></span>  
  
 <span data-ttu-id="1dfc7-336">[Icordebugremute-Schnittstelle](icordebugremote-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-336">[ICorDebugRemote Interface](icordebugremote-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-337">Bietet die Möglichkeit, einen verwalteten Debugger an einen Remotezielprozess anzufügen oder dort zu starten.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-337">Provides the ability to launch or attach a managed debugger to a remote target process.</span></span>  
  
 <span data-ttu-id="1dfc7-338">[Icordebugremotetarget-Schnittstelle](icordebugremotetarget-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-338">[ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-339">Stellt Methoden bereit, die Ihnen ermöglichen, Silverlight-basierte Anwendungen in der CLR-Umgebung debuggen zu können.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-339">Provides methods that enable you to debug Silverlight-based applications in the CLR environment.</span></span>  
  
 <span data-ttu-id="1dfc7-340">[Icordebugruntimeunwindableframe-Schnittstelle](icordebugruntimeunwindableframe-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-340">[ICorDebugRuntimeUnwindableFrame Interface](icordebugruntimeunwindableframe-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-341">Unterstützt nicht verwaltete Methoden, die das Entladen eines Frames durch die Common Language Runtime (CLR) erfordern.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-341">Provides support for unmanaged methods that require the common language runtime (CLR) to unwind a frame.</span></span>  
  
 <span data-ttu-id="1dfc7-342">[Icorentbugstackwalk-Schnittstelle](icordebugstackwalk-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-342">[ICorDebugStackWalk Interface](icordebugstackwalk-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-343">Stellt Methoden zum Abrufen der verwalteten Methoden oder Frames auf dem Stapel eines Threads bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-343">Provides methods for getting the managed methods, or frames, on a thread’s stack.</span></span>  
  
 <span data-ttu-id="1dfc7-344">[Icordebugstaticfieldsymbol-Schnittstelle](icordebugstaticfieldsymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-344">[ICorDebugStaticFieldSymbol Interface](icordebugstaticfieldsymbol-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-345">Stellt die Debugsymbolinformationen für ein statisches Feld dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-345">Represents the debug symbol information for a static field.</span></span> <span data-ttu-id="1dfc7-346">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-346">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-347">[Icorentbugstepper-Schnittstelle](icordebugstepper-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-347">[ICorDebugStepper Interface](icordebugstepper-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-348">Stellt einen Schritt in der Codeausführung dar, der von einem Debugger ausgeführt wird, dient zwischen der Veröffentlichung und dem Abschluss eines Befehls als Bezeichner und ermöglicht das Abbrechen eines Schritts.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-348">Represents a step in code execution that is performed by a debugger, serves as an identifier between the issuance and completion of a command, and provides a way to cancel a step.</span></span>  
  
 <span data-ttu-id="1dfc7-349">[ICorDebugStepper2-Schnittstelle](icordebugstepper2-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-349">[ICorDebugStepper2 Interface](icordebugstepper2-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-350">Bietet Unterstützung für Nur mein Code-Debuggen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-350">Provides support for Just My Code (JMC) debugging.</span></span>  
  
 <span data-ttu-id="1dfc7-351">[ICorDebug-Schnittstelle](icordebugstepperenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-351">[ICorDebugStepperEnum Interface](icordebugstepperenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-352">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugStepper`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-352">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugStepper` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-353">[Icorentbugstringvalue-Schnittstelle](icordebugstringvalue-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-353">[ICorDebugStringValue Interface](icordebugstringvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-354">Eine Unterklasse von `ICorDebugHeapValue`, die für Zeichenfolgenwerte gilt.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-354">A subclass of `ICorDebugHeapValue` that applies to string values.</span></span>  
  
 <span data-ttu-id="1dfc7-355">[Icorentbugsymbolprovider-Schnittstelle](icordebugsymbolprovider-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-355">[ICorDebugSymbolProvider Interface](icordebugsymbolprovider-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-356">Stellt Methoden bereit, die zum Abrufen von Debugsymbolinformationen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-356">Provides methods that can be used to retrieve debug symbol information.</span></span> <span data-ttu-id="1dfc7-357">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-357">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-358">[ICorDebugSymbolProvider2-Schnittstelle](icordebugsymbolprovider2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-358">[ICorDebugSymbolProvider2 Interface](icordebugsymbolprovider2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-359">Erweitert logisch die [icordebugsymbolprovider](icordebugsymbolprovider-interface.md) -Schnittstelle, um zusätzliche Debugsymbolinformationen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-359">Logically extends the [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) interface to retrieve additional debug symbol information.</span></span> <span data-ttu-id="1dfc7-360">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-360">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-361">[ICorDebugThread-Schnittstelle](icordebugthread-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-361">[ICorDebugThread Interface](icordebugthread-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-362">Stellt einen Thread in einem Prozess dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-362">Represents a thread in a process.</span></span> <span data-ttu-id="1dfc7-363">Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-363">The lifetime of an `ICorDebugThread` instance is the same as the lifetime of the thread it represents.</span></span>  
  
 <span data-ttu-id="1dfc7-364">[ICorDebugThread2-Schnittstelle](icordebugthread2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-364">[ICorDebugThread2 Interface](icordebugthread2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-365">Fungiert als logische Erweiterung von `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-365">Serves as a logical extension to `ICorDebugThread`.</span></span>  
  
 <span data-ttu-id="1dfc7-366">[ICorDebugThread3-Schnittstelle](icordebugthread3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-366">[ICorDebugThread3 Interface](icordebugthread3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-367">Stellt den Einstiegspunkt für [ICorDebugStackWalk](icordebugstackwalk-interface.md) und die entsprechenden Schnittstellen bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-367">Provides the entry point to the [ICorDebugStackWalk](icordebugstackwalk-interface.md) and corresponding interfaces.</span></span>  
  
 <span data-ttu-id="1dfc7-368">[ICorDebugThread4-Schnittstelle](icordebugthread4-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-368">[ICorDebugThread4 Interface](icordebugthread4-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-369">Stellt Informationen zur Threadblockierung bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-369">Provides thread blocking information.</span></span>  
  
 <span data-ttu-id="1dfc7-370">[Icorentbugthreaderum-Schnittstelle](icordebugthreadenum-interface1.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-370">[ICorDebugThreadEnum Interface](icordebugthreadenum-interface1.md)</span></span>\
 <span data-ttu-id="1dfc7-371">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugThread`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-371">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugThread` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-372">[ICorDebugType-Schnittstelle](icordebugtype-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-372">[ICorDebugType Interface](icordebugtype-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-373">Stellt einen Typ dar, der entweder grundlegend oder komplex (das heißt benutzerdefiniert) sein kann.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-373">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="1dfc7-374">Wenn der Typ generisch ist, stellt `ICorDebugType` den instanziierten generischen Typ dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-374">If the type is generic, `ICorDebugType` represents the instantiated generic type.</span></span>  
  
 <span data-ttu-id="1dfc7-375">[ICorDebugType2-Schnittstelle](icordebugtype2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-375">[ICorDebugType2 Interface](icordebugtype2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-376">Erweitert die [ICorDebugType](icordebugtype-interface.md) -Schnittstelle zum Abrufen des Typbezeichners eines Basistyps oder eines komplexen (benutzerdefinierten) Typs.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-376">Extends the [ICorDebugType](icordebugtype-interface.md) interface to retrieve the type identifier  of a base type or complex (user-defined) type.</span></span>  
  
 <span data-ttu-id="1dfc7-377">[Icorentbugtypeerum-Schnittstelle](icordebugtypeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-377">[ICorDebugTypeEnum Interface](icordebugtypeenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-378">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugType`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-378">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugType` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-379">[ICorDebugUnmanagedCallback-Schnittstelle](icordebugunmanagedcallback-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-379">[ICorDebugUnmanagedCallback Interface](icordebugunmanagedcallback-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-380">Stellt eine Benachrichtigung über systemeigene Ereignisse bereit, die sich nicht direkt auf die Common Language Runtime beziehen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-380">Provides notification of native events that are not directly related to the CLR.</span></span>  
  
 <span data-ttu-id="1dfc7-381">[ICorDebug Value](icordebugvalue-interface.md) -</span><span class="sxs-lookup"><span data-stu-id="1dfc7-381">[ICorDebugValue](icordebugvalue-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-382">Stellt einen Lese- oder Schreibwert in dem Prozess dar, der gedebuggt wird.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-382">Represents a read or write value in the process being debugged.</span></span>  
  
 <span data-ttu-id="1dfc7-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-383">[ICorDebugValue2](icordebugvalue2-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-384">Erweitert `ICorDebugValue`, um `ICorDebugType` zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-384">Extends `ICorDebugValue` to provide support for `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="1dfc7-385">[ICorDebugValue3-Schnittstelle](icordebugvalue3-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-385">[ICorDebugValue3 Interface](icordebugvalue3-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-386">Erweitert die Schnittstellen "ICorDebugValue" und "ICorDebugValue2", um Unterstützung für Arrays zu bieten, die größer als 2 GB sind.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-386">Extends the "ICorDebugValue" and "ICorDebugValue2" interfaces to provide support for arrays that are larger than 2 GB.</span></span>  
  
 <span data-ttu-id="1dfc7-387">[Icordebutbugvaluebreakpoint](icordebugvaluebreakpoint-interface.md) -</span><span class="sxs-lookup"><span data-stu-id="1dfc7-387">[ICorDebugValueBreakpoint](icordebugvaluebreakpoint-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-388">Erweitert `ICorDebugBreakpoint`, um Zugriff auf bestimmte Werte zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-388">Extends `ICorDebugBreakpoint` to provide access to specific values.</span></span>  
  
 <span data-ttu-id="1dfc7-389">[ICorDebug](icordebugvalueenum-interface.md) -</span><span class="sxs-lookup"><span data-stu-id="1dfc7-389">[ICorDebugValueEnum](icordebugvalueenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-390">Implementiert `ICorDebugEnum`-Methoden und listet `ICorDebugValue`-Arrays auf.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-390">Implements `ICorDebugEnum` methods, and enumerates `ICorDebugValue` arrays.</span></span>  
  
 <span data-ttu-id="1dfc7-391">[Icorentbugvariablehome-Schnittstelle](icordebugvariablehome-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-391">[ICorDebugVariableHome Interface](icordebugvariablehome-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-392">Stellt eine lokale Variable oder ein Argument einer Funktion dar.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-392">Represents a local variable or argument of a function.</span></span>  
  
 <span data-ttu-id="1dfc7-393">[ICorDebug-Schnittstelle](icordebugvariablehomeenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-393">[ICorDebugVariableHomeEnum Interface](icordebugvariablehomeenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-394">Stellt einen Enumerator für die lokalen Variablen und Argumente in einer Funktion bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-394">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
 <span data-ttu-id="1dfc7-395">[Icordebugvariablesymbol-Schnittstelle](icordebugvariablesymbol-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-395">[ICorDebugVariableSymbol Interface](icordebugvariablesymbol-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-396">Ruft Debugsymbolinformationen für eine Variable ab.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-396">Retrieves the debug symbol information for a variable.</span></span> <span data-ttu-id="1dfc7-397">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-397">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-398">[Icorentbugvirtualunwinder-Schnittstelle](icordebugvirtualunwinder-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-398">[ICorDebugVirtualUnwinder Interface](icordebugvirtualunwinder-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-399">Stellt Methoden bereit, um die Stapelentladung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-399">Provides methods to help in stack unwinding.</span></span> <span data-ttu-id="1dfc7-400">**Nur auf .net Native verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="1dfc7-400">**Available on .NET Native only.**</span></span>  
  
 <span data-ttu-id="1dfc7-401">[ICorPublish-Schnittstelle](icorpublish-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-401">[ICorPublish Interface](icorpublish-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-402">Fungiert als allgemeine Schnittstelle für die Veröffentlichungsprozesse.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-402">Serves as the general interface for the publishing processes.</span></span>  
  
 <span data-ttu-id="1dfc7-403">[ICorPublishAppDomain-Schnittstelle](icorpublishappdomain-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-403">[ICorPublishAppDomain Interface](icorpublishappdomain-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-404">Stellt Informationen zu einer Anwendungsdomäne dar und bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-404">Represents and provides information about an application domain.</span></span>  
  
 <span data-ttu-id="1dfc7-405">[Icorpublishappdomainerum-Schnittstelle](icorpublishappdomainenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-405">[ICorPublishAppDomainEnum Interface](icorpublishappdomainenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-406">Stellt Methoden bereit, die eine Auflistung von `ICorPublishAppDomain`-Objekten traversieren, die gerade innerhalb eines Prozesses vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-406">Provides methods that traverse a collection of `ICorPublishAppDomain` objects that currently exist within a process.</span></span>  
  
 <span data-ttu-id="1dfc7-407">[ICorPublishEnum-Schnittstelle](icorpublishenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-407">[ICorPublishEnum Interface](icorpublishenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-408">Fungiert als abstrakte Basis für die Veröffentlichung von Enumeratoren.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-408">Serves as the abstract base for publishing enumerators.</span></span>  
  
 <span data-ttu-id="1dfc7-409">[ICorPublishProcess-Schnittstelle](icorpublishprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-409">[ICorPublishProcess Interface](icorpublishprocess-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-410">Stellt Methoden bereit, die auf Informationen über einen Prozess zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-410">Provides methods that access information about a process.</span></span>  
  
 <span data-ttu-id="1dfc7-411">[ICorPublishProcessEnum-Schnittstelle](icorpublishprocessenum-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-411">[ICorPublishProcessEnum Interface](icorpublishprocessenum-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-412">Stellt Methoden bereit, die eine Auflistung von `ICorPublishProcess`-Objekten traversieren.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-412">Provides methods that traverse a collection of `ICorPublishProcess` objects.</span></span>  

 <span data-ttu-id="1dfc7-413">[Isosdacinterface-Schnittstelle](isosdacinterface-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-413">[ISOSDacInterface Interface](isosdacinterface-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-414">Stellt Hilfsmethoden für den Zugriff auf Daten aus `SOS`bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-414">Provides helper methods to access data from `SOS`.</span></span>

 <span data-ttu-id="1dfc7-415">[Ixclrdatamethoddefinition-Schnittstelle](ixclrdatamethoddefinition-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-415">[IXCLRDataMethodDefinition Interface](ixclrdatamethoddefinition-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-416">Stellt Methoden zum Abfragen von Informationen über eine Methoden Definition bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-416">Provides methods for querying information about a method definition.</span></span>
 
 <span data-ttu-id="1dfc7-417">[Ixclrdatamethodinstance-Schnittstelle](ixclrdatamethodinstance-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-417">[IXCLRDataMethodInstance Interface](ixclrdatamethodinstance-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-418">Stellt Methoden bereit, mit denen Informationen zu einer Methoden Instanz abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-418">Provides methods for querying information about a method instance.</span></span>
 
 <span data-ttu-id="1dfc7-419">[Ixclrdatamodule-Schnittstelle](ixclrdatamodule-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-419">[IXCLRDataModule Interface](ixclrdatamodule-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-420">Stellt Methoden zum Abfragen von Informationen über ein geladenes Modul bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-420">Provides methods for querying information about a loaded module.</span></span>
 
 <span data-ttu-id="1dfc7-421">[Ixclrdataprocess-Schnittstelle](ixclrdataprocess-interface.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-421">[IXCLRDataProcess Interface](ixclrdataprocess-interface.md)</span></span>\
 <span data-ttu-id="1dfc7-422">Stellt Methoden zum Abfragen von Informationen zu einem Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="1dfc7-422">Provides methods for querying information about a process.</span></span>
  
## <a name="related-sections"></a><span data-ttu-id="1dfc7-423">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="1dfc7-423">Related Sections</span></span>  
 <span data-ttu-id="1dfc7-424">[Debugging von Co-Klassen](debugging-coclasses.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-424">[Debugging Coclasses](debugging-coclasses.md)</span></span>\
 <span data-ttu-id="1dfc7-425">[Debuggen von globalen statischen Funktionen](debugging-global-static-functions.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-425">[Debugging Global Static Functions](debugging-global-static-functions.md)</span></span>\
 <span data-ttu-id="1dfc7-426">[Debuggen von Enumerationen](debugging-enumerations.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-426">[Debugging Enumerations](debugging-enumerations.md)</span></span>\
 <span data-ttu-id="1dfc7-427">[Debugstrukturen](debugging-structures.md)</span><span class="sxs-lookup"><span data-stu-id="1dfc7-427">[Debugging Structures](debugging-structures.md)</span></span>\
