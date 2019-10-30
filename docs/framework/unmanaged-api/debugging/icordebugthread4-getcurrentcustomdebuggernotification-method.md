---
title: ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.GetCurrentCustomDebuggerNotification Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::GetCurrentCustomDebuggerNotification
helpviewer_keywords:
- GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
- ICorDebugThread4::GetCurrentCustomDebuggerNotification method [.NET Framework debugging]
ms.assetid: 57e0f2d2-5f0e-4e2d-99ec-3f26632eb693
topic_type:
- apiref
ms.openlocfilehash: ba4375511fe7f5aaee032c4e132de54808041111
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122444"
---
# <a name="icordebugthread4getcurrentcustomdebuggernotification-method"></a><span data-ttu-id="44d77-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification-Methode</span><span class="sxs-lookup"><span data-stu-id="44d77-102">ICorDebugThread4::GetCurrentCustomDebuggerNotification Method</span></span>

<span data-ttu-id="44d77-103">Ruft das aktuelle [ICorDebugManagedCallback3:: CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) -Objekt für den aktuellen Thread ab.</span><span class="sxs-lookup"><span data-stu-id="44d77-103">Gets the current [ICorDebugManagedCallback3::CustomNotification](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback3-customnotification-method.md) object on the current thread.</span></span>

## <a name="syntax"></a><span data-ttu-id="44d77-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44d77-104">Syntax</span></span>

```cpp
HRESULT GetCurrentCustomDebuggerNotification(
    [out] ICorDebugValue **ppNotificationObject
    );
```

## <a name="parameters"></a><span data-ttu-id="44d77-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44d77-105">Parameters</span></span>

`ppNotificationObject`\
<span data-ttu-id="44d77-106">vorgenommen Ein Zeiger auf das aktuelle `ICorDebugManagedCallback3::CustomNotification`-Objekt im aktuellen Thread.</span><span class="sxs-lookup"><span data-stu-id="44d77-106">[out] A pointer to the current `ICorDebugManagedCallback3::CustomNotification` object on the current thread.</span></span>

## <a name="remarks"></a><span data-ttu-id="44d77-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44d77-107">Remarks</span></span>

<span data-ttu-id="44d77-108">Der Wert von `ppNotificationObject` ist NULL, wenn die Methode nicht innerhalb eines `ICorDebugManagedCallback3::CustomNotification` Rückrufs aufgerufen wird, oder, wenn kein Aktuelles Benachrichtigungs Objekt vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="44d77-108">The value of `ppNotificationObject` is null if the method is not called from within a `ICorDebugManagedCallback3::CustomNotification` callback, or if no current notification object exists.</span></span>

## <a name="requirements"></a><span data-ttu-id="44d77-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="44d77-109">Requirements</span></span>

<span data-ttu-id="44d77-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44d77-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="44d77-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="44d77-111">**Header:** CorDebug.idl, CorDebug.h</span></span>

<span data-ttu-id="44d77-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44d77-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="44d77-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44d77-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="44d77-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44d77-114">See also</span></span>

- [<span data-ttu-id="44d77-115">ICorDebugThread4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44d77-115">ICorDebugThread4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [<span data-ttu-id="44d77-116">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="44d77-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="44d77-117">Debuggen</span><span class="sxs-lookup"><span data-stu-id="44d77-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
