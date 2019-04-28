---
title: GetIdentityAuthority-Funktion
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3090887d3c670b2784b7b40c7d63832715596c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697601"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="bb9d6-102">GetIdentityAuthority-Funktion</span><span class="sxs-lookup"><span data-stu-id="bb9d6-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="bb9d6-103">Ruft einen Zeiger auf ein [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) -Instanz, die Schlüssel für die Codeobjekte verwaltet.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb9d6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb9d6-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb9d6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bb9d6-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="bb9d6-106">[out] Das zurückgegebene `IIdentityAuthority` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="bb9d6-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb9d6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bb9d6-107">Requirements</span></span>  
 <span data-ttu-id="bb9d6-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb9d6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb9d6-109">**Header:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bb9d6-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bb9d6-110">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb9d6-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb9d6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb9d6-111">See also</span></span>

- [<span data-ttu-id="bb9d6-112">IIdentityAuthority-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bb9d6-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="bb9d6-113">Fusion: Globale statistische Funktionen</span><span class="sxs-lookup"><span data-stu-id="bb9d6-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
