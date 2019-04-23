---
title: IHostSecurityContext-Schnittstelle
ms.date: 03/30/2017
api_name:
- IHostSecurityContext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityContext
helpviewer_keywords:
- IHostSecurityContext interface [.NET Framework hosting]
ms.assetid: 88e2eac0-8ccb-404f-abbc-287d55159842
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d71b7e1265110a70329377ce8ab7430e1943c49
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59124025"
---
# <a name="ihostsecuritycontext-interface"></a><span data-ttu-id="99ffc-102">IHostSecurityContext-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99ffc-102">IHostSecurityContext Interface</span></span>
<span data-ttu-id="99ffc-103">Ermöglicht die common Language Runtime (CLR), die Informationen vom Host implementierte Kontext beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="99ffc-103">Allows the common language runtime (CLR) to maintain security context information implemented by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="99ffc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="99ffc-104">Methods</span></span>  
  
|<span data-ttu-id="99ffc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="99ffc-105">Method</span></span>|<span data-ttu-id="99ffc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99ffc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="99ffc-107">Capture-Methode</span><span class="sxs-lookup"><span data-stu-id="99ffc-107">Capture Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-capture-method.md)|<span data-ttu-id="99ffc-108">Ruft einen Klon der `IHostSecurityContext` Instanz zurückgegeben, von einem Aufruf von [IHostSecurityManager:: GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span><span class="sxs-lookup"><span data-stu-id="99ffc-108">Gets a clone of the `IHostSecurityContext` instance returned from a call to [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="99ffc-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="99ffc-109">Remarks</span></span>  
 <span data-ttu-id="99ffc-110">Ein Host kann alle Codezugriff auf Threadtoken von der CLR und die Benutzer Code steuern.</span><span class="sxs-lookup"><span data-stu-id="99ffc-110">A host can control all code access to thread tokens by both the CLR and user code.</span></span> <span data-ttu-id="99ffc-111">Sie können auch sicherstellen, dass vollständige Informationen über asynchrone Vorgänge oder Codepunkte mit eingeschränktem Codezugriff übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="99ffc-111">It can also ensure that complete security context information is passed across asynchronous operations or code points with restricted code access.</span></span> <span data-ttu-id="99ffc-112">`IHostSecurityContext` kapselt dieses Sicherheitskontextinformationen, die für die Laufzeit nicht transparent ist.</span><span class="sxs-lookup"><span data-stu-id="99ffc-112">`IHostSecurityContext` encapsulates this security context information, which is opaque to the runtime.</span></span> <span data-ttu-id="99ffc-113">Die Laufzeit erfasst diese Informationen mithilfe `Capture`, und verschiebt ihn für Threadpool Worker Element Dispatch, Modul und jeder Klasse Konstruktoren und Finalizerausführung.</span><span class="sxs-lookup"><span data-stu-id="99ffc-113">The runtime captures this information using `Capture`, and moves it across thread pool worker item dispatch, finalizer execution, and module and class constructors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99ffc-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99ffc-114">Requirements</span></span>  
 <span data-ttu-id="99ffc-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99ffc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99ffc-116">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="99ffc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="99ffc-117">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99ffc-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99ffc-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99ffc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99ffc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99ffc-119">See also</span></span>

- [<span data-ttu-id="99ffc-120">ICLRHostProtectionManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99ffc-120">ICLRHostProtectionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [<span data-ttu-id="99ffc-121">IHostSecurityManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="99ffc-121">IHostSecurityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [<span data-ttu-id="99ffc-122">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99ffc-122">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
