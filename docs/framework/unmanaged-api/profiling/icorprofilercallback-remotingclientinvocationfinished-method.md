---
title: ICorProfilerCallback::RemotingClientInvocationFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RemotingClientInvocationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RemotingClientInvocationFinished
helpviewer_keywords:
- RemotingClientInvocationFinished method [.NET Framework profiling]
- ICorProfilerCallback::RemotingClientInvocationFinished method [.NET Framework profiling]
ms.assetid: ea4b283b-1210-4f41-a7a2-c398b1adde4e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2722497db5622dee4adcfd9381837477b89a8f63
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041885"
---
# <a name="icorprofilercallbackremotingclientinvocationfinished-method"></a><span data-ttu-id="e34c1-102">ICorProfilerCallback::RemotingClientInvocationFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="e34c1-102">ICorProfilerCallback::RemotingClientInvocationFinished Method</span></span>
<span data-ttu-id="e34c1-103">Benachrichtigt den Profiler an, dass ein Remoteaufrufs bis zum Abschluss, auf dem Client ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="e34c1-103">Notifies the profiler that a remoting call has run to completion on the client.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e34c1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e34c1-104">Syntax</span></span>  
  
```  
HRESULT RemotingClientInvocationFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e34c1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e34c1-105">Remarks</span></span>  
 <span data-ttu-id="e34c1-106">Wenn der Remotingaufruf für synchrone war, hat es auch auf dem Server bis zum Abschluss ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e34c1-106">If the remoting call was synchronous, it has also run to completion on the server.</span></span> <span data-ttu-id="e34c1-107">Wenn der Remotingaufruf für asynchrone war, ggf. eine Antwort immer noch erwartet werden, wenn der Aufruf verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e34c1-107">If the remoting call was asynchronous, a reply might still be expected when the call is handled.</span></span> <span data-ttu-id="e34c1-108">Wenn eine Antwort erwartet wird, wird er als Aufruf auftreten [ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und einen zusätzlichen Aufruf `RemotingClientInvocationFinished` an die sekundären erforderliche Verarbeitung eines asynchronen Aufrufs.</span><span class="sxs-lookup"><span data-stu-id="e34c1-108">If a reply is expected, it will occur as a call to [ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and an additional call to `RemotingClientInvocationFinished` to indicate the required secondary processing of an asynchronous call.</span></span>  
  
 <span data-ttu-id="e34c1-109">Jedes der folgenden Paare von Rückrufen wird auf dem gleichen Thread erfolgen:</span><span class="sxs-lookup"><span data-stu-id="e34c1-109">Each of the following pairs of callbacks will occur on the same thread:</span></span>  
  
- <span data-ttu-id="e34c1-110">`RemotingClientInvocationStarted` und [ICorProfilerCallback:: RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span><span class="sxs-lookup"><span data-stu-id="e34c1-110">`RemotingClientInvocationStarted` and [ICorProfilerCallback::RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)</span></span>  
  
- <span data-ttu-id="e34c1-111">[ICorProfilerCallback:: RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) und [ICorProfilerCallback:: RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span><span class="sxs-lookup"><span data-stu-id="e34c1-111">[ICorProfilerCallback::RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md) and [ICorProfilerCallback::RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)</span></span>  
  
- <span data-ttu-id="e34c1-112">[ICorProfilerCallback:: RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) und [ICorProfilerCallback:: RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span><span class="sxs-lookup"><span data-stu-id="e34c1-112">[ICorProfilerCallback::RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md) and [ICorProfilerCallback::RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)</span></span>  
  
 <span data-ttu-id="e34c1-113">Sie sollten die folgenden Probleme mit den Remotingrückrufen bewusst sein:</span><span class="sxs-lookup"><span data-stu-id="e34c1-113">You should be aware of the following issues with the remoting callbacks:</span></span>  
  
- <span data-ttu-id="e34c1-114">Ausführung einer Remotingfunktion wird nicht widergespiegelt, durch den Profiler-API, damit Benachrichtigungen für Funktionen, die vom Client aufgerufen und ausgeführt wird, auf dem Server nicht ordnungsgemäß empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="e34c1-114">Execution of a remoting function is not reflected by the profiler API, so notifications for functions that are called from the client and executed on the server are not properly received.</span></span> <span data-ttu-id="e34c1-115">Der eigentliche Aufruf erfolgt über einen Proxy-Objekt; um den Profiler wird es angezeigt, dass bestimmte Funktionen JIT-kompiliert, aber nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e34c1-115">The actual invocation happens via a proxy object; to the profiler, it appears that certain functions are JIT-compiled but never used.</span></span>  
  
- <span data-ttu-id="e34c1-116">Der Profiler erhalten Sie keine genaue Benachrichtigungen für asynchrones Remoting-Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="e34c1-116">The profiler does not receive accurate notifications for asynchronous remoting events.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e34c1-117">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e34c1-117">Requirements</span></span>  
 <span data-ttu-id="e34c1-118">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e34c1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e34c1-119">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e34c1-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e34c1-120">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e34c1-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e34c1-121">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e34c1-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e34c1-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e34c1-122">See also</span></span>

- [<span data-ttu-id="e34c1-123">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e34c1-123">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
