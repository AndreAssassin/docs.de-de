---
title: AddFile-Methode
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ff6bde5009e834bfca156fe4d3ad16da53ded85
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67742384"
---
# <a name="addfile-method"></a><span data-ttu-id="7fff3-102">AddFile-Methode</span><span class="sxs-lookup"><span data-stu-id="7fff3-102">AddFile Method</span></span>
<span data-ttu-id="7fff3-103">Dateien hinzugefügt der Assembly.</span><span class="sxs-lookup"><span data-stu-id="7fff3-103">Adds files to the assembly.</span></span> <span data-ttu-id="7fff3-104">Kann auch zum Erstellen von ungebundener Modules verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7fff3-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fff3-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="7fff3-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7fff3-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="7fff3-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7fff3-107">Eindeutige ID der Assembly, die erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="7fff3-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="7fff3-108">Voll gekennzeichnete Name der hinzuzufügenden Datei um.</span><span class="sxs-lookup"><span data-stu-id="7fff3-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="7fff3-109">COM+ FileDef-flags, z. B. `ffContainsNoMetaData` und `ffWriteable`.</span><span class="sxs-lookup"><span data-stu-id="7fff3-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="7fff3-110">`dwFlags` wird zum übergeben [DefineFile-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="7fff3-110">`dwFlags` is passed to [DefineFile Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="7fff3-111">[IMetaDataEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) Schnittstelle, die zum Ausgeben von Metadaten verwendet werden, bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="7fff3-111">[IMetaDataEmit Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="7fff3-112">Zeiger auf, wo die eindeutige ID der hinzugefügten Datei gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="7fff3-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7fff3-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7fff3-113">Return Value</span></span>  
 <span data-ttu-id="7fff3-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="7fff3-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fff3-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7fff3-115">Requirements</span></span>  
 <span data-ttu-id="7fff3-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="7fff3-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fff3-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7fff3-117">See also</span></span>

- [<span data-ttu-id="7fff3-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fff3-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="7fff3-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7fff3-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="7fff3-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="7fff3-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
