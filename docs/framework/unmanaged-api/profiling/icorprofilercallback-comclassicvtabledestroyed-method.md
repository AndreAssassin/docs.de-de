---
title: ICorProfilerCallback::COMClassicVTableDestroyed-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63dc9ee81c98a23f01948a142018369eca7210b1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59116754"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="fd931-102">ICorProfilerCallback::COMClassicVTableDestroyed-Methode</span><span class="sxs-lookup"><span data-stu-id="fd931-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="fd931-103">Benachrichtigt den Profiler, dass eine COM-Interop-Vtable zerstört wird.</span><span class="sxs-lookup"><span data-stu-id="fd931-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd931-104">Dieser Rückruf ist nie zu rechnen ist, da die Zerstörung des Vtables sehr nahe Herunterfahren auftritt.</span><span class="sxs-lookup"><span data-stu-id="fd931-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd931-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd931-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd931-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="fd931-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="fd931-107">[in] Die ID der Klasse für die diese Vtable erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="fd931-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="fd931-108">[in] Die ID der von der Klasse implementierten Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fd931-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="fd931-109">Dieser Wert kann NULL sein, wenn die Schnittstelle ausschließlich intern verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fd931-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="fd931-110">[in] Ein Zeiger auf den Anfang der Vtable.</span><span class="sxs-lookup"><span data-stu-id="fd931-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd931-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd931-111">Remarks</span></span>  
 <span data-ttu-id="fd931-112">Der Profiler sollte die Implementierung dieser Methode nicht blockieren, da der Stapel nicht in einem Zustand handeln, der Garbagecollection zulässt, und daher die Präemptive Garbagecollection kann nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd931-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="fd931-113">Wenn der Profiler hier blockiert und Garbagecollection wird versucht, die Laufzeit blockiert, bis dieser Rückruf zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fd931-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="fd931-114">Der Profiler Implementierung dieser Methode sollte nicht in verwaltetem Code oder in einer verwalteten Speicher reservieren aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fd931-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd931-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fd931-115">Requirements</span></span>  
 <span data-ttu-id="fd931-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd931-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd931-117">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd931-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd931-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd931-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd931-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd931-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd931-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd931-120">See also</span></span>

- [<span data-ttu-id="fd931-121">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fd931-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="fd931-122">COMClassicVTableCreated-Methode</span><span class="sxs-lookup"><span data-stu-id="fd931-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
