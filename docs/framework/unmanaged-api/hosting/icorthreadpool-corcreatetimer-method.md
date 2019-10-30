---
title: ICorThreadpool::CorCreateTimer-Methode
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorCreateTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorCreateTimer
helpviewer_keywords:
- CorCreateTimer method [.NET Framework hosting]
- ICorThreadpool::CorCreateTimer method [.NET Framework hosting]
ms.assetid: 0d56ef25-30f1-4499-8a1f-76e7654ec614
topic_type:
- apiref
ms.openlocfilehash: 17afd0922930bc6db122e8dc07125dcafd483cf5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133311"
---
# <a name="icorthreadpoolcorcreatetimer-method"></a><span data-ttu-id="8af08-102">ICorThreadpool::CorCreateTimer-Methode</span><span class="sxs-lookup"><span data-stu-id="8af08-102">ICorThreadpool::CorCreateTimer Method</span></span>
<span data-ttu-id="8af08-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8af08-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af08-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8af08-104">Syntax</span></span>  
  
```cpp  
HRESULT CorCreateTimer (  
    [in]  HANDLE*             phNewTimer,  
    [in]  WAITORTIMERCALLBACK Callback,  
    [in]  PVOID               Parameter,  
    [in]  DWORD               DueTime,  
    [in]  DWORD               Period,  
    [out] BOOL*               result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8af08-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8af08-105">Requirements</span></span>  
 <span data-ttu-id="8af08-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af08-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af08-107">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="8af08-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af08-108">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8af08-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af08-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8af08-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af08-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8af08-110">See also</span></span>

- [<span data-ttu-id="8af08-111">ICorThreadpool-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8af08-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
