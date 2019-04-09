---
title: ICorProfilerInfo3::SetFunctionIDMapper2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetFunctionIDMapper2 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetFunctionIDMapper2
helpviewer_keywords:
- SetFunctionIDMapper2 method [.NET Framework profiling]
- ICorProfilerInfo3::SetFunctionIDMapper2 method [.NET Framework profiling]
ms.assetid: 8cdb1188-952a-4ba8-9f05-bfebc18cdd29
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1d04c15fa181d0e7bf8a92c1b6ecdef5b8b13bd7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182428"
---
# <a name="icorprofilerinfo3setfunctionidmapper2-method"></a><span data-ttu-id="36c5b-102">ICorProfilerInfo3::SetFunctionIDMapper2-Methode</span><span class="sxs-lookup"><span data-stu-id="36c5b-102">ICorProfilerInfo3::SetFunctionIDMapper2 Method</span></span>
<span data-ttu-id="36c5b-103">Gibt die vom Profiler implementierte Funktion an, die aufgerufen wird, um die `FunctionID`-Werte alternativen Werten zuzuordnen, die an die Funktionseinstiegs-/-exithooks des Profilers übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="36c5b-103">Specifies the profiler-implemented function that will be called to map `FunctionID` values to alternative values, which are passed to the profiler's function entry/exit hooks.</span></span> <span data-ttu-id="36c5b-104">Diese Methode erweitert die [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) Methode mit einem Parameter für zusätzliche Daten, die Profiler verwenden, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="36c5b-104">This method extends the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method with an additional data parameter, which profilers may use to disambiguate among runtimes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c5b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="36c5b-105">Syntax</span></span>  
  
```  
HRESULT SetFunctionIDMapper2(  
       [in] FunctionIDMapper2 *pFunc,  
       [in] void *clientData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c5b-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="36c5b-106">Parameters</span></span>  
 `pFunc`  
 <span data-ttu-id="36c5b-107">[in] Ein Zeiger auf eine [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) -Implementierung, die aufgerufen wird, um das Zuordnen der `FunctionID` -Werte alternativen Werten.</span><span class="sxs-lookup"><span data-stu-id="36c5b-107">[in] A pointer to a [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) implementation that will be called to map the `FunctionID` values to their alternative values.</span></span>  
  
 `clientData`  
 <span data-ttu-id="36c5b-108">[in] Ein Zeiger, der auf alle übergebenen [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) Funktionsaufruf, die von der aktuellen Laufzeit vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="36c5b-108">[in] A pointer that is passed to every [FunctionIDMapper2](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md) function call made by the current runtime.</span></span> <span data-ttu-id="36c5b-109">Der Profiler kann diese Informationen verwenden, um Mehrdeutigkeiten zwischen Laufzeiten aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="36c5b-109">The profiler can use this information to disambiguate among runtimes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="36c5b-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="36c5b-110">Return Value</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36c5b-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36c5b-111">Remarks</span></span>  
 <span data-ttu-id="36c5b-112">Die alternativen für die FunctionID Werte werden der Profiler Funktion Einstiegs-/ausstiegsspunkt Hooks übergeben werden ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) ; oder [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), und [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) dem angegebenen die [ SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) oder [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="36c5b-112">The alternatives for the FunctionID values will be passed to the profiler's function entry/exit hooks ([FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md); or [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)) that are specified by the [SetEnterLeaveFunctionHooks3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md) or [SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method.</span></span>  
  
 <span data-ttu-id="36c5b-113">Die `FunctionIDMapper2` Methode kann nur einmal festgelegt werden; es wird empfohlen, sie Sie in legen der [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="36c5b-113">The `FunctionIDMapper2` method can be set only once; we recommend that you set it in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c5b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="36c5b-114">Requirements</span></span>  
 <span data-ttu-id="36c5b-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c5b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c5b-116">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36c5b-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36c5b-117">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36c5b-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="36c5b-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="36c5b-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36c5b-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36c5b-119">See also</span></span>

- [<span data-ttu-id="36c5b-120">SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="36c5b-120">SetFunctionIDMapper</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="36c5b-121">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="36c5b-121">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="36c5b-122">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="36c5b-122">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="36c5b-123">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="36c5b-123">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
