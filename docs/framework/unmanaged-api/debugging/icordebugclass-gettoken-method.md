---
title: ICorDebugClass::GetToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetToken
helpviewer_keywords:
- GetToken method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetToken method [.NET Framework debugging]
ms.assetid: ee5c848a-eac4-4462-b07a-07ccd76a75df
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4f33bb15a351be5fe8318dcc3339d429dec039e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750761"
---
# <a name="icordebugclassgettoken-method"></a><span data-ttu-id="f0900-102">ICorDebugClass::GetToken-Methode</span><span class="sxs-lookup"><span data-stu-id="f0900-102">ICorDebugClass::GetToken Method</span></span>
<span data-ttu-id="f0900-103">Ruft die `TypeDef` Metadatentoken, das die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="f0900-103">Gets the `TypeDef` metadata token that references the definition of this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0900-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0900-104">Syntax</span></span>  
  
```  
HRESULT GetToken (  
    [out] mdTypeDef          *pTypeDef  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0900-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0900-105">Parameters</span></span>  
 `pTypeDef`  
 <span data-ttu-id="f0900-106">[out] Ein Zeiger auf ein `mdTypeDef` Token, das die Definition dieser Klasse verweist.</span><span class="sxs-lookup"><span data-stu-id="f0900-106">[out] A pointer to an `mdTypeDef` token that references the definition of this class.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0900-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0900-107">Requirements</span></span>  
 <span data-ttu-id="f0900-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0900-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0900-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0900-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0900-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0900-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0900-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0900-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0900-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0900-112">See also</span></span>

- [<span data-ttu-id="f0900-113">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="f0900-113">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
