---
title: ICLRTask::LocksHeld-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.LocksHeld
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::LocksHeld
helpviewer_keywords:
- LocksHeld method [.NET Framework hosting]
- ICLRTask::LocksHeld method [.NET Framework hosting]
ms.assetid: e88a4dc3-02cc-4703-a474-292b71c40657
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f548d8b19a76aaccbae276dd63f091e4488690b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763554"
---
# <a name="iclrtasklocksheld-method"></a><span data-ttu-id="532b1-102">ICLRTask::LocksHeld-Methode</span><span class="sxs-lookup"><span data-stu-id="532b1-102">ICLRTask::LocksHeld Method</span></span>
<span data-ttu-id="532b1-103">Ruft die Anzahl der Sperren für den Task ab.</span><span class="sxs-lookup"><span data-stu-id="532b1-103">Gets the number of locks currently held on the task.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="532b1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="532b1-104">Syntax</span></span>  
  
```  
HRESULT LocksHeld (  
    [out] SIZE_T *pLockCount  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="532b1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="532b1-105">Parameters</span></span>  
 `pLockCount`  
 <span data-ttu-id="532b1-106">[out] Die Anzahl der aufrechterhaltenen Sperren auf die Aufgabe zum Zeitpunkt des Methodenaufrufs.</span><span class="sxs-lookup"><span data-stu-id="532b1-106">[out] The number of locks held on the task at the time of the method call.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="532b1-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="532b1-107">Return Value</span></span>  
  
|<span data-ttu-id="532b1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="532b1-108">HRESULT</span></span>|<span data-ttu-id="532b1-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="532b1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="532b1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="532b1-110">S_OK</span></span>|<span data-ttu-id="532b1-111">`LocksHeld` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="532b1-111">`LocksHeld` returned successfully.</span></span>|  
|<span data-ttu-id="532b1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="532b1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="532b1-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="532b1-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="532b1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="532b1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="532b1-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="532b1-115">The call timed out.</span></span>|  
|<span data-ttu-id="532b1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="532b1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="532b1-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="532b1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="532b1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="532b1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="532b1-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="532b1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="532b1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="532b1-120">E_FAIL</span></span>|<span data-ttu-id="532b1-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="532b1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="532b1-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="532b1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="532b1-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="532b1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="532b1-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="532b1-124">Requirements</span></span>  
 <span data-ttu-id="532b1-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="532b1-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="532b1-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="532b1-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="532b1-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="532b1-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="532b1-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="532b1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="532b1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="532b1-129">See also</span></span>

- [<span data-ttu-id="532b1-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="532b1-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="532b1-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="532b1-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="532b1-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="532b1-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="532b1-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="532b1-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
