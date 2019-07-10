---
title: CorAttributeTargets-Enumeration
ms.date: 03/30/2017
api_name:
- CorAttributeTargets
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorAttributeTargets
helpviewer_keywords:
- CorAttributeTargets enumeration [.NET Framework metadata]
ms.assetid: 694c0fa0-7011-41a9-9dfd-f0e16ea574b5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9fb1dff80fccc920540d370797441b3a019d766c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780910"
---
# <a name="corattributetargets-enumeration"></a><span data-ttu-id="17abb-102">CorAttributeTargets-Enumeration</span><span class="sxs-lookup"><span data-stu-id="17abb-102">CorAttributeTargets Enumeration</span></span>
<span data-ttu-id="17abb-103">Gibt die Anwendungselemente an, auf die Attribute angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="17abb-103">Specifies the application elements on which it is valid to apply an attribute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="17abb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="17abb-104">Syntax</span></span>  
  
```cpp  
typedef enum CorAttributeTargets  
{  
    catAssembly            = 0x0001,  
    catModule              = 0x0002,  
    catClass               = 0x0004,  
    catStruct              = 0x0008,  
    catEnum                = 0x0010,  
    catConstructor         = 0x0020,  
    catMethod              = 0x0040,  
    catProperty            = 0x0080,  
    catField               = 0x0100,  
    catEvent               = 0x0200,  
    catInterface           = 0x0400,  
    catParameter           = 0x0800,  
    catDelegate            = 0x1000,  
    catGenericParameter    = 0x4000,  
  
    catAll                 =   
        catAssembly | catModule | catClass | catStruct |   
        catEnum | catConstructor | catMethod | catProperty |   
        catField | catEvent | catInterface | catParameter |   
        catDelegate | catGenericParameter,  
  
    catClassMembers        =   
        catClass | catStruct | catEnum | catConstructor |   
        catMethod | catProperty | catField | catEvent |   
        catDelegate | catInterface  
  
} CorAttributeTargets;  
```  
  
## <a name="members"></a><span data-ttu-id="17abb-105">Member</span><span class="sxs-lookup"><span data-stu-id="17abb-105">Members</span></span>  
  
|<span data-ttu-id="17abb-106">Member</span><span class="sxs-lookup"><span data-stu-id="17abb-106">Member</span></span>|<span data-ttu-id="17abb-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="17abb-107">Description</span></span>|  
|------------|-----------------|  
|`catAssembly`|<span data-ttu-id="17abb-108">Attribut kann auf eine Assembly angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-108">Attribute can be applied to an assembly.</span></span>|  
|`catModule`|<span data-ttu-id="17abb-109">Attribut kann auf ein portierbare ausführbare Datei (.dll oder .exe) Modul angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-109">Attribute can be applied to a portable executable (.dll or .exe) module.</span></span>|  
|`catClass`|<span data-ttu-id="17abb-110">Attribut kann auf eine Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-110">Attribute can be applied to a class.</span></span>|  
|`catStruct`|<span data-ttu-id="17abb-111">Auf einer Struktur können Attribute angewendet werden; Typ, d. h. ein Wert.</span><span class="sxs-lookup"><span data-stu-id="17abb-111">Attribute can be applied to a structure; that is, a value type.</span></span>|  
|`catEnum`|<span data-ttu-id="17abb-112">Attribut kann auf eine Enumeration angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-112">Attribute can be applied to an enumeration.</span></span>|  
|`catConstructor`|<span data-ttu-id="17abb-113">Attribut kann an einen Konstruktor angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-113">Attribute can be applied to a constructor.</span></span>|  
|`catMethod`|<span data-ttu-id="17abb-114">Attribut kann auf eine Methode angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-114">Attribute can be applied to a method.</span></span>|  
|`catProperty`|<span data-ttu-id="17abb-115">Attribut kann auf eine Eigenschaft angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-115">Attribute can be applied to a property.</span></span>|  
|`catField`|<span data-ttu-id="17abb-116">Attribut kann auf ein Feld angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-116">Attribute can be applied to a field.</span></span>|  
|`catEvent`|<span data-ttu-id="17abb-117">Attribut kann auf ein Ereignis angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-117">Attribute can be applied to an event.</span></span>|  
|`catInterface`|<span data-ttu-id="17abb-118">Attribut kann auf eine Schnittstelle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-118">Attribute can be applied to an interface.</span></span>|  
|`catParameter`|<span data-ttu-id="17abb-119">Attribut kann auf einen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-119">Attribute can be applied to a parameter.</span></span>|  
|`catDelegate`|<span data-ttu-id="17abb-120">In einen Delegaten können Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-120">Attribute can be applied to a delegate.</span></span>|  
|`catGenericParameter`|<span data-ttu-id="17abb-121">Attribut kann auf einen generischen Parameter angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-121">Attribute can be applied to a generic parameter.</span></span>|  
|`catAll`|<span data-ttu-id="17abb-122">Auf jedes Anwendungselement kann Attribute angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-122">Attribute can be applied to any application element.</span></span>|  
|`catClassMembers`|<span data-ttu-id="17abb-123">Attribut kann auf einen Member einer Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="17abb-123">Attribute can be applied to a member of a class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17abb-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="17abb-124">Remarks</span></span>  
 <span data-ttu-id="17abb-125">Die `CorAttributeTargets` Enumerationswerte können kombiniert werden, mit der eine bitweise OR-Operation, um die gewünschte Kombination zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="17abb-125">The `CorAttributeTargets` enumeration values can be combined with a bitwise OR operation to get the preferred combination.</span></span>  
  
 <span data-ttu-id="17abb-126">Die `CorAttributeTargets` gleicht die verwaltete <xref:System.AttributeTargets?displayProperty=nameWithType> Enumeration.</span><span class="sxs-lookup"><span data-stu-id="17abb-126">The `CorAttributeTargets` parallels the managed <xref:System.AttributeTargets?displayProperty=nameWithType> enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="17abb-127">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="17abb-127">Requirements</span></span>  
 <span data-ttu-id="17abb-128">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17abb-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17abb-129">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="17abb-129">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="17abb-130">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="17abb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17abb-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="17abb-131">See also</span></span>

- [<span data-ttu-id="17abb-132">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="17abb-132">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
