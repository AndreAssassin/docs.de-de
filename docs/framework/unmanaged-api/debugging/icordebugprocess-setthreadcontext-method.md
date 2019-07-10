---
title: ICorDebugProcess::SetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.SetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::SetThreadContext
helpviewer_keywords:
- ICorDebugProcess::SetThreadContext method [.NET Framework debugging]
- SetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: a7b50175-2bf1-40be-8f65-64aec7aa1247
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b949961e854facf8414c81c47f995b2ac57af3f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755380"
---
# <a name="icordebugprocesssetthreadcontext-method"></a><span data-ttu-id="76e8b-102">ICorDebugProcess::SetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="76e8b-102">ICorDebugProcess::SetThreadContext Method</span></span>
<span data-ttu-id="76e8b-103">Legt den Kontext für den angegebenen Thread in diesem Prozess fest.</span><span class="sxs-lookup"><span data-stu-id="76e8b-103">Sets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76e8b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="76e8b-104">Syntax</span></span>  
  
```cpp  
HRESULT SetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="76e8b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="76e8b-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="76e8b-106">[in] Die ID des Threads für den Kontext festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="76e8b-106">[in] The ID of the thread for which to set the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="76e8b-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="76e8b-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="76e8b-108">[in] Ein Array von Bytes, die Kontext des Threads zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="76e8b-108">[in] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="76e8b-109">Der Kontext gibt die Architektur des Prozessors auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="76e8b-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="76e8b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="76e8b-110">Remarks</span></span>  
 <span data-ttu-id="76e8b-111">Der Debugger sollte diese Methode anstelle der Win32-Aufrufen `SetThreadContext` Funktion, da der Thread tatsächlich "gehackte" sind, möglicherweise in der der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="76e8b-111">The debugger should call this method rather than the Win32 `SetThreadContext` function, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="76e8b-112">Diese Methode sollte verwendet werden, nur wenn ein Thread in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="76e8b-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="76e8b-113">Verwendung [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="76e8b-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span> <span data-ttu-id="76e8b-114">Sie müssen nicht den Kontext eines Threads während eines Out-of-Band (OOB) Debug-Ereignisses zu ändern.</span><span class="sxs-lookup"><span data-stu-id="76e8b-114">You should never need to modify the context of a thread during an out-of-band (OOB) debug event.</span></span>  
  
 <span data-ttu-id="76e8b-115">Die übergebenen Daten muss ein Context-Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="76e8b-115">The data passed must be a context structure for the current platform.</span></span>  
  
 <span data-ttu-id="76e8b-116">Diese Methode kann die Laufzeit beschädigt werden, wenn nicht ordnungsgemäß verwendet.</span><span class="sxs-lookup"><span data-stu-id="76e8b-116">This method can corrupt the runtime if used improperly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76e8b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="76e8b-117">Requirements</span></span>  
 <span data-ttu-id="76e8b-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76e8b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76e8b-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="76e8b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="76e8b-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="76e8b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="76e8b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76e8b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
