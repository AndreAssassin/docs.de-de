---
title: IHostTaskManager::BeginDelayAbort-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginDelayAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginDelayAbort
helpviewer_keywords:
- BeginDelayAbort method [.NET Framework hosting]
- IHostTaskManager::BeginDelayAbort method [.NET Framework hosting]
ms.assetid: 75f42a8b-ed68-4718-a030-a179cfba7d72
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 328462343669b3ea6bed2d86514ea348f6ae2b1e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789532"
---
# <a name="ihosttaskmanagerbegindelayabort-method"></a><span data-ttu-id="4361c-102">IHostTaskManager::BeginDelayAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="4361c-102">IHostTaskManager::BeginDelayAbort Method</span></span>
<span data-ttu-id="4361c-103">Benachrichtigt, dass der Host, der von Code verwaltetem eine Phase eintritt, in dem die aktuelle Aufgabe nicht abgebrochen werden muss.</span><span class="sxs-lookup"><span data-stu-id="4361c-103">Notifies the host that managed code is entering a period in which the current task must not be aborted.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4361c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4361c-104">Syntax</span></span>  
  
```  
HRESULT BeginDelayAbort ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="4361c-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4361c-105">Return Value</span></span>  
  
|<span data-ttu-id="4361c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4361c-106">HRESULT</span></span>|<span data-ttu-id="4361c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4361c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4361c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="4361c-108">S_OK</span></span>|<span data-ttu-id="4361c-109">`BeginDelayAbort` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="4361c-109">`BeginDelayAbort` returned successfully.</span></span>|  
|<span data-ttu-id="4361c-110">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4361c-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4361c-111">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="4361c-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4361c-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4361c-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4361c-113">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4361c-113">The call timed out.</span></span>|  
|<span data-ttu-id="4361c-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4361c-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4361c-115">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="4361c-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4361c-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4361c-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4361c-117">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="4361c-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4361c-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4361c-118">E_FAIL</span></span>|<span data-ttu-id="4361c-119">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="4361c-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4361c-120">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4361c-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4361c-121">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="4361c-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4361c-122">E_UNEXPECTED</span><span class="sxs-lookup"><span data-stu-id="4361c-122">E_UNEXPECTED</span></span>|<span data-ttu-id="4361c-123">`BeginDelayAbort` wurde bereits aufgerufen, aber die zugehörigen Aufruf an [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) wurde noch nicht empfangen.</span><span class="sxs-lookup"><span data-stu-id="4361c-123">`BeginDelayAbort` has already been called, but the corresponding call to [EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md) has not yet been received.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4361c-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4361c-124">Remarks</span></span>  
 <span data-ttu-id="4361c-125">Der Host muss nicht abbrechen, bis die aktuelle Aufgabe `EndDelayAbort` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4361c-125">The host must not abort the current task until `EndDelayAbort` is called.</span></span> <span data-ttu-id="4361c-126">Wenn ein weiterer Aufruf `BeginDelayAbort` erfolgt, ohne einen zwischenzeitlichen Aufruf `EndDelayAbort`, der Host sollte E_UNEXPECTED zurückgegeben von `BeginDelayAbort`, und keine Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="4361c-126">If another call to `BeginDelayAbort` is made without an intervening call to `EndDelayAbort`, the host should return E_UNEXPECTED from `BeginDelayAbort`, and should take no action.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4361c-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4361c-127">Requirements</span></span>  
 <span data-ttu-id="4361c-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4361c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4361c-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4361c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4361c-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4361c-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4361c-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4361c-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4361c-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4361c-132">See also</span></span>

- [<span data-ttu-id="4361c-133">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4361c-133">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="4361c-134">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4361c-134">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="4361c-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4361c-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
