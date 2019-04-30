---
title: ICorProfilerInfo5::SetEventMask2-Methode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- IcorProfilerInfo5.SetEventMask2
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 05dbbe2b-049c-4a60-be69-2ad7a949405e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266219894ffefa0d4066c6ca68c7cadf6265e098
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000479"
---
# <a name="icorprofilerinfo5seteventmask2-method"></a><span data-ttu-id="17c09-102">ICorProfilerInfo5::SetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="17c09-102">ICorProfilerInfo5::SetEventMask2 Method</span></span>
<span data-ttu-id="17c09-103">[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="17c09-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="17c09-104">Legt einen Wert fest, der die Ereignistypen angibt, für die der Profiler Ereignisbenachrichtigungen von der Common Language Runtime (CLR) erhalten soll.</span><span class="sxs-lookup"><span data-stu-id="17c09-104">Sets a value that specifies the types of events for which the profiler wants to receive event notifications from the common language runtime (CLR).</span></span> <span data-ttu-id="17c09-105">Sie bietet mehr Funktionen als die [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="17c09-105">It provides more functionality than the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17c09-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="17c09-106">Syntax</span></span>  
  
```cpp
HRESULT SetEventMask2(        [in] DWORD dwEventsLow,        [in] DWORD dwEventsHigh  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="17c09-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="17c09-107">Parameters</span></span>  
 `dwEventsLow`  
 <span data-ttu-id="17c09-108">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="17c09-108">[in] A 4-byte value that specifies the categories of events.</span></span> <span data-ttu-id="17c09-109">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="17c09-109">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="17c09-110">Die Bits werden beschrieben, der [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="17c09-110">The bits are described in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 `dwEventsHigh`  
 <span data-ttu-id="17c09-111">[in] Ein 4-Byte-Wert, der die Ereigniskategorien angibt.</span><span class="sxs-lookup"><span data-stu-id="17c09-111">[in] A 4-byte value that specifies the categories of events.</span></span>  <span data-ttu-id="17c09-112">Jedes Bit steuert eine andere Funktion, ein Verhalten oder den Ereignistyp.</span><span class="sxs-lookup"><span data-stu-id="17c09-112">Each bit controls a different capability, behavior, or type of event.</span></span> <span data-ttu-id="17c09-113">Die Bits werden beschrieben, der [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="17c09-113">The bits are described in the [COR_PRF_HIGH_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="17c09-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17c09-114">Remarks</span></span>  
 <span data-ttu-id="17c09-115">Die `SetEventMask2`-Methode wird verwendet, um die Rückrufe festzulegen, die der Profiler abonniert.</span><span class="sxs-lookup"><span data-stu-id="17c09-115">The `SetEventMask2` method is used to set the callbacks to which the profiler subscribes.</span></span> <span data-ttu-id="17c09-116">In der Regel rufen Sie die [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) Methode, um zu bestimmen, welche Bits festgelegt sind, führen Sie ein logisches OR der seine `pdwEventsLow` und `pdwEventsHigh` Werte sowie neuer Bits festgelegt, und klicken Sie dann aufgerufen werden soll die `SetEventMask2` Methode.</span><span class="sxs-lookup"><span data-stu-id="17c09-116">Typically, you call the [GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) method to determine which bits are set, perform a logical OR of its `pdwEventsLow` and `pdwEventsHigh` values and any new bits you want to set, and then call the `SetEventMask2` method.</span></span>  
  
 <span data-ttu-id="17c09-117">Diese Methode ist die empfohlene Alternative zur der [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="17c09-117">This method is the recommended alternative to the [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17c09-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17c09-118">Requirements</span></span>  
 <span data-ttu-id="17c09-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17c09-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17c09-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="17c09-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="17c09-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="17c09-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="17c09-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17c09-122">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17c09-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17c09-123">See also</span></span>

- [<span data-ttu-id="17c09-124">ICorProfilerInfo5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="17c09-124">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
- [<span data-ttu-id="17c09-125">GetEventMask2-Methode</span><span class="sxs-lookup"><span data-stu-id="17c09-125">GetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)
