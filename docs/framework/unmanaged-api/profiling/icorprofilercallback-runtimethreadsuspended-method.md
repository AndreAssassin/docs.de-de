---
title: ICorProfilerCallback::RuntimeThreadSuspended-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b6d03e760d2b08cd9ee8cdfd85e2e28223aeacd4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747230"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended-Methode
Benachrichtigt den Profiler an, der angegebene Thread wurde angehalten oder unterbrochen wird.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Parameter  
 `threadId`  
 [in] Die ID des Threads, der angehalten wurde.  
  
## <a name="remarks"></a>Hinweise  
 Die `RuntimeThreadSuspended` Notifications können jederzeit zwischen der [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) und den zugehörigen [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) Rückrufe. Benachrichtigungen, die zwischen den [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) und `RuntimeResumeStarted` sind für Threads, die ausgeführt wurden, in nicht Code verwaltetem und beim Einstieg in die Laufzeit angehalten wurden.  
  
 Im Allgemeinen tritt dieser Rückruf unmittelbar nach ein Thread angehalten wird. Allerdings ist der aktuell ausgeführte Thread (der Thread, der dieser Rückruf aufgerufen wird) die, die gesperrt wird, wird dieser Rückruf auftreten, kurz bevor der Thread angehalten wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeThreadResumed-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
