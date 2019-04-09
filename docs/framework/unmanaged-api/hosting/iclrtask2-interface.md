---
title: ICLRTask2-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518248651de6d8afdf25692c5f48da52b11eb0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172470"
---
# <a name="iclrtask2-interface"></a><span data-ttu-id="a7d39-102">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7d39-102">ICLRTask2 Interface</span></span>
<span data-ttu-id="a7d39-103">Bietet alle Funktionen des die [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle; darüber hinaus bietet Methoden, mit denen Threadabbrüche um verzögert werden, für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="a7d39-103">Provides all the functionality of the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface; in addition, provides methods that allow thread aborts to be delayed on the current thread.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7d39-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a7d39-104">Methods</span></span>  
  
|<span data-ttu-id="a7d39-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a7d39-105">Method</span></span>|<span data-ttu-id="a7d39-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a7d39-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7d39-107">BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="a7d39-107">BeginPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|<span data-ttu-id="a7d39-108">Verzögerungen bei der neuer Thread abgebrochen werden Anforderungen für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="a7d39-108">Delays new thread abort requests on the current thread.</span></span>|  
|[<span data-ttu-id="a7d39-109">EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="a7d39-109">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|<span data-ttu-id="a7d39-110">Ermöglicht, dass neue oder bricht ausstehende Thread Abort-Anforderungen zu einer Thread ab, für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="a7d39-110">Allows new or pending thread abort requests to result in thread aborts on the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7d39-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a7d39-111">Remarks</span></span>  
 <span data-ttu-id="a7d39-112">Die `ICLRTask2` Schnittstelle erbt die `ICLRTask` Schnittstelle und fügt die Methoden, die der Host verzögert Threadabbrüche, um einen Bereich von Code zu schützen, die nicht fehlschlagen darf.</span><span class="sxs-lookup"><span data-stu-id="a7d39-112">The `ICLRTask2` interface inherits the `ICLRTask` interface and adds methods that allow the host to delay thread aborts, to protect a region of code that must not fail.</span></span> <span data-ttu-id="a7d39-113">Aufrufen von `BeginPreventAsyncAbort` erhöht den Zähler Verzögerung Threadabbruchs für den aktuellen Thread aufrufen und `EndPreventAsyncAbort` verringert es.</span><span class="sxs-lookup"><span data-stu-id="a7d39-113">Calling `BeginPreventAsyncAbort` increments the delay-thread-abort counter for the current thread, and calling `EndPreventAsyncAbort` decrements it.</span></span> <span data-ttu-id="a7d39-114">Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="a7d39-114">Calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` can be nested.</span></span> <span data-ttu-id="a7d39-115">Solange der Zähler größer als 0 (null) ist, verzögert Threadabbrüche für den aktuellen Thread werden.</span><span class="sxs-lookup"><span data-stu-id="a7d39-115">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span>  
  
 <span data-ttu-id="a7d39-116">Wenn Aufrufe von `BeginPreventAsyncAbort` und `EndPreventAsyncAbort` sind nicht gekoppelt werden, es ist möglich, einen Zustand zu erreichen, in welchem Thread Threadabbrüche für den aktuellen Thread nicht übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="a7d39-116">If calls to `BeginPreventAsyncAbort` and `EndPreventAsyncAbort` are not paired, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="a7d39-117">Die Verzögerung wird für einen Thread, der selbst abbricht, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="a7d39-117">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="a7d39-118">Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="a7d39-118">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="a7d39-119">Falsche Verwendung dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="a7d39-119">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="a7d39-120">Zum Beispiel der Aufruf `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn es zuvor von der virtuellen Computer erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="a7d39-120">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="a7d39-121">Auf ähnliche Weise wird der interne Zähler nicht auf Überläufe überprüft.</span><span class="sxs-lookup"><span data-stu-id="a7d39-121">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="a7d39-122">Wenn es die ganzzahligen Grenzwert überschreitet, da er sowohl auf dem Host und auf dem virtuellen Computer um eins erhöht wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="a7d39-122">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
 <span data-ttu-id="a7d39-123">Für Informationen zu Elementen von geerbt `ICLRTask` und zur Verwendung dieser Schnittstelle, finden Sie unter den [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a7d39-123">For information about members inherited from `ICLRTask` and about the other uses of this interface, see the [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7d39-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a7d39-124">Requirements</span></span>  
 <span data-ttu-id="a7d39-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7d39-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7d39-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7d39-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7d39-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a7d39-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a7d39-128">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a7d39-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a7d39-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a7d39-129">See also</span></span>

- [<span data-ttu-id="a7d39-130">ICLRTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7d39-130">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="a7d39-131">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7d39-131">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="a7d39-132">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7d39-132">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="a7d39-133">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a7d39-133">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="a7d39-134">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a7d39-134">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
