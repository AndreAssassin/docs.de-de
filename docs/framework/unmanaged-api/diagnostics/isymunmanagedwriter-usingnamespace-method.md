---
title: ISymUnmanagedWriter::UsingNamespace-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.UsingNamespace
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d0739cc38d1f12967f0daef2d6828e04a256ade6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650673"
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="3a544-102">ISymUnmanagedWriter::UsingNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="3a544-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="3a544-103">Gibt an, dass es sich bei der angegebenen Namen für den vollqualifizierten Namespace im geöffneten lexikalischen Gültigkeitsbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3a544-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="3a544-104">Der Namespace wird in allen Bereichen verwendet, die von der aktuell geöffneten Bereich erben.</span><span class="sxs-lookup"><span data-stu-id="3a544-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="3a544-105">Schließen den aktuellen Bereich wird die Verwendung des Namespace auch beendet werden.</span><span class="sxs-lookup"><span data-stu-id="3a544-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a544-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a544-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a544-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="3a544-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="3a544-108">[in] Ein Zeiger auf den vollqualifizierten Namen des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="3a544-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a544-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3a544-109">Return Value</span></span>  
 <span data-ttu-id="3a544-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="3a544-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a544-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a544-111">Requirements</span></span>  
 <span data-ttu-id="3a544-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3a544-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a544-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a544-113">See also</span></span>

- [<span data-ttu-id="3a544-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3a544-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
