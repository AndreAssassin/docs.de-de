---
title: IHostAssemblyManager::GetAssemblyStore-Methode
ms.date: 03/30/2017
api_name:
- IHostAssemblyManager.GetAssemblyStore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostAssemblyManager::GetAssemblyStore
helpviewer_keywords:
- IHostAssemblyManager::GetAssemblyStore method [.NET Framework hosting]
- GetAssemblyStore method [.NET Framework hosting]
ms.assetid: d0f74593-9bb1-4a11-8096-e29734b20698
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 194b40b0873cee848124a5afc9a47740d59969c8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779455"
---
# <a name="ihostassemblymanagergetassemblystore-method"></a><span data-ttu-id="9ee7d-102">IHostAssemblyManager::GetAssemblyStore-Methode</span><span class="sxs-lookup"><span data-stu-id="9ee7d-102">IHostAssemblyManager::GetAssemblyStore Method</span></span>
<span data-ttu-id="9ee7d-103">Ruft einen Schnittstellenzeiger auf ein [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) , das die Liste der Assemblys, die vom Host geladen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-103">Gets an interface pointer to an [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md) that represents the list of assemblies loaded by the host.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ee7d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ee7d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyStore (  
    [out] IHostAssemblyStore **ppAssemblyStore  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ee7d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9ee7d-105">Parameters</span></span>  
 `ppAssemblyStore`  
 <span data-ttu-id="9ee7d-106">[out] Ein Funktionszeiger auf eine `IHostAssemblyStore` -Instanz oder null, wenn der Host keine implementiert `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-106">[out] A function pointer to an `IHostAssemblyStore` instance, or null, if the host does not implement `IHostAssemblyStore`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ee7d-107">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ee7d-107">Return Value</span></span>  
  
|<span data-ttu-id="9ee7d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ee7d-108">HRESULT</span></span>|<span data-ttu-id="9ee7d-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ee7d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ee7d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ee7d-110">S_OK</span></span>|<span data-ttu-id="9ee7d-111">`GetAssemblyStore` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-111">`GetAssemblyStore` returned successfully.</span></span>|  
|<span data-ttu-id="9ee7d-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ee7d-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ee7d-113">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ee7d-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ee7d-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ee7d-115">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-115">The call timed out.</span></span>|  
|<span data-ttu-id="9ee7d-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ee7d-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ee7d-117">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ee7d-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ee7d-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ee7d-119">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ee7d-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ee7d-120">E_FAIL</span></span>|<span data-ttu-id="9ee7d-121">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ee7d-122">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ee7d-123">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="9ee7d-124">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="9ee7d-124">E_NOINTERFACE</span></span>|<span data-ttu-id="9ee7d-125">Der Host stellt keine Implementierung von `IHostAssemblyStore`.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-125">The host does not provide an implementation of `IHostAssemblyStore`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee7d-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ee7d-126">Remarks</span></span>  
 <span data-ttu-id="9ee7d-127">`IHostAssemblyStore` enthält Methoden, die einen Host zum Binden an Assemblys und Modulen unabhängig von der CLR zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-127">`IHostAssemblyStore` provides methods that allow a host to bind to assemblies and modules independently of the CLR.</span></span> <span data-ttu-id="9ee7d-128">Hosts stellen normalerweise die Assembly speichert, um die Assemblys aus Zertifikatformate als das Dateisystem geladen werden können.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-128">Hosts typically provide assembly stores to allow assemblies to be loaded from formats other than the file system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9ee7d-129">Wenn der Host keine implementiert `IHostAssemblyStore`, `GetAssemblyStore` E_NOINTERFACE HRESULT-Wert zurückgeben und sollte festgelegt `ppAssemblyStore` auf Null.</span><span class="sxs-lookup"><span data-stu-id="9ee7d-129">If the host does not implement `IHostAssemblyStore`, `GetAssemblyStore` should return an HRESULT value of E_NOINTERFACE, and should set `ppAssemblyStore` to null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ee7d-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ee7d-130">Requirements</span></span>  
 <span data-ttu-id="9ee7d-131">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ee7d-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ee7d-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ee7d-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ee7d-133">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="9ee7d-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9ee7d-134">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ee7d-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ee7d-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ee7d-135">See also</span></span>

- [<span data-ttu-id="9ee7d-136">IHostAssemblyManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ee7d-136">IHostAssemblyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)
- [<span data-ttu-id="9ee7d-137">IHostAssemblyStore-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ee7d-137">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
