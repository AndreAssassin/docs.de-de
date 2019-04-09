---
title: ISymUnmanagedWriter::RemapToken-Methode
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.RemapToken
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::RemapToken
helpviewer_keywords:
- ISymUnmanagedWriter::RemapToken method [.NET Framework debugging]
- RemapToken method [.NET Framework debugging]
ms.assetid: bca92682-ee1e-467f-8fb0-d8d4617f82fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 979d14b4c404c3bf12c427bd5b8b1d4997805e7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160679"
---
# <a name="isymunmanagedwriterremaptoken-method"></a><span data-ttu-id="b8cbc-102">ISymUnmanagedWriter::RemapToken-Methode</span><span class="sxs-lookup"><span data-stu-id="b8cbc-102">ISymUnmanagedWriter::RemapToken Method</span></span>
<span data-ttu-id="b8cbc-103">Benachrichtigt dem Symbolwriter, dass ein Metadatentoken neu zugeordnet wurde, als die Metadaten ausgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="b8cbc-103">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span> <span data-ttu-id="b8cbc-104">Wenn Sie der Symbolwriter das alte Token im Symbolspeicher gespeichert ist, muss er entweder aktualisieren, wenn das gespeicherte Token mit den neuen Wert oder die Zuordnung für den entsprechenden Symbolreader, neu zuzuordnen, während der read-Phase speichern muss.</span><span class="sxs-lookup"><span data-stu-id="b8cbc-104">If the symbol writer has stored the old token within the symbol store, it must either update the stored token with the new value, or it must save the map for the corresponding symbol reader to remap during the read phase.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8cbc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8cbc-105">Syntax</span></span>  
  
```  
HRESULT RemapToken(  
    [in] mdToken  oldToken,  
    [in] mdToken  newToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8cbc-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8cbc-106">Parameters</span></span>  
 `oldToken`  
 <span data-ttu-id="b8cbc-107">[in] Das Metadatentoken, das neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b8cbc-107">[in] The metadata token that was remapped.</span></span>  
  
 `newToken`  
 <span data-ttu-id="b8cbc-108">[in] Das neue Metadatentoken, `oldToken` neu zugeordnet wurde.</span><span class="sxs-lookup"><span data-stu-id="b8cbc-108">[in] The new metadata token to which `oldToken` was remapped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b8cbc-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8cbc-109">Return Value</span></span>  
 <span data-ttu-id="b8cbc-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="b8cbc-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8cbc-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8cbc-111">Requirements</span></span>  
 <span data-ttu-id="b8cbc-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8cbc-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8cbc-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8cbc-113">See also</span></span>

- [<span data-ttu-id="b8cbc-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8cbc-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
