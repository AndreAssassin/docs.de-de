---
title: ICorProfilerCallback::RuntimeSuspendAborted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e9aaf7325b8e7e65aa98904513cc7efe94e35087
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180566"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a><span data-ttu-id="acad5-102">ICorProfilerCallback::RuntimeSuspendAborted-Methode</span><span class="sxs-lookup"><span data-stu-id="acad5-102">ICorProfilerCallback::RuntimeSuspendAborted Method</span></span>
<span data-ttu-id="acad5-103">Benachrichtigt den Profiler, dass die Runtime die Runtime-Unterbrechung abgebrochen wurde, die aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="acad5-103">Notifies the profiler that the runtime has aborted the runtime suspension that was occurring.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acad5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="acad5-104">Syntax</span></span>  
  
```  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a><span data-ttu-id="acad5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="acad5-105">Remarks</span></span>  
 <span data-ttu-id="acad5-106">Die Runtime-Unterbrechung kann abgebrochen werden, wenn zwei Threads gleichzeitig versuchen, die Laufzeit angehalten.</span><span class="sxs-lookup"><span data-stu-id="acad5-106">The run-time suspension might be aborted if two threads simultaneously attempt to suspend the runtime.</span></span>  
  
 <span data-ttu-id="acad5-107">Entweder die [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) Rückruf oder `RuntimeSuspendAborted` Rückruf erfolgt in einer einzelnen Thread nach einem [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="acad5-107">Either the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) callback or the `RuntimeSuspendAborted` callback will occur on a single thread following a [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span>  
  
 <span data-ttu-id="acad5-108">Die `RuntimeSuspendAborted` Rückruf wird garantiert auf im gleichen Thread wie der `RuntimeSuspendStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="acad5-108">The `RuntimeSuspendAborted` callback is guaranteed to occur on the same thread as the `RuntimeSuspendStarted` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acad5-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="acad5-109">Requirements</span></span>  
 <span data-ttu-id="acad5-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acad5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acad5-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="acad5-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="acad5-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acad5-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="acad5-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="acad5-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="acad5-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="acad5-114">See also</span></span>

- [<span data-ttu-id="acad5-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="acad5-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
