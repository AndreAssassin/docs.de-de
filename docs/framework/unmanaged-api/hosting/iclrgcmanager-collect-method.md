---
title: ICLRGCManager::Collect-Methode
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1746527a2667676dfeab89e72874204460bcd33c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984723"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="9db11-102">ICLRGCManager::Collect-Methode</span><span class="sxs-lookup"><span data-stu-id="9db11-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="9db11-103">Erzwingt eine Garbagecollection für die angegebene Generation.</span><span class="sxs-lookup"><span data-stu-id="9db11-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9db11-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9db11-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9db11-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9db11-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="9db11-106">[in] Die Generierung zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="9db11-106">[in] The generation to collect.</span></span> <span data-ttu-id="9db11-107">Der Wert-1 erzwingt, dass eine Sammlung für alle Generationen.</span><span class="sxs-lookup"><span data-stu-id="9db11-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9db11-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9db11-108">Return Value</span></span>  
  
|<span data-ttu-id="9db11-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9db11-109">HRESULT</span></span>|<span data-ttu-id="9db11-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9db11-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9db11-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="9db11-111">S_OK</span></span>|<span data-ttu-id="9db11-112">`Collect` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9db11-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="9db11-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9db11-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9db11-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9db11-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9db11-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9db11-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9db11-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9db11-116">The call timed out.</span></span>|  
|<span data-ttu-id="9db11-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9db11-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9db11-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9db11-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9db11-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9db11-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9db11-120">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9db11-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9db11-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9db11-121">E_FAIL</span></span>|<span data-ttu-id="9db11-122">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9db11-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9db11-123">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9db11-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9db11-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9db11-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9db11-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9db11-125">Remarks</span></span>  
 <span data-ttu-id="9db11-126">Die `Collect` Methode erzwingt der CLR Garbagecollector eine Garbage Collection unabhängig von seinem aktuellen Zustand ausführen.</span><span class="sxs-lookup"><span data-stu-id="9db11-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9db11-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9db11-127">Requirements</span></span>  
 <span data-ttu-id="9db11-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9db11-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9db11-129">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9db11-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9db11-130">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9db11-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9db11-131">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9db11-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9db11-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9db11-132">See also</span></span>

- [<span data-ttu-id="9db11-133">Automatische Speicherverwaltung</span><span class="sxs-lookup"><span data-stu-id="9db11-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)
- [<span data-ttu-id="9db11-134">Garbage Collection</span><span class="sxs-lookup"><span data-stu-id="9db11-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)
- [<span data-ttu-id="9db11-135">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9db11-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9db11-136">ICLRGCManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9db11-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [<span data-ttu-id="9db11-137">CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="9db11-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [<span data-ttu-id="9db11-138">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9db11-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="9db11-139">Hosting</span><span class="sxs-lookup"><span data-stu-id="9db11-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
