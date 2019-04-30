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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a553f2cbac6110e82803e6d0dd872cfaa15d773
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987830"
---
# <a name="icordebugnativeframe2ismatchingparentframe-method"></a><span data-ttu-id="663df-102">ICorDebugNativeFrame2::IsMatchingParentFrame-Methode</span><span class="sxs-lookup"><span data-stu-id="663df-102">ICorDebugNativeFrame2::IsMatchingParentFrame Method</span></span>
<span data-ttu-id="663df-103">Bestimmt, ob der angegebene Rahmen um das übergeordnete Element des aktuellen Frames ist.</span><span class="sxs-lookup"><span data-stu-id="663df-103">Determines whether the specified frame is the parent of the current frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="663df-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="663df-104">Syntax</span></span>  
  
```  
HRESULT IsMatchingParentFrame([in] ICorDebugNativeFrame2  
                                      *pPotentialParentFrame,  
                              [out] BOOL *pIsParent);  
```  
  
## <a name="parameters"></a><span data-ttu-id="663df-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="663df-105">Parameters</span></span>  
 `pPotentialParentFrame`  
 <span data-ttu-id="663df-106">[in] Ein Zeiger auf den Frameobjekt, das Sie für den übergeordneten Status auswerten möchten.</span><span class="sxs-lookup"><span data-stu-id="663df-106">[in] A pointer to the frame object that you want to evaluate for parent status.</span></span>  
  
 `pIsParent`  
 <span data-ttu-id="663df-107">[out] `true` Wenn `pPotentialParentFrame` ist der aktuelle Frame übergeordnete Element ist, andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="663df-107">[out] `true` if `pPotentialParentFrame` is the current frame’s parent; otherwise, `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="663df-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="663df-108">Return Value</span></span>  
 <span data-ttu-id="663df-109">Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.</span><span class="sxs-lookup"><span data-stu-id="663df-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="663df-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="663df-110">HRESULT</span></span>|<span data-ttu-id="663df-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="663df-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="663df-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="663df-112">S_OK</span></span>|<span data-ttu-id="663df-113">Der übergeordnete Status wurden erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="663df-113">The parent status was successfully returned.</span></span>|  
|<span data-ttu-id="663df-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="663df-114">E_FAIL</span></span>|<span data-ttu-id="663df-115">Der übergeordnete Status konnte nicht zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="663df-115">The parent status could not be returned.</span></span>|  
|<span data-ttu-id="663df-116">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="663df-116">E_INVALIDARG</span></span>|<span data-ttu-id="663df-117">`pPotentialParentFrame` oder `pIsParent` ist NULL.</span><span class="sxs-lookup"><span data-stu-id="663df-117">`pPotentialParentFrame` or `pIsParent` is null.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="663df-118">Ausnahmen</span><span class="sxs-lookup"><span data-stu-id="663df-118">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="663df-119">Hinweise</span><span class="sxs-lookup"><span data-stu-id="663df-119">Remarks</span></span>  
 <span data-ttu-id="663df-120">`IsMatchingParentFrame` Gibt `true` ist das Frame-Objekt, das Sie an die Methode übergeben, das übergeordnete Element des Frame-Objekts auf dem die Methode wurde aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="663df-120">`IsMatchingParentFrame` returns `true` if the frame object you pass to the method is the parent of the frame object on which the method was called.</span></span> <span data-ttu-id="663df-121">Wenn Sie die Methode für einen Frame, die nicht auf ein untergeordnetes Element des angegebenen Rahmens ist aufrufen, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="663df-121">If you call the method on a frame that is not a child of the specified frame, it returns an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="663df-122">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="663df-122">Requirements</span></span>  
 <span data-ttu-id="663df-123">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="663df-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="663df-124">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="663df-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="663df-125">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="663df-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="663df-126">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="663df-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="663df-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="663df-127">See also</span></span>

- [<span data-ttu-id="663df-128">ICorDebugNativeFrame2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="663df-128">ICorDebugNativeFrame2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugnativeframe2-interface.md)
- [<span data-ttu-id="663df-129">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="663df-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="663df-130">Debuggen</span><span class="sxs-lookup"><span data-stu-id="663df-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
