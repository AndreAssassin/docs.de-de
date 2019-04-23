---
title: ICorProfilerCallback2::HandleCreated-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleCreated
helpviewer_keywords:
- HandleCreated method [.NET Framework profiling]
- ICorProfilerCallback2::HandleCreated method [.NET Framework profiling]
ms.assetid: 6bbb7786-7c38-490f-9834-91aa2795c355
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cd8b08c630d56ca3b59cad768e285b630d64e59
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59175772"
---
# <a name="icorprofilercallback2handlecreated-method"></a><span data-ttu-id="6fb99-102">ICorProfilerCallback2::HandleCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="6fb99-102">ICorProfilerCallback2::HandleCreated Method</span></span>
<span data-ttu-id="6fb99-103">Benachrichtigt den Profiler an, dass eine Garbage Collection-Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6fb99-103">Notifies the code profiler that a garbage collection handle has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fb99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6fb99-104">Syntax</span></span>  
  
```  
HRESULT HandleCreated(  
    [in] GCHandleID handleId,  
    [in] ObjectID initialObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fb99-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6fb99-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="6fb99-106">[in] Die ID des Handles für die Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="6fb99-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
 `initialObjectId`  
 <span data-ttu-id="6fb99-107">[in] Die ID des Objekts für die die Garbage Collection-Handle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="6fb99-107">[in] The ID of the object for which the garbage collection handle was created.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fb99-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6fb99-108">Requirements</span></span>  
 <span data-ttu-id="6fb99-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fb99-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fb99-110">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6fb99-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6fb99-111">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fb99-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fb99-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fb99-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fb99-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fb99-113">See also</span></span>

- [<span data-ttu-id="6fb99-114">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fb99-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="6fb99-115">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6fb99-115">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
