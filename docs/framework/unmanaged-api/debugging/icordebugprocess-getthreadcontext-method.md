---
title: ICorDebugProcess::GetThreadContext-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.GetThreadContext
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::GetThreadContext
helpviewer_keywords:
- ICorDebugProcess::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: 5b132ef1-8d4b-4525-89b3-54123596c194
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d54becc2d7cd4359c78415f25f579b968cb3f4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775600"
---
# <a name="icordebugprocessgetthreadcontext-method"></a><span data-ttu-id="31569-102">ICorDebugProcess::GetThreadContext-Methode</span><span class="sxs-lookup"><span data-stu-id="31569-102">ICorDebugProcess::GetThreadContext Method</span></span>
<span data-ttu-id="31569-103">Ruft den Kontext für den angegebenen Thread in diesem Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="31569-103">Gets the context for the given thread in this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31569-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="31569-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
    [in] DWORD threadID,  
    [in] ULONG32 contextSize,  
    [in, out, length_is(contextSize), size_is(contextSize)]  
    BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31569-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="31569-105">Parameters</span></span>  
 `threadID`  
 <span data-ttu-id="31569-106">[in] Die ID des Threads, für den zum Abrufen des Kontexts.</span><span class="sxs-lookup"><span data-stu-id="31569-106">[in] The ID of the thread for which to retrieve the context.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="31569-107">[in] Die Größe des `context`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="31569-107">[in] The size of the `context` array.</span></span>  
  
 `context`  
 <span data-ttu-id="31569-108">[in, out] Ein Array von Bytes, die Kontext des Threads zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="31569-108">[in, out] An array of bytes that describe the thread's context.</span></span>  
  
 <span data-ttu-id="31569-109">Der Kontext gibt die Architektur des Prozessors auf dem der Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31569-109">The context specifies the architecture of the processor on which the thread is executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31569-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="31569-110">Remarks</span></span>  
 <span data-ttu-id="31569-111">Der Debugger sollte diese Methode anstelle der Win32-Aufrufen `GetThreadContext` -Methode, da der Thread tatsächlich "gehackte" sind, möglicherweise in der der Kontext vorübergehend geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="31569-111">The debugger should call this method rather than the Win32 `GetThreadContext` method, because the thread may actually be in a "hijacked" state, in which its context has been temporarily changed.</span></span> <span data-ttu-id="31569-112">Diese Methode sollte verwendet werden, nur wenn ein Thread in systemeigenem Code.</span><span class="sxs-lookup"><span data-stu-id="31569-112">This method should be used only when a thread is in native code.</span></span> <span data-ttu-id="31569-113">Verwendung [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) für Threads in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="31569-113">Use [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) for threads in managed code.</span></span>  
  
 <span data-ttu-id="31569-114">Die zurückgegebenen Daten ist ein Context-Struktur für die aktuelle Plattform.</span><span class="sxs-lookup"><span data-stu-id="31569-114">The data returned is a context structure for the current platform.</span></span> <span data-ttu-id="31569-115">Genau wie bei der Win32 `GetThreadContext` -Methode, die der Aufrufer sollte Initialisieren der `context` -Parameter vor dem Aufrufen dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="31569-115">Just as with the Win32 `GetThreadContext` method, the caller should initialize the `context` parameter before calling this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31569-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31569-116">Requirements</span></span>  
 <span data-ttu-id="31569-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31569-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31569-118">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="31569-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31569-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31569-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31569-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31569-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
