---
title: IGCHost2-Schnittstelle
ms.date: 03/30/2017
api_name:
- IGCHost2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IGCHost2
helpviewer_keywords:
- IGCHost2 interface [.NET Framework hosting]
ms.assetid: e5323fa4-18ac-424d-859d-a65a550d08d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75bef91eb70c8109653741452362cd2e85f625ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59138137"
---
# <a name="igchost2-interface"></a><span data-ttu-id="42431-102">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="42431-102">IGCHost2 Interface</span></span>
<span data-ttu-id="42431-103">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="42431-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="42431-104">Für Neuentwicklungen, wir empfehlen die Verwendung der [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="42431-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="42431-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="42431-105">Methods</span></span>  
  
|<span data-ttu-id="42431-106">Methode</span><span class="sxs-lookup"><span data-stu-id="42431-106">Method</span></span>|<span data-ttu-id="42431-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="42431-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="42431-108">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="42431-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="42431-109">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="42431-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="42431-110">Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="42431-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42431-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="42431-111">Requirements</span></span>  
 <span data-ttu-id="42431-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42431-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42431-113">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="42431-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="42431-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="42431-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="42431-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42431-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42431-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="42431-116">See also</span></span>

- [<span data-ttu-id="42431-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="42431-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="42431-118">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="42431-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="42431-119">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="42431-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
