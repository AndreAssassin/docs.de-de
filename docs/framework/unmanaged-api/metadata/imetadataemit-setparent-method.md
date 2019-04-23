---
title: IMetaDataEmit::SetParent-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParent
helpviewer_keywords:
- SetParent method [.NET Framework metadata]
- IMetaDataEmit::SetParent method [.NET Framework metadata]
ms.assetid: 02a02ff7-ae0e-4692-a20e-372405f23052
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fe27d8a0508a13c1f54eef00d5119bec4daec4a7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59140438"
---
# <a name="imetadataemitsetparent-method"></a><span data-ttu-id="ebd67-102">IMetaDataEmit::SetParent-Methode</span><span class="sxs-lookup"><span data-stu-id="ebd67-102">IMetaDataEmit::SetParent Method</span></span>
<span data-ttu-id="ebd67-103">Erstellt, durch die das angegebene Element gemäß Definition durch einen vorherigen Aufruf von [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), ein Mitglied über den angegebenen Typ ist, gemäß einem vorherigen Aufruf von [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="ebd67-103">Establishes that the specified member, as defined by a prior call to [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md), is a member of the specified type, as defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebd67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ebd67-104">Syntax</span></span>  
  
```  
HRESULT SetParent (   
    [in]  mdMemberRef mr,   
    [in]  mdToken     tk   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebd67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ebd67-105">Parameters</span></span>  
 `mr`  
 <span data-ttu-id="ebd67-106">[in] Die `mdMemberRef` Token um ein neues übergeordnetes Element zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ebd67-106">[in] The `mdMemberRef` token to receive a new parent.</span></span>  
  
 `tk`  
 <span data-ttu-id="ebd67-107">[in] Die `mdToken` für das neue übergeordnete Element.</span><span class="sxs-lookup"><span data-stu-id="ebd67-107">[in] The `mdToken` for the new parent.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebd67-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ebd67-108">Requirements</span></span>  
 <span data-ttu-id="ebd67-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebd67-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebd67-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ebd67-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ebd67-111">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ebd67-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ebd67-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebd67-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebd67-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebd67-113">See also</span></span>

- [<span data-ttu-id="ebd67-114">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebd67-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="ebd67-115">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ebd67-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
