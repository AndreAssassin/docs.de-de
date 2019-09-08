---
title: SetAssemblyFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76d341aca7c96e5932a1fc155ccaee17ce6585da
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777001"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="7ceca-102">SetAssemblyFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7ceca-102">SetAssemblyFile Method</span></span>
<span data-ttu-id="7ceca-103">Weist den Namen der Assembly zu, die erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="7ceca-103">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="7ceca-104">Nicht für die Verwendung beim Erstellen von ungebundenen Modulen.</span><span class="sxs-lookup"><span data-stu-id="7ceca-104">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ceca-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ceca-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ceca-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ceca-106">Parameters</span></span>  
 `pszFilename`  
 <span data-ttu-id="7ceca-107">Der voll qualifizierte Name der Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="7ceca-107">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7ceca-108">Zeiger auf die [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) -Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="7ceca-108">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="7ceca-109">Flags, wie in [AssemblyFlags-Enumeration](../metadata/assemblyflags-enumeration.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="7ceca-109">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="7ceca-110">Zeiger auf die ID der resultierenden Assembly.</span><span class="sxs-lookup"><span data-stu-id="7ceca-110">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ceca-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7ceca-111">Return Value</span></span>  
 <span data-ttu-id="7ceca-112">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7ceca-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ceca-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7ceca-113">Requirements</span></span>  
 <span data-ttu-id="7ceca-114">Erfordert Alink. h.</span><span class="sxs-lookup"><span data-stu-id="7ceca-114">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ceca-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7ceca-115">See also</span></span>

- [<span data-ttu-id="7ceca-116">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ceca-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7ceca-117">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ceca-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7ceca-118">Alink-API</span><span class="sxs-lookup"><span data-stu-id="7ceca-118">ALink API</span></span>](index.md)
