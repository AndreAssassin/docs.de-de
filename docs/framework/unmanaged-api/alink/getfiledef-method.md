---
title: GetFileDef-Methode
ms.date: 03/30/2017
api_name:
- IALink2.GetFileDef
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetFileDef
helpviewer_keywords:
- GetFileDef method
ms.assetid: 4e3fbe6c-b82a-4181-ab17-7faa1263f5b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a51e8c83d0949f68a41f6a4e10396adbc4f3c9c1
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741891"
---
# <a name="getfiledef-method"></a><span data-ttu-id="cb631-102">GetFileDef-Methode</span><span class="sxs-lookup"><span data-stu-id="cb631-102">GetFileDef Method</span></span>
<span data-ttu-id="cb631-103">Ruft ab, das tatsächliche FileDef-Token, die in den Metadaten (im Gegensatz zu das Token von ALink zugewiesen wird) verwendet.</span><span class="sxs-lookup"><span data-stu-id="cb631-103">Retrieves the actual FileDef token used in metadata (as opposed to the token assigned by ALink).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb631-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cb631-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileDef(  
    mdAssembly AssemblyID,  
    mdFile TargetFile,  
    mdFile* pScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb631-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="cb631-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="cb631-106">Die ID der Assembly.</span><span class="sxs-lookup"><span data-stu-id="cb631-106">ID of the assembly.</span></span>  
  
 `TargetFile`  
 <span data-ttu-id="cb631-107">Der hinzugefügten Datei AddFile-Methode oder AddImport-Methode abgerufene Token.</span><span class="sxs-lookup"><span data-stu-id="cb631-107">Token of the added file as retrieved from AddFile Method or AddImport Method.</span></span>  
  
 `pScope`  
 <span data-ttu-id="cb631-108">Empfängt die FileDef-Token.</span><span class="sxs-lookup"><span data-stu-id="cb631-108">Receives the FileDef token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cb631-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="cb631-109">Return Value</span></span>  
 <span data-ttu-id="cb631-110">Gibt S_OK zurück, wenn die Methode erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="cb631-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb631-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cb631-111">Requirements</span></span>  
 <span data-ttu-id="cb631-112">Erfordert alink.h</span><span class="sxs-lookup"><span data-stu-id="cb631-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb631-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb631-113">See also</span></span>

- [<span data-ttu-id="cb631-114">IALink2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb631-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="cb631-115">IALink-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="cb631-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="cb631-116">Alink-API</span><span class="sxs-lookup"><span data-stu-id="cb631-116">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
