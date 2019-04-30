---
title: IGCHostControl::RequestVirtualMemLimit-Methode
ms.date: 03/30/2017
api_name:
- IGCHostControl.RequestVirtualMemLimit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RequestVirtualMemLimit
helpviewer_keywords:
- IGCHostControl::RequestVirtualMemLimit method [.NET Framework hosting]
- RequestVirtualMemLimit method [.NET Framework hosting]
ms.assetid: f4984a8c-4c0e-4460-9aa1-d022b3621228
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 948b18832ccfc5e0fc2e42ee58e6444a581de260
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61968271"
---
# <a name="igchostcontrolrequestvirtualmemlimit-method"></a><span data-ttu-id="690fa-102">IGCHostControl::RequestVirtualMemLimit-Methode</span><span class="sxs-lookup"><span data-stu-id="690fa-102">IGCHostControl::RequestVirtualMemLimit Method</span></span>
<span data-ttu-id="690fa-103">Fordert den Host zum Ändern der Grenzen des virtuellen Speichers an.</span><span class="sxs-lookup"><span data-stu-id="690fa-103">Requests the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="690fa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="690fa-104">Syntax</span></span>  
  
```  
HRESULT RequestVirtualMemLimit (  
    [in] SIZE_T       sztMaxVirtualMemMB,  
    [in, out] SIZE_T* psztNewMaxVirtualMemMB  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="690fa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="690fa-105">Parameters</span></span>  
 `sztMaxVirtualMemMB`  
 <span data-ttu-id="690fa-106">[in] Die angeforderte Größe des Arbeitsspeichers, die zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="690fa-106">[in] The requested size of memory to be allocated.</span></span>  
  
 `psztNewMaxVirtualMemMB`  
 <span data-ttu-id="690fa-107">[in, out] Ein Zeiger auf die tatsächliche Größe des belegten Arbeitsspeichers.</span><span class="sxs-lookup"><span data-stu-id="690fa-107">[in, out] A pointer to the actual size of memory allocated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="690fa-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="690fa-108">Requirements</span></span>  
 <span data-ttu-id="690fa-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="690fa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="690fa-110">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="690fa-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="690fa-111">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="690fa-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="690fa-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="690fa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="690fa-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="690fa-113">See also</span></span>

- [<span data-ttu-id="690fa-114">IGCHostControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="690fa-114">IGCHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md)
