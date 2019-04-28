---
title: ICorProfilerCallback::AssemblyLoadFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e32af790c755f65b5435455c326d011656da19ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597374"
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a><span data-ttu-id="fae19-102">ICorProfilerCallback::AssemblyLoadFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="fae19-102">ICorProfilerCallback::AssemblyLoadFinished Method</span></span>
<span data-ttu-id="fae19-103">Benachrichtigt den Profiler an, dass eine Assembly geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fae19-103">Notifies the profiler that an assembly has finished loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fae19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fae19-104">Syntax</span></span>  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fae19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="fae19-105">Parameters</span></span>  
 `assemblyId`  
 <span data-ttu-id="fae19-106">[in] Identifiziert die Assembly, die geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fae19-106">[in] Identifies the assembly that was loaded.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="fae19-107">[in] Ein HRESULT, der angibt, ob die Assembly erfolgreich fertig geladen wurde.</span><span class="sxs-lookup"><span data-stu-id="fae19-107">[in] An HRESULT that indicates whether the assembly finished loading successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fae19-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fae19-108">Remarks</span></span>  
 <span data-ttu-id="fae19-109">Der Wert des `assemblyId` gilt nicht für eine Anforderung von Informationen bis der `AssemblyLoadFinished` Methode wird aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fae19-109">The value of `assemblyId` is not valid for an information request until the `AssemblyLoadFinished` method is called.</span></span>  
  
 <span data-ttu-id="fae19-110">Laden Sie die Assembly möglicherweise weiterhin nach den `AssemblyLoadFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="fae19-110">Some parts of loading the assembly might continue after the `AssemblyLoadFinished` callback.</span></span> <span data-ttu-id="fae19-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="fae19-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="fae19-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil beim Laden der Assembly erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="fae19-112">However, a success HRESULT in `hrStatus` indicates only that the first part of loading the assembly has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fae19-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fae19-113">Requirements</span></span>  
 <span data-ttu-id="fae19-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fae19-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fae19-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fae19-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fae19-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fae19-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fae19-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fae19-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fae19-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fae19-118">See also</span></span>

- [<span data-ttu-id="fae19-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fae19-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
