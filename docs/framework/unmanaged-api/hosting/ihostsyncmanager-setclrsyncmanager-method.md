---
title: IHostSyncManager::SetCLRSyncManager-Methode
ms.date: 03/30/2017
api_name:
- IHostSyncManager.SetCLRSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::SetCLRSyncManager
helpviewer_keywords:
- IHostSyncManager::SetCLRSyncManager method [.NET Framework hosting]
- SetCLRSyncManager method [.NET Framework hosting]
ms.assetid: 2b8bbe76-a45d-4989-bacb-11df42f8798c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5006e171e2d5bbdd0d9d4a484299b1860c079b3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59105793"
---
# <a name="ihostsyncmanagersetclrsyncmanager-method"></a><span data-ttu-id="08c34-102">IHostSyncManager::SetCLRSyncManager-Methode</span><span class="sxs-lookup"><span data-stu-id="08c34-102">IHostSyncManager::SetCLRSyncManager Method</span></span>
<span data-ttu-id="08c34-103">Legt die [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Instanz für die die aktuelle Zuweisung [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="08c34-103">Sets the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instance to associate with the current [IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08c34-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="08c34-104">Syntax</span></span>  
  
```  
HRESULT SetCLRSyncManager (  
    [in] ICLRSyncManager *pManager  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="08c34-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="08c34-105">Parameters</span></span>  
 `pManager`  
 <span data-ttu-id="08c34-106">[in] Ein Zeiger auf ein `ICLRSyncManager` Instanz, die von der common Language Runtime (CLR) bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="08c34-106">[in] A pointer to an `ICLRSyncManager` instance supplied by the common language runtime (CLR).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="08c34-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="08c34-107">Return Value</span></span>  
  
|<span data-ttu-id="08c34-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="08c34-108">HRESULT</span></span>|<span data-ttu-id="08c34-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08c34-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="08c34-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="08c34-110">S_OK</span></span>|<span data-ttu-id="08c34-111">`SetCLRSyncManager` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="08c34-111">`SetCLRSyncManager` returned successfully.</span></span>|  
|<span data-ttu-id="08c34-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="08c34-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="08c34-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="08c34-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="08c34-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="08c34-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="08c34-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08c34-115">The call timed out.</span></span>|  
|<span data-ttu-id="08c34-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="08c34-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="08c34-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="08c34-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="08c34-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="08c34-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="08c34-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="08c34-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="08c34-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="08c34-120">E_FAIL</span></span>|<span data-ttu-id="08c34-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="08c34-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="08c34-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="08c34-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="08c34-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="08c34-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="08c34-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="08c34-124">Remarks</span></span>  
 <span data-ttu-id="08c34-125">Um die Kommunikation zwischen dem Host und der CLR zu erleichtern, treten Hostingschnittstellen generell in Paaren.</span><span class="sxs-lookup"><span data-stu-id="08c34-125">To facilitate communication between the host and the CLR, hosting interfaces generally come in pairs.</span></span> <span data-ttu-id="08c34-126">Ein Element des Paars wird vom Host implementiert, und das andere Element wird von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="08c34-126">One member of the pair is implemented by the host, and the other member is implemented by the CLR.</span></span> <span data-ttu-id="08c34-127">Als hostseitige-Implementierung die `IHostSyncManager` Schnittstelle entspricht der `ICLRSyncManager` Schnittstelle, die von der CLR implementiert.</span><span class="sxs-lookup"><span data-stu-id="08c34-127">As a host-side implementation, the `IHostSyncManager` interface corresponds to the `ICLRSyncManager` interface implemented by the CLR.</span></span> <span data-ttu-id="08c34-128">Die CLR ruft `SetCLRSyncManager` angeben einer `ICLRSyncManager` -Instanz für den Host mit dem aktuellen zuordnen `IHostSyncManager` Instanz.</span><span class="sxs-lookup"><span data-stu-id="08c34-128">The CLR calls `SetCLRSyncManager` to supply an `ICLRSyncManager` instance for the host to associate with the current `IHostSyncManager` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08c34-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="08c34-129">Requirements</span></span>  
 <span data-ttu-id="08c34-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08c34-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08c34-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="08c34-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="08c34-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="08c34-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="08c34-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08c34-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c34-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="08c34-134">See also</span></span>

- [<span data-ttu-id="08c34-135">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08c34-135">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [<span data-ttu-id="08c34-136">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="08c34-136">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
