---
title: IHostTaskManager::GetCurrentTask-Methode
ms.date: 03/30/2017
api_name:
- IHostTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: f17bca49-90bd-4dee-a5e1-b9a57ea46f85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2436288e2f2f241cab15b16abf4df99c73caec25
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789414"
---
# <a name="ihosttaskmanagergetcurrenttask-method"></a><span data-ttu-id="ede73-102">IHostTaskManager::GetCurrentTask-Methode</span><span class="sxs-lookup"><span data-stu-id="ede73-102">IHostTaskManager::GetCurrentTask Method</span></span>
<span data-ttu-id="ede73-103">Ruft einen Schnittstellenzeiger auf die Aufgabe, die derzeit für den Betriebssystem-Thread ausgeführt wird, von dem dieser Aufruf erfolgt.</span><span class="sxs-lookup"><span data-stu-id="ede73-103">Gets an interface pointer to the task that is currently executing on the operating system thread from which this call is made.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ede73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ede73-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentTask (  
    [out] IHostTask **pTask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ede73-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ede73-105">Parameters</span></span>  
 `pTask`  
 <span data-ttu-id="ede73-106">[out] Ein Zeiger auf die Adresse einer [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) -Instanz, der aktuell ausgeführten Aufgabe oder Null, darstellt, wenn keine Aufgabe derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ede73-106">[out] A pointer to the address of an [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance that represents the currently executing task, or null, if no task is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ede73-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ede73-107">Return Value</span></span>  
  
|<span data-ttu-id="ede73-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ede73-108">HRESULT</span></span>|<span data-ttu-id="ede73-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ede73-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ede73-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ede73-110">S_OK</span></span>|<span data-ttu-id="ede73-111">`GetCurrentTask` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ede73-111">`GetCurrentTask` returned successfully.</span></span>|  
|<span data-ttu-id="ede73-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ede73-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ede73-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="ede73-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ede73-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ede73-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ede73-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ede73-115">The call timed out.</span></span>|  
|<span data-ttu-id="ede73-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ede73-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ede73-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="ede73-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ede73-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ede73-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ede73-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="ede73-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ede73-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ede73-120">E_FAIL</span></span>|<span data-ttu-id="ede73-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="ede73-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ede73-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ede73-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ede73-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="ede73-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ede73-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="ede73-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="ede73-125">`GetCurrentTask` wurde ein Betriebssystemthread außerhalb der Kontrolle des Hosts aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="ede73-125">`GetCurrentTask` was called on an operating system thread outside the control of the host.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ede73-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ede73-126">Remarks</span></span>  
 <span data-ttu-id="ede73-127">Der Host kann auch festlegen, die `pTask` Parameter auf null, um zu verhindern, dass eine Aufgabe, die sie nicht initiiert haben in der CLR.</span><span class="sxs-lookup"><span data-stu-id="ede73-127">The host can also set the `pTask` parameter to null to prevent a task that it did not initiate from entering the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ede73-128">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ede73-128">Requirements</span></span>  
 <span data-ttu-id="ede73-129">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ede73-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ede73-130">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ede73-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ede73-131">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ede73-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ede73-132">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ede73-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ede73-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ede73-133">See also</span></span>

- [<span data-ttu-id="ede73-134">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ede73-134">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ede73-135">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ede73-135">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ede73-136">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ede73-136">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ede73-137">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ede73-137">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
