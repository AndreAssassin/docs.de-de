---
title: ICorDebugNativeFrame::SetIP-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.SetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::SetIP
helpviewer_keywords:
- ICorDebugNativeFrame::SetIP method [.NET Framework debugging]
- SetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
ms.assetid: 57784a51-c76d-48f8-9392-584d0e1946d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bc442e0bcd8d392041284269e46821e0642d0891
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67765883"
---
# <a name="icordebugnativeframesetip-method"></a><span data-ttu-id="c2035-102">ICorDebugNativeFrame::SetIP-Methode</span><span class="sxs-lookup"><span data-stu-id="c2035-102">ICorDebugNativeFrame::SetIP Method</span></span>
<span data-ttu-id="c2035-103">Legt den Anweisungszeiger auf die angegebenen Offsetposition in systemeigenem Code fest.</span><span class="sxs-lookup"><span data-stu-id="c2035-103">Sets the instruction pointer to the specified offset location in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2035-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c2035-104">Syntax</span></span>  
  
```cpp  
HRESULT SetIP (  
    [in] ULONG32 nOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2035-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c2035-105">Parameters</span></span>  
 `nOffset`  
 <span data-ttu-id="c2035-106">[in] Die Offsetposition im nativen Code.</span><span class="sxs-lookup"><span data-stu-id="c2035-106">[in] The offset location in the native code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2035-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c2035-107">Remarks</span></span>  
 <span data-ttu-id="c2035-108">Aufrufe von `SetIP` direkt für ungültig erklären alle Rahmen und Ketten für den aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="c2035-108">Calls to `SetIP` immediately invalidate all frames and chains for the current thread.</span></span> <span data-ttu-id="c2035-109">Wenn der Debugger die Frame-Informationen nach einem Aufruf von benötigt `SetIP`, müssen sie eine neue stapelüberwachung ausführen.</span><span class="sxs-lookup"><span data-stu-id="c2035-109">If the debugger needs frame information after a call to `SetIP`, it must perform a new stack trace.</span></span>  
  
 <span data-ttu-id="c2035-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) wird versucht, den Stapelrahmen in einem gültigen Zustand zu halten.</span><span class="sxs-lookup"><span data-stu-id="c2035-110">[ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md) will attempt to keep the stack frame in a valid state.</span></span> <span data-ttu-id="c2035-111">Allerdings auch, wenn der Frame in einem gültigen Zustand ist, als die Runtime geht, gibt es immer noch möglicherweise Probleme, z. B. nicht initialisierten lokalen Variablen und So weiter.</span><span class="sxs-lookup"><span data-stu-id="c2035-111">However, even if the frame is in a valid state, as far as the runtime is concerned, there still may be problems, such as uninitialized local variables, and so on.</span></span> <span data-ttu-id="c2035-112">Der Aufrufer ist verantwortlich für die Kohärenz des laufenden Programms.</span><span class="sxs-lookup"><span data-stu-id="c2035-112">The caller is responsible for insuring coherency of the running program.</span></span>  
  
 <span data-ttu-id="c2035-113">Auf 64-Bit-Plattformen kann nicht von der Anweisungszeiger verschoben werden eine `catch` oder `finally` Block.</span><span class="sxs-lookup"><span data-stu-id="c2035-113">On 64-bit platforms, the instruction pointer cannot be moved out of a `catch` or `finally` block.</span></span> <span data-ttu-id="c2035-114">Wenn `SetIP` wird aufgerufen, um eine solche Verschiebung auf einer 64-Bit-Plattform zu machen, wird einen HRESULT-Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c2035-114">If `SetIP` is called to make such a move on a 64-bit platform, it will return an HRESULT indicating failure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2035-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c2035-115">Requirements</span></span>  
 <span data-ttu-id="c2035-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2035-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2035-117">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c2035-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2035-118">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2035-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2035-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2035-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2035-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c2035-120">See also</span></span>
