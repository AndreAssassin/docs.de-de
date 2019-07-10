---
title: ICorDebugValue::GetSize-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94d8fbf4d93bbfbaaeb7c1268004aada22b9b7df
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768916"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="8daf2-102">ICorDebugValue::GetSize-Methode</span><span class="sxs-lookup"><span data-stu-id="8daf2-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="8daf2-103">Ruft die Größe des dieses "ICorDebugValue"-Objekts in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="8daf2-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8daf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8daf2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8daf2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8daf2-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="8daf2-106">[out] Die Größe des dieses Wertobjekts in Bytes.</span><span class="sxs-lookup"><span data-stu-id="8daf2-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8daf2-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8daf2-107">Remarks</span></span>  
 <span data-ttu-id="8daf2-108">Wenn der Typ des Werts ein Verweistyp ist, gibt diese Methode auf, die Größe des Zeigers, anstatt die Größe des Objekts.</span><span class="sxs-lookup"><span data-stu-id="8daf2-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="8daf2-109">Die `ICorDebugValue::GetSize` Methodenrückgabe `COR_E_OVERFLOW` für Objekte, die größer als 4 GB auf 64-Bit-Plattformen sind.</span><span class="sxs-lookup"><span data-stu-id="8daf2-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="8daf2-110">Verwenden der [icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) Methode stattdessen für Objekte, die größer sind als 4 GB.</span><span class="sxs-lookup"><span data-stu-id="8daf2-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8daf2-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8daf2-111">Requirements</span></span>  
 <span data-ttu-id="8daf2-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8daf2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8daf2-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8daf2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8daf2-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8daf2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8daf2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8daf2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8daf2-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8daf2-116">See also</span></span>

- [<span data-ttu-id="8daf2-117">GetSize64-Methode</span><span class="sxs-lookup"><span data-stu-id="8daf2-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
