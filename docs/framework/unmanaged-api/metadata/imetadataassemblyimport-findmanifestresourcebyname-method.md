---
title: IMetaDataAssemblyImport::FindManifestResourceByName-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bf61da362251577acadb83915404eba7508b3099
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905062"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a><span data-ttu-id="c44a6-102">IMetaDataAssemblyImport::FindManifestResourceByName-Methode</span><span class="sxs-lookup"><span data-stu-id="c44a6-102">IMetaDataAssemblyImport::FindManifestResourceByName Method</span></span>
<span data-ttu-id="c44a6-103">Ruft einen Zeiger auf die Manifestressource mit dem angegebenen Namen ab.</span><span class="sxs-lookup"><span data-stu-id="c44a6-103">Gets a pointer to the manifest resource with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c44a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c44a6-104">Syntax</span></span>  
  
```  
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,   
    [out] mdManifestResource     *ptkManifestResource  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="c44a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c44a6-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c44a6-106">[in] Der Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="c44a6-106">[in] The name of the resource.</span></span>  
  
 `ptkManifestResource`  
 <span data-ttu-id="c44a6-107">[out] Das Array zum Speichern der `mdManifestResource` Metadatentoken verwendet, von denen jede eine Manifestressource darstellt.</span><span class="sxs-lookup"><span data-stu-id="c44a6-107">[out] The array used to store the `mdManifestResource` metadata tokens, each of which represents a manifest resource.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c44a6-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c44a6-108">Remarks</span></span>  
 <span data-ttu-id="c44a6-109">Die `FindManifestResourceByName` -Methode verwendet die Standardregeln, die von der common Language Runtime zum Auflösen von verweisen.</span><span class="sxs-lookup"><span data-stu-id="c44a6-109">The `FindManifestResourceByName` method uses the standard rules employed by the common language runtime for resolving references.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c44a6-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c44a6-110">Requirements</span></span>  
 <span data-ttu-id="c44a6-111">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c44a6-111">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c44a6-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c44a6-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c44a6-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c44a6-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c44a6-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c44a6-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c44a6-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c44a6-115">See also</span></span>

- [<span data-ttu-id="c44a6-116">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c44a6-116">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="c44a6-117">So sucht Common Language Runtime nach Assemblys</span><span class="sxs-lookup"><span data-stu-id="c44a6-117">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
