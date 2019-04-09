---
title: CorNativeLinkType-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59170062"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="c0b99-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="c0b99-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="c0b99-103">Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="c0b99-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0b99-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0b99-104">Syntax</span></span>  
  
```  
typedef enum   
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="c0b99-105">Member</span><span class="sxs-lookup"><span data-stu-id="c0b99-105">Members</span></span>  
  
|<span data-ttu-id="c0b99-106">Member</span><span class="sxs-lookup"><span data-stu-id="c0b99-106">Member</span></span>|<span data-ttu-id="c0b99-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0b99-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="c0b99-108">Gibt an, dass keines der Schlüsselwörter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="c0b99-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="c0b99-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c0b99-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="c0b99-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben wird</span><span class="sxs-lookup"><span data-stu-id="c0b99-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="c0b99-111">Gibt an, dass ein Schlüsselwort "Auto" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c0b99-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="c0b99-112">Gibt an, dass ein OLE-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="c0b99-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="c0b99-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="c0b99-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0b99-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0b99-114">Requirements</span></span>  
 <span data-ttu-id="c0b99-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0b99-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0b99-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0b99-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0b99-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0b99-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="c0b99-118">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="c0b99-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c0b99-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0b99-119">See also</span></span>

- [<span data-ttu-id="c0b99-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="c0b99-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
