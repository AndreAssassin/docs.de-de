---
title: IMetaDataAssemblyImport::GetFileProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4f3883b0cd1b7aca6265b738eace483c81eb37b9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760140"
---
# <a name="imetadataassemblyimportgetfileprops-method"></a><span data-ttu-id="49aa0-102">IMetaDataAssemblyImport::GetFileProps-Methode</span><span class="sxs-lookup"><span data-stu-id="49aa0-102">IMetaDataAssemblyImport::GetFileProps Method</span></span>
<span data-ttu-id="49aa0-103">Ruft die Eigenschaften der Datei mit der angegebenen Metadaten-Signatur ab.</span><span class="sxs-lookup"><span data-stu-id="49aa0-103">Gets the properties of the file with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49aa0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="49aa0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="49aa0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="49aa0-105">Parameters</span></span>  
 `mdf`  
 <span data-ttu-id="49aa0-106">[in] Die `mdFile` Metadatentoken, das die Datei für das Abrufen der Eigenschaften darstellt.</span><span class="sxs-lookup"><span data-stu-id="49aa0-106">[in] The `mdFile` metadata token that represents the file for which to get the properties.</span></span>  
  
 `szName`  
 <span data-ttu-id="49aa0-107">[out] Der einfache Name der Datei.</span><span class="sxs-lookup"><span data-stu-id="49aa0-107">[out] The simple name of the file.</span></span>  
  
 `cchName`  
 <span data-ttu-id="49aa0-108">[in] Die Größe in Breitzeichen von `szName`.</span><span class="sxs-lookup"><span data-stu-id="49aa0-108">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="49aa0-109">[out] Die Anzahl der tatsächlich zurückgegebenen Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="49aa0-109">[out] The number of wide chars actually returned in `szName`.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="49aa0-110">[out] Ein Zeiger auf den Hashwert.</span><span class="sxs-lookup"><span data-stu-id="49aa0-110">[out] A pointer to the hash value.</span></span> <span data-ttu-id="49aa0-111">Dies ist der Hash, mit dem SHA-1-Algorithmus, der Datei.</span><span class="sxs-lookup"><span data-stu-id="49aa0-111">This is the hash, using the SHA-1 algorithm, of the file.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="49aa0-112">[out] Die Anzahl von Breitzeichen in den zurückgegebenen Hashwert.</span><span class="sxs-lookup"><span data-stu-id="49aa0-112">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwFileFlags`  
 <span data-ttu-id="49aa0-113">[out] Ein Zeiger auf die Flags, die auf eine Datei angewendete Metadaten beschreiben.</span><span class="sxs-lookup"><span data-stu-id="49aa0-113">[out] A pointer to the flags that describe the metadata applied to a file.</span></span> <span data-ttu-id="49aa0-114">Der Wert des Flags ist eine Kombination aus einem oder mehreren [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) Werte.</span><span class="sxs-lookup"><span data-stu-id="49aa0-114">The flags value is a combination of one or more [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49aa0-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="49aa0-115">Requirements</span></span>  
 <span data-ttu-id="49aa0-116">**Plattform:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49aa0-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49aa0-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="49aa0-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="49aa0-118">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="49aa0-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="49aa0-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49aa0-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49aa0-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="49aa0-120">See also</span></span>

- [<span data-ttu-id="49aa0-121">IMetaDataAssemblyImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="49aa0-121">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
