---
title: ICLRPolicyManager::SetActionOnTimeout-Methode
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetActionOnTimeout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetActionOnTimeout
helpviewer_keywords:
- SetActionOnTimeout method [.NET Framework hosting]
- ICLRPolicyManager::SetActionOnTimeout method [.NET Framework hosting]
ms.assetid: 38439fa1-2b99-4fa8-a6ec-08afc0f83b9c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e8d99f4f0615e7d25991b37030b7cb609985192f
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64910667"
---
# <a name="iclrpolicymanagersetactionontimeout-method"></a><span data-ttu-id="159e2-102">ICLRPolicyManager::SetActionOnTimeout-Methode</span><span class="sxs-lookup"><span data-stu-id="159e2-102">ICLRPolicyManager::SetActionOnTimeout Method</span></span>
<span data-ttu-id="159e2-103">Gibt die Richtlinienaktion, die die common Language Runtime (CLR) ausgeführt werden soll, wenn der angegebene Vorgang ein auftritt Timeout.</span><span class="sxs-lookup"><span data-stu-id="159e2-103">Specifies the policy action the common language runtime (CLR) should take when the specified operation times out.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="159e2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="159e2-104">Syntax</span></span>  
  
```  
HRESULT SetActionOnTimeout (  
    [in] EClrOperation operation,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="159e2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="159e2-105">Parameters</span></span>  
 `operation`  
 <span data-ttu-id="159e2-106">[in] Eines der [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) Werte, der den Vorgang für die die Timeoutaktion an.</span><span class="sxs-lookup"><span data-stu-id="159e2-106">[in] One of the [EClrOperation](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md) values, indicating the operation for which to specify the timeout action.</span></span> <span data-ttu-id="159e2-107">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="159e2-107">The following values are supported:</span></span>  
  
- <span data-ttu-id="159e2-108">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="159e2-108">OPR_AppDomainUnload</span></span>  
  
- <span data-ttu-id="159e2-109">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="159e2-109">OPR_ProcessExit</span></span>  
  
- <span data-ttu-id="159e2-110">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="159e2-110">OPR_ThreadRudeAbortInCriticalRegion</span></span>  
  
- <span data-ttu-id="159e2-111">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="159e2-111">OPR_ThreadRudeAbortInNonCriticalRegion</span></span>  
  
 `action`  
 <span data-ttu-id="159e2-112">[in] Eines der [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) Werte, die die Richtlinienaktion, die ausgeführt werden, wenn der Vorgang ein auftritt Timeout.</span><span class="sxs-lookup"><span data-stu-id="159e2-112">[in] One of the [EPolicyAction](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md) values, indicating the policy action to be taken when the operation times out.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="159e2-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="159e2-113">Return Value</span></span>  
  
|<span data-ttu-id="159e2-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="159e2-114">HRESULT</span></span>|<span data-ttu-id="159e2-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="159e2-115">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="159e2-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="159e2-116">S_OK</span></span>|<span data-ttu-id="159e2-117">`SetActionOnTimeout` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="159e2-117">`SetActionOnTimeout` returned successfully.</span></span>|  
|<span data-ttu-id="159e2-118">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="159e2-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="159e2-119">Die CLR wurde nicht in einen Prozess geladen und befindet sich in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="159e2-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="159e2-120">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="159e2-120">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="159e2-121">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="159e2-121">The call timed out.</span></span>|  
|<span data-ttu-id="159e2-122">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="159e2-122">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="159e2-123">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="159e2-123">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="159e2-124">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="159e2-124">HOST_E_ABANDONED</span></span>|<span data-ttu-id="159e2-125">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="159e2-125">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="159e2-126">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="159e2-126">E_FAIL</span></span>|<span data-ttu-id="159e2-127">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="159e2-127">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="159e2-128">Wenn eine Methode E_FAIL zurückgegeben hat, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="159e2-128">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="159e2-129">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="159e2-129">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="159e2-130">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="159e2-130">E_INVALIDARG</span></span>|<span data-ttu-id="159e2-131">Ein Timeout kann nicht festgelegt werden für den angegebenen `operation`, oder es wurde ein ungültiger Wert für bereitgestellt `operation`.</span><span class="sxs-lookup"><span data-stu-id="159e2-131">A timeout cannot be set for the specified `operation`, or an invalid value was supplied for `operation`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="159e2-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="159e2-132">Remarks</span></span>  
 <span data-ttu-id="159e2-133">Der Timeoutwert kann sein, entweder das standardmäßige Timeout, die von der CLR festgelegt oder ein Wert angegeben wird, durch den Host in einem Aufruf der [ICLRPolicyManager:: SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="159e2-133">The timeout value can be either the default timeout set by the CLR, or a value specified by the host in a call to the [ICLRPolicyManager::SetTimeout](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-settimeout-method.md) method.</span></span>  
  
 <span data-ttu-id="159e2-134">Nicht alle Richtlinien Action-Werte können als das Timeoutverhalten für CLR-Vorgänge angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="159e2-134">Not all policy action values can be specified as the timeout behavior for CLR operations.</span></span> <span data-ttu-id="159e2-135">`SetActionOnTimeout` wird in der Regel nur für die Eskalation von Verhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="159e2-135">`SetActionOnTimeout` is typically used only to escalate behavior.</span></span> <span data-ttu-id="159e2-136">Ein Host kann beispielsweise angeben, dass es sich bei Threadabbrüche in grobe umgewandelt werden thread-Abbrüche, aber nicht das Gegenteil angeben.</span><span class="sxs-lookup"><span data-stu-id="159e2-136">For example, a host can specify that thread aborts be turned into rude thread aborts, but cannot specify the opposite.</span></span> <span data-ttu-id="159e2-137">Die folgende Tabelle beschreibt die gültigen `action` Werte für gültige `operation` Werte.</span><span class="sxs-lookup"><span data-stu-id="159e2-137">The table below describes the valid `action` values for valid `operation` values.</span></span>  
  
|<span data-ttu-id="159e2-138">Wert für `operation`</span><span class="sxs-lookup"><span data-stu-id="159e2-138">Value for `operation`</span></span>|<span data-ttu-id="159e2-139">Gültige Werte für `action`</span><span class="sxs-lookup"><span data-stu-id="159e2-139">Valid values for `action`</span></span>|  
|---------------------------|-------------------------------|  
|<span data-ttu-id="159e2-140">OPR_ThreadRudeAbortInNonCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="159e2-140">OPR_ThreadRudeAbortInNonCriticalRegion</span></span><br /><br /> <span data-ttu-id="159e2-141">OPR_ThreadRudeAbortInCriticalRegion</span><span class="sxs-lookup"><span data-stu-id="159e2-141">OPR_ThreadRudeAbortInCriticalRegion</span></span>|<span data-ttu-id="159e2-142">-   eRudeAbortThread</span><span class="sxs-lookup"><span data-stu-id="159e2-142">-   eRudeAbortThread</span></span><br /><span data-ttu-id="159e2-143">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="159e2-143">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="159e2-144">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="159e2-144">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="159e2-145">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-145">-   eExitProcess</span></span><br /><span data-ttu-id="159e2-146">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-146">-   eFastExitProcess</span></span><br /><span data-ttu-id="159e2-147">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-147">-   eRudeExitProcess</span></span><br /><span data-ttu-id="159e2-148">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="159e2-148">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="159e2-149">OPR_AppDomainUnload</span><span class="sxs-lookup"><span data-stu-id="159e2-149">OPR_AppDomainUnload</span></span>|<span data-ttu-id="159e2-150">-   eUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="159e2-150">-   eUnloadAppDomain</span></span><br /><span data-ttu-id="159e2-151">-   eRudeUnloadAppDomain</span><span class="sxs-lookup"><span data-stu-id="159e2-151">-   eRudeUnloadAppDomain</span></span><br /><span data-ttu-id="159e2-152">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-152">-   eExitProcess</span></span><br /><span data-ttu-id="159e2-153">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-153">-   eFastExitProcess</span></span><br /><span data-ttu-id="159e2-154">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-154">-   eRudeExitProcess</span></span><br /><span data-ttu-id="159e2-155">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="159e2-155">-   eDisableRuntime</span></span>|  
|<span data-ttu-id="159e2-156">OPR_ProcessExit</span><span class="sxs-lookup"><span data-stu-id="159e2-156">OPR_ProcessExit</span></span>|<span data-ttu-id="159e2-157">-eExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-157">-   eExitProcess</span></span><br /><span data-ttu-id="159e2-158">-   eFastExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-158">-   eFastExitProcess</span></span><br /><span data-ttu-id="159e2-159">-   eRudeExitProcess</span><span class="sxs-lookup"><span data-stu-id="159e2-159">-   eRudeExitProcess</span></span><br /><span data-ttu-id="159e2-160">-   eDisableRuntime</span><span class="sxs-lookup"><span data-stu-id="159e2-160">-   eDisableRuntime</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="159e2-161">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="159e2-161">Requirements</span></span>  
 <span data-ttu-id="159e2-162">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="159e2-162">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="159e2-163">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="159e2-163">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="159e2-164">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="159e2-164">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="159e2-165">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="159e2-165">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="159e2-166">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="159e2-166">See also</span></span>

- [<span data-ttu-id="159e2-167">EClrOperation-Enumeration</span><span class="sxs-lookup"><span data-stu-id="159e2-167">EClrOperation Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclroperation-enumeration.md)
- [<span data-ttu-id="159e2-168">EPolicyAction-Enumeration</span><span class="sxs-lookup"><span data-stu-id="159e2-168">EPolicyAction Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/epolicyaction-enumeration.md)
- [<span data-ttu-id="159e2-169">ICLRControl-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="159e2-169">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="159e2-170">ICLRPolicyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="159e2-170">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
