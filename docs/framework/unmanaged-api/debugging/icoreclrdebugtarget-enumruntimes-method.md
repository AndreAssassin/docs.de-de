---
title: ICoreClrDebugTarget::EnumRuntimes-Methode
ms.date: 03/30/2017
api_name:
- ICoreClrDebugTarget.EnumRuntimes
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- ICoreClrDebugTarget::EnumRuntimes
helpviewer_keywords:
- remote debugging API [Silverlight]
- ICorClrDebugTarget::EnumRuntimes method [Silverlight debugging]
- EnumRuntimes method, ICoreClrDebugTarget interface [Silverlight debugging]
- Silverlight, remote debugging
ms.assetid: 316df866-442d-40cc-b049-45e8adcb65d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: afb31646d21ec7e15f79601f5fe83ea6ce44fa90
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134677"
---
# <a name="icoreclrdebugtargetenumruntimes-method"></a><span data-ttu-id="b08e0-102">ICoreClrDebugTarget::EnumRuntimes-Methode</span><span class="sxs-lookup"><span data-stu-id="b08e0-102">ICoreClrDebugTarget::EnumRuntimes Method</span></span>
<span data-ttu-id="b08e0-103">Listet die CLR-Laufzeiten (Common Language Runtime) im angegebenen Prozess auf, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b08e0-103">Enumerates the common language runtimes (CLRs) in the specified process that is running on a remote computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b08e0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b08e0-104">Syntax</span></span>  
  
```  
HRESULT EnumRuntimes (  
      [in] DWORD       dwInternalProcessID,  
      [out] DWORD*     pcRuntimes,  
      [out] CoreClrDebugRuntimeInfo**    ppRuntimes  
    );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b08e0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b08e0-105">Parameters</span></span>  
 `dwInternalProcessID`  
 <span data-ttu-id="b08e0-106">[in] Die interne Prozess-ID des Prozesses, für den Laufzeiten aufgelistet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b08e0-106">[in] The internal process ID of the process for which you want to enumerate runtimes.</span></span> <span data-ttu-id="b08e0-107">Dies `m_dwInternalID` aus der entsprechenden [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span><span class="sxs-lookup"><span data-stu-id="b08e0-107">This will be `m_dwInternalID` from the corresponding [CoreClrDebugProcInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugprocinfo-structure.md).</span></span>  
  
 `pcRuntimes`  
 <span data-ttu-id="b08e0-108">[out] Die Anzahl der in `ppRuntimes` zurückgegebenen Laufzeiten.</span><span class="sxs-lookup"><span data-stu-id="b08e0-108">[out] The number of runtimes returned in `ppRuntimes`.</span></span> <span data-ttu-id="b08e0-109">Dieser Wert kann 0 (null) sein.</span><span class="sxs-lookup"><span data-stu-id="b08e0-109">This value can be 0 (zero).</span></span>  
  
 `ppRuntimes`  
 <span data-ttu-id="b08e0-110">[out] Ein Array von [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) Strukturen, die Laufzeiten darstellen, die in der remote-Zielprozess geladen.</span><span class="sxs-lookup"><span data-stu-id="b08e0-110">[out] An array of [CoreClrDebugRuntimeInfo](../../../../docs/framework/unmanaged-api/debugging/coreclrdebugruntimeinfo-structure.md) structures that represent the runtimes loaded in the remote target process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b08e0-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b08e0-111">Return Value</span></span>  
 <span data-ttu-id="b08e0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b08e0-112">S_OK</span></span>  
 <span data-ttu-id="b08e0-113">Erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="b08e0-113">Success.</span></span>  
  
 <span data-ttu-id="b08e0-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b08e0-114">S_FALSE</span></span>  
 `dwInternalProcessID` <span data-ttu-id="b08e0-115">entspricht keiner Prozess, der auf dem Computer ausgeführt wird wahrscheinlich weil der Prozess beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="b08e0-115">does not match any process that is running on the computer, probably because the process was terminated.</span></span> `pcRuntimes` <span data-ttu-id="b08e0-116">und `ppRuntimes` NULL.</span><span class="sxs-lookup"><span data-stu-id="b08e0-116">and `ppRuntimes` will be null.</span></span>  
  
 <span data-ttu-id="b08e0-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="b08e0-117">E_OUTOFMEMORY</span></span>  
 <span data-ttu-id="b08e0-118">Für `ppRuntimes` kann nicht genug Arbeitsspeicher zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="b08e0-118">Unable to allocate enough memory for `ppRuntimes`.</span></span>  
  
 <span data-ttu-id="b08e0-119">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="b08e0-119">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="b08e0-120">Andere Fehler.</span><span class="sxs-lookup"><span data-stu-id="b08e0-120">Other failures.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b08e0-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b08e0-121">Remarks</span></span>  
 <span data-ttu-id="b08e0-122">Um den Arbeitsspeicher freizugeben, der von dieser Methode belegt wurde, rufen Sie die [ICoreClrDebugTarget:: FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="b08e0-122">To free the memory that was allocated by this method, call the [ICoreClrDebugTarget::FreeMemory](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-freememory-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b08e0-123">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b08e0-123">Requirements</span></span>  
 <span data-ttu-id="b08e0-124">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b08e0-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b08e0-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="b08e0-125">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b08e0-126">**Bibliothek:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b08e0-126">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b08e0-127">**.NET Framework-Versionen:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b08e0-127">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b08e0-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b08e0-128">See also</span></span>

- [<span data-ttu-id="b08e0-129">ICoreClrDebugTarget-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b08e0-129">ICoreClrDebugTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md)
