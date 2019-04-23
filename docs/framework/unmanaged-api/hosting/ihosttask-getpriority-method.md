---
title: IHostTask::GetPriority-Methode
ms.date: 03/30/2017
api_name:
- IHostTask.GetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::GetPriority
helpviewer_keywords:
- GetPriority method [.NET Framework hosting]
- IHostTask::GetPriority method [.NET Framework hosting]
ms.assetid: 4b463cd6-77c1-4f9a-8518-346ad8fc4b70
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 702992ab4edfea3f0b699efefedb195cd87586ea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59136772"
---
# <a name="ihosttaskgetpriority-method"></a><span data-ttu-id="7c3c6-102">IHostTask::GetPriority-Methode</span><span class="sxs-lookup"><span data-stu-id="7c3c6-102">IHostTask::GetPriority Method</span></span>
<span data-ttu-id="7c3c6-103">Ruft die Prioritätsebene von der Aufgabe, die vom aktuellen [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) Instanz.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-103">Gets the thread priority level of the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c3c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c3c6-104">Syntax</span></span>  
  
```  
HRESULT GetPriority (  
    [out] int *pPriority  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c3c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7c3c6-105">Parameters</span></span>  
 `pPriority`  
 <span data-ttu-id="7c3c6-106">[out] Ein Zeiger auf eine ganze Zahl, die die Prioritätsebene von der Aufgabe, die vom aktuellen angibt `IHostTask` Instanz.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-106">[out] A pointer to an integer that indicates the thread priority level of the task represented by the current `IHostTask` instance.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c3c6-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7c3c6-107">Return Value</span></span>  
  
|<span data-ttu-id="7c3c6-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7c3c6-108">HRESULT</span></span>|<span data-ttu-id="7c3c6-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7c3c6-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7c3c6-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="7c3c6-110">S_OK</span></span>|<span data-ttu-id="7c3c6-111">`GetPriority` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-111">`GetPriority` returned successfully.</span></span>|  
|<span data-ttu-id="7c3c6-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="7c3c6-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="7c3c6-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="7c3c6-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="7c3c6-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="7c3c6-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-115">The call timed out.</span></span>|  
|<span data-ttu-id="7c3c6-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="7c3c6-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="7c3c6-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="7c3c6-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="7c3c6-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="7c3c6-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="7c3c6-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7c3c6-120">E_FAIL</span></span>|<span data-ttu-id="7c3c6-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="7c3c6-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="7c3c6-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c3c6-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7c3c6-124">Remarks</span></span>  
 <span data-ttu-id="7c3c6-125">Ebene Thread Priority-Werte werden definiert, durch die Win32- `SetThreadPriority` Funktion.</span><span class="sxs-lookup"><span data-stu-id="7c3c6-125">Thread priority level values are defined by the Win32 `SetThreadPriority` function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c3c6-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c3c6-126">Requirements</span></span>  
 <span data-ttu-id="7c3c6-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c3c6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c3c6-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7c3c6-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7c3c6-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c3c6-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7c3c6-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c3c6-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c3c6-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c3c6-131">See also</span></span>

- [<span data-ttu-id="7c3c6-132">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3c6-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="7c3c6-133">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3c6-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="7c3c6-134">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3c6-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="7c3c6-135">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c3c6-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
