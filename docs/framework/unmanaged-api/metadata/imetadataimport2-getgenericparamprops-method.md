---
title: IMetaDataImport2::GetGenericParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cf9f6cc1e568463f2ca9afa38c10f50d0c247013
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755349"
---
# <a name="imetadataimport2getgenericparamprops-method"></a><span data-ttu-id="d60df-102">IMetaDataImport2::GetGenericParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="d60df-102">IMetaDataImport2::GetGenericParamProps Method</span></span>
<span data-ttu-id="d60df-103">Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d60df-103">Gets the metadata associated with the generic parameter represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d60df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d60df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d60df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d60df-105">Parameters</span></span>  
 `gp`  
 <span data-ttu-id="d60df-106">[in] Das Token, das den generischen Parameter für die zurückzugebenden Metadaten darstellt.</span><span class="sxs-lookup"><span data-stu-id="d60df-106">[in] The token that represents the generic parameter for which to return metadata.</span></span>  
  
 `pulParamSeq`  
 <span data-ttu-id="d60df-107">[out] Die Ordnungsposition der `Type` Parameter in der übergeordneten Konstruktor oder die Methode.</span><span class="sxs-lookup"><span data-stu-id="d60df-107">[out] The ordinal position of the `Type` parameter in the parent constructor or method.</span></span>  
  
 `pdwParamFlags`  
 <span data-ttu-id="d60df-108">[out] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) Enumeration, die beschreibt die `Type` für den generischen Parameter.</span><span class="sxs-lookup"><span data-stu-id="d60df-108">[out] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the `Type` for the generic parameter.</span></span>  
  
 `ptOwner`  
 <span data-ttu-id="d60df-109">[out] Eine TypeDef oder MethodDef-Token, das den Besitzer des Parameters darstellt.</span><span class="sxs-lookup"><span data-stu-id="d60df-109">[out] A TypeDef or MethodDef token that represents the owner of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="d60df-110">[out] Reserviert für zukünftige Erweiterbarkeit.</span><span class="sxs-lookup"><span data-stu-id="d60df-110">[out] Reserved for future extensibility.</span></span>  
  
 `wzName`  
 <span data-ttu-id="d60df-111">[out] Der Name des generischen Parameters.</span><span class="sxs-lookup"><span data-stu-id="d60df-111">[out] The name of the generic parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d60df-112">[in] Die Größe der `wzName` Puffer.</span><span class="sxs-lookup"><span data-stu-id="d60df-112">[in] The size of the `wzName` buffer.</span></span>  
  
 `pchName`  
 <span data-ttu-id="d60df-113">[out] Die zurückgegebene Größe mit dem Namen, in Breitzeichen.</span><span class="sxs-lookup"><span data-stu-id="d60df-113">[out] The returned size of the name, in wide characters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d60df-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d60df-114">Requirements</span></span>  
 <span data-ttu-id="d60df-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d60df-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d60df-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d60df-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d60df-117">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d60df-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d60df-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d60df-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60df-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d60df-119">See also</span></span>

- [<span data-ttu-id="d60df-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d60df-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="d60df-121">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d60df-121">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
