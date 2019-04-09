---
title: ICorProfilerCallback::FunctionUnloadStarted-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.FunctionUnloadStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c1c1c9a15e9f56765710ffb2015a29b4206b3bd4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59152606"
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="6d07d-102">ICorProfilerCallback::FunctionUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="6d07d-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="6d07d-103">Benachrichtigt den Profiler, dass die Laufzeit gestartet wurde, um eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="6d07d-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d07d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6d07d-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
## <a name="parameters"></a><span data-ttu-id="6d07d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6d07d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6d07d-106">[in] Die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="6d07d-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d07d-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6d07d-107">Remarks</span></span>  
 <span data-ttu-id="6d07d-108">Der Wert des der `functionId` Parameter ist nicht mehr gültig, nachdem diese Methode an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6d07d-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d07d-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6d07d-109">Requirements</span></span>  
 <span data-ttu-id="6d07d-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d07d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d07d-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d07d-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d07d-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d07d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6d07d-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="6d07d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6d07d-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d07d-114">See also</span></span>

- [<span data-ttu-id="6d07d-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6d07d-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
