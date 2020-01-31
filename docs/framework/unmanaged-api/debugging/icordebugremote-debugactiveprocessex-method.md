---
title: ICorDebugRemote::DebugActiveProcessEx-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugRemote.DebugActiveProcessEx
api_location:
- CorDebug.dll
api_type:
- COM
f1_keywords:
- ICorDebugRemoteTarget::DebugActiveProcessEx
helpviewer_keywords:
- ICorDebugRemote::DebugActiveProcessEx method [.NET Framework debugging]
- DebugActiveProcessEx method, ICorDebugRemote interface [.NET Framework debugging]
ms.assetid: b0df5c5d-9a2e-47bf-894c-6f8a9fe24a1f
topic_type:
- apiref
ms.openlocfilehash: b78bff2994cefc6c35a4bd59133338392c3a1b24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791971"
---
# <a name="icordebugremotedebugactiveprocessex-method"></a><span data-ttu-id="9ba82-102">ICorDebugRemote::DebugActiveProcessEx-Methode</span><span class="sxs-lookup"><span data-stu-id="9ba82-102">ICorDebugRemote::DebugActiveProcessEx Method</span></span>
<span data-ttu-id="9ba82-103">Startet einen Prozess auf einem Remote Computer unter dem Debugger.</span><span class="sxs-lookup"><span data-stu-id="9ba82-103">Launches a process on a remote machine under the debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ba82-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9ba82-104">Syntax</span></span>  
  
```cpp  
HRESULT DebugActiveProcessEx (  
    [in]  ICorDebugRemoteTarget *   pRemoteTarget,  
    [in]  DWORD                     dwProcessId,  
    [in]  BOOL                      fWin32Attach,  
    [out] ICorDebugProcess **       ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ba82-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9ba82-105">Parameters</span></span>  
 `pRemoteTarget`  
 <span data-ttu-id="9ba82-106">[in] Zeiger auf eine [ICorDebugRemoteTarget-Schnittstelle](icordebugremotetarget-interface.md).</span><span class="sxs-lookup"><span data-stu-id="9ba82-106">[in] Pointer to an [ICorDebugRemoteTarget Interface](icordebugremotetarget-interface.md).</span></span> <span data-ttu-id="9ba82-107">Dieser Parameter wird verwendet, um den Computer zu ermitteln, auf dem der Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="9ba82-107">This parameter is used to determine the machine on which the process is running.</span></span>  
  
 `id`  
 <span data-ttu-id="9ba82-108">in Die ID des Prozesses, an den der Debugger angefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9ba82-108">[in] The ID of the process to which the debugger is to be attached.</span></span>  
  
 `win32Attach`  
 <span data-ttu-id="9ba82-109">[in] `true`, wenn sich der Debugger als Win32-Debugger für den Prozessverhalten soll und die nicht verwalteten Rückrufe versendet. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="9ba82-109">[in] `true` if the debugger should behave as the Win32 debugger for the process and dispatch the unmanaged callbacks; otherwise, `false`.</span></span>  
  
 `ppProcess`  
 <span data-ttu-id="9ba82-110">vorgenommen Ein Zeiger auf die Adresse eines ICorDebugProcess-Objekts, das den Prozess darstellt, dem der Debugger angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="9ba82-110">[out] A pointer to the address of an "ICorDebugProcess" object that represents the process to which the debugger has been attached.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ba82-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9ba82-111">Return Value</span></span>  
 <span data-ttu-id="9ba82-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ba82-112">S_OK</span></span>  
 <span data-ttu-id="9ba82-113">Erfolgreich an den Prozess auf dem Remote Computer angefügt.</span><span class="sxs-lookup"><span data-stu-id="9ba82-113">Successfully attached to the process on the remote machine.</span></span>  
  
 <span data-ttu-id="9ba82-114">E_FAIL (oder andere E_-Rückgabecodes)</span><span class="sxs-lookup"><span data-stu-id="9ba82-114">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="9ba82-115">Das Anfügen an den Prozess auf dem Remote Computer ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="9ba82-115">Unable to attach to the process on the remote machine.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9ba82-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9ba82-116">Remarks</span></span>  
 <span data-ttu-id="9ba82-117">Das Debuggen im gemischten Modus wird in Silverlight nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9ba82-117">Mixed-mode debugging is not supported in Silverlight.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ba82-118">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9ba82-118">Requirements</span></span>  
 <span data-ttu-id="9ba82-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ba82-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ba82-120">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ba82-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ba82-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ba82-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ba82-122">**.NET Framework Versionen:** 4,5, 4, 3,5 SP1</span><span class="sxs-lookup"><span data-stu-id="9ba82-122">**.NET Framework Versions:** 4.5, 4, 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ba82-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9ba82-123">See also</span></span>

- [<span data-ttu-id="9ba82-124">ICorDebugRemote-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ba82-124">ICorDebugRemote Interface</span></span>](icordebugremote-interface.md)
- [<span data-ttu-id="9ba82-125">ICorDebug-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9ba82-125">ICorDebug Interface</span></span>](icordebug-interface.md)

- [<span data-ttu-id="9ba82-126">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="9ba82-126">Debugging Interfaces</span></span>](debugging-interfaces.md)
