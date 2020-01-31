---
title: ICorDebugManagedCallback::LogMessage-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.LogMessage
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::LogMessage
helpviewer_keywords:
- ICorDebugManagedCallback::LogMessage method [.NET Framework debugging]
- LogMessage method [.NET Framework debugging]
ms.assetid: d218554a-bf42-4d88-833d-ede30de67a53
topic_type:
- apiref
ms.openlocfilehash: 4306c4ae44b0ae1ade2bf374981492fa1a4df76f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788370"
---
# <a name="icordebugmanagedcallbacklogmessage-method"></a><span data-ttu-id="30a6e-102">ICorDebugManagedCallback::LogMessage-Methode</span><span class="sxs-lookup"><span data-stu-id="30a6e-102">ICorDebugManagedCallback::LogMessage Method</span></span>
<span data-ttu-id="30a6e-103">Benachrichtigt den Debugger, dass ein von Common Language Runtime (CLR) verwalteter Thread eine Methode in der <xref:System.Diagnostics.EventLog>-Klasse aufgerufen hat, um ein Ereignis zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="30a6e-103">Notifies the debugger that a common language runtime (CLR) managed thread has called a method in the <xref:System.Diagnostics.EventLog> class to log an event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30a6e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="30a6e-104">Syntax</span></span>  
  
```cpp  
HRESULT LogMessage (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] LONG                 lLevel,  
    [in] WCHAR               *pLogSwitchName,  
    [in] WCHAR               *pMessage  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30a6e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="30a6e-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="30a6e-106">in Ein Zeiger auf ein ICorDebugAppDomain-Objekt, das die Anwendungsdomäne darstellt, die den verwalteten Thread enthält, der das Ereignis protokolliert hat.</span><span class="sxs-lookup"><span data-stu-id="30a6e-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the managed thread that logged the event.</span></span>  
  
 `pThread`  
 <span data-ttu-id="30a6e-107">[in] Ein Zeiger auf ein ICorDebugThread-Objekt, das den verwalteten Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="30a6e-107">[in] A pointer to an ICorDebugThread object that represents the managed thread.</span></span>  
  
 `lLevel`  
 <span data-ttu-id="30a6e-108">in Ein Wert der [logginglevelenumum](logginglevelenum-enumeration.md) -Enumeration, der den Schweregrad der beschreibenden Meldung angibt, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="30a6e-108">[in] A value of the [LoggingLevelEnum](logginglevelenum-enumeration.md) enumeration that indicates the severity level of the descriptive message that was written to the event log.</span></span>  
  
 `pLogSwitchName`  
 <span data-ttu-id="30a6e-109">in Ein Zeiger auf den Namen des Ablaufverfolgungs-Schalters.</span><span class="sxs-lookup"><span data-stu-id="30a6e-109">[in] A pointer to the name of the tracing switch.</span></span>  
  
 `pMessage`  
 <span data-ttu-id="30a6e-110">in Ein Zeiger auf die Meldung, die in das Ereignisprotokoll geschrieben wurde.</span><span class="sxs-lookup"><span data-stu-id="30a6e-110">[in] A pointer to the message that was written to the event log.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30a6e-111">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="30a6e-111">Requirements</span></span>  
 <span data-ttu-id="30a6e-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30a6e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30a6e-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="30a6e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="30a6e-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="30a6e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="30a6e-115">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30a6e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30a6e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30a6e-116">See also</span></span>

- [<span data-ttu-id="30a6e-117">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="30a6e-117">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
