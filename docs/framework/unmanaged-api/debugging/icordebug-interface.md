---
title: ICorDebug-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICorDebug
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug
helpviewer_keywords:
- ICorDebug interface [.NET Framework debugging]
ms.assetid: 33f431d7-ab1a-494d-8af2-20ab15aba194
topic_type:
- apiref
ms.openlocfilehash: ee6bcbc9f3377735ed289d52afddb6efa755b16d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134077"
---
# <a name="icordebug-interface"></a><span data-ttu-id="e74de-102">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e74de-102">ICorDebug Interface</span></span>
<span data-ttu-id="e74de-103">Stellt Methoden bereit, mit denen Entwickler Anwendungen in der Common Language Runtime-Umgebung (CLR) Debuggen können.</span><span class="sxs-lookup"><span data-stu-id="e74de-103">Provides methods that allow developers to debug applications in the common language runtime (CLR) environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e74de-104">Das Debuggen im gemischten Modus (verwalteter und nativer Code) wird unter Windows 95, Windows 98 oder Windows Me oder auf nicht-x86-Plattformen (z. b. ia64 und amd64) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e74de-104">Mixed-mode (managed and native code) debugging is not supported on Windows 95, Windows 98, or Windows ME, or on non-x86 platforms (such as IA64 and AMD64).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e74de-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="e74de-105">Methods</span></span>  
  
|<span data-ttu-id="e74de-106">Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-106">Method</span></span>|<span data-ttu-id="e74de-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e74de-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e74de-108">CanLaunchOrAttach-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-108">CanLaunchOrAttach Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-canlaunchorattach-method.md)|<span data-ttu-id="e74de-109">Bestimmt, ob das Starten eines neuen Prozesses oder das Anfügen an den angegebenen Prozess innerhalb des Kontexts der aktuellen Computer-und Laufzeitkonfiguration möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e74de-109">Determines whether launching a new process or attaching to the given process is possible within the context of the current machine and runtime configuration.</span></span>|  
|[<span data-ttu-id="e74de-110">CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-110">CreateProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md)|<span data-ttu-id="e74de-111">Startet einen Prozess und seinen primären Thread unter der Kontrolle des Debuggers.</span><span class="sxs-lookup"><span data-stu-id="e74de-111">Launches a process and its primary thread under the control of the debugger.</span></span>|  
|[<span data-ttu-id="e74de-112">DebugActiveProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-112">DebugActiveProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-debugactiveprocess-method.md)|<span data-ttu-id="e74de-113">Fügt den Debugger an einen vorhandenen Prozess an.</span><span class="sxs-lookup"><span data-stu-id="e74de-113">Attaches the debugger to an existing process.</span></span>|  
|[<span data-ttu-id="e74de-114">EnumerateProcesses-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-114">EnumerateProcesses Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-enumerateprocesses-method.md)|<span data-ttu-id="e74de-115">Ruft einen Enumerator für die Prozesse ab, die gedeentschlgt werden.</span><span class="sxs-lookup"><span data-stu-id="e74de-115">Gets an enumerator for the processes that are being debugged.</span></span>|  
|[<span data-ttu-id="e74de-116">GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-116">GetProcess Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-getprocess-method.md)|<span data-ttu-id="e74de-117">Gibt das "ICorDebugProcess"-Objekt mit der angegebenen Prozess-ID zurück.</span><span class="sxs-lookup"><span data-stu-id="e74de-117">Returns the "ICorDebugProcess" object with the given process ID.</span></span>|  
|[<span data-ttu-id="e74de-118">Initialize-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-118">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-initialize-method.md)|<span data-ttu-id="e74de-119">Initialisiert das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e74de-119">Initializes the `ICorDebug` object.</span></span>|  
|[<span data-ttu-id="e74de-120">SetManagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-120">SetManagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md)|<span data-ttu-id="e74de-121">Gibt das Ereignishandlerobjekt für verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="e74de-121">Specifies the event handler object for managed events.</span></span>|  
|[<span data-ttu-id="e74de-122">SetUnmanagedHandler-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-122">SetUnmanagedHandler Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-setunmanagedhandler-method.md)|<span data-ttu-id="e74de-123">Gibt das Ereignishandlerobjekt für nicht verwaltete Ereignisse an.</span><span class="sxs-lookup"><span data-stu-id="e74de-123">Specifies the event handler object for unmanaged events.</span></span>|  
|[<span data-ttu-id="e74de-124">Terminate-Methode</span><span class="sxs-lookup"><span data-stu-id="e74de-124">Terminate Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)|<span data-ttu-id="e74de-125">Beendet das `ICorDebug`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e74de-125">Terminates the `ICorDebug` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e74de-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e74de-126">Remarks</span></span>  
 <span data-ttu-id="e74de-127">`ICorDebug` stellt eine Ereignis Verarbeitungs Schleife für einen Debuggerprozess dar.</span><span class="sxs-lookup"><span data-stu-id="e74de-127">`ICorDebug` represents an event processing loop for a debugger process.</span></span> <span data-ttu-id="e74de-128">Der Debugger muss auf den Rückruf für den [ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) -Rückruf von allen debuggten Prozessen warten, bevor er diese Schnittstelle freigibt.</span><span class="sxs-lookup"><span data-stu-id="e74de-128">The debugger must wait for the [ICorDebugManagedCallback::ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) callback from all processes being debugged before releasing this interface.</span></span>  
  
 <span data-ttu-id="e74de-129">Das `ICorDebug`-Objekt ist das erste Objekt, das alle weiteren verwalteten Debuggen steuert.</span><span class="sxs-lookup"><span data-stu-id="e74de-129">The `ICorDebug` object is the initial object to control all further managed debugging.</span></span> <span data-ttu-id="e74de-130">In den .NET Framework Versionen 1,0 und 1,1 war dieses Objekt ein `CoClass` Objekt, das aus com erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e74de-130">In the .NET Framework versions 1.0 and 1.1, this object was a `CoClass` object created from COM.</span></span> <span data-ttu-id="e74de-131">In der .NET Framework Version 2,0 ist dieses Objekt kein `CoClass` Objekt mehr.</span><span class="sxs-lookup"><span data-stu-id="e74de-131">In the .NET Framework version 2.0, this object is no longer a `CoClass` object.</span></span> <span data-ttu-id="e74de-132">Sie muss von der Funktion " [dedeedebugginginterfakefromversion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) " erstellt werden, die Versions abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="e74de-132">It must be created by the [CreateDebuggingInterfaceFromVersion](../../../../docs/framework/unmanaged-api/hosting/createdebugginginterfacefromversion-function.md) function, which is more version-aware.</span></span> <span data-ttu-id="e74de-133">Diese neue Erstellungs Funktion ermöglicht es Clients, eine bestimmte Implementierung von `ICorDebug`zu erhalten, wodurch auch eine bestimmte Version der Debug-API emuliert wird.</span><span class="sxs-lookup"><span data-stu-id="e74de-133">This new creation function enables clients to get a specific implementation of `ICorDebug`, which also emulates a specific version of the debugging API.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e74de-134">Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="e74de-134">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e74de-135">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e74de-135">Requirements</span></span>  
 <span data-ttu-id="e74de-136">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e74de-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e74de-137">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e74de-137">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e74de-138">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e74de-138">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e74de-139">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e74de-139">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e74de-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e74de-140">See also</span></span>

- [<span data-ttu-id="e74de-141">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e74de-141">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
