---
title: IInstallReferenceItem::GetReference-Methode
ms.date: 03/30/2017
api_name:
- IInstallReferenceItem.GetReference
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IInstallReferenceItem::GetReference
helpviewer_keywords:
- IInstallReferenceItem::GetReference method [.NET Framework fusion]
- GetReference method [.NET Framework fusion]
ms.assetid: 8960332f-c98a-405a-ba92-7003de0c1187
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cd0a554535122b81f5812102c7951f56b294796a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213362"
---
# <a name="iinstallreferenceitemgetreference-method"></a><span data-ttu-id="7911f-102">IInstallReferenceItem::GetReference-Methode</span><span class="sxs-lookup"><span data-stu-id="7911f-102">IInstallReferenceItem::GetReference Method</span></span>
<span data-ttu-id="7911f-103">Ruft einen Zeiger auf die [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) dargestellt durch diese Struktur [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="7911f-103">Gets a pointer to the [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure represented by this [IInstallReferenceItem](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7911f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7911f-104">Syntax</span></span>  
  
```  
HRESULT GetReference (  
    [out] LPFUSION_INSTALL_REFERENCE *ppRefData,  
    [in]  DWORD dwFlags,  
    [in]  LPVOID pvReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7911f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7911f-105">Parameters</span></span>  
 `ppRefData`  
 <span data-ttu-id="7911f-106">[out] Das zurückgegebene `FUSION_INSTALL_REFERENCE` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="7911f-106">[out] The returned `FUSION_INSTALL_REFERENCE` pointer.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7911f-107">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="7911f-107">[in] Reserved for future extensibility.</span></span> `dwFlags` <span data-ttu-id="7911f-108">0 (null) muss sein.</span><span class="sxs-lookup"><span data-stu-id="7911f-108">must be 0 (zero).</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="7911f-109">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="7911f-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="7911f-110">ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="7911f-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7911f-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7911f-111">Requirements</span></span>  
 <span data-ttu-id="7911f-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7911f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7911f-113">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7911f-113">**Header:** Fusion.h</span></span>  
  
 **<span data-ttu-id="7911f-114">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7911f-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7911f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7911f-115">See also</span></span>

- [<span data-ttu-id="7911f-116">IInstallReferenceItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7911f-116">IInstallReferenceItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceitem-interface.md)
- [<span data-ttu-id="7911f-117">FUSION_INSTALL_REFERENCE-Struktur</span><span class="sxs-lookup"><span data-stu-id="7911f-117">FUSION_INSTALL_REFERENCE Structure</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md)
