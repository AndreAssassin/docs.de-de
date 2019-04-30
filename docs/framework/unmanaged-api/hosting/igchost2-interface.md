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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946106"
---
# <a name="igchost2-interface"></a><span data-ttu-id="242f4-102">IGCHost2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="242f4-102">IGCHost2 Interface</span></span>
<span data-ttu-id="242f4-103">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="242f4-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="242f4-104">Für Neuentwicklungen, wir empfehlen die Verwendung der [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="242f4-104">For new development, we recommend that you use the [ICLRGCManager2](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-interface.md) interface instead.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="242f4-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="242f4-105">Methods</span></span>  
  
|<span data-ttu-id="242f4-106">Methode</span><span class="sxs-lookup"><span data-stu-id="242f4-106">Method</span></span>|<span data-ttu-id="242f4-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="242f4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="242f4-108">SetGCStartupLimitsEx-Methode</span><span class="sxs-lookup"><span data-stu-id="242f4-108">SetGCStartupLimitsEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md)|<span data-ttu-id="242f4-109">Legt die Größe des Segments und die maximale Größe für Generation 0 fest.</span><span class="sxs-lookup"><span data-stu-id="242f4-109">Sets the segment size and the maximum size for generation 0.</span></span> <span data-ttu-id="242f4-110">Ermöglicht die Generation 0 und größer als Größe der Segmente `DWORD`.</span><span class="sxs-lookup"><span data-stu-id="242f4-110">Enables generation 0 and segment sizes larger than `DWORD`.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="242f4-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="242f4-111">Requirements</span></span>  
 <span data-ttu-id="242f4-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="242f4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="242f4-113">**Header:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="242f4-113">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="242f4-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="242f4-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="242f4-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="242f4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="242f4-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="242f4-116">See also</span></span>

- [<span data-ttu-id="242f4-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="242f4-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="242f4-118">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="242f4-118">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="242f4-119">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="242f4-119">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
