---
title: ICorDebugController::HasQueuedCallbacks-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
ms.openlocfilehash: 51ee8b3631bffe9fd7fef4351e0aa67d1cbbe2c9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125396"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks-Methode
Ruft einen Wert ab, der angibt, ob verwaltete Rückrufe zurzeit für den angegebenen Thread in die Warteschlange eingereiht werden.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parameter  
 `pThread`  
 in Ein Zeiger auf ein ICorDebugThread-Objekt, das den Thread darstellt.  
  
 `pbQueued`  
 vorgenommen Ein Zeiger auf einen Wert, der `true` wird, wenn verwaltete Rückrufe aktuell für den angegebenen Thread in die Warteschlange eingereiht werden. Andernfalls `false`.  
  
 Wenn NULL für den `pThread`-Parameter angegeben wird, gibt `HasQueuedCallbacks` `true` zurück, wenn derzeit verwaltete Rückrufe für einen beliebigen Thread in die Warteschlange eingereiht werden.  
  
## <a name="remarks"></a>Hinweise  
 Rückrufe werden einzeln verteilt, jedes Mal, wenn " [icordbugcontroller:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) " aufgerufen wird. Der Debugger kann dieses Flag überprüfen, wenn mehrere Debugereignisse, die gleichzeitig auftreten, gemeldet werden sollen.  
  
 Wenn Debugereignisse in die Warteschlange eingereiht werden, sind Sie bereits aufgetreten, sodass der Debugger die gesamte Warteschlange entfernen muss, um sicherzustellen, dass der Zustand der zu debuggenden Komponente sicher ist. (Wenden Sie `ICorDebugController::Continue` an, um die Warteschlange zu leeren.) Wenn die Warteschlange z. b. zwei Debuggingereignisse für Thread *x*enthält und der Debugger Thread *x* nach dem ersten Debugereignis anhält und dann `ICorDebugController::Continue`aufruft, wird das zweite Debugereignis für Thread *x* gesendet, obwohl der der Thread wurde angehalten.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch
