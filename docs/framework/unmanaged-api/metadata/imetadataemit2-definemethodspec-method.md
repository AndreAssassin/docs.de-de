---
title: IMetaDataEmit2::DefineMethodSpec-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineMethodSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineMethodSpec
helpviewer_keywords:
- DefineMethodSpec method [.NET Framework metadata]
- IMetaDataEmit2::DefineMethodSpec method [.NET Framework metadata]
ms.assetid: 3c24e552-fc69-4971-b65a-a3e4b5f7f1e8
topic_type:
- apiref
ms.openlocfilehash: 7547d7557169b1279125141afb5b05e22341942a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432744"
---
# <a name="imetadataemit2definemethodspec-method"></a><span data-ttu-id="d5d29-102">IMetaDataEmit2::DefineMethodSpec-Methode</span><span class="sxs-lookup"><span data-stu-id="d5d29-102">IMetaDataEmit2::DefineMethodSpec Method</span></span>
<span data-ttu-id="d5d29-103">Creates a generic instance of a method, and gets a token to the definition.</span><span class="sxs-lookup"><span data-stu-id="d5d29-103">Creates a generic instance of a method, and gets a token to the definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5d29-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d5d29-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMethodSpec (  
    [in]  mdToken           tkParent,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMethodSpec      *pmi  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5d29-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d5d29-105">Parameters</span></span>  
 `tkParent`  
 <span data-ttu-id="d5d29-106">[in] A token for the method of which to create the generic instance.</span><span class="sxs-lookup"><span data-stu-id="d5d29-106">[in] A token for the method of which to create the generic instance.</span></span> <span data-ttu-id="d5d29-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span><span class="sxs-lookup"><span data-stu-id="d5d29-107">The token must be of type `mdMethodDef` or `mdMemberRef`.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="d5d29-108">[in] A pointer to the binary COM+ signature of the method.</span><span class="sxs-lookup"><span data-stu-id="d5d29-108">[in] A pointer to the binary COM+ signature of the method.</span></span>  
  
 `cbSibBlob`  
 <span data-ttu-id="d5d29-109">[in] The size, in bytes, of `pvSigBlob`.</span><span class="sxs-lookup"><span data-stu-id="d5d29-109">[in] The size, in bytes, of `pvSigBlob`.</span></span>  
  
 `pmi`  
 <span data-ttu-id="d5d29-110">[out] A token to the metadata signature definition of the method.</span><span class="sxs-lookup"><span data-stu-id="d5d29-110">[out] A token to the metadata signature definition of the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5d29-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d5d29-111">Requirements</span></span>  
 <span data-ttu-id="d5d29-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d5d29-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5d29-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5d29-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5d29-114">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5d29-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5d29-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5d29-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5d29-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d5d29-116">See also</span></span>

- [<span data-ttu-id="d5d29-117">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5d29-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="d5d29-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d5d29-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
