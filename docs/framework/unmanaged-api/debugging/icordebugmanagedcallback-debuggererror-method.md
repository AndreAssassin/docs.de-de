---
title: ICorDebugManagedCallback::DebuggerError-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.DebuggerError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type:
- apiref
ms.openlocfilehash: c03be2405e1ab0287a2921b6e2e293862c67a193
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137372"
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="a62dd-102">ICorDebugManagedCallback::DebuggerError-Methode</span><span class="sxs-lookup"><span data-stu-id="a62dd-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="a62dd-103">Benachrichtigt den Debugger, dass beim Verarbeiten eines Ereignisses aus dem Common Language Runtime (CLR) ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a62dd-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a62dd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a62dd-104">Syntax</span></span>  
  
```cpp  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a62dd-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a62dd-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="a62dd-106">in Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, in dem das Ereignis aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a62dd-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="a62dd-107">in Der HRESULT-Wert, der vom Ereignishandler zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a62dd-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="a62dd-108">in Eine ganze Zahl, die den CLR-Fehler angibt.</span><span class="sxs-lookup"><span data-stu-id="a62dd-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a62dd-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a62dd-109">Remarks</span></span>  
 <span data-ttu-id="a62dd-110">Der Prozess kann je nach Art des Fehlers in den Pass-Through-Modus versetzt werden.</span><span class="sxs-lookup"><span data-stu-id="a62dd-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="a62dd-111">Der `DebugError` Rückruf gibt an, dass debuggingdienste aufgrund eines Fehlers deaktiviert wurden. Daher sollten Debugger dem Benutzer die Fehlermeldung zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="a62dd-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="a62dd-112">[ICorDebugProcess:: GetId](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) kann sicher aufgerufen werden, aber alle anderen Methoden, einschließlich [ICorDebug::](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)End, dürfen nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="a62dd-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="a62dd-113">Der Debugger sollte Betriebssystemfunktionen zum Beenden von Prozessen verwenden.</span><span class="sxs-lookup"><span data-stu-id="a62dd-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a62dd-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a62dd-114">Requirements</span></span>  
 <span data-ttu-id="a62dd-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a62dd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a62dd-116">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a62dd-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a62dd-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a62dd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a62dd-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a62dd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a62dd-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a62dd-119">See also</span></span>

- [<span data-ttu-id="a62dd-120">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a62dd-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
