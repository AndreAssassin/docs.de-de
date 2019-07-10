---
title: IHostMemoryManager::VirtualProtect-Methode
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1aa4ab44fc8ef1033dcef1a9b36d7487da86cd58
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779353"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="21b6f-102">IHostMemoryManager::VirtualProtect-Methode</span><span class="sxs-lookup"><span data-stu-id="21b6f-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="21b6f-103">Dient als ein logischer Wrapper für die entsprechenden Win32-Funktion.</span><span class="sxs-lookup"><span data-stu-id="21b6f-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="21b6f-104">Die Win32-Implementierung von `VirtualProtect` ändert den Schutz in einem Bereich der Seiten im virtuellen Adressraum des aufrufenden Prozesses, die ein Commit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="21b6f-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21b6f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="21b6f-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="21b6f-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="21b6f-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="21b6f-107">[in] Ein Zeiger auf die Basisadresse des virtuellen Speichers, deren Schutzattribute sind geändert werden.</span><span class="sxs-lookup"><span data-stu-id="21b6f-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="21b6f-108">[in] Die Größe in Bytes des Bereichs der Seiten im Arbeitsspeicher geändert werden.</span><span class="sxs-lookup"><span data-stu-id="21b6f-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="21b6f-109">[in] Der Typ des Speicherschutzes angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="21b6f-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="21b6f-110">[out] Ein Zeiger auf den Wert des vorherigen Arbeitsspeichers Schutz.</span><span class="sxs-lookup"><span data-stu-id="21b6f-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21b6f-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21b6f-111">Return Value</span></span>  
  
|<span data-ttu-id="21b6f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21b6f-112">HRESULT</span></span>|<span data-ttu-id="21b6f-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21b6f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21b6f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="21b6f-114">S_OK</span></span>|<span data-ttu-id="21b6f-115">`VirtualProtect` wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="21b6f-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="21b6f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="21b6f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21b6f-117">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen wurde, oder die CLR ist in einem Zustand, in dem nicht verwalteten Code ausführen oder den Aufruf erfolgreich zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="21b6f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21b6f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21b6f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21b6f-119">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="21b6f-119">The call timed out.</span></span>|  
|<span data-ttu-id="21b6f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21b6f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21b6f-121">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="21b6f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21b6f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21b6f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21b6f-123">Ein Ereignis wurde abgebrochen, während sich der blockierte Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="21b6f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21b6f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21b6f-124">E_FAIL</span></span>|<span data-ttu-id="21b6f-125">Ein Unbekannter Schwerwiegender Fehler ist aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="21b6f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21b6f-126">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr im Prozess verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21b6f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21b6f-127">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="21b6f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21b6f-128">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21b6f-128">Remarks</span></span>  
 <span data-ttu-id="21b6f-129">Diese Implementierung der `VirtualProtect` einen HRESULT-Wert, während die Win32-Implementierung einen Wert ungleich Null zum Erfolg zurückgibt und einen Nullwert, während ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="21b6f-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="21b6f-130">Weitere Informationen finden Sie in der Dokumentation zur Windows-Plattform.</span><span class="sxs-lookup"><span data-stu-id="21b6f-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21b6f-131">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21b6f-131">Requirements</span></span>  
 <span data-ttu-id="21b6f-132">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21b6f-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21b6f-133">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21b6f-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21b6f-134">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="21b6f-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21b6f-135">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21b6f-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21b6f-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21b6f-136">See also</span></span>

- [<span data-ttu-id="21b6f-137">IHostMemoryManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21b6f-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
