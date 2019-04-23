---
title: IMetaDataAssemblyImport::GetAssemblyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4817a62d276bfdb50bfcbf658f40f5568673bea0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59163214"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a><span data-ttu-id="ca807-102">IMetaDataAssemblyImport::GetAssemblyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ca807-102">IMetaDataAssemblyImport::GetAssemblyProps Method</span></span>
<span data-ttu-id="ca807-103">Ruft den Satz von Eigenschaften für die Assembly mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="ca807-103">Gets the set of properties for the assembly with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca807-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ca807-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca807-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ca807-105">Parameters</span></span>  
 `mda`  
 <span data-ttu-id="ca807-106">[in].</span><span class="sxs-lookup"><span data-stu-id="ca807-106">[in].</span></span> <span data-ttu-id="ca807-107">Die `mdAssembly` Metadatentoken, das die Assembly für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="ca807-107">The `mdAssembly` metadata token that represents the assembly for which to get the properties.</span></span>  
  
 `ppbPublicKey`  
 <span data-ttu-id="ca807-108">[out] Ein Zeiger auf den öffentlichen Schlüssel oder das Metadatentoken.</span><span class="sxs-lookup"><span data-stu-id="ca807-108">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKey`  
 <span data-ttu-id="ca807-109">[out] Die Anzahl der Bytes in den zurückgegebenen öffentlichen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="ca807-109">[out] The number of bytes in the returned public key.</span></span>  
  
 `pulHashAlgId`  
 <span data-ttu-id="ca807-110">[out] Ein Zeiger auf den Algorithmus für die Dateien in der Assembly zu hashen.</span><span class="sxs-lookup"><span data-stu-id="ca807-110">[out] A pointer to the algorithm used to hash the files in the assembly.</span></span>  
  
 `szName`  
 <span data-ttu-id="ca807-111">[out] Der einfache Name der Assembly.</span><span class="sxs-lookup"><span data-stu-id="ca807-111">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ca807-112">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="ca807-112">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ca807-113">[out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="ca807-113">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="ca807-114">[out] Ein Zeiger auf ein ASSEMBLYMETADATA-Struktur, die die Metadaten der Assembly an.</span><span class="sxs-lookup"><span data-stu-id="ca807-114">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `pdwAssemblyFlags`  
 <span data-ttu-id="ca807-115">[out] Flags, die auf eine Assembly angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ca807-115">[out] Flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="ca807-116">Dieser Wert ist eine Kombination aus einem oder mehreren [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="ca807-116">This value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca807-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ca807-117">Requirements</span></span>  
 <span data-ttu-id="ca807-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca807-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca807-119">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ca807-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca807-120">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ca807-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca807-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca807-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca807-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ca807-122">See also</span></span>

- [<span data-ttu-id="ca807-123">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ca807-123">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
