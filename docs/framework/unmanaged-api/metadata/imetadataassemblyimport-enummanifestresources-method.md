---
title: IMetaDataAssemblyImport::EnumManifestResources-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumManifestResources
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumManifestResources
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumManifestResources method [.NET Framework metadata]
- EnumManifestResources method [.NET Framework metadata]
ms.assetid: 9543b111-5705-40c9-935c-a3ffc7a581aa
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7abcb7b69d0f0f2c53cd236c9b4092a94e0f421c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044695"
---
# <a name="imetadataassemblyimportenummanifestresources-method"></a><span data-ttu-id="13ca1-102">IMetaDataAssemblyImport::EnumManifestResources-Methode</span><span class="sxs-lookup"><span data-stu-id="13ca1-102">IMetaDataAssemblyImport::EnumManifestResources Method</span></span>
<span data-ttu-id="13ca1-103">Ruft einen Zeiger auf einen Enumerator für die Ressourcen, die in der aktuellen Assemblymanifest verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13ca1-103">Gets a pointer to an enumerator for the resources referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ca1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13ca1-104">Syntax</span></span>  
  
```  
HRESULT EnumManifestResources (  
    [in, out] HCORENUM         *phEnum,   
    [out] mdManifestResource   rManifestResources[],   
    [in]  ULONG                cMax,   
    [out] ULONG                *pcTokens  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="13ca1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13ca1-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="13ca1-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="13ca1-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="13ca1-107">Dies muss ein NULL-Wert sein Wert fest, wenn die `EnumManifestResources` Methode zum ersten Mal aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="13ca1-107">This must be a null value when the `EnumManifestResources` method is called for the first time.</span></span>  
  
 `rManifestResources`  
 <span data-ttu-id="13ca1-108">[out] Das Array zum Speichern der `mdManifestResource` Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="13ca1-108">[out] The array used to store the `mdManifestResource` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="13ca1-109">[in] Die maximale Anzahl von `mdManifestResource` Token, die in eingefügt werden können `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="13ca1-109">[in] The maximum number of `mdManifestResource` tokens that can be placed in `rManifestResources`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="13ca1-110">[out] Die Anzahl der `mdManifestResource` Token, die tatsächlich in `rManifestResources`.</span><span class="sxs-lookup"><span data-stu-id="13ca1-110">[out] The number of `mdManifestResource` tokens actually placed in `rManifestResources`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13ca1-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="13ca1-111">Return Value</span></span>  
  
|<span data-ttu-id="13ca1-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13ca1-112">HRESULT</span></span>|<span data-ttu-id="13ca1-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13ca1-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="13ca1-114">`EnumManifestResources` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="13ca1-114">`EnumManifestResources` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="13ca1-115">Es gibt keine Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="13ca1-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="13ca1-116">In diesem Fall `pcTokens` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="13ca1-116">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13ca1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13ca1-117">Requirements</span></span>  
 <span data-ttu-id="13ca1-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13ca1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13ca1-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13ca1-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13ca1-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="13ca1-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13ca1-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13ca1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ca1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13ca1-122">See also</span></span>

- [<span data-ttu-id="13ca1-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13ca1-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
