---
title: IMetaDataEmit::DefineParam-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 86711d107636505ab7aa23f0f72f70bd3e27635d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167771"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="25ba7-102">IMetaDataEmit::DefineParam-Methode</span><span class="sxs-lookup"><span data-stu-id="25ba7-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="25ba7-103">Erstellt eine Parameterdefinition mit der angegebenen Signatur für die Methode auf, die durch das angegebene Token verwiesen wird und ruft ein Token für diese Parameterdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="25ba7-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ba7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="25ba7-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="25ba7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="25ba7-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="25ba7-106">[in] Das Token für die Methode, deren Parameter definiert wird.</span><span class="sxs-lookup"><span data-stu-id="25ba7-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="25ba7-107">[in] Die Sequenznummer des Parameters.</span><span class="sxs-lookup"><span data-stu-id="25ba7-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="25ba7-108">[in] Der Name des Parameters im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="25ba7-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="25ba7-109">[in] Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="25ba7-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="25ba7-110">Dies ist eine Bitmaske der `CorParamAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="25ba7-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="25ba7-111">[in] `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="25ba7-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="25ba7-112">[in] Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="25ba7-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="25ba7-113">[in] Die Größe in Unicode-Zeichen von `pValue`.</span><span class="sxs-lookup"><span data-stu-id="25ba7-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="25ba7-114">[out] Die `mdParamDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="25ba7-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="25ba7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25ba7-115">Remarks</span></span>  
 <span data-ttu-id="25ba7-116">Die Sequenzwerte `ulParamSeq` beginnen mit 1 für Parameter.</span><span class="sxs-lookup"><span data-stu-id="25ba7-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="25ba7-117">Ein Wert zurückgegeben hat eine Sequenznummer 0.</span><span class="sxs-lookup"><span data-stu-id="25ba7-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ba7-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="25ba7-118">Requirements</span></span>  
 <span data-ttu-id="25ba7-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25ba7-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ba7-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="25ba7-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="25ba7-121">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="25ba7-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="25ba7-122">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="25ba7-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="25ba7-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25ba7-123">See also</span></span>

- [<span data-ttu-id="25ba7-124">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25ba7-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="25ba7-125">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="25ba7-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
