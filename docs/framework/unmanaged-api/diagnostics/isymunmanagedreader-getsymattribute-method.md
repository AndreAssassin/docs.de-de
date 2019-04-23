---
title: ISymUnmanagedReader::GetSymAttribute-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetSymAttribute
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetSymAttribute
helpviewer_keywords:
- GetSymAttribute method [.NET Framework debugging]
- ISymUnmanagedReader::GetSymAttribute method [.NET Framework debugging]
ms.assetid: c675ce7e-76e7-45ff-8273-3b6489a2767c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 89831261c5da156343cb098ace715495ddafccaf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086090"
---
# <a name="isymunmanagedreadergetsymattribute-method"></a><span data-ttu-id="b35e5-102">ISymUnmanagedReader::GetSymAttribute-Methode</span><span class="sxs-lookup"><span data-stu-id="b35e5-102">ISymUnmanagedReader::GetSymAttribute Method</span></span>
<span data-ttu-id="b35e5-103">Ruft ein benutzerdefiniertes Attribut anhand seines Namens ab.</span><span class="sxs-lookup"><span data-stu-id="b35e5-103">Gets a custom attribute based upon its name.</span></span> <span data-ttu-id="b35e5-104">Im Gegensatz zu benutzerdefinierten Metadatenattributen befinden sich diese benutzerdefinierten Attribute im Symbolspeicher.</span><span class="sxs-lookup"><span data-stu-id="b35e5-104">Unlike metadata custom attributes, these custom attributes are held in the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b35e5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b35e5-105">Syntax</span></span>  
  
```  
HRESULT GetSymAttribute (  
    [in]  mdToken  parent,  
    [in]  WCHAR    *name,  
    [in]  ULONG32  cBuffer,  
    [out] ULONG32  *pcBuffer,  
    [out, size_is (cBuffer),  
        length_is (*pcBuffer)] BYTE buffer[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b35e5-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b35e5-106">Parameters</span></span>  
 `parent`  
 <span data-ttu-id="b35e5-107">[in] Das Metadatentoken für das Objekt, das für das das Attribut angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="b35e5-107">[in] The metadata token for the object for which the attribute is requested.</span></span>  
  
 `name`  
 <span data-ttu-id="b35e5-108">[in] Ein Zeiger auf die Variable, die das abzurufende Attribut angibt.</span><span class="sxs-lookup"><span data-stu-id="b35e5-108">[in] A pointer to the variable that indicates the attribute to retrieve.</span></span>  
  
 `cBuffer`  
 <span data-ttu-id="b35e5-109">[in] Die Größe des `buffer`-Arrays.</span><span class="sxs-lookup"><span data-stu-id="b35e5-109">[in] The size of the `buffer` array.</span></span>  
  
 `pcBuffer`  
 <span data-ttu-id="b35e5-110">[out] Ein Zeiger auf die Variable, die die Länge der Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="b35e5-110">[out] A pointer to the variable that receives the length of the attribute data.</span></span>  
  
 `buffer`  
 <span data-ttu-id="b35e5-111">[out] Ein Zeiger auf die Variable, die Attributdaten empfängt.</span><span class="sxs-lookup"><span data-stu-id="b35e5-111">[out] A pointer to the variable that receives the attribute data.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b35e5-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b35e5-112">Return Value</span></span>  
 <span data-ttu-id="b35e5-113">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b35e5-113">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b35e5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b35e5-114">Requirements</span></span>  
 <span data-ttu-id="b35e5-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b35e5-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b35e5-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b35e5-116">See also</span></span>

- [<span data-ttu-id="b35e5-117">ISymUnmanagedReader-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b35e5-117">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
