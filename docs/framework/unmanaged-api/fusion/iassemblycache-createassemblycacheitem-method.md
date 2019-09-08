---
title: IAssemblyCache::CreateAssemblyCacheItem-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyCache.CreateAssemblyCacheItem
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 215eb3a508a746230d36fdda3e8ba992287be62c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796831"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="900a6-102">IAssemblyCache::CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="900a6-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="900a6-103">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](iassemblycacheitem-interface.md) -Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="900a6-103">Gets a reference to a new [IAssemblyCacheItem](iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="900a6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="900a6-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="900a6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="900a6-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="900a6-106">in In Fusion. idl definierte Flags.</span><span class="sxs-lookup"><span data-stu-id="900a6-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="900a6-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="900a6-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="900a6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span><span class="sxs-lookup"><span data-stu-id="900a6-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="900a6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="900a6-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="900a6-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="900a6-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="900a6-111">`pvReserved`muss ein NULL-Verweis sein.</span><span class="sxs-lookup"><span data-stu-id="900a6-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="900a6-112">vorgenommen Der zurück `IAssemblyCacheItem` gegebene Zeiger.</span><span class="sxs-lookup"><span data-stu-id="900a6-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="900a6-113">[in, optional] Nicht kanonisierte, durch Trennzeichen `name=value` getrennte Paare.</span><span class="sxs-lookup"><span data-stu-id="900a6-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="900a6-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="900a6-114">Requirements</span></span>  
 <span data-ttu-id="900a6-115">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="900a6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="900a6-116">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="900a6-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="900a6-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="900a6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="900a6-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="900a6-118">See also</span></span>

- [<span data-ttu-id="900a6-119">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="900a6-119">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
- [<span data-ttu-id="900a6-120">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="900a6-120">IAssemblyCacheItem Interface</span></span>](iassemblycacheitem-interface.md)
