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
ms.openlocfilehash: 4432b17e5d9aa875d8346b3329cd618e15222040
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771020"
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="291c3-102">IAssemblyCache::CreateAssemblyCacheItem-Methode</span><span class="sxs-lookup"><span data-stu-id="291c3-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="291c3-103">Ruft einen Verweis auf ein neues [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="291c3-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="291c3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="291c3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="291c3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="291c3-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="291c3-106">[in] Flags, die in Fusion.idl definiert sind.</span><span class="sxs-lookup"><span data-stu-id="291c3-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="291c3-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="291c3-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="291c3-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0 X 00000001)</span><span class="sxs-lookup"><span data-stu-id="291c3-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
- <span data-ttu-id="291c3-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span><span class="sxs-lookup"><span data-stu-id="291c3-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="291c3-110">[in] Für zukünftige Erweiterungen reserviert.</span><span class="sxs-lookup"><span data-stu-id="291c3-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="291c3-111">`pvReserved` ein null-Verweis muss sein.</span><span class="sxs-lookup"><span data-stu-id="291c3-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="291c3-112">[out] Das zurückgegebene `IAssemblyCacheItem` Zeiger.</span><span class="sxs-lookup"><span data-stu-id="291c3-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="291c3-113">[in, optional] Uncanonicalized, durch Trennzeichen getrennte `name=value` Paare.</span><span class="sxs-lookup"><span data-stu-id="291c3-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="291c3-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="291c3-114">Requirements</span></span>  
 <span data-ttu-id="291c3-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="291c3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="291c3-116">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="291c3-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="291c3-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="291c3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="291c3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="291c3-118">See also</span></span>

- [<span data-ttu-id="291c3-119">IAssemblyCache-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="291c3-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [<span data-ttu-id="291c3-120">IAssemblyCacheItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="291c3-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
