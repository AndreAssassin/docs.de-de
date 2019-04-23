---
title: ICorDebugTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum::Next
helpviewer_keywords:
- ICorDebugTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: d0fdeba3-c195-4ece-8caf-79b1f40025d2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d47f14ff2adb37fca16cf6774a2b80cb2e074b17
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157312"
---
# <a name="icordebugtypeenumnext-method"></a><span data-ttu-id="089d0-102">ICorDebugTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="089d0-102">ICorDebugTypeEnum::Next Method</span></span>
<span data-ttu-id="089d0-103">Ruft die Anzahl der "ICorDebugType"-Instanzen, die anhand des `celt` aus der Enumeration, die an der aktuellen Position ab.</span><span class="sxs-lookup"><span data-stu-id="089d0-103">Gets the number of "ICorDebugType" instances specified by `celt` from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="089d0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="089d0-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in]  ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugType *values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="089d0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="089d0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="089d0-106">[in] Die Anzahl der `ICorDebugType` Instanzen abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="089d0-106">[in] The number of `ICorDebugType` instances to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="089d0-107">[out] Ein Array von Zeigern, die jeweils auf eine `ICorDebugType` Objekt.</span><span class="sxs-lookup"><span data-stu-id="089d0-107">[out] An array of pointers, each of which points to an `ICorDebugType` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="089d0-108">[out] Zeiger auf die Anzahl der `ICorDebugType` Instanzen, die tatsächlich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="089d0-108">[out] Pointer to the number of `ICorDebugType` instances actually returned.</span></span> <span data-ttu-id="089d0-109">Dieser Wert kann null sein, wenn `celt` ist.</span><span class="sxs-lookup"><span data-stu-id="089d0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="089d0-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="089d0-110">Requirements</span></span>  
 <span data-ttu-id="089d0-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="089d0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="089d0-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="089d0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="089d0-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="089d0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="089d0-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="089d0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="089d0-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="089d0-115">See also</span></span>
