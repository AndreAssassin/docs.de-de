---
title: ISymUnmanagedReader::GetDocuments-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetDocuments
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetDocuments
helpviewer_keywords:
- GetDocuments method [.NET Framework debugging]
- ISymUnmanagedReader::GetDocuments method [.NET Framework debugging]
ms.assetid: e3b73a3f-d089-4101-a9a9-5e0765d05b61
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: efcf5b6673fbdc37fad99d082f91ab3077abbea9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939463"
---
# <a name="isymunmanagedreadergetdocuments-method"></a><span data-ttu-id="d819d-102">ISymUnmanagedReader::GetDocuments-Methode</span><span class="sxs-lookup"><span data-stu-id="d819d-102">ISymUnmanagedReader::GetDocuments Method</span></span>
<span data-ttu-id="d819d-103">Gibt ein Array aller im Symbolspeicher definierten Dokumente.</span><span class="sxs-lookup"><span data-stu-id="d819d-103">Returns an array of all the documents defined in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d819d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d819d-104">Syntax</span></span>  
  
```  
HRESULT GetDocuments (  
    [in]  ULONG32  cDocs,  
    [out] ULONG32  *pcDocs,  
    [out, size_is (cDocs),  
        length_is (*pcDocs)] ISymUnmanagedDocument *pDocs[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d819d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d819d-105">Parameters</span></span>  
 `cDocs`  
 <span data-ttu-id="d819d-106">[in] Die Größe des `pDocs`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="d819d-106">[in] The size of the `pDocs` array.</span></span>  
  
 `pcDocs`  
 <span data-ttu-id="d819d-107">[out] Ein Zeiger auf eine Variable, die Länge des Arrays empfängt.</span><span class="sxs-lookup"><span data-stu-id="d819d-107">[out] A pointer to a variable that receives the array length.</span></span>  
  
 `pDocs`  
 <span data-ttu-id="d819d-108">[out] Ein Zeiger auf eine Variable, die das Dokumentarray empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="d819d-108">[out] A pointer to a variable that receives the document array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d819d-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d819d-109">Return Value</span></span>  
 <span data-ttu-id="d819d-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="d819d-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d819d-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d819d-111">Requirements</span></span>  
 <span data-ttu-id="d819d-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="d819d-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d819d-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d819d-113">See also</span></span>

- [<span data-ttu-id="d819d-114">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d819d-114">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
