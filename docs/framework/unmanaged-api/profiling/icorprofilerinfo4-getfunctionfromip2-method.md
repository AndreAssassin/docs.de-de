---
title: ICorProfilerInfo4::GetFunctionFromIP2-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7281f1aa0da417eba618b748ac68ba1fefb4907d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780856"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="d79bb-102">ICorProfilerInfo4::GetFunctionFromIP2-Methode</span><span class="sxs-lookup"><span data-stu-id="d79bb-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="d79bb-103">Ordnet einen Anweisungszeiger im verwalteten Code die JIT-kompilierten Version einer Funktion.</span><span class="sxs-lookup"><span data-stu-id="d79bb-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79bb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d79bb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79bb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d79bb-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="d79bb-106">[in] Der Anweisungszeiger in verwaltetem Code.</span><span class="sxs-lookup"><span data-stu-id="d79bb-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="d79bb-107">[out] Der Funktions-ID</span><span class="sxs-lookup"><span data-stu-id="d79bb-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="d79bb-108">[out] Die Identität der erneut JIT-kompilierten Version der Funktion.</span><span class="sxs-lookup"><span data-stu-id="d79bb-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d79bb-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d79bb-109">Remarks</span></span>  
 <span data-ttu-id="d79bb-110">`GetFunctionFromIP2` ist vergleichbar mit `GetFunctionFromIP`, außer dass es sich um die erneut JIT-kompilierten ID anstelle der Funktions-ID der Funktion abruft, die die angegebene IP-Adresse enthält.</span><span class="sxs-lookup"><span data-stu-id="d79bb-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d79bb-111">`GetFunctionFromIP2` kann eine Garbagecollection auslösen, während `GetFunctionFromIP` nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="d79bb-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="d79bb-112">Weitere Informationen finden Sie unter [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="d79bb-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79bb-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d79bb-113">Requirements</span></span>  
 <span data-ttu-id="d79bb-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d79bb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79bb-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d79bb-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d79bb-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d79bb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d79bb-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79bb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79bb-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d79bb-118">See also</span></span>

- [<span data-ttu-id="d79bb-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d79bb-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
