---
title: ITypeName::GetNames-Methode
ms.date: 03/30/2017
api_name:
- ITypeName.GetNames
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetNames
helpviewer_keywords:
- ITypeName::GetNames method [.NET Framework hosting]
- GetNames method [.NET Framework hosting]
ms.assetid: e2a3637b-d1e9-4d93-9e9b-0555fbff793d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28076a36880febad20d457ff5a6b290de3d6f173
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121549"
---
# <a name="itypenamegetnames-method"></a><span data-ttu-id="8204b-102">ITypeName::GetNames-Methode</span><span class="sxs-lookup"><span data-stu-id="8204b-102">ITypeName::GetNames Method</span></span>
<span data-ttu-id="8204b-103">Diese Methode unterstützt die .NET Framework-Infrastruktur und ist nicht für eine direkte Verwendung im Code vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8204b-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8204b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8204b-104">Syntax</span></span>  
  
```  
HRESULT GetNames (  
    [in] DWORD           count,  
    [out] BSTR*          rgbszNames,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8204b-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8204b-105">Requirements</span></span>  
 <span data-ttu-id="8204b-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8204b-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8204b-107">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8204b-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8204b-108">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8204b-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="8204b-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="8204b-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8204b-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8204b-110">See also</span></span>

- [<span data-ttu-id="8204b-111">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="8204b-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
