---
title: ICLRRuntimeHost::Stop-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85116244ad21842fab025ddd48106deef75f210b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166971"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="e7f53-102">ICLRRuntimeHost::Stop-Methode</span><span class="sxs-lookup"><span data-stu-id="e7f53-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="e7f53-103">Beendet die Ausführung von Code von der common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e7f53-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e7f53-104">Diese Methode nicht freigeben von Ressourcen mit dem Host, Anwendungsdomänen zu entladen oder Zerstören von Threads.</span><span class="sxs-lookup"><span data-stu-id="e7f53-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="e7f53-105">Sie müssen den Vorgang, um diese Ressourcen freizugeben, beenden.</span><span class="sxs-lookup"><span data-stu-id="e7f53-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7f53-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7f53-106">Syntax</span></span>  
  
```  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e7f53-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="e7f53-107">Return Value</span></span>  
  
|<span data-ttu-id="e7f53-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e7f53-108">HRESULT</span></span>|<span data-ttu-id="e7f53-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7f53-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e7f53-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e7f53-110">S_OK</span></span>|<span data-ttu-id="e7f53-111">`Stop` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7f53-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="e7f53-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e7f53-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e7f53-113">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="e7f53-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e7f53-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e7f53-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e7f53-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e7f53-115">The call timed out.</span></span>|  
|<span data-ttu-id="e7f53-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e7f53-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e7f53-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="e7f53-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e7f53-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e7f53-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e7f53-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="e7f53-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e7f53-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e7f53-120">E_FAIL</span></span>|<span data-ttu-id="e7f53-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="e7f53-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e7f53-122">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7f53-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e7f53-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="e7f53-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7f53-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7f53-124">Requirements</span></span>  
 <span data-ttu-id="e7f53-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7f53-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7f53-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7f53-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7f53-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e7f53-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7f53-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7f53-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f53-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7f53-129">See also</span></span>

- [<span data-ttu-id="e7f53-130">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e7f53-130">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
