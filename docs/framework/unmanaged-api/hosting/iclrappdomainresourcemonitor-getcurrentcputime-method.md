---
title: ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor.GetCurrentCpuTime
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime
helpviewer_keywords:
- ICLRAppDomainResourceMonitor::GetCurrentCpuTime method [.NET Framework hosting]
- GetCurrentCpuTime method [.NET Framework hosting]
ms.assetid: ebc9cc33-fcd6-4cae-9ecb-ea21c51874e6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4d5149c7e3430c5e7c59a47c4ab5dc98d878de39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67766665"
---
# <a name="iclrappdomainresourcemonitorgetcurrentcputime-method"></a><span data-ttu-id="f9de0-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime-Methode</span><span class="sxs-lookup"><span data-stu-id="f9de0-102">ICLRAppDomainResourceMonitor::GetCurrentCpuTime Method</span></span>
<span data-ttu-id="f9de0-103">Ruft die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9de0-103">Gets the total processor time that has been used by all threads while executing in the current application domain, since the application domain was created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9de0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9de0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentCpuTime([in]  DWORD dwAppDomainId,  
                          [out] ULONGLONG* pMilliseconds);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9de0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9de0-105">Parameters</span></span>  
 `dwAppDomainId`  
 <span data-ttu-id="f9de0-106">[in] Die ID des angeforderten Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f9de0-106">[in] The ID of the requested application domain.</span></span>  
  
 `pMilliseconds`  
 <span data-ttu-id="f9de0-107">[out] Ein Zeiger auf die gesamte Prozessorzeit, die von allen Threads beim Ausführen in der aktuellen Anwendungsdomäne seit der Erstellung der Anwendungsdomäne verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f9de0-107">[out] A pointer to the total processor time that has been used by all threads while executing in the current application domain since the application domain was created.</span></span> <span data-ttu-id="f9de0-108">Dieser Parameter kann `null` sein.</span><span class="sxs-lookup"><span data-stu-id="f9de0-108">This parameter can be `null`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f9de0-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f9de0-109">Return Value</span></span>  
  
|<span data-ttu-id="f9de0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f9de0-110">HRESULT</span></span>|<span data-ttu-id="f9de0-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9de0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f9de0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f9de0-112">S_OK</span></span>|<span data-ttu-id="f9de0-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f9de0-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="f9de0-114">COR_E_APPDOMAINUNLOADED</span><span class="sxs-lookup"><span data-stu-id="f9de0-114">COR_E_APPDOMAINUNLOADED</span></span>|<span data-ttu-id="f9de0-115">Die Anwendungsdomäne entladen wurde, oder es ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f9de0-115">The application domain has been unloaded or does not exist.</span></span>|  
|<span data-ttu-id="f9de0-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="f9de0-116">E_FAIL</span></span>|<span data-ttu-id="f9de0-117">Ressourcenüberwachung der Anwendungsdomäne ist nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f9de0-117">Application domain resource monitoring is not enabled.</span></span><br /><br /> <span data-ttu-id="f9de0-118">- oder -</span><span class="sxs-lookup"><span data-stu-id="f9de0-118">-or-</span></span><br /><br /> <span data-ttu-id="f9de0-119">Alle anderen Fehler.</span><span class="sxs-lookup"><span data-stu-id="f9de0-119">All other failures.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f9de0-120">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f9de0-120">Remarks</span></span>  
 <span data-ttu-id="f9de0-121">Diese Methode ist, die nicht verwaltete Entsprechung der verwalteten <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f9de0-121">This method is the unmanaged equivalent of the managed <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9de0-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9de0-122">Requirements</span></span>  
 <span data-ttu-id="f9de0-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9de0-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9de0-124">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="f9de0-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f9de0-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9de0-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9de0-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9de0-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9de0-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9de0-127">See also</span></span>

- [<span data-ttu-id="f9de0-128">ICLRAppDomainResourceMonitor-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9de0-128">ICLRAppDomainResourceMonitor Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-interface.md)
- [<span data-ttu-id="f9de0-129">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f9de0-129">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f9de0-130">Überwachung von Anwendungsdomänenressourcen</span><span class="sxs-lookup"><span data-stu-id="f9de0-130">Application Domain Resource Monitoring</span></span>](../../../../docs/standard/garbage-collection/app-domain-resource-monitoring.md)
- [<span data-ttu-id="f9de0-131">Hosting</span><span class="sxs-lookup"><span data-stu-id="f9de0-131">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
