---
title: ICLRRuntimeHost::ExecuteApplication-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ce7e9ff4041abd1e89330bd3a565b755875d3b2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59194226"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="2a41d-102">ICLRRuntimeHost::ExecuteApplication-Methode</span><span class="sxs-lookup"><span data-stu-id="2a41d-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="2a41d-103">In Szenarien für die ClickOnce-Manifest-basierten verwendet, an die Anwendung in einer neuen Domäne aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="2a41d-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="2a41d-104">Weitere Informationen zu diesen Szenarien finden Sie unter [ClickOnce-Sicherheit und Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="2a41d-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a41d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2a41d-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2a41d-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="2a41d-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="2a41d-107">[in] Der vollständige Name der Anwendung entsprechend der Definition für <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="2a41d-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="2a41d-108">[in] Die Anzahl der Zeichenfolgen, die innerhalb der `ppwzManifestPaths` Array.</span><span class="sxs-lookup"><span data-stu-id="2a41d-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="2a41d-109">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="2a41d-109">[in] Optional.</span></span> <span data-ttu-id="2a41d-110">Ein Zeichenfolgenarray, das Manifestspfade für die Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="2a41d-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="2a41d-111">[in] Die Anzahl der Zeichenfolgen, die innerhalb der `ppwzActivationData` Array.</span><span class="sxs-lookup"><span data-stu-id="2a41d-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="2a41d-112">[in] Optional.</span><span class="sxs-lookup"><span data-stu-id="2a41d-112">[in] Optional.</span></span> <span data-ttu-id="2a41d-113">Ein Zeichenfolgenarray mit den von der Anwendung Aktivierungsdaten wie z. B. den Abfragezeichenfolgenabschnitt der URL für Anwendungen, die über das Internet bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2a41d-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="2a41d-114">[out] Der Wert, der von den Einstiegspunkt der Anwendung zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2a41d-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2a41d-115">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2a41d-115">Return Value</span></span>  
  
|<span data-ttu-id="2a41d-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2a41d-116">HRESULT</span></span>|<span data-ttu-id="2a41d-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2a41d-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2a41d-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="2a41d-118">S_OK</span></span>|<span data-ttu-id="2a41d-119">`ExecuteApplication` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2a41d-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="2a41d-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2a41d-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2a41d-121">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="2a41d-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2a41d-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2a41d-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2a41d-123">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2a41d-123">The call timed out.</span></span>|  
|<span data-ttu-id="2a41d-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2a41d-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2a41d-125">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="2a41d-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2a41d-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2a41d-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2a41d-127">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="2a41d-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2a41d-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2a41d-128">E_FAIL</span></span>|<span data-ttu-id="2a41d-129">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="2a41d-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2a41d-130">Wenn eine Methode E_FAIL zurückgegeben wird, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2a41d-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2a41d-131">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="2a41d-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a41d-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2a41d-132">Remarks</span></span>  
 <span data-ttu-id="2a41d-133">`ExecuteApplication` Dient zum Aktivieren von ClickOnce-Anwendungen in eine neu erstellte Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="2a41d-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="2a41d-134">Die `pReturnValue` Output-Parameter von der Anwendung zurückgegebenen Wert festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="2a41d-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="2a41d-135">Wenn Sie angeben, dass der Wert Null für `pReturnValue`, `ExecuteApplication` schlägt nicht fehl, aber keinen Wert zurück.</span><span class="sxs-lookup"><span data-stu-id="2a41d-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2a41d-136">Rufen Sie nicht die [Methode starten](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) Methode vor dem Aufruf der `ExecuteApplication` Methode, um eine manifestbasierte Anwendung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2a41d-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="2a41d-137">Wenn die `Start` Methode zuerst aufgerufen wird, die `ExecuteApplication` Methodenaufruf schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="2a41d-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a41d-138">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2a41d-138">Requirements</span></span>  
 <span data-ttu-id="2a41d-139">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a41d-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a41d-140">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a41d-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a41d-141">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="2a41d-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a41d-142">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a41d-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a41d-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2a41d-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="2a41d-144">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2a41d-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="2a41d-145">SetAppDomainManager-Methode</span><span class="sxs-lookup"><span data-stu-id="2a41d-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="2a41d-146">Exemplarische Vorgehensweise: Herunterladen von Assemblys bei Bedarf mit der API für die ClickOnce-Bereitstellung unter Verwendung des Designers</span><span class="sxs-lookup"><span data-stu-id="2a41d-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
