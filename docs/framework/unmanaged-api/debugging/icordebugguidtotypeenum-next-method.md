---
title: ICorDebugGuidToTypeEnum::Next-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 160ddbf9be8eb9f3b99d159aa8b36a22b58a9f55
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025811"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="9f280-102">ICorDebugGuidToTypeEnum::Next-Methode</span><span class="sxs-lookup"><span data-stu-id="9f280-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="9f280-103">Ruft die angegebene Anzahl von [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Instanzen, die GUIDs, die Typinformationen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="9f280-103">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f280-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f280-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f280-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9f280-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9f280-106">[in] Die Anzahl der auf den Typ GUID Zuordnen von Objekten abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9f280-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="9f280-107">[out] Ein Array von Zeigern, die jeweils auf eine [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) Objekt, eine Windows-Runtime-GUID mit der entsprechenden ICorDebugType-Objekt zugeordnet, ist.</span><span class="sxs-lookup"><span data-stu-id="9f280-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9f280-108">[out] Ein Zeiger auf die Anzahl der [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) tatsächlich zurückgegebenen Objekte `values`.</span><span class="sxs-lookup"><span data-stu-id="9f280-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9f280-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f280-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f280-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9f280-110">Requirements</span></span>  
 <span data-ttu-id="9f280-111">**Plattformen:** Windows-Runtime</span><span class="sxs-lookup"><span data-stu-id="9f280-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="9f280-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9f280-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9f280-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9f280-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9f280-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f280-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f280-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f280-115">See also</span></span>

- [<span data-ttu-id="9f280-116">ICorDebugGuidToTypeEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9f280-116">ICorDebugGuidToTypeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="9f280-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9f280-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
