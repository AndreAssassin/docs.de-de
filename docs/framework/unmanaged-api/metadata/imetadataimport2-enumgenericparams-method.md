---
title: IMetaDataImport2::EnumGenericParams-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.EnumGenericParams
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::EnumGenericParams
helpviewer_keywords:
- EnumGenericParams method [.NET Framework metadata]
- IMetaDataImport2::EnumGenericParams method [.NET Framework metadata]
ms.assetid: b50488a5-3cf0-483c-82dc-2892a3ec61ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7edd2eeafcce6a22c3256d0684a9c4f961b34002
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157637"
---
# <a name="imetadataimport2enumgenericparams-method"></a><span data-ttu-id="e67bf-102">IMetaDataImport2::EnumGenericParams-Methode</span><span class="sxs-lookup"><span data-stu-id="e67bf-102">IMetaDataImport2::EnumGenericParams Method</span></span>
<span data-ttu-id="e67bf-103">Ruft einen Enumerator für ein Array von generischen Parameter-Token mit dem angegebenen TypeDef oder MethodDef verknüpften token.</span><span class="sxs-lookup"><span data-stu-id="e67bf-103">Gets an enumerator for an array of generic parameter tokens associated with the specified TypeDef or MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e67bf-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e67bf-104">Syntax</span></span>  
  
```  
HRESULT EnumGenericParams (  
   [in, out] HCORENUM     *phEnum,   
   [in]  mdToken          tk,  
   [out] mdGenericParam   rGenericParams[],   
   [in]  ULONG            cMax,   
   [out] ULONG            *pcGenericParams  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e67bf-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e67bf-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="e67bf-106">[in, out] Ein Zeiger auf den Enumerator.</span><span class="sxs-lookup"><span data-stu-id="e67bf-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `tk`  
 <span data-ttu-id="e67bf-107">[in] Das TypeDef oder MethodDef-Token, dessen generischen Parametern werden aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e67bf-107">[in] The TypeDef or MethodDef token whose generic parameters are to be enumerated.</span></span>  
  
 `rGenericParams`  
 <span data-ttu-id="e67bf-108">[out] Das Array der generischen Parameter aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="e67bf-108">[out] The array of generic parameters to enumerate.</span></span>  
  
 `cMax`  
 <span data-ttu-id="e67bf-109">[in] Die angeforderte maximale Anzahl von Token in platzieren `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="e67bf-109">[in] The requested maximum number of tokens to place in `rGenericParams`.</span></span>  
  
 `pcGenericParams`  
 <span data-ttu-id="e67bf-110">[out] Die zurückgegebene Anzahl von Token in platziert `rGenericParams`.</span><span class="sxs-lookup"><span data-stu-id="e67bf-110">[out] The returned number of tokens placed in `rGenericParams`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e67bf-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e67bf-111">Return Value</span></span>  
  
|<span data-ttu-id="e67bf-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e67bf-112">HRESULT</span></span>|<span data-ttu-id="e67bf-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e67bf-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumGenericParams` <span data-ttu-id="e67bf-114">wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e67bf-114">returned successfully.</span></span>|  
|`S_FALSE`|`phEnum` <span data-ttu-id="e67bf-115">enthält keine Memberelemente.</span><span class="sxs-lookup"><span data-stu-id="e67bf-115">has no member elements.</span></span> <span data-ttu-id="e67bf-116">In diesem Fall `pcGenericParams` auf 0 (null) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e67bf-116">In this case, `pcGenericParams` is set to 0 (zero).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e67bf-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e67bf-117">Requirements</span></span>  
 <span data-ttu-id="e67bf-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e67bf-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e67bf-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e67bf-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e67bf-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="e67bf-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e67bf-121">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e67bf-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e67bf-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e67bf-122">See also</span></span>

- [<span data-ttu-id="e67bf-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e67bf-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="e67bf-124">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e67bf-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
