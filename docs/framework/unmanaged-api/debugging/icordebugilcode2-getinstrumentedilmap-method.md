---
title: ICorDebugILCode2::GetInstrumentedILMap-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 7dede4e5af702f1b86b430450db4a669c326c062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131066"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a><span data-ttu-id="d79c4-102">ICorDebugILCode2::GetInstrumentedILMap-Methode</span><span class="sxs-lookup"><span data-stu-id="d79c4-102">ICorDebugILCode2::GetInstrumentedILMap Method</span></span>
<span data-ttu-id="d79c4-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="d79c4-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="d79c4-104">Gibt eine Zuordnung von Profiler-instrumentierten Intermediate Language (IL) Offsets zu ILs der ursprünglichen Methode für diese Instanz aus.</span><span class="sxs-lookup"><span data-stu-id="d79c4-104">Returns a map from profiler-instrumented intermediate language (IL) offsets to original method IL offsets for this instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d79c4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d79c4-105">Syntax</span></span>  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d79c4-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="d79c4-106">Parameters</span></span>  
 <span data-ttu-id="d79c4-107">cMap</span><span class="sxs-lookup"><span data-stu-id="d79c4-107">cMap</span></span>  
 <span data-ttu-id="d79c4-108">[in] Die Speicherkapazität für das `map`-Array.</span><span class="sxs-lookup"><span data-stu-id="d79c4-108">[in] The storage capacity of the `map` array.</span></span> <span data-ttu-id="d79c4-109">Weitere Informationen finden Sie im Abschnitt Hinweise.</span><span class="sxs-lookup"><span data-stu-id="d79c4-109">See the Remarks section for more information.</span></span>  
  
 <span data-ttu-id="d79c4-110">pcMap</span><span class="sxs-lookup"><span data-stu-id="d79c4-110">pcMap</span></span>  
 <span data-ttu-id="d79c4-111">vorgenommen Die Anzahl der COR_IL_MAP-Werte, die in das Karten Array geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d79c4-111">[out] The number of COR_IL_MAP values written to the map array.</span></span>  
  
 <span data-ttu-id="d79c4-112">Zuordnung</span><span class="sxs-lookup"><span data-stu-id="d79c4-112">map</span></span>  
 <span data-ttu-id="d79c4-113">vorgenommen Ein Array von COR_IL_MAP-Werten, die Informationen zu Zuordnungen von Profiler-instrumentierter Il zum Il der ursprünglichen Methode bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d79c4-113">[out] An array of COR_IL_MAP values that provide information on mappings from profiler-instrumented IL to the IL of the original method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d79c4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d79c4-114">Remarks</span></span>  
 <span data-ttu-id="d79c4-115">Wenn der Profiler die Zuordnung durch Aufrufen der [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) -Methode festlegt, kann der Debugger diese Methode aufrufen, um die Zuordnung abzurufen und die Zuordnung intern zu verwenden, wenn IL-Offsets für Stapel Überwachungen und Variablen berechnet werden. Lebensdauer.</span><span class="sxs-lookup"><span data-stu-id="d79c4-115">If the profiler sets the mapping by calling the [ICorProfilerInfo::SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) method, the debugger can call this method to retrieve the mapping and to use the mapping internally when calculating IL offsets for stack traces and variable lifetimes.</span></span>  
  
 <span data-ttu-id="d79c4-116">Wenn `cMap` 0 und `pcMap` nicht**null**ist, wird `pcMap` auf die Anzahl der verfügbaren COR_IL_MAP-Werte festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d79c4-116">If `cMap` is 0 and `pcMap` is non-**null**, `pcMap` is set to the number of available COR_IL_MAP values.</span></span> <span data-ttu-id="d79c4-117">Wenn `cMap` nicht NULL ist, stellt es die Speicherkapazität des `map`-Arrays dar.</span><span class="sxs-lookup"><span data-stu-id="d79c4-117">If `cMap` is non-zero, it represents the storage capacity of the `map` array.</span></span> <span data-ttu-id="d79c4-118">Wenn die Methode zurückgibt, enthält `map` maximal `cMap` Elemente, und `pcMap` auf die Anzahl der COR_IL_MAP-Werte festgelegt, die tatsächlich in das `map` Array geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="d79c4-118">When the method returns, `map` contains a maximum of `cMap` items, and `pcMap` is set to the number of COR_IL_MAP values actually written to the `map` array.</span></span>  
  
 <span data-ttu-id="d79c4-119">Wenn das IL instrumentiert oder die Zuordnung nicht von einem Profiler bereitgestellt wurde, gibt diese Methode `S_OK` aus und legt `pcMap` auf 0 fest.</span><span class="sxs-lookup"><span data-stu-id="d79c4-119">If the IL hasn't been instrumented or the mapping wasn't provided by a profiler, this method returns `S_OK` and sets `pcMap` to 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d79c4-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d79c4-120">Requirements</span></span>  
 <span data-ttu-id="d79c4-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d79c4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d79c4-122">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d79c4-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d79c4-123">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d79c4-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d79c4-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d79c4-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d79c4-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d79c4-125">See also</span></span>

- [<span data-ttu-id="d79c4-126">ICorProfilerInfo:: Setup-Code Map</span><span class="sxs-lookup"><span data-stu-id="d79c4-126">ICorProfilerInfo::SetILInstrumentedCodeMap</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [<span data-ttu-id="d79c4-127">ICorDebugILCode2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d79c4-127">ICorDebugILCode2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [<span data-ttu-id="d79c4-128">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d79c4-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
