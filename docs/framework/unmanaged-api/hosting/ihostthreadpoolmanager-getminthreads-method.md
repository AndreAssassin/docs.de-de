---
title: IHostThreadPoolManager::GetMinThreads-Methode
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f1230a72d06677b4d36d10a8a31d63638c1fcd41
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59170689"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a><span data-ttu-id="57b51-102">IHostThreadPoolManager::GetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="57b51-102">IHostThreadPoolManager::GetMinThreads Method</span></span>
<span data-ttu-id="57b51-103">Ruft die minimale Anzahl von Threads im Leerlauf, die den Host in den Threadpool in der Erwartung Anforderungen ab.</span><span class="sxs-lookup"><span data-stu-id="57b51-103">Gets the minimum number of idle threads that the host maintains in the thread pool in anticipation of requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b51-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="57b51-104">Syntax</span></span>  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="57b51-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="57b51-105">Parameters</span></span>  
 `MinThreads`  
 <span data-ttu-id="57b51-106">[out] Ein Zeiger auf die minimale Anzahl von Arbeitsthreads im Leerlauf, die der Host zurzeit verwaltet.</span><span class="sxs-lookup"><span data-stu-id="57b51-106">[out] A pointer to the minimum number of idle worker threads that the host currently maintains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="57b51-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="57b51-107">Return Value</span></span>  
  
|<span data-ttu-id="57b51-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="57b51-108">HRESULT</span></span>|<span data-ttu-id="57b51-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="57b51-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="57b51-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="57b51-110">S_OK</span></span>|<span data-ttu-id="57b51-111">`GetMinThreads` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="57b51-111">`GetMinThreads` returned successfully.</span></span>|  
|<span data-ttu-id="57b51-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="57b51-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="57b51-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="57b51-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="57b51-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="57b51-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="57b51-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="57b51-115">The call timed out.</span></span>|  
|<span data-ttu-id="57b51-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="57b51-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="57b51-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="57b51-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="57b51-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="57b51-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="57b51-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="57b51-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="57b51-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="57b51-120">E_FAIL</span></span>|<span data-ttu-id="57b51-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="57b51-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="57b51-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="57b51-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="57b51-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="57b51-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="57b51-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="57b51-124">E_NOTIMPL</span></span>|<span data-ttu-id="57b51-125">Der Host stellt keine Implementierung von `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="57b51-125">The host does not provide an implementation of `GetMinThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="57b51-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="57b51-126">Remarks</span></span>  
 <span data-ttu-id="57b51-127">Der Host ist nicht erforderlich, um eine Implementierung der `GetMinThreads`.</span><span class="sxs-lookup"><span data-stu-id="57b51-127">The host is not required to provide an implementation of `GetMinThreads`.</span></span> <span data-ttu-id="57b51-128">In diesem Fall sollte es einen HRESULT-Wert E_NOTIMPL zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="57b51-128">In this case, it should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57b51-129">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="57b51-129">Requirements</span></span>  
 <span data-ttu-id="57b51-130">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57b51-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57b51-131">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="57b51-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57b51-132">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="57b51-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57b51-133">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b51-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b51-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="57b51-134">See also</span></span>

- <xref:System.Threading.ThreadPool.GetMinThreads%2A>
- <xref:System.Threading.ThreadPool>
- [<span data-ttu-id="57b51-135">GetMaxThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="57b51-135">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)
- [<span data-ttu-id="57b51-136">SetMinThreads-Methode</span><span class="sxs-lookup"><span data-stu-id="57b51-136">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)
- [<span data-ttu-id="57b51-137">IHostThreadPoolManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="57b51-137">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
