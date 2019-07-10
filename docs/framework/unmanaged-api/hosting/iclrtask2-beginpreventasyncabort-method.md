---
title: ICLRTask2::BeginPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 23ead080823ace1b091568108af8866dcbca14ec
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770265"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a><span data-ttu-id="dd3da-102">ICLRTask2::BeginPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="dd3da-102">ICLRTask2::BeginPreventAsyncAbort Method</span></span>
<span data-ttu-id="dd3da-103">Verzögerungen bei der neuer Thread abgebrochen werden Anforderungen von Threadabbrüche für den aktuellen Thread führt.</span><span class="sxs-lookup"><span data-stu-id="dd3da-103">Delays new thread abort requests from resulting in thread aborts on the current thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd3da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dd3da-104">Syntax</span></span>  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a><span data-ttu-id="dd3da-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="dd3da-105">Return Value</span></span>  
 <span data-ttu-id="dd3da-106">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd3da-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="dd3da-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="dd3da-107">HRESULT</span></span>|<span data-ttu-id="dd3da-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dd3da-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="dd3da-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="dd3da-109">S_OK</span></span>|<span data-ttu-id="dd3da-110">Die Methode wurde erfolgreich abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="dd3da-110">The method completed successfully.</span></span>|  
|<span data-ttu-id="dd3da-111">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="dd3da-111">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="dd3da-112">Die Methode wurde in einem Thread aufgerufen, die nicht der aktuelle Thread ist.</span><span class="sxs-lookup"><span data-stu-id="dd3da-112">The method was called on a thread which is not the current thread.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dd3da-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dd3da-113">Remarks</span></span>  
 <span data-ttu-id="dd3da-114">Das Aufrufen dieser Methode wird die Verzögerung Threadabbruchs Leistungsindikator für den aktuellen Thread um eins inkrementiert.</span><span class="sxs-lookup"><span data-stu-id="dd3da-114">Calling this method increments the delay-thread-abort counter for the current thread by one.</span></span>  
  
 <span data-ttu-id="dd3da-115">Aufrufe von `BeginPreventAsyncAbort` und [ICLRTask2:: EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) können geschachtelt werden.</span><span class="sxs-lookup"><span data-stu-id="dd3da-115">Calls to `BeginPreventAsyncAbort` and [ICLRTask2::EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) can be nested.</span></span> <span data-ttu-id="dd3da-116">Solange der Zähler größer als 0 (null) ist, verzögert Threadabbrüche für den aktuellen Thread werden.</span><span class="sxs-lookup"><span data-stu-id="dd3da-116">As long as the counter is greater than zero, thread aborts for the current thread are delayed.</span></span> <span data-ttu-id="dd3da-117">Wenn dieser Aufruf mit einem Aufruf von nicht paarweise angegeben, wird die `EndPreventAsyncAbort` -Methode, es ist möglich, einen Zustand zu erreichen, in welchem Thread Threadabbrüche für den aktuellen Thread nicht übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="dd3da-117">If this call is not paired with a call to the `EndPreventAsyncAbort` method, it is possible to reach a state in which thread aborts cannot be delivered to the current thread.</span></span>  
  
 <span data-ttu-id="dd3da-118">Die Verzögerung wird für einen Thread, der selbst abbricht, nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="dd3da-118">The delay is not honored for a thread that aborts itself.</span></span>  
  
 <span data-ttu-id="dd3da-119">Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet.</span><span class="sxs-lookup"><span data-stu-id="dd3da-119">The functionality that is exposed by this feature is used internally by the virtual machine (VM).</span></span> <span data-ttu-id="dd3da-120">Falsche Verwendung dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="dd3da-120">Misuse of these methods may cause unspecified behavior in the VM.</span></span> <span data-ttu-id="dd3da-121">Zum Beispiel der Aufruf `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn es zuvor von der virtuellen Computer erhöht wurde.</span><span class="sxs-lookup"><span data-stu-id="dd3da-121">For example, calling `EndPreventAsyncAbort` without first calling `BeginPreventAsyncAbort` could set the counter to zero when the VM has previously incremented it.</span></span> <span data-ttu-id="dd3da-122">Auf ähnliche Weise wird der interne Zähler nicht auf Überläufe überprüft.</span><span class="sxs-lookup"><span data-stu-id="dd3da-122">Similarly, the internal counter is not checked for overflow.</span></span> <span data-ttu-id="dd3da-123">Wenn es die ganzzahligen Grenzwert überschreitet, da er sowohl auf dem Host und auf dem virtuellen Computer um eins erhöht wird, ist das resultierende Verhalten nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="dd3da-123">If it exceeds its integral limit because it is incremented by both the host and the VM, the resulting behavior is unspecified.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd3da-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dd3da-124">Requirements</span></span>  
 <span data-ttu-id="dd3da-125">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd3da-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd3da-126">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dd3da-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dd3da-127">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="dd3da-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dd3da-128">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd3da-128">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3da-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd3da-129">See also</span></span>

- [<span data-ttu-id="dd3da-130">EndPreventAsyncAbort-Methode</span><span class="sxs-lookup"><span data-stu-id="dd3da-130">EndPreventAsyncAbort Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [<span data-ttu-id="dd3da-131">ICLRTask2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd3da-131">ICLRTask2 Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [<span data-ttu-id="dd3da-132">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd3da-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="dd3da-133">IHostTask-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd3da-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="dd3da-134">IHostTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dd3da-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [<span data-ttu-id="dd3da-135">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="dd3da-135">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
