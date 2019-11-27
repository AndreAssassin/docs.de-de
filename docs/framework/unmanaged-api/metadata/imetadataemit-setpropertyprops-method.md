---
title: IMetaDataEmit::SetPropertyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: 0fdec87324d6efa0f911e37573093c19b93c0349
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440550"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="302ec-102">IMetaDataEmit::SetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="302ec-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="302ec-103">Legt die in den Metadaten gespeicherten Features für eine Eigenschaft fest, die durch einen vorherigen-Befehl der [DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)definiert wird.</span><span class="sxs-lookup"><span data-stu-id="302ec-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="302ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="302ec-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="302ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="302ec-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="302ec-106">in Das Token für die Eigenschaft, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="302ec-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="302ec-107">in Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="302ec-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="302ec-108">in Der Typ des Standardwerts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="302ec-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="302ec-109">in Der Standardwert für die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="302ec-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="302ec-110">in Die Anzahl von (Unicode-) Zeichen in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="302ec-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="302ec-111">in Die Methode, die den Eigenschafts Wert festlegt.</span><span class="sxs-lookup"><span data-stu-id="302ec-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="302ec-112">in Die Methode, die den Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="302ec-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="302ec-113">in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="302ec-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="302ec-114">Beenden Sie dieses Array mit einem `mdTokenNil`-Token.</span><span class="sxs-lookup"><span data-stu-id="302ec-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="302ec-115">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="302ec-115">Requirements</span></span>  
 <span data-ttu-id="302ec-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="302ec-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="302ec-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="302ec-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="302ec-118">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="302ec-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="302ec-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="302ec-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="302ec-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="302ec-120">See also</span></span>

- [<span data-ttu-id="302ec-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="302ec-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="302ec-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="302ec-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
