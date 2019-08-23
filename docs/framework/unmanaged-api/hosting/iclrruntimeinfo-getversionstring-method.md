---
title: ICLRRuntimeInfo::GetVersionString-Methode
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.GetVersionString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetVersionString
helpviewer_keywords:
- ICLRRuntimeInfo::GetVersionString method [.NET Framework hosting]
- GetVersionString method, ICLRRuntimeInfo interface [.NET Framework hosting]
ms.assetid: 98b097ef-2276-4dd9-8551-b03c972e8179
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a886106e5da49e7124dac5c8ea7416859aa441da
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69929848"
---
# <a name="iclrruntimeinfogetversionstring-method"></a><span data-ttu-id="7da10-102">ICLRRuntimeInfo::GetVersionString-Methode</span><span class="sxs-lookup"><span data-stu-id="7da10-102">ICLRRuntimeInfo::GetVersionString Method</span></span>
<span data-ttu-id="7da10-103">Ruft die einer bestimmten [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) -Schnittstelle zugeordneten Common Language Runtime (CLR) ab.</span><span class="sxs-lookup"><span data-stu-id="7da10-103">Gets common language runtime (CLR) version information associated with a given [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="7da10-104">Diese Methode ersetzt die folgenden Funktionen:</span><span class="sxs-lookup"><span data-stu-id="7da10-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="7da10-105">GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="7da10-105">GetRequestedRuntimeInfo</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
  
- [<span data-ttu-id="7da10-106">GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="7da10-106">GetRequestedRuntimeVersion</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="7da10-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7da10-107">Syntax</span></span>  
  
```cpp  
HRESULT GetVersionString(  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out]  DWORD *pcchBuffer);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7da10-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7da10-108">Parameters</span></span>  
 `pwzBuffer`  
 <span data-ttu-id="7da10-109">vorgenommen Die .NET Framework Kompilierungs Version im Format "v*A*. *B* [. *X*] ".</span><span class="sxs-lookup"><span data-stu-id="7da10-109">[out] The .NET Framework compilation version in the format "v*A*.*B*[.*X*]".</span></span> <span data-ttu-id="7da10-110">*A*, *B*und *X* sind Dezimalzahlen, die der Hauptversion, der neben Version und der Buildnummer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="7da10-110">*A*, *B*, and *X* are decimal numbers that correspond to the major version, the minor version, and the build number.</span></span> <span data-ttu-id="7da10-111">*X* ist optional.</span><span class="sxs-lookup"><span data-stu-id="7da10-111">*X* is optional.</span></span> <span data-ttu-id="7da10-112">Wenn *X* nicht vorhanden ist, gibt es keinen nachfolgenden Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="7da10-112">If *X* is not present, there is no trailing period.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7da10-113">Dieser Parameter muss dem Verzeichnisnamen für die .NET Framework Version entsprechen, wie er unter "c:\WINDOWS\Microsoft.NET\Framework" angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="7da10-113">This parameter must match the directory name for the .NET Framework version, as it appears under C:\Windows\Microsoft.NET\Framework.</span></span>  
  
 <span data-ttu-id="7da10-114">Beispiel Werte sind "v 1.0.3705", "v 1.1.4322", "v 2.0.50727" und "v 4.0". *x*", wobei *x* von der installierten Buildnummer abhängig ist.</span><span class="sxs-lookup"><span data-stu-id="7da10-114">Example values are "v1.0.3705", "v1.1.4322", "v2.0.50727", and "v4.0.*x*", where *x* depends on the build number installed.</span></span> <span data-ttu-id="7da10-115">Beachten Sie, dass das Präfix "v" obligatorisch ist.</span><span class="sxs-lookup"><span data-stu-id="7da10-115">Note that the "v" prefix is mandatory.</span></span>  
  
 `pchBuffer`  
 <span data-ttu-id="7da10-116">[in, out] Gibt die Größe von `pwzBuffer` an, um Pufferüberläufe zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="7da10-116">[in, out] Specifies the size of `pwzBuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="7da10-117">Wenn `pwzBuffer` ist `null`, `pwzBuffer` wird die erforderliche Größe von zurückgegeben, um die vorab Zuordnung zuzulassen. `pchBuffer`</span><span class="sxs-lookup"><span data-stu-id="7da10-117">If `pwzBuffer` is `null`, `pchBuffer` returns the required size of `pwzBuffer` to allow preallocation.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7da10-118">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7da10-118">Return Value</span></span>  
 <span data-ttu-id="7da10-119">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7da10-119">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7da10-120">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7da10-120">HRESULT</span></span>|<span data-ttu-id="7da10-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7da10-121">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7da10-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="7da10-122">S_OK</span></span>|<span data-ttu-id="7da10-123">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7da10-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="7da10-124">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="7da10-124">E_POINTER</span></span>|<span data-ttu-id="7da10-125">`pwzBuffer` oder `pchBuffer` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="7da10-125">`pwzBuffer` or `pchBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7da10-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7da10-126">Requirements</span></span>  
 <span data-ttu-id="7da10-127">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7da10-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7da10-128">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="7da10-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="7da10-129">**Fern** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7da10-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7da10-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7da10-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7da10-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7da10-131">See also</span></span>

- [<span data-ttu-id="7da10-132">ICLRRuntimeInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7da10-132">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="7da10-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="7da10-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="7da10-134">In .NET Framework 4 und 4.5 hinzugefügte CLR-Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="7da10-134">CLR Hosting Interfaces Added in the .NET Framework 4 and 4.5</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)
- [<span data-ttu-id="7da10-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="7da10-135">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
