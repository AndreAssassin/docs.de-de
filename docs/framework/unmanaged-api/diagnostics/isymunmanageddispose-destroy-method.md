---
title: ISymUnmanagedDispose::Destroy-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedDispose.Destroy
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedDispose::Destroy
helpviewer_keywords:
- ISymUnmanagedDispose::Destroy method [.NET Framework debugging]
- Destroy method [.NET Framework debugging]
ms.assetid: a854ab9f-d2ba-470e-867f-808c1e7bd07a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51d2f0aedffdd88974a8184954ecbb9a231b70c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213668"
---
# <a name="isymunmanageddisposedestroy-method"></a><span data-ttu-id="eeea7-102">ISymUnmanagedDispose::Destroy-Methode</span><span class="sxs-lookup"><span data-stu-id="eeea7-102">ISymUnmanagedDispose::Destroy Method</span></span>
<span data-ttu-id="eeea7-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span><span class="sxs-lookup"><span data-stu-id="eeea7-103">Causes the underlying object to release all internal references and return failure on any subsequent method calls.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eeea7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eeea7-104">Syntax</span></span>  
  
```  
HRESULT Destroy();  
```  
  
## <a name="return-value"></a><span data-ttu-id="eeea7-105">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="eeea7-105">Return Value</span></span>  
 <span data-ttu-id="eeea7-106">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="eeea7-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eeea7-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eeea7-107">Requirements</span></span>  
 <span data-ttu-id="eeea7-108">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="eeea7-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eeea7-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eeea7-109">See also</span></span>

- [<span data-ttu-id="eeea7-110">ISymUnmanagedDispose-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eeea7-110">ISymUnmanagedDispose Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddispose-interface.md)
