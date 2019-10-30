---
title: ICorDebugFunction2::EnumerateNativeCode-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.EnumerateNativeCode
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::EnumerateNativeCode
helpviewer_keywords:
- ICorDebugFunction2::EnumerateNativeCode method [.NET Framework debugging]
- EnumerateNativeCode method [.NET Framework debugging]
ms.assetid: d383f5cc-1144-4b6d-b57a-db34d9134ab2
topic_type:
- apiref
ms.openlocfilehash: d5b24ee02a682b38dcf0cb3449f0dff197e91bf9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137828"
---
# <a name="icordebugfunction2enumeratenativecode-method"></a><span data-ttu-id="ff43e-102">ICorDebugFunction2::EnumerateNativeCode-Methode</span><span class="sxs-lookup"><span data-stu-id="ff43e-102">ICorDebugFunction2::EnumerateNativeCode Method</span></span>
<span data-ttu-id="ff43e-103">Ruft einen Schnittstellen Zeiger auf ein ICorDebugCodeEnum-Objekt ab, das die systemeigenen Code Anweisungen in der Funktion enthält, auf die von diesem ICorDebugFunction2-Objekt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ff43e-103">Gets an interface pointer to an ICorDebugCodeEnum object that contains the native code statements in the function referenced by this ICorDebugFunction2 object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ff43e-104">`EnumerateNativeCode` ist nicht in der aktuellen Version des .NET Framework implementiert.</span><span class="sxs-lookup"><span data-stu-id="ff43e-104">`EnumerateNativeCode` is not implemented in the current version of the .NET Framework.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff43e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ff43e-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateNativeCode (  
    [out] ICorDebugCodeEnum   **ppCodeEnum  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="ff43e-106">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ff43e-106">Requirements</span></span>  
 <span data-ttu-id="ff43e-107">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff43e-107">**Header:** CorDebug.idl, CorDebug.h</span></span>
