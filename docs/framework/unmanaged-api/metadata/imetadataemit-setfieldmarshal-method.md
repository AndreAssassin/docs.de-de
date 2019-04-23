---
title: IMetaDataEmit::SetFieldMarshal-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82675af85f049aeb288b3dcc18f222c0387a37b3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150396"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="4cd19-102">IMetaDataEmit::SetFieldMarshal-Methode</span><span class="sxs-lookup"><span data-stu-id="4cd19-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="4cd19-103">Legt die Marshallinginformationen für den Parameter Feld, Methode zurückgeben, oder eine Methode, die auf die verwiesen wird durch das angegebene Token PInvoke fest.</span><span class="sxs-lookup"><span data-stu-id="4cd19-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cd19-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cd19-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cd19-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cd19-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="4cd19-106">[in] Das Token für die Ziel-Datenelement.</span><span class="sxs-lookup"><span data-stu-id="4cd19-106">[in] The token for target data item.</span></span> <span data-ttu-id="4cd19-107">Dies ist entweder ein `mdFieldDef` oder `mdParamDef` token.</span><span class="sxs-lookup"><span data-stu-id="4cd19-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="4cd19-108">[in] Die Signatur für nicht verwalteten Typ.</span><span class="sxs-lookup"><span data-stu-id="4cd19-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="4cd19-109">[in] Die Anzahl der Bytes im `pvNativeType`.</span><span class="sxs-lookup"><span data-stu-id="4cd19-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4cd19-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4cd19-110">Requirements</span></span>  
 <span data-ttu-id="4cd19-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cd19-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cd19-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4cd19-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cd19-113">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4cd19-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4cd19-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cd19-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd19-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4cd19-115">See also</span></span>

- [<span data-ttu-id="4cd19-116">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cd19-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4cd19-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cd19-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
