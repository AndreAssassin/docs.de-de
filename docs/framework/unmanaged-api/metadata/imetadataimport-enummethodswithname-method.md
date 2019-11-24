---
title: IMetaDataImport::EnumMethodsWithName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
ms.openlocfilehash: b0817288040550b5f4c3c4ec063f6a7fdb004137
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450058"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="07f1c-102">IMetaDataImport::EnumMethodsWithName-Methode</span><span class="sxs-lookup"><span data-stu-id="07f1c-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="07f1c-103">Zählt Methoden auf, die den angegebenen Namen aufweisen und durch den Typ definiert sind, auf den durch das angegebene TypeDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="07f1c-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07f1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07f1c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07f1c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="07f1c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="07f1c-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="07f1c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="07f1c-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="07f1c-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="07f1c-108">[in] A TypeDef token representing the type whose methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="07f1c-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="07f1c-109">[in] The name that limits the scope of the enumeration.</span><span class="sxs-lookup"><span data-stu-id="07f1c-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="07f1c-110">[out] The array used to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="07f1c-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="07f1c-111">[in] Die maximale Größe des `rMethods`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="07f1c-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="07f1c-112">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="07f1c-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="07f1c-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07f1c-113">Remarks</span></span>  
 <span data-ttu-id="07f1c-114">This method enumerates fields and methods, but not properties or events.</span><span class="sxs-lookup"><span data-stu-id="07f1c-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="07f1c-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span><span class="sxs-lookup"><span data-stu-id="07f1c-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="07f1c-116">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="07f1c-116">Return Value</span></span>  
  
|<span data-ttu-id="07f1c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="07f1c-117">HRESULT</span></span>|<span data-ttu-id="07f1c-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="07f1c-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="07f1c-119">`EnumMethodsWithName` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="07f1c-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="07f1c-120">There are no tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="07f1c-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="07f1c-121">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="07f1c-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07f1c-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="07f1c-122">Requirements</span></span>  
 <span data-ttu-id="07f1c-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07f1c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07f1c-124">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="07f1c-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07f1c-125">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="07f1c-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07f1c-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07f1c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f1c-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07f1c-127">See also</span></span>

- [<span data-ttu-id="07f1c-128">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07f1c-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="07f1c-129">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="07f1c-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
