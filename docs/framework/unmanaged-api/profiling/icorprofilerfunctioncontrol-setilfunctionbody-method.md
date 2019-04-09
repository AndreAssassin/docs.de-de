---
title: ICorProfilerFunctionControl::SetILFunctionBody-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILFunctionBody method [.NET Framework profiling]
- SetILFunctionBody method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 2c33f0f7-75b2-4c19-b2c7-c94b54997576
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3f3351c13530b636cb6715c815b81ab4d9306f53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115777"
---
# <a name="icorprofilerfunctioncontrolsetilfunctionbody-method"></a><span data-ttu-id="86dc4-102">ICorProfilerFunctionControl::SetILFunctionBody-Methode</span><span class="sxs-lookup"><span data-stu-id="86dc4-102">ICorProfilerFunctionControl::SetILFunctionBody Method</span></span>
<span data-ttu-id="86dc4-103">Ersetzt den CIL-Text (Common Intermediate Language) der Methode.</span><span class="sxs-lookup"><span data-stu-id="86dc4-103">Replaces the Common Intermediate Language (CIL) body of the method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86dc4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="86dc4-104">Syntax</span></span>  
  
```  
HRESULT SetILFunctionBody(  
    [in]  ULONG   cbNewILMethodHeader,  
    [in, size_is(cbNewILMethodHeader)] LPCBYTE pbNewILMethodHeader);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86dc4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="86dc4-105">Parameters</span></span>  
 `cbNewILMethodHeader`  
 <span data-ttu-id="86dc4-106">[in] Die Gesamtgröße der neuen CIL, einschließlich des Headers und aller Strukturen, die nach dem Text folgen.</span><span class="sxs-lookup"><span data-stu-id="86dc4-106">[in] The total size of the new CIL, including the header and any structures that come after the body.</span></span>  
  
 `pbNewILMethodHeader`  
 <span data-ttu-id="86dc4-107">[in] Ein Zeiger auf den neuen CIL-Header.</span><span class="sxs-lookup"><span data-stu-id="86dc4-107">[in] A pointer to the new CIL header.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86dc4-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="86dc4-108">Return Value</span></span>  
 <span data-ttu-id="86dc4-109">Diese Methode gibt die folgenden spezifischen HRESULTs zurück.</span><span class="sxs-lookup"><span data-stu-id="86dc4-109">This method returns the following specific HRESULTs.</span></span>  
  
|<span data-ttu-id="86dc4-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86dc4-110">HRESULT</span></span>|<span data-ttu-id="86dc4-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="86dc4-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86dc4-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="86dc4-112">S_OK</span></span>|<span data-ttu-id="86dc4-113">Die Ersetzung war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="86dc4-113">The replacement was successful.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86dc4-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86dc4-114">Remarks</span></span>  
 <span data-ttu-id="86dc4-115">Im Gegensatz zu den [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) -Methode, die `SetILFunctionBody` Methode verwaltet den erforderlichen Speicher für den neuen CIL-Text.</span><span class="sxs-lookup"><span data-stu-id="86dc4-115">Unlike the [ICorProfilerInfo::SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) method, the `SetILFunctionBody` method manages the memory required for the new CIL body.</span></span> <span data-ttu-id="86dc4-116">Dies bedeutet, dass die vom Profiler bereitgestellte CIL-Text nicht unbedingt mit zugeordnet werden die [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) -Schnittstelle zugeordnet oder innerhalb eines bestimmten Bereichs.</span><span class="sxs-lookup"><span data-stu-id="86dc4-116">This means that the CIL body provided by the profiler does not have to be allocated by using the [IMethodMalloc](../../../../docs/framework/unmanaged-api/profiling/imethodmalloc-interface.md) interface or allocated within a particular range.</span></span> <span data-ttu-id="86dc4-117">Er kann auf jedem Heap zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="86dc4-117">It can be allocated on any heap.</span></span> <span data-ttu-id="86dc4-118">Der Profiler kann den für seinen CIL-Text, nach dem verwendeten Arbeitsspeicher frei `SetILFunctionBody` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="86dc4-118">The profiler can free the memory used for its CIL body after `SetILFunctionBody` returns.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86dc4-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="86dc4-119">Requirements</span></span>  
 <span data-ttu-id="86dc4-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86dc4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86dc4-121">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86dc4-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86dc4-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86dc4-122">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="86dc4-123">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="86dc4-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="86dc4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86dc4-124">See also</span></span>

- [<span data-ttu-id="86dc4-125">ICorProfilerFunctionControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="86dc4-125">ICorProfilerFunctionControl Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-interface.md)
