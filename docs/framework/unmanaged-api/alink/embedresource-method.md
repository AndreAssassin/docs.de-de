---
title: EmbedResource-Methode
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ef7d6272c04c3edab8ef652bcb2759861ff2b982
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129570"
---
# <a name="embedresource-method"></a><span data-ttu-id="a943e-102">EmbedResource-Methode</span><span class="sxs-lookup"><span data-stu-id="a943e-102">EmbedResource Method</span></span>
<span data-ttu-id="a943e-103">Deklariert eine eingebettete Ressource.</span><span class="sxs-lookup"><span data-stu-id="a943e-103">Declares an embedded resource.</span></span> <span data-ttu-id="a943e-104">Diese Methode können Sie die Ressource nicht tatsächlich einbetten.</span><span class="sxs-lookup"><span data-stu-id="a943e-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a943e-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="a943e-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="a943e-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="a943e-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="a943e-107">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="a943e-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="a943e-108">Datei-Token "oder" Assembly-ID der Datei, die die Ressource enthält.</span><span class="sxs-lookup"><span data-stu-id="a943e-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="a943e-109">Name der Ressource.</span><span class="sxs-lookup"><span data-stu-id="a943e-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="a943e-110">Der Offset der Ressource von RVA.</span><span class="sxs-lookup"><span data-stu-id="a943e-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="a943e-111">Barrierefreiheit flags, z. B. `mrPublic` und `mrPrivate`.</span><span class="sxs-lookup"><span data-stu-id="a943e-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="a943e-112">Diese Flags können übergeben werden, um [DefineExportedType-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span><span class="sxs-lookup"><span data-stu-id="a943e-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a943e-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a943e-113">Return Value</span></span>  
 <span data-ttu-id="a943e-114">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="a943e-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a943e-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a943e-115">Requirements</span></span>  
 <span data-ttu-id="a943e-116">Erfordert alink.h an.</span><span class="sxs-lookup"><span data-stu-id="a943e-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a943e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a943e-117">See also</span></span>

- [<span data-ttu-id="a943e-118">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a943e-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="a943e-119">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a943e-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="a943e-120">Alink-API</span><span class="sxs-lookup"><span data-stu-id="a943e-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
