---
title: ICLRMetadataLocator::GetMetadata-Methode
ms.date: 03/30/2017
api_name:
- ICLRMetadataLocator.GetMetadata
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRMetadataLocator::GetMetadata
helpviewer_keywords:
- GetMetadata method, ICLRMetadataLocator interface [.NET Framework debugging]
- ICLRMetadataLocator::GetMetadata method [.NET Framework debugging]
ms.assetid: 704a8893-ac56-43b4-90ea-715f38ccb40e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e677aefd5420f71867c1f11a2c9408c77d305c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697835"
---
# <a name="iclrmetadatalocatorgetmetadata-method"></a><span data-ttu-id="1aae8-102">ICLRMetadataLocator::GetMetadata-Methode</span><span class="sxs-lookup"><span data-stu-id="1aae8-102">ICLRMetadataLocator::GetMetadata Method</span></span>
<span data-ttu-id="1aae8-103">Wird aufgerufen, von der common Language Runtime (CLR) Daten Access Services zum Abrufen der Metadaten eines Bilds.</span><span class="sxs-lookup"><span data-stu-id="1aae8-103">Called by the common language runtime (CLR) data access services to retrieve the metadata of an image.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1aae8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1aae8-104">Syntax</span></span>  
  
```  
HRESULT GetMetadata(  
    [in]  LPCWSTR         imagePath,  
    [in]  ULONG32         imageTimestamp,  
    [in]  ULONG32         imageSize,  
    [in]  GUID*           mvid,  
    [in]  ULONG32         mdRva,  
    [in]  ULONG32         flags,  
    [in]  ULONG32         bufferSize,  
    [out, size_is(bufferSize), length_is(*dataSize)]  
          BYTE*           buffer,  
    [out] ULONG32*        dataSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1aae8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1aae8-105">Parameters</span></span>  
 `imagePath`  
 <span data-ttu-id="1aae8-106">[in] Eine Zeichenfolge, die den Pfad der Bilddatei angibt.</span><span class="sxs-lookup"><span data-stu-id="1aae8-106">[in] A string that specifies the path of the image file.</span></span>  
  
 `imageTimestamp`  
 <span data-ttu-id="1aae8-107">[in] Der Zeitstempel der Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="1aae8-107">[in] The time stamp of the image file.</span></span>  
  
 `imageSize`  
 <span data-ttu-id="1aae8-108">[in] Die Größe der Bilddatei.</span><span class="sxs-lookup"><span data-stu-id="1aae8-108">[in] The size of the image file.</span></span>  
  
 `mvid`  
 <span data-ttu-id="1aae8-109">[in] Der global eindeutige Bezeichner des Bilds.</span><span class="sxs-lookup"><span data-stu-id="1aae8-109">[in] The globally unique identifier of the image.</span></span>  
  
 `mdRva`  
 <span data-ttu-id="1aae8-110">[in] Die relative virtuelle Adresse (RVA) der Metadaten.</span><span class="sxs-lookup"><span data-stu-id="1aae8-110">[in] The relative virtual address (RVA) of the metadata.</span></span> <span data-ttu-id="1aae8-111">Die Adresse ist relativ zur Basisadresse Abbilds.</span><span class="sxs-lookup"><span data-stu-id="1aae8-111">The address is relative to the image base address.</span></span>  
  
 `flags`  
 <span data-ttu-id="1aae8-112">[in] Für die zukünftige Verwendung reserviert.</span><span class="sxs-lookup"><span data-stu-id="1aae8-112">[in] Reserved for future use.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="1aae8-113">[in] Die Größe des Puffers, in dem die Metadaten zu platzieren.</span><span class="sxs-lookup"><span data-stu-id="1aae8-113">[in] The size of the buffer in which to place the metadata.</span></span>  
  
 `buffer`  
 <span data-ttu-id="1aae8-114">[out] Der Puffer, in dem die Metadaten gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1aae8-114">[out] The buffer in which to place the metadata.</span></span>  
  
 `dataSize`  
 <span data-ttu-id="1aae8-115">[out] Die Größe der Metadaten, die zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1aae8-115">[out] The size of the metadata that is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1aae8-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1aae8-116">Remarks</span></span>  
 <span data-ttu-id="1aae8-117">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="1aae8-117">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1aae8-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1aae8-118">Requirements</span></span>  
 <span data-ttu-id="1aae8-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1aae8-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1aae8-120">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="1aae8-120">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="1aae8-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1aae8-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1aae8-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1aae8-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1aae8-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1aae8-123">See also</span></span>

- [<span data-ttu-id="1aae8-124">ICLRMetadataLocator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1aae8-124">ICLRMetadataLocator Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrmetadatalocator-interface.md)
