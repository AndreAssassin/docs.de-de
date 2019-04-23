---
title: ICorDebugManagedCallback::CreateProcess-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.CreateProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::CreateProcess
helpviewer_keywords:
- ICorDebugManagedCallback::CreateProcess method [.NET Framework debugging]
- CreateProcess method, ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: 8e89d5ee-e4e3-4738-8302-0b7d1cf4846e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eda214200ca4c3837ad89ed14887ef6b09af7d30
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59160367"
---
# <a name="icordebugmanagedcallbackcreateprocess-method"></a><span data-ttu-id="2df24-102">ICorDebugManagedCallback::CreateProcess-Methode</span><span class="sxs-lookup"><span data-stu-id="2df24-102">ICorDebugManagedCallback::CreateProcess Method</span></span>
<span data-ttu-id="2df24-103">Benachrichtigt den Debugger an, wenn ein Prozess angefügt oder zum ersten Mal gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2df24-103">Notifies the debugger when a process has been attached or started for the first time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df24-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2df24-104">Syntax</span></span>  
  
```  
HRESULT CreateProcess (  
    [in] ICorDebugProcess *pProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2df24-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2df24-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="2df24-106">[in] Ein Zeiger auf ein ICorDebugProcess-Objekt, das den Prozess darstellt, der angefügt oder gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2df24-106">[in] A pointer to an ICorDebugProcess object that represents the process that has been attached or started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2df24-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2df24-107">Remarks</span></span>  
 <span data-ttu-id="2df24-108">Diese Methode wird nicht aufgerufen werden, bis die common Language Runtime initialisiert ist.</span><span class="sxs-lookup"><span data-stu-id="2df24-108">This method is not called until the common language runtime is initialized.</span></span> <span data-ttu-id="2df24-109">Die meisten der [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) -Methoden geben CORDBG_E_NOTREADY vor der `CreateProcess` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="2df24-109">Most of the [ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) methods will return CORDBG_E_NOTREADY before the `CreateProcess` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2df24-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2df24-110">Requirements</span></span>  
 <span data-ttu-id="2df24-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2df24-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2df24-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2df24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2df24-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2df24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2df24-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2df24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2df24-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2df24-115">See also</span></span>

- [<span data-ttu-id="2df24-116">ICorDebugManagedCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2df24-116">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
