---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 73321a28b1c61775d08e2c60ee2b9a863b8250dd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000557"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="010ce-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3-Methode</span><span class="sxs-lookup"><span data-stu-id="010ce-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="010ce-103">Gibt an, die vom Profiler implementierten Funktionen, die aufgerufen werden, auf die [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) Funktionen.</span><span class="sxs-lookup"><span data-stu-id="010ce-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="010ce-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="010ce-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="010ce-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="010ce-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="010ce-106">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionEnter3` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="010ce-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="010ce-107">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionLeave3` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="010ce-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="010ce-108">[in] Ein Zeiger auf die Implementierung, die als dienen der `FunctionTailcall3` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="010ce-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="010ce-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="010ce-109">Remarks</span></span>  
 <span data-ttu-id="010ce-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), und [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) Hooks bieten keine Stack Stapelrahmen und Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="010ce-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="010ce-111">Zugriff auf diese Informationen, die `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, und/oder `COR_PRF_ENABLE_FRAME_INFO` Flags festgelegt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="010ce-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="010ce-112">Der Profiler kann mithilfe der [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode, um die Ereignisflags festgelegt, und klicken Sie dann die [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) Methode zum Registrieren Ihrer die Implementierung dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="010ce-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="010ce-113">Nur einen Satz von Rückrufen zu einem Zeitpunkt aktiv sein kann, und die neueste Version Vorrang.</span><span class="sxs-lookup"><span data-stu-id="010ce-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="010ce-114">Aus diesem Grund, wenn ein Profiler, sowohl aufruft die [SetEnterLeaveFunctionHooks2-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) und `SetEnterLeaveFunctionHooks3` -Methode, `SetEnterLeaveFunctionHooks3` wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="010ce-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="010ce-115">Die `SetEnterLeaveFunctionHooks3` Methode aufgerufen werden kann, nur über die Profiler [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="010ce-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="010ce-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="010ce-116">Requirements</span></span>  
 <span data-ttu-id="010ce-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="010ce-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="010ce-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="010ce-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="010ce-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="010ce-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="010ce-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="010ce-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="010ce-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="010ce-121">See also</span></span>

- [<span data-ttu-id="010ce-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="010ce-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="010ce-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="010ce-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="010ce-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="010ce-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="010ce-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="010ce-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="010ce-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="010ce-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="010ce-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="010ce-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="010ce-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="010ce-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="010ce-129">Profilerstellung für globale statische Funktionen</span><span class="sxs-lookup"><span data-stu-id="010ce-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="010ce-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="010ce-130">ICorProfilerInfo3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="010ce-131">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="010ce-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="010ce-132">Profilerstellung</span><span class="sxs-lookup"><span data-stu-id="010ce-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
