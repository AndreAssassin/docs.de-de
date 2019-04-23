---
title: ICLRTask::SetTaskIdentifier-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask.SetTaskIdentifier
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SetTaskIdentifier
helpviewer_keywords:
- SetTaskIdentifier method [.NET Framework hosting]
- ICLRTask::SetTaskIdentifier method [.NET Framework hosting]
ms.assetid: bdb7f047-1e90-40fc-9e3b-d44a16509073
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abd8848ed54b26b66090e4865f9c3a0e5c4d20db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078316"
---
# <a name="iclrtasksettaskidentifier-method"></a><span data-ttu-id="cbd65-102">ICLRTask::SetTaskIdentifier-Methode</span><span class="sxs-lookup"><span data-stu-id="cbd65-102">ICLRTask::SetTaskIdentifier Method</span></span>
<span data-ttu-id="cbd65-103">Weist die common Language Runtime (CLR), die Aufgabe, die vom aktuellen Wert der angegebenen ID zugeordnet werden soll [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="cbd65-103">Instructs the common language runtime (CLR) to associate the specified identifier value with the task represented by the current [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbd65-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cbd65-104">Syntax</span></span>  
  
```  
HRESULT SetTaskIdentifier (  
    [in] DWORD Asked  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cbd65-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cbd65-105">Parameters</span></span>  
 `Asked`  
 <span data-ttu-id="cbd65-106">[in] Der eindeutige Bezeichner für die common Language Runtime zugeordnet, der vom aktuellen Task `ICLRTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="cbd65-106">[in] The unique identifier for the common language runtime to associate with the task represented by the current `ICLRTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cbd65-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cbd65-107">Return Value</span></span>  
  
|<span data-ttu-id="cbd65-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cbd65-108">HRESULT</span></span>|<span data-ttu-id="cbd65-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cbd65-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cbd65-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="cbd65-110">S_OK</span></span>|<span data-ttu-id="cbd65-111">`SetTaskIdentifier` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="cbd65-111">`SetTaskIdentifier` returned successfully.</span></span>|  
|<span data-ttu-id="cbd65-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cbd65-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cbd65-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cbd65-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cbd65-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cbd65-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cbd65-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cbd65-115">The call timed out.</span></span>|  
|<span data-ttu-id="cbd65-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cbd65-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cbd65-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="cbd65-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cbd65-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cbd65-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cbd65-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="cbd65-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cbd65-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cbd65-120">E_FAIL</span></span>|<span data-ttu-id="cbd65-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="cbd65-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cbd65-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbd65-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cbd65-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="cbd65-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbd65-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cbd65-124">Remarks</span></span>  
 <span data-ttu-id="cbd65-125">Der Host kann einen Bezeichner mit einer Aufgabe zum unterstützen der Integration der CLR und des Hosts in einer Debugumgebung zuordnen.</span><span class="sxs-lookup"><span data-stu-id="cbd65-125">The host can associate an identifier with a task to help integrate the CLR and the host in a debugging environment.</span></span> <span data-ttu-id="cbd65-126">Der Bezeichner hat keine Bedeutung für die CLR.</span><span class="sxs-lookup"><span data-stu-id="cbd65-126">The identifier has no meaning for the CLR.</span></span> <span data-ttu-id="cbd65-127">Die CLR übergibt ihn an einen Debuggeranwendung.</span><span class="sxs-lookup"><span data-stu-id="cbd65-127">The CLR passes it along to a debugger application.</span></span> <span data-ttu-id="cbd65-128">Der Debugger kann verwenden diesen Bezeichner, eine Aufrufliste für den Host eine CLR-Aufrufliste zugeordnet werden soll, und aktivieren die entsprechenden Ablaufverfolgungsinformationen an vereinheitlicht werden, wenn Sie in der Benutzeroberfläche des Debuggers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cbd65-128">The debugger can use this identifier to associate a CLR call stack with a host call stack, and enable their respective trace information to be unified when viewed in the debugger's user interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbd65-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cbd65-129">Requirements</span></span>  
 <span data-ttu-id="cbd65-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbd65-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbd65-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cbd65-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cbd65-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cbd65-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cbd65-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbd65-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbd65-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbd65-134">See also</span></span>

- [<span data-ttu-id="cbd65-135">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbd65-135">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="cbd65-136">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbd65-136">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="cbd65-137">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbd65-137">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="cbd65-138">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cbd65-138">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
