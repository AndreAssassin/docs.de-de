---
title: IMetaDataEmit::DefineTypeDef-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0777151d10149ec7311a7761bc7f6bff5ba98e0e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777490"
---
# <a name="imetadataemitdefinetypedef-method"></a><span data-ttu-id="522de-102">IMetaDataEmit::DefineTypeDef-Methode</span><span class="sxs-lookup"><span data-stu-id="522de-102">IMetaDataEmit::DefineTypeDef Method</span></span>
<span data-ttu-id="522de-103">Erstellt eine Typdefinition für einen Typ der common Language Runtime und ruft ein Metadatentoken für diese Typdefinition.</span><span class="sxs-lookup"><span data-stu-id="522de-103">Creates a type definition for a common language runtime type, and gets a metadata token for that type definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="522de-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="522de-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="522de-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="522de-105">Parameters</span></span>  
 `szTypeDef`  
 <span data-ttu-id="522de-106">[in] Der Name des Typs im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="522de-106">[in] The name of the type in Unicode.</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="522de-107">[in] `TypeDef` Attribute.</span><span class="sxs-lookup"><span data-stu-id="522de-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="522de-108">Dies ist eine Bitmaske der `CoreTypeAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="522de-108">This is a bitmask of `CoreTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="522de-109">[in] Das Token der Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="522de-109">[in] The token of the base class.</span></span> <span data-ttu-id="522de-110">Es muss entweder eine `mdTypeDef` oder `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="522de-110">It must be either an `mdTypeDef` or an `mdTypeRef` token.</span></span>  
  
 `rtkImplements`  
 <span data-ttu-id="522de-111">[in] Ein Array von Token, die die Schnittstellen, die diese Klasse oder Schnittstelle implementiert angeben.</span><span class="sxs-lookup"><span data-stu-id="522de-111">[in] An array of tokens specifying the interfaces that this class or interface implements.</span></span>  
  
 `ptd`  
 <span data-ttu-id="522de-112">[out] Die `mdTypeDef` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="522de-112">[out] The `mdTypeDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="522de-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="522de-113">Remarks</span></span>  
 <span data-ttu-id="522de-114">Ein Flag in `dwTypeDefFlags` angibt, ob der erstellte Typ wird ein common Type System Verweistyp (Klasse oder Schnittstelle) oder ein common Type System-Werttyp ist.</span><span class="sxs-lookup"><span data-stu-id="522de-114">A flag in `dwTypeDefFlags` specifies whether the type being created is a common type system reference type (class or interface) or a common type system value type.</span></span>  
  
 <span data-ttu-id="522de-115">Je nach den angegebenen Parametern kann diese Methode eine nebenerscheinung erstellt auch möglicherweise eine `mdInterfaceImpl` Datensatz für jede Schnittstelle, die von diesem Typ implementiert oder geerbt.</span><span class="sxs-lookup"><span data-stu-id="522de-115">Depending on the parameters supplied, this method, as a side effect, may also create an `mdInterfaceImpl` record for each interface that is inherited or implemented by this type.</span></span> <span data-ttu-id="522de-116">Aber diese Methode gibt nicht zurück um eines dieser `mdInterfaceImpl` Token.</span><span class="sxs-lookup"><span data-stu-id="522de-116">However, this method does not return any of these `mdInterfaceImpl` tokens.</span></span> <span data-ttu-id="522de-117">Wenn ein Client zum später hinzufügen oder ändern möchte ein `mdInterfaceImpl` token ist, darf Sie verwenden die `IMetaDataImport` Schnittstelle, um diese aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="522de-117">If a client wants to later add or modify an `mdInterfaceImpl` token, it must use the `IMetaDataImport` interface to enumerate them.</span></span> <span data-ttu-id="522de-118">Wenn Sie COM-Semantik der verwenden möchten die `[default]` -Schnittstelle, sollten Sie die Standard-Schnittstelle bereitstellen, als das erste Element im `rtkImplements`; ein benutzerdefiniertes Attribut für die Klasse festgelegt wird, dass die Klasse eine Standardschnittstelle angegeben (der wird immer als die zuerst `mdInterfaceImpl` Token für die Klasse deklariert).</span><span class="sxs-lookup"><span data-stu-id="522de-118">If you want to use COM semantics of the `[default]` interface, you should supply the default interface as the first element in `rtkImplements`; a custom attribute set on the class will indicate that the class has a default interface (which is always assumed to be the first `mdInterfaceImpl` token declared for the class).</span></span>  
  
 <span data-ttu-id="522de-119">Jedes Element der `rtkImplements` Arrays enthält ein `mdTypeDef` oder `mdTypeRef` token.</span><span class="sxs-lookup"><span data-stu-id="522de-119">Each element of the `rtkImplements` array holds an `mdTypeDef` or `mdTypeRef` token.</span></span> <span data-ttu-id="522de-120">Das letzte Element im Array muss `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="522de-120">The last element in the array must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="522de-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="522de-121">Requirements</span></span>  
 <span data-ttu-id="522de-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="522de-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="522de-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="522de-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="522de-124">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="522de-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="522de-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="522de-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="522de-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="522de-126">See also</span></span>

- [<span data-ttu-id="522de-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="522de-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="522de-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="522de-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
