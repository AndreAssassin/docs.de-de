---
title: ICLRTask2::EndPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 60997717baf70e10366e7f0ba6a06daa1f35f8cd
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121666"
---
# <a name="iclrtask2endpreventasyncabort-method"></a><span data-ttu-id="51b75-102">ICLRTask2::EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="51b75-102">ICLRTask2::EndPreventAsyncAbort Method</span></span>
<span data-ttu-id="51b75-103">Ermöglicht, dass neue oder bricht ausstehende Thread Abort-Anforderungen zu einer Thread ab, für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="51b75-103">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51b75-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="51b75-104">Syntax</span></span>  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="51b75-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="51b75-105">Return Value</span></span>  
 <span data-ttu-id="51b75-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51b75-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="51b75-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51b75-107">HRESULT</span></span>|<span data-ttu-id="51b75-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="51b75-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51b75-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="51b75-109">S_OK</span></span>|<span data-ttu-id="51b75-110">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="51b75-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="51b75-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="51b75-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="51b75-112">Die Methode wurde in einem Thread aufgerufen, die nicht der aktuelle Thread ist.</span><span class="sxs-lookup"><span data-stu-id="51b75-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51b75-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="51b75-113">Remarks</span></span>  
 <span data-ttu-id="51b75-114">Aufrufen von dieser Methode verringert die Verzögerung Threadabbruchs Leistungsindikator für den aktuellen Thread um eins.</span><span class="sxs-lookup"><span data-stu-id="51b75-114">Calling this method decrements the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="51b75-115">Aufrufe von [ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) und `EndPreventAsyncAbort` können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="51b75-115">Calls to [ICLRTask2::BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="51b75-116">Solange der Zähler größer als 0 (null) ist, verzögert Threadabbrüche für den aktuellen Thread werden.</span><span class="sxs-lookup"><span data-stu-id="51b75-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="51b75-117">Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="51b75-117">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="51b75-118">Falsche Verwendung dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="51b75-118">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="51b75-119">Zum Beispiel der Aufruf `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn es zuvor von der virtuellen Computer erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="51b75-119">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="51b75-120">Auf ähnliche Weise wird der interne Zähler nicht auf Überläufe überprüft.</span><span class="sxs-lookup"><span data-stu-id="51b75-120">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="51b75-121">Wenn es die ganzzahligen Grenzwert überschreitet, da er sowohl auf dem Host und auf dem virtuellen Computer um eins erhöht wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="51b75-121">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51b75-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="51b75-122">Requirements</span></span>  
 <span data-ttu-id="51b75-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51b75-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51b75-124">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="51b75-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="51b75-125">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="51b75-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51b75-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51b75-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b75-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="51b75-127">See also</span></span>

- [<span data-ttu-id="51b75-128">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="51b75-128">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)
- [<span data-ttu-id="51b75-129">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51b75-129">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="51b75-130">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51b75-130">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="51b75-131">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51b75-131">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="51b75-132">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="51b75-132">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="51b75-133">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="51b75-133">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
