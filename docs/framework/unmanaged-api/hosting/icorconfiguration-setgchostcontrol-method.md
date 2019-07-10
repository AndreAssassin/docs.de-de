---
title: ICorConfiguration::SetGCHostControl-Methode
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetGCHostControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetGCHostControl
helpviewer_keywords:
- ICorConfiguration::SetGCHostControl method [.NET Framework hosting]
- SetGCHostControl method [.NET Framework hosting]
ms.assetid: bca6bd79-e288-475a-aa46-6bf81541d966
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a23c2793dce5be459b3aa0f183179c584592c115
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779881"
---
# <a name="icorconfigurationsetgchostcontrol-method"></a><span data-ttu-id="2fd10-102">ICorConfiguration::SetGCHostControl-Methode</span><span class="sxs-lookup"><span data-stu-id="2fd10-102">ICorConfiguration::SetGCHostControl Method</span></span>
<span data-ttu-id="2fd10-103">Legt die Rückrufschnittstelle, die vom Garbage Collector verwendet werden, um den Host zum Ändern der Grenzen des virtuellen Arbeitsspeichers anzufordern.</span><span class="sxs-lookup"><span data-stu-id="2fd10-103">Sets the callback interface to be used by the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fd10-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2fd10-104">Syntax</span></span>  
  
```cpp  
HRESULT SetGCHostControl (  
    [in] IGCHostControl* pGCHostControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fd10-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2fd10-105">Parameters</span></span>  
 `pGCHostControl`  
 <span data-ttu-id="2fd10-106">[in] Ein Zeiger auf ein [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) Objekt, das von der Garbage Collector, den Host zum Ändern der Grenzen des virtuellen Speichers ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="2fd10-106">[in] A pointer to an [IGCHostControl](../../../../docs/framework/unmanaged-api/hosting/igchostcontrol-interface.md) object that allows the garbage collector to request the host to change the limits of virtual memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fd10-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2fd10-107">Requirements</span></span>  
 <span data-ttu-id="2fd10-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fd10-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fd10-109">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2fd10-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2fd10-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2fd10-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2fd10-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fd10-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd10-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fd10-112">See also</span></span>

- [<span data-ttu-id="2fd10-113">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2fd10-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
