---
title: ICorDebugEval::GetThread-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 64cc5b6e7c6fe44080b35dc07f029ad311b88ca7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989052"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="eff27-102">ICorDebugEval::GetThread-Methode</span><span class="sxs-lookup"><span data-stu-id="eff27-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="eff27-103">Ruft den Thread, in dem diese Auswertung ausgeführt wird, oder ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eff27-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eff27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eff27-104">Syntax</span></span>  
  
```  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eff27-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eff27-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="eff27-106">[out] Ein Zeiger auf die Adresse des ein ICorDebugThread-Objekt, das den Thread darstellt.</span><span class="sxs-lookup"><span data-stu-id="eff27-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eff27-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eff27-107">Requirements</span></span>  
 <span data-ttu-id="eff27-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eff27-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eff27-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="eff27-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="eff27-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eff27-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eff27-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eff27-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
