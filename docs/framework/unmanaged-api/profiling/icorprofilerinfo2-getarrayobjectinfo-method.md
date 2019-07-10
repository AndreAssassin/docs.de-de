---
title: ICorProfilerInfo2::GetArrayObjectInfo-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3ebf8c736cdd1362cae1b1e0b734ce14bea49b18
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67751886"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="58195-102">ICorProfilerInfo2::GetArrayObjectInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="58195-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="58195-103">Ruft detaillierte Informationen zu einem Arrayobjekt.</span><span class="sxs-lookup"><span data-stu-id="58195-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58195-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58195-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58195-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="58195-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="58195-106">[in] Die ID der ein gültiges Array-Objekt.</span><span class="sxs-lookup"><span data-stu-id="58195-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="58195-107">[in] Der Rang (Anzahl der Dimensionen) des Arrays.</span><span class="sxs-lookup"><span data-stu-id="58195-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="58195-108">[out] Ein Array mit ganzen Zahlen, jede die Größe einer Dimension des Arrays darstellt.</span><span class="sxs-lookup"><span data-stu-id="58195-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="58195-109">[out] Ein Array mit ganzen Zahlen, die jeweils die untere darstellen einer Dimension des Arrays gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="58195-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="58195-110">[out] Ein Zeiger auf den unformatierten Puffer für das Array, das entsprechend angeordnet ist die Adresse der C++ Konvention.</span><span class="sxs-lookup"><span data-stu-id="58195-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58195-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58195-111">Remarks</span></span>  
 <span data-ttu-id="58195-112">Die `pDimensionSizes` und `pDimensionLowerBounds` sind parallele Arrays, also die Elemente im gleichen Index in jedem Array Merkmale der gleichen Entität.</span><span class="sxs-lookup"><span data-stu-id="58195-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58195-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58195-113">Requirements</span></span>  
 <span data-ttu-id="58195-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58195-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58195-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58195-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58195-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58195-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58195-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58195-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58195-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58195-118">See also</span></span>

- [<span data-ttu-id="58195-119">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58195-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="58195-120">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="58195-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
