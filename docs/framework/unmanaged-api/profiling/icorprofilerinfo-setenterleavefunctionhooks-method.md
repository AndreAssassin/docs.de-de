---
title: ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2d45e98f3e7b71375b14c43c4bff4929bc79494
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61860936"
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="987ae-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks-Methode</span><span class="sxs-lookup"><span data-stu-id="987ae-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="987ae-103">Gibt an, Profiler implementierten Funktionen in "eingeben", "verlassen" und "Tailcall" Hooks von verwalteten Funktionen aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="987ae-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="987ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="987ae-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
## <a name="parameters"></a><span data-ttu-id="987ae-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="987ae-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="987ae-106">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="987ae-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="987ae-107">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="987ae-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="987ae-108">[in] Ein Zeiger auf die Implementierung, die als dienen der [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="987ae-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="987ae-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="987ae-109">Remarks</span></span>  
 <span data-ttu-id="987ae-110">In .NET Framework, Version 1.0 kann jede Funktionszeiger So deaktivieren Sie diesen entsprechenden Rückruf null sein.</span><span class="sxs-lookup"><span data-stu-id="987ae-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="987ae-111">Nur einen Satz von Rückrufen kann jeweils aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="987ae-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="987ae-112">Also, wenn ein Profiler, beide aufruft `SetEnterLeaveFunctionHooks` und [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), klicken Sie dann `SetEnterLeaveFunctionHooks2` hat Vorrang vor.</span><span class="sxs-lookup"><span data-stu-id="987ae-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="987ae-113">Die `SetEnterLeaveFunctionHooks` Methode kann aufgerufen werden, nur über die Profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="987ae-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="987ae-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="987ae-114">Requirements</span></span>  
 <span data-ttu-id="987ae-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="987ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987ae-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="987ae-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="987ae-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="987ae-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="987ae-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="987ae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987ae-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="987ae-119">See also</span></span>

- [<span data-ttu-id="987ae-120">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="987ae-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
