---
title: IMetaDataTables2::GetMetaDataStreamInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStreamInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStreamInfo
helpviewer_keywords:
- GetMetaDataStreamInfo method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStreamInfo method [.NET Framework metadata]
ms.assetid: 8b280627-cc74-4789-95da-1fefc966de05
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f70187ba9bd71225162e6e10184e4992b5600f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59228847"
---
# <a name="imetadatatables2getmetadatastreaminfo-method"></a><span data-ttu-id="2ba25-102">IMetaDataTables2::GetMetaDataStreamInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="2ba25-102">IMetaDataTables2::GetMetaDataStreamInfo Method</span></span>
<span data-ttu-id="2ba25-103">Ruft ab, der Name, Größe und Inhalt des Metadatenstreams am angegebenen Index.</span><span class="sxs-lookup"><span data-stu-id="2ba25-103">Gets the name, size, and contents of the metadata stream at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2ba25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2ba25-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStreamInfo (  
   [in]  ULONG        ix,  
   [out] const char   **ppchName,  
   [out] const void   **ppv,  
   [out] ULONG        *pcb  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2ba25-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2ba25-105">Parameters</span></span>  
 `ix`  
 <span data-ttu-id="2ba25-106">[in] Der Index des angeforderten Metadatenstreams.</span><span class="sxs-lookup"><span data-stu-id="2ba25-106">[in] The index of the requested metadata stream.</span></span>  
  
 `ppchName`  
 <span data-ttu-id="2ba25-107">[out] Ein Zeiger auf den Namen des Datenstroms.</span><span class="sxs-lookup"><span data-stu-id="2ba25-107">[out] A pointer to the name of the stream.</span></span>  
  
 `ppv`  
 <span data-ttu-id="2ba25-108">[out] Ein Zeiger auf die Metadaten-Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="2ba25-108">[out] A pointer to the metadata stream.</span></span>  
  
 `pcb`  
 <span data-ttu-id="2ba25-109">[out] Die Größe in Bytes, des `ppv`.</span><span class="sxs-lookup"><span data-stu-id="2ba25-109">[out] The size, in bytes, of `ppv`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2ba25-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2ba25-110">Requirements</span></span>  
 <span data-ttu-id="2ba25-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2ba25-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2ba25-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2ba25-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2ba25-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2ba25-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2ba25-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2ba25-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2ba25-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2ba25-115">See also</span></span>

- [<span data-ttu-id="2ba25-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ba25-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="2ba25-117">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2ba25-117">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
