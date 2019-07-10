---
title: ICorDebugProcess5::GetTypeFields-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d413b17da0b6f241f9078bfeb3bd035d4d07a81
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767628"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="3debc-102">ICorDebugProcess5::GetTypeFields-Methode</span><span class="sxs-lookup"><span data-stu-id="3debc-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="3debc-103">Enthält Informationen zu den Feldern, die auf einen Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="3debc-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3debc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3debc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3debc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3debc-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="3debc-106">[in] Der Bezeichner des Typs, dessen Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3debc-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="3debc-107">[in] Die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) -Objekte, deren Feldinformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3debc-107">[in] The number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="3debc-108">[out] Ein Array von [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekte, die Informationen zu den Feldern bereitstellen, die in den Typ gehören.</span><span class="sxs-lookup"><span data-stu-id="3debc-108">[out] An array of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="3debc-109">[out] Ein Zeiger auf die Anzahl der [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) Objekttypen `fields`.</span><span class="sxs-lookup"><span data-stu-id="3debc-109">[out] A pointer to the number of [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3debc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3debc-110">Remarks</span></span>  
 <span data-ttu-id="3debc-111">Die `celt` -Parameter, der die Anzahl von Feldern gibt an, deren Feldinformationen, die die Methode, die zum Auffüllen verwendet `fields`, sollte auf den Wert der entsprechen den `COR_TYPE_LAYOUT::numFields` Feld.</span><span class="sxs-lookup"><span data-stu-id="3debc-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3debc-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3debc-112">Requirements</span></span>  
 <span data-ttu-id="3debc-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3debc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3debc-114">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3debc-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3debc-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3debc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3debc-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3debc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3debc-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3debc-117">See also</span></span>

- [<span data-ttu-id="3debc-118">ICorDebugProcess5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3debc-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="3debc-119">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="3debc-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
