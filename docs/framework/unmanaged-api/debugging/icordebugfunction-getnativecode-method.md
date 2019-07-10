---
title: ICorDebugFunction::GetNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c0507d59011f6b584ecb1ae11c35c456c80793af
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754597"
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="bf8af-102">ICorDebugFunction::GetNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="bf8af-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="bf8af-103">Ruft den systemeigenen Code für die Funktion, die von dieser Instanz ICorDebugFunction dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="bf8af-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf8af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf8af-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf8af-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf8af-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="bf8af-106">[out] Ein Zeiger auf die ICorDebugCode-Instanz, die den nativen Code für diese Funktion, oder Null, darstellt, wenn diese Funktion Microsoft intermediate Language (MSIL)-Code, die nicht mit just ist-in-Time (JIT) kompiliert wurde.</span><span class="sxs-lookup"><span data-stu-id="bf8af-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf8af-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf8af-107">Remarks</span></span>  
 <span data-ttu-id="bf8af-108">Wenn die Funktion, die von diesem dargestellt wird `ICorDebugFunction` Instanz wurde mit JIT kompiliert wurden mehr als einmal als im Fall von generischen Typen `GetNativeCode` gibt eine zufällige systemeigenen Code-Objekt zurück.</span><span class="sxs-lookup"><span data-stu-id="bf8af-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf8af-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bf8af-109">Requirements</span></span>  
 <span data-ttu-id="bf8af-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf8af-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf8af-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf8af-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf8af-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf8af-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf8af-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf8af-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
