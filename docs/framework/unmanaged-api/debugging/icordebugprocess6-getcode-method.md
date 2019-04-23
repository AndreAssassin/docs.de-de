---
title: ICorDebugProcess6::GetCode-Methode
ms.date: 03/30/2017
ms.assetid: faa538c2-60c9-4064-b996-1b4c24ebd751
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7349a20da35eb0b87894440026a0974d49ae2aa0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097290"
---
# <a name="icordebugprocess6getcode-method"></a><span data-ttu-id="70fb7-102">ICorDebugProcess6::GetCode-Methode</span><span class="sxs-lookup"><span data-stu-id="70fb7-102">ICorDebugProcess6::GetCode Method</span></span>
<span data-ttu-id="70fb7-103">Ruft Informationen über den verwalteten Code an einer bestimmten Codeadresse ab.</span><span class="sxs-lookup"><span data-stu-id="70fb7-103">Gets information about the managed code at a particular code address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70fb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="70fb7-104">Syntax</span></span>  
  
```  
HRESULT GetCode(  
    [in] CORDB_ADDRESS codeAddress,   
    [out] ICorDebugCode **ppCode);  
```  
  
## <a name="parameters"></a><span data-ttu-id="70fb7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="70fb7-105">Parameters</span></span>  
 `codeAddress`  
 <span data-ttu-id="70fb7-106">[in] Ein [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) Wert, der die Startadresse des verwalteten Codesegments angibt.</span><span class="sxs-lookup"><span data-stu-id="70fb7-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that specifies the starting address of the managed code segment.</span></span>  
  
 `ppCode`  
 <span data-ttu-id="70fb7-107">[out] Ein Zeiger auf die Adresse ein "ICorDebugCode"-Objekt, das ein Segment von verwaltetem Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="70fb7-107">[out] A pointer to the address of an "ICorDebugCode" object that represents a segment of managed code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="70fb7-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="70fb7-108">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="70fb7-109">Diese Methode ist nur mit .NET Native verfügbar.</span><span class="sxs-lookup"><span data-stu-id="70fb7-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="70fb7-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="70fb7-110">Requirements</span></span>  
 <span data-ttu-id="70fb7-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="70fb7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70fb7-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="70fb7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="70fb7-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="70fb7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="70fb7-114">**.NET Framework-Versionen:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="70fb7-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="70fb7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="70fb7-115">See also</span></span>

- [<span data-ttu-id="70fb7-116">ICorDebugProcess6-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="70fb7-116">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="70fb7-117">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="70fb7-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
