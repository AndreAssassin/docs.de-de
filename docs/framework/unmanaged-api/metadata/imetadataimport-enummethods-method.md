---
title: IMetaDataImport::EnumMethods-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bab625b8415183b9cf90c35cba140c4d28095805
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59076873"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="35cd4-102">IMetaDataImport::EnumMethods-Methode</span><span class="sxs-lookup"><span data-stu-id="35cd4-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="35cd4-103">Zählt MethodDef-Token auf, die Methoden des angegebenen Typs darstellen.</span><span class="sxs-lookup"><span data-stu-id="35cd4-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35cd4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="35cd4-104">Syntax</span></span>  
  
```  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35cd4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="35cd4-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="35cd4-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="35cd4-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="35cd4-107">Dies muss NULL sein, für den ersten Aufruf dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="35cd4-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="35cd4-108">[in] Eine TypeDef-Token, das mit den Methoden zum Aufzählen der Typ darstellt.</span><span class="sxs-lookup"><span data-stu-id="35cd4-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="35cd4-109">[out] Das Array zum Speichern der MethodDef-Token.</span><span class="sxs-lookup"><span data-stu-id="35cd4-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35cd4-110">[in] Die maximale Größe der MethodDef `rMethods` Array.</span><span class="sxs-lookup"><span data-stu-id="35cd4-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="35cd4-111">[out] Die Anzahl der zurückgegebenen MethodDef-Token `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="35cd4-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35cd4-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="35cd4-112">Return Value</span></span>  
  
|<span data-ttu-id="35cd4-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35cd4-113">HRESULT</span></span>|<span data-ttu-id="35cd4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="35cd4-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="35cd4-115">`EnumMethods` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="35cd4-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="35cd4-116">Es sind keine MethodDef-Token aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="35cd4-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="35cd4-117">In diesem Fall `pcTokens` ist 0 (null).</span><span class="sxs-lookup"><span data-stu-id="35cd4-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="35cd4-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="35cd4-118">Requirements</span></span>  
 <span data-ttu-id="35cd4-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35cd4-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35cd4-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="35cd4-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35cd4-121">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="35cd4-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35cd4-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35cd4-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35cd4-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="35cd4-123">See also</span></span>

- [<span data-ttu-id="35cd4-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35cd4-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="35cd4-125">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="35cd4-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
