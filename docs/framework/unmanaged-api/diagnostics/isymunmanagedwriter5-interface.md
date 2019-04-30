---
title: ISymUnmanagedWriter5-Schnittstelle
ms.date: 03/30/2017
ms.assetid: 15b8526e-4f5d-475c-a1e3-d8b2d145c879
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6ed8c6e61c558a4bc9e3f92d559615ac93ecff8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962338"
---
# <a name="isymunmanagedwriter5-interface"></a><span data-ttu-id="23d27-102">ISymUnmanagedWriter5-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23d27-102">ISymUnmanagedWriter5 Interface</span></span>
<span data-ttu-id="23d27-103">ISymUnmanagedWriter5-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="23d27-103">ISymUnmanagedWriter5 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d27-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23d27-104">Syntax</span></span>  
  
```idl  
[object,uuid(DCF7780D-BDE9-45DF-ACFE-21731A32000C),pointer_default(unique)]interface ISymUnmanagedWriter5 : ISymUnmanagedWriter4  
```  
  
## <a name="methods"></a><span data-ttu-id="23d27-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="23d27-105">Methods</span></span>  
 <span data-ttu-id="23d27-106">Diese Schnittstelle enthält die folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="23d27-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="23d27-107">Methode</span><span class="sxs-lookup"><span data-stu-id="23d27-107">Method</span></span>|<span data-ttu-id="23d27-108">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23d27-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23d27-109">CloseMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="23d27-109">CloseMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md)|<span data-ttu-id="23d27-110">Spezielle benutzerdefinierte Data-Abschnitt für Token-to-Source-Spanne, die Zuordnungsinformationen zu schließen.</span><span class="sxs-lookup"><span data-stu-id="23d27-110">Close the special custom data section for token-to- source span mapping information.</span></span> <span data-ttu-id="23d27-111">Nachdem sie geschlossen wurde, kann keine weiteren Zuordnungsinformationen hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23d27-111">After it is closed, no more mapping information can be added.</span></span>|  
|[<span data-ttu-id="23d27-112">MapTokenToSourceSpan-Methode</span><span class="sxs-lookup"><span data-stu-id="23d27-112">MapTokenToSourceSpan Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-maptokentosourcespan-method.md)|<span data-ttu-id="23d27-113">Zuordnungen in die Zeile für die angegebene Quelle das angegebene Metadatentoken umfassen, in der angegebenen Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="23d27-113">Maps the given metadata token to the given source line span in the specified source file.</span></span><br /><br /> <span data-ttu-id="23d27-114">Muss aufgerufen werden, zwischen den Aufrufen [OpenMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) und [CloseMapTokensToSourceSpans-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span><span class="sxs-lookup"><span data-stu-id="23d27-114">Must be called between calls to [OpenMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md) and [CloseMapTokensToSourceSpans Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-closemaptokenstosourcespans-method.md).</span></span>|  
|[<span data-ttu-id="23d27-115">OpenMapTokensToSourceSpans-Methode</span><span class="sxs-lookup"><span data-stu-id="23d27-115">OpenMapTokensToSourceSpans Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter5-openmaptokenstosourcespans-method.md)|<span data-ttu-id="23d27-116">Öffnen Sie einen spezielle benutzerdefinierte Daten im Abschnitt zum Ausgeben der Span-Token-to-Source-Zuordnungsinformationen in.</span><span class="sxs-lookup"><span data-stu-id="23d27-116">Open a special custom data section to emit token-to- source span mapping information into.</span></span> <span data-ttu-id="23d27-117">Öffnen in diesem Abschnitt aus, wenn eine Methode bereits geöffnet ist, oder umgekehrt, ein Fehler wird.</span><span class="sxs-lookup"><span data-stu-id="23d27-117">Opening this section when a method is already open, or vice versa, is an error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23d27-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="23d27-118">Requirements</span></span>  
 <span data-ttu-id="23d27-119">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="23d27-119">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d27-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23d27-120">See also</span></span>

- [<span data-ttu-id="23d27-121">Diagnosesymbolspeicher-Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="23d27-121">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="23d27-122">ISymUnmanagedWriter4-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="23d27-122">ISymUnmanagedWriter4 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-interface.md)
