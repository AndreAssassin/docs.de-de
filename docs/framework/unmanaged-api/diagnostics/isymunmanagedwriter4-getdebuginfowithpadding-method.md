---
title: ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode
ms.date: 03/30/2017
ms.assetid: 881e20ca-8131-4bd0-ba41-c2d6391b0fe2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 191aa16c285b3a28beed65004d65525c9214ec93
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081567"
---
# <a name="isymunmanagedwriter4getdebuginfowithpadding-method"></a><span data-ttu-id="b8d07-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding-Methode</span><span class="sxs-lookup"><span data-stu-id="b8d07-102">ISymUnmanagedWriter4::GetDebugInfoWithPadding Method</span></span>
<span data-ttu-id="b8d07-103">Funktioniert genauso wie [GetDebugInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) mit dem Unterschied, dass die Path-Zeichenfolge mit Nullen nach dem das abschließende Nullzeichen, um den Zeichenfolgendaten eine feste Größe von machen aufgefüllt wird `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="b8d07-103">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="b8d07-104">Auffüllung wird nur ausgegeben, wenn die Länge der Zeichenfolge Pfad selbst ist kleiner als `MAX_PATH`.</span><span class="sxs-lookup"><span data-stu-id="b8d07-104">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span>  
  
 <span data-ttu-id="b8d07-105">Dies erleichtert es, Tools, Unterschied PE-Dateien zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b8d07-105">This makes it easier to write tools that difference PE files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8d07-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8d07-106">Syntax</span></span>  
  
```idl  
HRESULT GetDebugInfoWithPadding(    [in, out] IMAGE_DEBUG_DIRECTORY *pIDD,    [in] DWORD cData,    [out] DWORD *pcData,    [out, size_is(cData), length_is(*pcData)] BYTE data[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8d07-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8d07-107">Parameters</span></span>  
  
|<span data-ttu-id="b8d07-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8d07-108">Parameter</span></span>|<span data-ttu-id="b8d07-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b8d07-109">Description</span></span>|  
|---------------|-----------------|  
|`pIDD`||  
|`cData`||  
|`pcData`||  
|`data`||  
  
## <a name="return-value"></a><span data-ttu-id="b8d07-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b8d07-110">Return Value</span></span>  
 <span data-ttu-id="b8d07-111">Gibt `HRESULT`zurück.</span><span class="sxs-lookup"><span data-stu-id="b8d07-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8d07-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8d07-112">Requirements</span></span>  
 <span data-ttu-id="b8d07-113">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b8d07-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8d07-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8d07-114">See also</span></span>

- [<span data-ttu-id="b8d07-115">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8d07-115">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
