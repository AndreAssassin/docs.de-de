---
title: ICLRStrongName::StrongNameHashSize-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91b84a980e8a670b8e8b2970cfc96ddd6f4c33b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704075"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="e4d70-102">ICLRStrongName::StrongNameHashSize-Methode</span><span class="sxs-lookup"><span data-stu-id="e4d70-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="e4d70-103">Ruft mit dem angegebenen Hashalgorithmus die Puffergröße ab, die für einen Hash erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="e4d70-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4d70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e4d70-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4d70-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e4d70-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="e4d70-106">[in] Der Hashalgorithmus verwendet, um die Größe des Puffers zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="e4d70-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="e4d70-107">[out] Die Größe des zurückgegebenen Puffers in Bytes.</span><span class="sxs-lookup"><span data-stu-id="e4d70-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4d70-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e4d70-108">Return Value</span></span>  
 <span data-ttu-id="e4d70-109">`S_OK` Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).</span><span class="sxs-lookup"><span data-stu-id="e4d70-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4d70-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e4d70-110">Requirements</span></span>  
 <span data-ttu-id="e4d70-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4d70-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4d70-112">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e4d70-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e4d70-113">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e4d70-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e4d70-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4d70-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4d70-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e4d70-115">See also</span></span>

- [<span data-ttu-id="e4d70-116">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e4d70-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
