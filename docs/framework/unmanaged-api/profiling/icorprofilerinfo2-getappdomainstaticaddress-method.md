---
title: ICorProfilerInfo2::GetAppDomainStaticAddress-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e68178a71d7ba73b4956a7d23854c23300301d8e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67747862"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a><span data-ttu-id="bd5bc-102">ICorProfilerInfo2::GetAppDomainStaticAddress-Methode</span><span class="sxs-lookup"><span data-stu-id="bd5bc-102">ICorProfilerInfo2::GetAppDomainStaticAddress Method</span></span>
<span data-ttu-id="bd5bc-103">Ruft die Adresse des angegebenen Anwendung Domäne statischen Felds, das im Bereich der angegebenen Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-103">Gets the address of the specified application domain-static field that is in the scope of the specified application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd5bc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd5bc-104">Syntax</span></span>  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd5bc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd5bc-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="bd5bc-106">[in] Die Klassen-ID der Klasse, die die angeforderte Domäne statischen Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-106">[in] The class ID of the class that contains the requested application domain-static field.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="bd5bc-107">[in] Das Metadatentoken für die angeforderte Domäne statischen Feld.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-107">[in] The metadata token for the requested application domain-static field.</span></span>  
  
 `appDomainId`  
 <span data-ttu-id="bd5bc-108">[in] Die ID der Anwendungsdomäne, die den Bereich für die angeforderte statische Feld.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-108">[in] The ID of the application domain that is the scope for the requested static field.</span></span>  
  
 `ppAddress`  
 <span data-ttu-id="bd5bc-109">[out] Ein Zeiger auf die Adresse eines statischen Felds, das innerhalb der angegebenen Anwendungsdomäne ist.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-109">[out] A pointer to the address of the static field that is within the specified application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bd5bc-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bd5bc-110">Remarks</span></span>  
 <span data-ttu-id="bd5bc-111">Die `GetAppDomainStaticAddress` Methode gibt möglicherweise einen der folgenden zurück:</span><span class="sxs-lookup"><span data-stu-id="bd5bc-111">The `GetAppDomainStaticAddress` method may return one of the following:</span></span>  
  
- <span data-ttu-id="bd5bc-112">Ein HRESULT CORPROF_E_DATAINCOMPLETE, wenn das angegebene statische Feld eine Adresse im angegebenen Kontext nicht zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-112">A CORPROF_E_DATAINCOMPLETE HRESULT if the given static field has not been assigned an address in the specified context.</span></span>  
  
- <span data-ttu-id="bd5bc-113">Die Adressen von Objekten, die möglicherweise in die Garbage Collection-Heap.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-113">The addresses of objects that may be in the garbage collection heap.</span></span> <span data-ttu-id="bd5bc-114">Diese Adressen können nach der Garbagecollection, ungültig werden. daher nach der Garbagecollection, Profiler nicht davon auszugehen, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-114">These addresses may become invalid after garbage collection, so after garbage collection, profilers should not assume that they are valid.</span></span>  
  
 <span data-ttu-id="bd5bc-115">Vor dem Abschluss einer Klasse Klassenkonstruktor `GetAppDomainStaticAddress` CORPROF_E_DATAINCOMPLETE zurück für alle seine statische Felder, obwohl einige der statischen Felder bereits initialisiert werden kann und rooting-Garbage Collection-Objekten.</span><span class="sxs-lookup"><span data-stu-id="bd5bc-115">Before a class’s class constructor is completed, `GetAppDomainStaticAddress` will return CORPROF_E_DATAINCOMPLETE for all its static fields, although some of the static fields may already be initialized and rooting garbage collection objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd5bc-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd5bc-116">Requirements</span></span>  
 <span data-ttu-id="bd5bc-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd5bc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd5bc-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bd5bc-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bd5bc-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd5bc-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd5bc-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd5bc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd5bc-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd5bc-121">See also</span></span>

- [<span data-ttu-id="bd5bc-122">ICorProfilerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5bc-122">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="bd5bc-123">ICorProfilerInfo2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd5bc-123">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
