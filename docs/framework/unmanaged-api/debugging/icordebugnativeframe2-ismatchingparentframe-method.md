---
title: ICorDebugNativeFrame2::IsMatchingParentFrame-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame2.IsMatchingParentFrame Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame2::IsMatchingParentFrame
helpviewer_keywords:
- IsMatchingParentFrame method [.NET Framework debugging]
- ICorDebugNativeFrame2::IsMatchingParentFrame method [.NET Framework debugging]
ms.assetid: d2ca20db-df22-4528-a0dd-a09ea62c8998
topic_type:
- apiref
ms.openlocfilehash: aa06b7db6b7371e66853ed242f5e118fb5e5ff0c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096201"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="d26d9-102">ICorDebugNativeFrame2::IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="d26d9-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="d26d9-103">Bestimmt, ob der angegebene Frame dem aktuellen Frame übergeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="d26d9-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d26d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d26d9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d26d9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d26d9-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="d26d9-106">in Ein Zeiger auf das Frame Objekt, das Sie für den übergeordneten Status auswerten möchten.</span><span class="sxs-lookup"><span data-stu-id="d26d9-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="d26d9-107">[out] `true`, wenn `pPotentialParentFrame` das übergeordnete Element des aktuellen Frames ist. Andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="d26d9-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d26d9-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d26d9-108">Return Value</span></span>  
 <span data-ttu-id="d26d9-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="d26d9-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d26d9-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d26d9-110">HRESULT</span></span>|<span data-ttu-id="d26d9-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d26d9-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d26d9-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="d26d9-112">S_OK</span></span>|<span data-ttu-id="d26d9-113">Der übergeordnete Status wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d26d9-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="d26d9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d26d9-114">E_FAIL</span></span>|<span data-ttu-id="d26d9-115">Der übergeordnete Status konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d26d9-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="d26d9-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d26d9-116">E_INVALIDARG</span></span>|<span data-ttu-id="d26d9-117">`pPotentialParentFrame` oder `pIsParent` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="d26d9-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="d26d9-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="d26d9-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d26d9-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d26d9-119">Remarks</span></span>  
 <span data-ttu-id="d26d9-120">`IsMatchingParentFrame` gibt `true` zurück, wenn das Frame Objekt, das Sie an die Methode übergeben, das übergeordnete Element des Frame Objekts ist, für das die Methode aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="d26d9-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="d26d9-121">Wenn Sie die-Methode für einen Frame aufzurufen, der kein untergeordnetes Element des angegebenen Frames ist, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d26d9-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d26d9-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d26d9-122">Requirements</span></span>  
 <span data-ttu-id="d26d9-123">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d26d9-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d26d9-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d26d9-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d26d9-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d26d9-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d26d9-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d26d9-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d26d9-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d26d9-127">See also</span></span>

- [<span data-ttu-id="d26d9-128">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d26d9-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="d26d9-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d26d9-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="d26d9-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d26d9-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
