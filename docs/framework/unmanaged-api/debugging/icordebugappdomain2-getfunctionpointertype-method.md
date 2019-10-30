---
title: ICorDebugAppDomain2::GetFunctionPointerType-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2.GetFunctionPointerType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type:
- apiref
ms.openlocfilehash: 5a6e0b009674ff52595aaa0ae4a060f1cdfd1398
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089045"
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="410cc-102">ICorDebugAppDomain2::GetFunctionPointerType-Methode</span><span class="sxs-lookup"><span data-stu-id="410cc-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="410cc-103">Ruft einen Zeiger auf eine Funktion ab, die über eine angegebene Signatur verfügt.</span><span class="sxs-lookup"><span data-stu-id="410cc-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="410cc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="410cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="410cc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="410cc-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="410cc-106">in Die Anzahl der Typargumente für die Funktion.</span><span class="sxs-lookup"><span data-stu-id="410cc-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="410cc-107">in Ein Array von Zeigern, von denen jedes auf ein ICorDebugType-Objekt verweist, das ein Typargument der Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="410cc-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="410cc-108">Das erste Element ist der Rückgabetyp. Jedes der anderen Elemente ist ein Parametertyp.</span><span class="sxs-lookup"><span data-stu-id="410cc-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="410cc-109">vorgenommen Ein Zeiger auf die Adresse eines `ICorDebugType` Objekts, das den Zeiger auf die Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="410cc-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="410cc-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="410cc-110">Requirements</span></span>  
 <span data-ttu-id="410cc-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="410cc-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="410cc-112">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="410cc-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="410cc-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="410cc-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="410cc-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="410cc-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
