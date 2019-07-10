---
title: ICorProfilerCallback::AppDomainShutdownFinished-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e214af178972623bad3536565aa9bc51edc97260
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67763107"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="53e27-102">ICorProfilerCallback::AppDomainShutdownFinished-Methode</span><span class="sxs-lookup"><span data-stu-id="53e27-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="53e27-103">Benachrichtigt den Profiler an, eine Anwendungsdomäne von einem Prozess entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="53e27-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53e27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53e27-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53e27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53e27-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="53e27-106">[in] Identifiziert die Domäne, in der die Assemblys der Anwendung gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="53e27-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="53e27-107">[in] Ein HRESULT, der angibt, ob die Anwendungsdomäne erfolgreich entladen wurde.</span><span class="sxs-lookup"><span data-stu-id="53e27-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="53e27-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="53e27-108">Remarks</span></span>  
 <span data-ttu-id="53e27-109">Der Wert des `appDomainId` gilt nicht für eine informationsanforderung nach der [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) Methodenrückgabe.</span><span class="sxs-lookup"><span data-stu-id="53e27-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="53e27-110">Das Entladen der Anwendungsdomäne möglicherweise weiterhin nach den `AppDomainCreationFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="53e27-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="53e27-111">Fehler-HRESULT in `hrStatus` gibt einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="53e27-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="53e27-112">Allerdings einen HRESULT-Erfolg in `hrStatus` gibt nur an, dass der erste Teil des Entladen der Anwendungsdomäne erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="53e27-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53e27-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="53e27-113">Requirements</span></span>  
 <span data-ttu-id="53e27-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53e27-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53e27-115">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="53e27-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="53e27-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53e27-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53e27-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53e27-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53e27-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53e27-118">See also</span></span>

- [<span data-ttu-id="53e27-119">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53e27-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
