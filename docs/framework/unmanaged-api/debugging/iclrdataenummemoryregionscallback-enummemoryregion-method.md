---
title: ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode
ms.date: 03/30/2017
api_name:
- ICLRDataEnumMemoryRegionsCallback.EnumMemoryRegion
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion
helpviewer_keywords:
- EnumMemoryRegion method [.NET Framework debugging]
- ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion method [.NET Framework debugging]
ms.assetid: 9bb93fab-57e8-4f9a-9ef3-1794504fa896
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85b1c5455cb2008a352461d6b506e43fcef48d17
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130922"
---
# <a name="iclrdataenummemoryregionscallbackenummemoryregion-method"></a><span data-ttu-id="5ff82-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion-Methode</span><span class="sxs-lookup"><span data-stu-id="5ff82-102">ICLRDataEnumMemoryRegionsCallback::EnumMemoryRegion Method</span></span>
<span data-ttu-id="5ff82-103">Wird aufgerufen, indem [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) zum Berichten an den Debugger des Ergebnis der Versuch, einen angegebenen Speicherbereich aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="5ff82-103">Called by [ICLRDataEnumMemoryRegions::EnumMemoryRegions](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregions-enummemoryregions-method.md) to report to the debugger the result of an attempt to enumerate a specified region of memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ff82-104">Syntax</span></span>  
  
```  
HRESULT EnumMemoryRegion (  
    [in] CLRDATA_ADDRESS  address,  
    [in] ULONG32          size  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff82-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ff82-105">Parameters</span></span>  
 `address`  
 <span data-ttu-id="5ff82-106">[in] Die Startadresse des Arbeitsspeicherbereichs, die aufgelistet werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ff82-106">[in] The starting address of the memory region that was to be enumerated.</span></span>  
  
 `size`  
 <span data-ttu-id="5ff82-107">[in] Die Größe des Arbeitsspeicherbereichs in Bytes.</span><span class="sxs-lookup"><span data-stu-id="5ff82-107">[in] The size, in bytes, of the memory region.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ff82-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5ff82-108">Remarks</span></span>  
 <span data-ttu-id="5ff82-109">Die `ICLRDataEnumMemoryRegions::EnumMemoryRegions` Methode wird diese Callback-Methode aufrufen, nach jedem Versuch, einen Speicher aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="5ff82-109">The `ICLRDataEnumMemoryRegions::EnumMemoryRegions` method will call this callback method after each attempt to enumerate a memory region.</span></span> <span data-ttu-id="5ff82-110">Die Enumeration wird fortgesetzt, selbst wenn diese Methode einen HRESULT-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5ff82-110">The enumeration will continue even if this method returns an HRESULT indicating failure.</span></span>  
  
 <span data-ttu-id="5ff82-111">Regionen, die von diesem Rückruf gemeldeten können es sich um Duplikate oder überlappende Bereiche sein.</span><span class="sxs-lookup"><span data-stu-id="5ff82-111">Regions reported by this callback may be duplicates or overlapping regions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff82-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ff82-112">Requirements</span></span>  
 <span data-ttu-id="5ff82-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ff82-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff82-114">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="5ff82-114">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5ff82-115">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ff82-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5ff82-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="5ff82-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ff82-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ff82-117">See also</span></span>

- [<span data-ttu-id="5ff82-118">ICLRDataEnumMemoryRegionsCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ff82-118">ICLRDataEnumMemoryRegionsCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdataenummemoryregionscallback-interface.md)
