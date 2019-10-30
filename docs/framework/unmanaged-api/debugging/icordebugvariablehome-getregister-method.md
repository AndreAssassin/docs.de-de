---
title: 'Icordebugvariablehome:: getregiester-Methode'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetRegister
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetRegister
helpviewer_keywords:
- ICorDebugVariableHome::GetRegister method [.NET Framework debugging]
- GetRegister method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: a5eecd7b-b04c-4266-bff2-7c8771d519a8
topic_type:
- apiref
ms.openlocfilehash: 4c9932c3eeebd0101ee364c9b4d0b0a26862c4b1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125071"
---
# <a name="icordebugvariablehomegetregister-method"></a><span data-ttu-id="0d43b-102">Icordebugvariablehome:: getregiester-Methode</span><span class="sxs-lookup"><span data-stu-id="0d43b-102">ICorDebugVariableHome::GetRegister Method</span></span>
<span data-ttu-id="0d43b-103">Ruft das Register ab, das eine Variable mit dem Speicherorttyp `VLT_REGISTER`enthält, und das Basisregister für eine Variable mit dem Speicherorttyp `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="0d43b-103">Gets the register that contains a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d43b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0d43b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegister(  
    [out] CorDebugRegister *pRegister  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0d43b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0d43b-105">Parameters</span></span>  
 `pRegister`  
 <span data-ttu-id="0d43b-106">vorgenommen Ein CorDebugRegister-Enumerationswert, der das Register für eine Variable mit dem Speicherorttyp `VLT_REGISTER`angibt, und das Basisregister für eine Variable mit dem Speicherort `VLT_REGISTER_RELATIVE`.</span><span class="sxs-lookup"><span data-stu-id="0d43b-106">[out] A CorDebugRegister enumeration value  that indicates the register for a variable with a location type of `VLT_REGISTER`, and the base register for a variable with a location type of `VLT_REGISTER_RELATIVE`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0d43b-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="0d43b-107">Return Value</span></span>  
 <span data-ttu-id="0d43b-108">Die-Methode gibt die folgenden Werte zurück:</span><span class="sxs-lookup"><span data-stu-id="0d43b-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="0d43b-109">Wert</span><span class="sxs-lookup"><span data-stu-id="0d43b-109">Value</span></span>|<span data-ttu-id="0d43b-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0d43b-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="0d43b-111">Die Variable befindet sich in dem durch das `pRegister`-Argument aufgeführten Register.</span><span class="sxs-lookup"><span data-stu-id="0d43b-111">The variable is in the register indicated by the `pRegister` argument.</span></span>|  
|`E_FAIL`|<span data-ttu-id="0d43b-112">Die Variable befindet sich nicht in einem Registrierungs Speicherort oder in einem Register relativen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="0d43b-112">The variable is not in a register or a register-relative location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0d43b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0d43b-113">Requirements</span></span>  
 <span data-ttu-id="0d43b-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d43b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d43b-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0d43b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0d43b-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d43b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d43b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d43b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d43b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0d43b-118">See also</span></span>

- [<span data-ttu-id="0d43b-119">VariableLocationType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0d43b-119">VariableLocationType Enumeration</span></span>](../../../../docs/framework/unmanaged-api/debugging/variablelocationtype-enumeration.md)
- [<span data-ttu-id="0d43b-120">ICorDebugVariableHome-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0d43b-120">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
