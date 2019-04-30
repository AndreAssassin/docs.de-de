---
title: ICorDebugThread::GetProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetProcess
helpviewer_keywords:
- ICorDebugThread::GetProcess method [.NET Framework debugging]
- GetProcess method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 163816e7-0739-4566-b3df-cd256be8b8a4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46aa2ec5a282ef56f28d5fa0499571028e6602e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987030"
---
# <a name="icordebugthreadgetprocess-method"></a><span data-ttu-id="95b00-102">ICorDebugThread::GetProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="95b00-102">ICorDebugThread::GetProcess Method</span></span>
<span data-ttu-id="95b00-103">Ruft einen Schnittstellenzeiger an den Prozess, von dem diese ICorDebugThread Bestandteil, ab.</span><span class="sxs-lookup"><span data-stu-id="95b00-103">Gets an interface pointer to the process of which this ICorDebugThread forms a part.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95b00-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="95b00-104">Syntax</span></span>  
  
```  
HRESULT GetProcess (  
    [out] ICorDebugProcess   **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95b00-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="95b00-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="95b00-106">[out] Ein Zeiger auf die Adresse eines Objekts der ICorDebugProcess-Schnittstelle, die den Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="95b00-106">[out] A pointer to the address of an ICorDebugProcess interface object that represents the process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95b00-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="95b00-107">Requirements</span></span>  
 <span data-ttu-id="95b00-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="95b00-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95b00-109">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95b00-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95b00-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95b00-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95b00-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95b00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
