---
title: ICorProfilerFunctionEnum::GetCount-Methode
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.GetCount Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::GetCount
helpviewer_keywords:
- ICorProfilerFunctionEnum::GetCount method [.NET Framework profiling]
- GetCount method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 62ec65e3-3e9d-400b-ae61-d24b8963995b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6403540f9641ce885edf2760370e35f48faf1f10
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780317"
---
# <a name="icorprofilerfunctionenumgetcount-method"></a><span data-ttu-id="e2791-102">ICorProfilerFunctionEnum::GetCount-Methode</span><span class="sxs-lookup"><span data-stu-id="e2791-102">ICorProfilerFunctionEnum::GetCount Method</span></span>
<span data-ttu-id="e2791-103">Ruft die Anzahl der Funktionen ab, die von der Anwendung oder erzwungen vom Profiler geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="e2791-103">Gets the number of functions that were loaded by the application or forcibly loaded by the profiler.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2791-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e2791-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount([out] ULONG * pcelt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2791-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e2791-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="e2791-106">[out] Die Anzahl der Funktionen, die geladen wurden.</span><span class="sxs-lookup"><span data-stu-id="e2791-106">[out] The number of functions that were loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2791-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e2791-107">Requirements</span></span>  
 <span data-ttu-id="e2791-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2791-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2791-109">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2791-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2791-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2791-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2791-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2791-111">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2791-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e2791-112">See also</span></span>

- [<span data-ttu-id="e2791-113">ICorProfilerFunctionEnum-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e2791-113">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="e2791-114">Profilerstellungsschnittstellen</span><span class="sxs-lookup"><span data-stu-id="e2791-114">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
