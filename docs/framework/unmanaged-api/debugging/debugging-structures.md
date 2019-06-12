---
title: Debuggen von Strukturen
ms.date: 03/30/2017
helpviewer_keywords:
- unmanaged structures [.NET Framework], debugging
- debugging structures [.NET Framework]
- structures [.NET Framework debugging]
ms.assetid: 173ba2c2-ab34-49ae-b6a8-e5c49882bf05
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45a4b5c2a65ae7e4c01ffc3977875e598d076557
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025928"
---
# <a name="debugging-structures"></a><span data-ttu-id="6af68-102">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="6af68-102">Debugging Structures</span></span>

<span data-ttu-id="6af68-103">In diesem Abschnitt werden die nicht verwalteten Strukturen beschrieben, die die Debug-API verwendet.</span><span class="sxs-lookup"><span data-stu-id="6af68-103">This section describes the unmanaged structures that the debugging API uses.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="6af68-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6af68-104">In This Section</span></span>
 <span data-ttu-id="6af68-105">[CLRDATA_ADDRESS_RANGE Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) ein Adressbereichs definiert.</span><span class="sxs-lookup"><span data-stu-id="6af68-105">[CLRDATA_ADDRESS_RANGE Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-address-range-structure.md) Defines an address range.</span></span>

 <span data-ttu-id="6af68-106">[CLRDATA_IL_ADDRESS_MAP Struktur](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) definiert eine IL-Adresszuordnung</span><span class="sxs-lookup"><span data-stu-id="6af68-106">[CLRDATA_IL_ADDRESS_MAP Structure](../../../../docs/framework/unmanaged-api/debugging/clrdata-il-address-map-structure.md) Defines an IL to address mapping</span></span>

 <span data-ttu-id="6af68-107">[CLR_DEBUGGING_VERSION-Struktur](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) definiert die Produktversion aus, der die common Language Runtime (CLR) zu Debugzwecken.</span><span class="sxs-lookup"><span data-stu-id="6af68-107">[CLR_DEBUGGING_VERSION Structure](../../../../docs/framework/unmanaged-api/debugging/clr-debugging-version-structure.md) Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>

 <span data-ttu-id="6af68-108">[CodeChunkInfo-Struktur](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) stellt einen einzelnen Codeabschnitt im Speicher.</span><span class="sxs-lookup"><span data-stu-id="6af68-108">[CodeChunkInfo Structure](../../../../docs/framework/unmanaged-api/debugging/codechunkinfo-structure.md) Represents a single chunk of code in memory.</span></span>

 <span data-ttu-id="6af68-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) enthält Informationen zu den Funktionen, die derzeit in den Rahmen eines Threads aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="6af68-109">[COR_ACTIVE_FUNCTION](cor-active-function-structure.md) Contains information about the functions that are currently active in a thread's frames.</span></span>

 <span data-ttu-id="6af68-110">[COR_ARRAY_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) enthält Informationen über das Layout eines Arrayobjekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="6af68-110">[COR_ARRAY_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-array-layout-structure.md) Provides information about the layout of an array object in memory.</span></span>

 <span data-ttu-id="6af68-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) enthält, die die Offsets, die verwendet werden, um das Zuordnen von Microsoft intermediate Language (MSIL) in systemeigenen Code Code.</span><span class="sxs-lookup"><span data-stu-id="6af68-111">[COR_DEBUG_IL_TO_NATIVE_MAP](cor-debug-il-to-native-map-structure.md) Contains the offsets that are used to map Microsoft intermediate language (MSIL) code to native code.</span></span>

 <span data-ttu-id="6af68-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) enthält die Offsetinformationen für einen Bereich von Code.</span><span class="sxs-lookup"><span data-stu-id="6af68-112">[COR_DEBUG_STEP_RANGE](cor-debug-step-range-structure.md) Contains the offset information for a range of code.</span></span>

 <span data-ttu-id="6af68-113">[COR_FIELD-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) enthält Informationen über ein Feld in einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="6af68-113">[COR_FIELD Structure](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Provides information about a field in an object.</span></span>

 <span data-ttu-id="6af68-114">[COR_GC_REFERENCE-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) enthält Informationen zu einem Objekt, das speicherbereinigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6af68-114">[COR_GC_REFERENCE Structure](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) Contains information about an object that is to be garbage-collected.</span></span>

 <span data-ttu-id="6af68-115">[COR_HEAPINFO-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) enthält allgemeine Informationen zur Garbage Collection-Heap, z. B., ob sie aufzählbar ist.</span><span class="sxs-lookup"><span data-stu-id="6af68-115">[COR_HEAPINFO Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Provides general information about the garbage collection heap, including whether it is enumerable.</span></span>

 <span data-ttu-id="6af68-116">[COR_HEAPOBJECT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) enthält Informationen zu einem Objekt auf dem verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="6af68-116">[COR_HEAPOBJECT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Provides information about an object on the managed heap.</span></span>

 <span data-ttu-id="6af68-117">[COR_IL_MAP](cor-il-map-structure.md) gibt Änderungen im relativen Offset einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="6af68-117">[COR_IL_MAP](cor-il-map-structure.md) Specifies changes in the relative offset of a function.</span></span>

 <span data-ttu-id="6af68-118">[COR_SEGMENT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) enthält Informationen zu einem Bereich des Arbeitsspeichers im verwalteten Heap.</span><span class="sxs-lookup"><span data-stu-id="6af68-118">[COR_SEGMENT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-segment-structure.md) Contains information about a region of memory in the managed heap.</span></span>

 <span data-ttu-id="6af68-119">[COR_TYPEID-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) enthält einen Typbezeichner.</span><span class="sxs-lookup"><span data-stu-id="6af68-119">[COR_TYPEID Structure](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) Contains a type identifier.</span></span>

 <span data-ttu-id="6af68-120">[COR_TYPE_LAYOUT-Struktur](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) enthält Informationen über das Layout eines Objekts im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="6af68-120">[COR_TYPE_LAYOUT Structure](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) Provides information about the layout of an object in memory.</span></span>

 <span data-ttu-id="6af68-121">[COR_VERSION](cor-version-structure.md) speichert die standardmäßige vierstellige Versionsnummer der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="6af68-121">[COR_VERSION](cor-version-structure.md) Stores the standard four-part version number of the common language runtime.</span></span>

 <span data-ttu-id="6af68-122">[CorDebugBlockingObject-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) definiert ein Objekt, die blockiert einen Thread und den Grund, weshalb der Thread blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="6af68-122">[CorDebugBlockingObject Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) Defines an object that is blocking a thread and the reason why the thread is blocked.</span></span>

 <span data-ttu-id="6af68-123">[CorDebugEHClause-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) stellt eine Klausel zur Ausnahmebehandlung (EH) für einen bestimmten intermediate Language (IL).</span><span class="sxs-lookup"><span data-stu-id="6af68-123">[CorDebugEHClause Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) Represents an exception handling (EH) clause for a given piece of intermediate language (IL).</span></span>

 <span data-ttu-id="6af68-124">[CorDebugExceptionObjectStackFrame-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) stellt stapelrahmeninformationen von einem Ausnahmeobjekt.</span><span class="sxs-lookup"><span data-stu-id="6af68-124">[CorDebugExceptionObjectStackFrame Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) Represents stack frame information from an exception object.</span></span>

 <span data-ttu-id="6af68-125">[CorDebugGuidToTypeMapping-Struktur](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) ordnet eine Windows-Runtime-GUID der entsprechenden [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="6af68-125">[CorDebugGuidToTypeMapping Structure](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Maps a Windows Runtime GUID to its corresponding [ICorDebugType](../../../../docs/framework/unmanaged-api/debugging/icordebugtype-interface.md) object.</span></span>

 <span data-ttu-id="6af68-126">[DacpGetModuleAddress Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) definiert der Container für eine Anforderung zum modulimport Adresse.</span><span class="sxs-lookup"><span data-stu-id="6af68-126">[DacpGetModuleAddress Structure](../../../../docs/framework/unmanaged-api/debugging/dacpgetmoduleaddress-structure.md) Defines the container for a module address request.</span></span>

 <span data-ttu-id="6af68-127">[DacpMethodDescData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) definiert einen Transport-Puffer für die Runtime-Informationen von einer Methode.</span><span class="sxs-lookup"><span data-stu-id="6af68-127">[DacpMethodDescData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmethoddescdata-structure.md) Defines a transport buffer for a method's runtime information.</span></span>

 <span data-ttu-id="6af68-128">[DacpModuleData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) definiert einen Transport-Puffer für die Runtime-Informationen des Moduls.</span><span class="sxs-lookup"><span data-stu-id="6af68-128">[DacpModuleData Structure](../../../../docs/framework/unmanaged-api/debugging/dacpmoduledata-structure.md) Defines a transport buffer for a module's runtime information.</span></span>

 <span data-ttu-id="6af68-129">[DacpReJitData Struktur](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) definiert die grundlegende Informationen zu einer bestimmten Profiler-instrumentierter Methode.</span><span class="sxs-lookup"><span data-stu-id="6af68-129">[DacpReJitData Structure](../../../../docs/framework/unmanaged-api/debugging/dacprejitdata-structure.md) Defines the basic information about a given profiler-instrumented method.</span></span>

 <span data-ttu-id="6af68-130">[StackTrace_SimpleContext-Struktur](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) bietet einen einfachen Kontext, die anstelle einer vollständigen verwendet werden kann `CONTEXT` Struktur.</span><span class="sxs-lookup"><span data-stu-id="6af68-130">[StackTrace_SimpleContext Structure](../../../../docs/framework/unmanaged-api/debugging/stacktrace-simplecontext-structure.md) Provides a simple context that can be used in place of a full `CONTEXT` structure.</span></span>

## <a name="related-sections"></a><span data-ttu-id="6af68-131">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6af68-131">Related Sections</span></span>

 [<span data-ttu-id="6af68-132">Debuggen von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="6af68-132">Debugging Coclasses</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-coclasses.md)

 [<span data-ttu-id="6af68-133">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6af68-133">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)

 [<span data-ttu-id="6af68-134">Debuggen von globalen statischen Funktionen</span><span class="sxs-lookup"><span data-stu-id="6af68-134">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)

 [<span data-ttu-id="6af68-135">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="6af68-135">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)

 [<span data-ttu-id="6af68-136">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6af68-136">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
