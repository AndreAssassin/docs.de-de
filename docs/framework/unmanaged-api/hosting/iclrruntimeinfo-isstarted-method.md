---
title: ICLRRuntimeInfo::IsStarted-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1297c84acadf0a53b418b06afe806237d374ee25
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59073896"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="cdb35-102">ICLRRuntimeInfo::IsStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="cdb35-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="cdb35-103">Gibt an, ob die Laufzeit gestartet wurde (d. h., ob die [ICLRRuntimeHost:: Start-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) aufgerufen wurde und erfolgreich war).</span><span class="sxs-lookup"><span data-stu-id="cdb35-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cdb35-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cdb35-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cdb35-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cdb35-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="cdb35-106">[out] `true` ist diese Laufzeit gestartet wurde, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="cdb35-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="cdb35-107">[out] Gibt die Optionen, die verwendet wurden, um die Runtime zu starten.</span><span class="sxs-lookup"><span data-stu-id="cdb35-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cdb35-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cdb35-108">Return Value</span></span>  
 <span data-ttu-id="cdb35-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cdb35-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="cdb35-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cdb35-110">HRESULT</span></span>|<span data-ttu-id="cdb35-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cdb35-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cdb35-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="cdb35-112">S_OK</span></span>|<span data-ttu-id="cdb35-113">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cdb35-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="cdb35-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="cdb35-114">E_NOTIMPL</span></span>|<span data-ttu-id="cdb35-115">Die Version der common Language Runtime (CLR) ist älter als die CLR-Version in der [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdb35-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cdb35-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="cdb35-116">Remarks</span></span>  
 <span data-ttu-id="cdb35-117">Diese Methode funktioniert nicht mit CLR-Versionen älter als die CLR-Version in der [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cdb35-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cdb35-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cdb35-118">Requirements</span></span>  
 <span data-ttu-id="cdb35-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cdb35-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cdb35-120">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="cdb35-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="cdb35-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cdb35-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cdb35-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cdb35-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cdb35-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cdb35-123">See also</span></span>

- [<span data-ttu-id="cdb35-124">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cdb35-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="cdb35-125">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="cdb35-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="cdb35-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="cdb35-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
