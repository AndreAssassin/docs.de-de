---
title: ICLRRuntimeHost::GetCurrentAppDomainId-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.GetCurrentAppDomainId
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId
helpviewer_keywords:
- ICLRRuntimeHost::GetCurrentAppDomainId method [.NET Framework hosting]
- GetCurrentAppDomainId method [.NET Framework hosting]
ms.assetid: 33800475-7815-4976-8aca-a1038761a2ef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 28d1655bdc3746dab87acef2e2aac6758883e74a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59096211"
---
# <a name="iclrruntimehostgetcurrentappdomainid-method"></a><span data-ttu-id="a0341-102">ICLRRuntimeHost::GetCurrentAppDomainId-Methode</span><span class="sxs-lookup"><span data-stu-id="a0341-102">ICLRRuntimeHost::GetCurrentAppDomainId Method</span></span>
<span data-ttu-id="a0341-103">Ruft den numerischen Bezeichner des der <xref:System.AppDomain> , die derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0341-103">Gets the numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0341-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a0341-104">Syntax</span></span>  
  
```  
HRESULT GetCurrentAppDomainId(  
    [out] DWORD* pdwAppDomainId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0341-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a0341-105">Parameters</span></span>  
 `pdwAppDomainId`  
 <span data-ttu-id="a0341-106">[out] Der numerische Bezeichner, der die <xref:System.AppDomain> , die derzeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0341-106">[out] The numeric identifier of the <xref:System.AppDomain> that is currently executing.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0341-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a0341-107">Return Value</span></span>  
  
|<span data-ttu-id="a0341-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a0341-108">HRESULT</span></span>|<span data-ttu-id="a0341-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a0341-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a0341-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="a0341-110">S_OK</span></span>|<span data-ttu-id="a0341-111">`GetCurrentAppDomainId` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a0341-111">`GetCurrentAppDomainId` returned successfully.</span></span>|  
|<span data-ttu-id="a0341-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a0341-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a0341-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="a0341-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a0341-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a0341-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a0341-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0341-115">The call timed out.</span></span>|  
|<span data-ttu-id="a0341-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a0341-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a0341-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="a0341-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a0341-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a0341-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a0341-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="a0341-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a0341-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a0341-120">E_FAIL</span></span>|<span data-ttu-id="a0341-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="a0341-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a0341-122">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a0341-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a0341-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="a0341-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0341-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a0341-124">Remarks</span></span>  
 <span data-ttu-id="a0341-125">Die `pdwAppDomainId` Parametersatz wird auf den Wert des der <xref:System.AppDomain.Id%2A> Eigenschaft der <xref:System.AppDomain> in dem der aktuelle Thread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a0341-125">The `pdwAppDomainId` parameter is set to the value of the <xref:System.AppDomain.Id%2A> property of the <xref:System.AppDomain> in which the current thread is executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0341-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a0341-126">Requirements</span></span>  
 <span data-ttu-id="a0341-127">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0341-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0341-128">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a0341-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0341-129">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a0341-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0341-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0341-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0341-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0341-131">See also</span></span>

- <xref:System.AppDomain>
- <xref:System.AppDomainManager>
- [<span data-ttu-id="a0341-132">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a0341-132">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
