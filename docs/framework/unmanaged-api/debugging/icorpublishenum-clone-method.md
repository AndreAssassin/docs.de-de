---
title: ICorPublishEnum::Clone-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Clone
helpviewer_keywords:
- Clone method, ICorPublishEnum interface [.NET Framework debugging]
- ICorPublishEnum::Clone method [.NET Framework debugging]
ms.assetid: c9a26ea3-b8eb-4b8e-854f-9a2ca26b3b39
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e0ce1d8c0074f62d35e16465b368269e233a713b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105130"
---
# <a name="icorpublishenumclone-method"></a><span data-ttu-id="3a8ea-102">ICorPublishEnum::Clone-Methode</span><span class="sxs-lookup"><span data-stu-id="3a8ea-102">ICorPublishEnum::Clone Method</span></span>
<span data-ttu-id="3a8ea-103">Erstellt eine Kopie dieses [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="3a8ea-103">Creates a copy of this [ICorPublishEnum](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8ea-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a8ea-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorPublishEnum   **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a8ea-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a8ea-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="3a8ea-106">[out] Ein Zeiger auf die Adresse einer `ICorPublishEnum` Objekt, das eine Kopie dieses `ICorPublishEnum` Objekt.</span><span class="sxs-lookup"><span data-stu-id="3a8ea-106">[out] A pointer to the address of an `ICorPublishEnum` object that is a copy of this `ICorPublishEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a8ea-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a8ea-107">Requirements</span></span>  
 <span data-ttu-id="3a8ea-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a8ea-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8ea-109">**Header:** CorPub.idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3a8ea-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3a8ea-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a8ea-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a8ea-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8ea-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8ea-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a8ea-112">See also</span></span>

- [<span data-ttu-id="3a8ea-113">ICorPublishEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a8ea-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
