---
title: ICorDebugEval2::NewParameterizedArray-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedArray
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedArray
helpviewer_keywords:
- ICorDebugEval2::NewParameterizedArray method [.NET Framework debugging]
- NewParameterizedArray method [.NET Framework debugging]
ms.assetid: 45efb8ba-c4de-4109-945f-e734d376b43c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 973f975885bbbf5cbed74adef7b9f4f423c42583
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753653"
---
# <a name="icordebugeval2newparameterizedarray-method"></a><span data-ttu-id="94a3b-102">ICorDebugEval2::NewParameterizedArray-Methode</span><span class="sxs-lookup"><span data-stu-id="94a3b-102">ICorDebugEval2::NewParameterizedArray Method</span></span>
<span data-ttu-id="94a3b-103">Ordnet ein neues Array mit den angegebenen Elementtyp und Dimensionen an.</span><span class="sxs-lookup"><span data-stu-id="94a3b-103">Allocates a new array of the specified element type and dimensions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94a3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94a3b-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedArray(  
    [in] ICorDebugType          *pElementType,  
    [in] ULONG32                rank,  
    [in, size_is(rank)] ULONG32 dims[],  
    [in, size_is(rank)] ULONG32 lowBounds[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94a3b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94a3b-105">Parameters</span></span>  
 `pElementType`  
 <span data-ttu-id="94a3b-106">[in] Ein Zeiger auf ein ICorDebugType-Objekt, das den Typ des im Array gespeicherten Elements darstellt.</span><span class="sxs-lookup"><span data-stu-id="94a3b-106">[in] A pointer to an ICorDebugType object that represents the type of element stored in the array.</span></span>  
  
 `rank`  
 <span data-ttu-id="94a3b-107">[in] Die Anzahl der Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="94a3b-107">[in] The number of dimensions of the array.</span></span> <span data-ttu-id="94a3b-108">In .NET Framework, Version 2.0 muss dieser Wert als 1 sein.</span><span class="sxs-lookup"><span data-stu-id="94a3b-108">In the .NET Framework version 2.0, this value must be 1.</span></span>  
  
 `dims`  
 <span data-ttu-id="94a3b-109">[in] Die Größe der einzelnen Dimensionen des Arrays in Bytes.</span><span class="sxs-lookup"><span data-stu-id="94a3b-109">[in] The size, in bytes, of each dimension of the array.</span></span>  
  
 `lowBounds`  
 <span data-ttu-id="94a3b-110">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="94a3b-110">[in] Optional.</span></span> <span data-ttu-id="94a3b-111">Die untere Grenze der einzelnen Dimensionen des Arrays.</span><span class="sxs-lookup"><span data-stu-id="94a3b-111">The lower bound of each dimension of the array.</span></span> <span data-ttu-id="94a3b-112">Wenn dieser Wert ausgelassen wird, wird eine Untergrenze von 0 (null) für jede Dimension ausgegangen.</span><span class="sxs-lookup"><span data-stu-id="94a3b-112">If this value is omitted, a lower bound of zero is assumed for each dimension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94a3b-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="94a3b-113">Remarks</span></span>  
 <span data-ttu-id="94a3b-114">Die Elemente des Arrays können es sich um Instanzen eines generischen Typs sein.</span><span class="sxs-lookup"><span data-stu-id="94a3b-114">The elements of the array may be instances of a generic type.</span></span> <span data-ttu-id="94a3b-115">Das Array wird immer in der Anwendungsdomäne erstellt, in dem der Thread gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="94a3b-115">The array is always created in the application domain in which the thread is currently running.</span></span> <span data-ttu-id="94a3b-116">In .NET Framework 2.0, den Wert der `rank` muss 1 sein.</span><span class="sxs-lookup"><span data-stu-id="94a3b-116">In the .NET Framework 2.0, the value of `rank` must be 1.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94a3b-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94a3b-117">Requirements</span></span>  
 <span data-ttu-id="94a3b-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94a3b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94a3b-119">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94a3b-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94a3b-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94a3b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94a3b-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94a3b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
