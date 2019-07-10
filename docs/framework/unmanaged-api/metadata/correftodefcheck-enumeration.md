---
title: CorRefToDefCheck-Enumeration
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2ae87dd4538a9a8e88591f498c0ce77b51bfa852
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781618"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="673f9-102">CorRefToDefCheck-Enumeration</span><span class="sxs-lookup"><span data-stu-id="673f9-102">CorRefToDefCheck Enumeration</span></span>
<span data-ttu-id="673f9-103">Gibt Flags an, mit denen gesteuert wird, welche Elemente, auf die verwiesen wird, zur Optimierung des Codes in ihre Definitionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="673f9-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="673f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="673f9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="673f9-105">Member</span><span class="sxs-lookup"><span data-stu-id="673f9-105">Members</span></span>  
  
|<span data-ttu-id="673f9-106">Member</span><span class="sxs-lookup"><span data-stu-id="673f9-106">Member</span></span>|<span data-ttu-id="673f9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="673f9-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="673f9-108">Gibt an, dass Verweise auf Typen und memberverweisen auf Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="673f9-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="673f9-109">Dies ist der Standardwert (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span><span class="sxs-lookup"><span data-stu-id="673f9-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="673f9-110">Gibt an, dass alle referenzierten Elemente in Definitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="673f9-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="673f9-111">Gibt an, dass keine Elemente auf die verwiesen wird, die in Definitionen konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="673f9-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="673f9-112">Gibt an, dass nur Verweise auf Typen um zu Typdefinitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="673f9-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="673f9-113">Gibt an, dass nur memberverweisen auf Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="673f9-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="673f9-114">D. h. sollen Elementverweise Methodendefinitionen oder Felddefinitionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="673f9-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="673f9-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="673f9-115">Requirements</span></span>  
 <span data-ttu-id="673f9-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="673f9-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="673f9-117">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="673f9-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="673f9-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="673f9-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673f9-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="673f9-119">See also</span></span>

- [<span data-ttu-id="673f9-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="673f9-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
