---
title: COUNINITIEE-Enumeration
ms.date: 03/30/2017
api_name:
- COUNINITIEE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COUNINITIEE
helpviewer_keywords:
- COUNINITIEE enumeration [.NET Framework metadata]
ms.assetid: c42baa79-f469-4330-95a2-baf7f021c2fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d8189365a73e85c0b9f5efb2aa03074385a3fb8
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750750"
---
# <a name="couninitiee-enumeration"></a><span data-ttu-id="cf58d-102">COUNINITIEE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf58d-102">COUNINITIEE Enumeration</span></span>
<span data-ttu-id="cf58d-103">Gibt Konstanten an, die von verwendet [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) beim Initialisieren der common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="cf58d-103">Specifies constants used by [CoUninitializeEE](../../../../docs/framework/unmanaged-api/hosting/couninitializeee-function.md) when initializing the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf58d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf58d-104">Syntax</span></span>  
  
```cpp  
typedef enum tagCOUNINITEE  
{  
    COUNINITEE_DEFAULT  = 0x0,   
    COUNINITEE_DLL      = 0x1  
} COUNINITIEE;  
```  
  
## <a name="members"></a><span data-ttu-id="cf58d-105">Member</span><span class="sxs-lookup"><span data-stu-id="cf58d-105">Members</span></span>  
  
|<span data-ttu-id="cf58d-106">Member</span><span class="sxs-lookup"><span data-stu-id="cf58d-106">Member</span></span>|<span data-ttu-id="cf58d-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cf58d-107">Description</span></span>|  
|------------|-----------------|  
|`COUNINITEE_DEFAULT`|<span data-ttu-id="cf58d-108">Gibt die Initialisierung der Standardmodus an.</span><span class="sxs-lookup"><span data-stu-id="cf58d-108">Indicates default uninitialization mode.</span></span>|  
|`COUNINITEE_DLL`|<span data-ttu-id="cf58d-109">Gibt die Initialisierung im Modus für das Entladen einer Assemblys an.</span><span class="sxs-lookup"><span data-stu-id="cf58d-109">Indicates uninitialization mode for unloading an assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf58d-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="cf58d-110">Requirements</span></span>  
 <span data-ttu-id="cf58d-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf58d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf58d-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="cf58d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cf58d-113">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="cf58d-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cf58d-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf58d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf58d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf58d-115">See also</span></span>

- [<span data-ttu-id="cf58d-116">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="cf58d-116">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
