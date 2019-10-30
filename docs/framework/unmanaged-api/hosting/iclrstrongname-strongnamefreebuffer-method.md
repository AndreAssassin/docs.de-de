---
title: ICLRStrongName::StrongNameFreeBuffer-Methode
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameFreeBuffer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameFreeBuffer method [.NET Framework hosting]
ms.assetid: 6148c508-bd1d-4a37-85c3-06ecb09cc857
topic_type:
- apiref
ms.openlocfilehash: e3d0c4791f6d487522ef4bb0ba31ccb6042589c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135111"
---
# <a name="iclrstrongnamestrongnamefreebuffer-method"></a><span data-ttu-id="589c3-102">ICLRStrongName::StrongNameFreeBuffer-Methode</span><span class="sxs-lookup"><span data-stu-id="589c3-102">ICLRStrongName::StrongNameFreeBuffer Method</span></span>
<span data-ttu-id="589c3-103">Gibt Arbeitsspeicher frei, der einem vorherigen Aufruf einer starken Namens Methode zugeordnet wurde, wie z. [b. ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)oder [ICLRStrongName:: StrongNameSignatureGeneration ](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span><span class="sxs-lookup"><span data-stu-id="589c3-103">Frees memory that was allocated with a previous call to a strong name method such as [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md), [ICLRStrongName::StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md), or [ICLRStrongName::StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="589c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="589c3-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="589c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="589c3-105">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="589c3-106">in Ein Zeiger auf den frei verfügbaren Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="589c3-106">[in] A pointer to the memory to free.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="589c3-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="589c3-107">Return Value</span></span>  
 <span data-ttu-id="589c3-108">`S_OK`, wenn die Methode erfolgreich abgeschlossen wurde. andernfalls ein HRESULT-Wert, der einen Fehler angibt (siehe [Allgemeine HRESULT-Werte](https://go.microsoft.com/fwlink/?LinkId=213878) für eine Liste).</span><span class="sxs-lookup"><span data-stu-id="589c3-108">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="589c3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="589c3-109">Requirements</span></span>  
 <span data-ttu-id="589c3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="589c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="589c3-111">**Header:** MetaHost. h</span><span class="sxs-lookup"><span data-stu-id="589c3-111">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="589c3-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="589c3-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="589c3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="589c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589c3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="589c3-114">See also</span></span>

- [<span data-ttu-id="589c3-115">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="589c3-115">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
