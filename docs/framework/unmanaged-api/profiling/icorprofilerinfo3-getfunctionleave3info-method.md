---
title: ICorProfilerInfo3::GetFunctionLeave3Info-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6470bd04e3661e7d27798747abc4ef0757bf4f1e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782156"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="b76e7-102">ICorProfilerInfo3::GetFunctionLeave3Info-Methode</span><span class="sxs-lookup"><span data-stu-id="b76e7-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="b76e7-103">Stellt den Stapelrahmen und den Rückgabewert der Funktion, die dem Profiler von gemeldet wird die [FunctionLeave3WithInfo-Funktion](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b76e7-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="b76e7-104">Diese Methode kann nur während des `FunctionLeave3WithInfo`-Rückrufs aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b76e7-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b76e7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b76e7-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b76e7-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b76e7-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="b76e7-107">[in] Die `FunctionID` der Funktion, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b76e7-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="b76e7-108">[in] Ein nicht transparentes Handle, das Informationen über einen bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="b76e7-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="b76e7-109">Der Profiler sollte gleich bereitstellen `eltInfo` , wurde übergeben, um dem Profiler von der [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) Funktion.</span><span class="sxs-lookup"><span data-stu-id="b76e7-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="b76e7-110">[out] Ein nicht transparentes Handle, das Genericsinformationen zu einem bestimmten Stapelrahmen entspricht.</span><span class="sxs-lookup"><span data-stu-id="b76e7-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="b76e7-111">Dieses Handle ist nur während des `FunctionLeave3WithInfo`-Rückrufs gültig, in dem der Profiler die `GetFunctionLeave3Info`-Methode aufgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="b76e7-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="b76e7-112">[out] Ein Zeiger auf eine [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) -Struktur, die den Wert enthält, die von der Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b76e7-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="b76e7-113">Informationen zum Rückgabewert, den Zugriff auf die `COR_PRF_ENABLE_FUNCTION_RETVAL` Flag festgelegt werden muss.</span><span class="sxs-lookup"><span data-stu-id="b76e7-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="b76e7-114">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) werden die Ereignisflags festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b76e7-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b76e7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b76e7-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b76e7-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b76e7-116">Requirements</span></span>  
 <span data-ttu-id="b76e7-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b76e7-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b76e7-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b76e7-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b76e7-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b76e7-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b76e7-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b76e7-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b76e7-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b76e7-121">See also</span></span>

- [<span data-ttu-id="b76e7-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b76e7-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="b76e7-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b76e7-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="b76e7-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="b76e7-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="b76e7-125">ICorProfilerInfo3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b76e7-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="b76e7-126">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="b76e7-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="b76e7-127">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="b76e7-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
