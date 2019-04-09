---
title: CorDeclSecurity-Enumeration
ms.date: 03/30/2017
api_name:
- CorDeclSecurity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeclSecurity
helpviewer_keywords:
- CorDeclSecurity enumeration [.NET Framework metadata]
ms.assetid: 864f1267-d267-4696-8df7-1f83f8444d6f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5409d1b89ba3e50c4ae17ed5aa6bf063cf6c93cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136967"
---
# <a name="cordeclsecurity-enumeration"></a><span data-ttu-id="e0b5a-102">CorDeclSecurity-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e0b5a-102">CorDeclSecurity Enumeration</span></span>
<span data-ttu-id="e0b5a-103">Gibt die Sicherheitsaktionen an, die mit deklarativer Sicherheit ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-103">Specifies the security actions that can be performed using declarative security.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e0b5a-104">Syntax</span></span>  
  
```  
typedef enum CorDeclSecurity {  
  
    dclActionMask               =   0x001f,  
    dclActionNil                =   0x0000,  
    dclRequest                  =   0x0001,  
    dclDemand                   =   0x0002,  
    dclAssert                   =   0x0003,  
    dclDeny                     =   0x0004,  
    dclPermitOnly               =   0x0005,  
    dclLinktimeCheck            =   0x0006,  
    dclInheritanceCheck         =   0x0007,  
    dclRequestMinimum           =   0x0008,  
    dclRequestOptional          =   0x0009,  
    dclRequestRefuse            =   0x000a,  
    dclPrejitGrant              =   0x000b,  
    dclPrejitDenied             =   0x000c,  
    dclNonCasDemand             =   0x000d,  
    dclNonCasLinkDemand         =   0x000e,  
    dclNonCasInheritance        =   0x000f,  
    dclLinkDemandChoice         =   0x0010,  
    dclInheritanceDemandChoice  =   0x0011,  
    dclDemandChoice             =   0x0012,  
    dclMaximumValue             =   0x0012  
  
} CorDeclSecurity;  
```  
  
## <a name="members"></a><span data-ttu-id="e0b5a-105">Member</span><span class="sxs-lookup"><span data-stu-id="e0b5a-105">Members</span></span>  
  
|<span data-ttu-id="e0b5a-106">Member</span><span class="sxs-lookup"><span data-stu-id="e0b5a-106">Member</span></span>|<span data-ttu-id="e0b5a-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e0b5a-107">Description</span></span>|  
|------------|-----------------|  
|`dclActionMask`|<span data-ttu-id="e0b5a-108">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-108">Reserved.</span></span>|  
|`dclActionNil`|<span data-ttu-id="e0b5a-109">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-109">Reserved.</span></span>|  
|`dclRequest`|<span data-ttu-id="e0b5a-110">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-110">Reserved.</span></span>|  
|`dclDemand`|<span data-ttu-id="e0b5a-111">Allen Aufrufern einer höheren Ebene in der Aufrufliste muss die vom aktuellen Berechtigungsobjekt angegebene Berechtigung erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-111">All callers higher in the call stack are required to have been granted the permission specified by the current permission object.</span></span>|  
|`dclAssert`|<span data-ttu-id="e0b5a-112">Der aufrufende Code kann die durch das aktuelle Berechtigungsobjekt identifizierte Ressource zugreifen, selbst wenn Aufrufern einer höheren Ebene im Stapel nicht die Berechtigung zum Zugriff auf die Ressource erteilt wurde</span><span class="sxs-lookup"><span data-stu-id="e0b5a-112">The calling code can access the resource identified by the current permission object, even if callers higher in the stack have not been granted permission to access the resource</span></span>|  
|`dclDeny`|<span data-ttu-id="e0b5a-113">Auch wenn diese Berechtigung für den Zugriff erteilt wurde, wird Aufrufern, der Zugriff auf die durch das aktuelle Berechtigungsobjekt angegebene Ressource verweigert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-113">The ability to access the resource specified by the current permission object is denied to callers, even if they have been granted permission to access it.</span></span>|  
|`dclPermitOnly`|<span data-ttu-id="e0b5a-114">Nur auf die durch dieses Berechtigungsobjekt angegebenen Ressourcen kann zugegriffen werden, selbst wenn dem Code die Berechtigung für den Zugriff auf andere Ressourcen gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-114">Only the resources specified by this permission object can be accessed, even if the code has been granted permission to access other resources.</span></span>|  
|`dclLinktimeCheck`|<span data-ttu-id="e0b5a-115">Der direkte Aufrufer muss die angegebene Berechtigung für einen bestimmten Zeitraum erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-115">The immediate caller is required to have been granted the specified permission for a given period of time.</span></span>|  
|`dclInheritanceCheck`|<span data-ttu-id="e0b5a-116">Die abgeleitete Klasse erbt von einer anderen Klasse oder eine Methode überschreibt muss die angegebene Berechtigung erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-116">The derived class inheriting another class or overriding a method is required to have been granted the specified permission.</span></span>|  
|`dclRequestMinimum`|<span data-ttu-id="e0b5a-117">Der Aufrufer kann für die minimalen Berechtigungen für den auszuführenden Code anfordern.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-117">The caller can request for the minimum permissions required for code to run.</span></span> <span data-ttu-id="e0b5a-118">Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-118">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestOptional`|<span data-ttu-id="e0b5a-119">Der Aufrufer kann für zusätzliche Berechtigungen anfordern, die optional sind (zur Ausführung nicht erforderlich).</span><span class="sxs-lookup"><span data-stu-id="e0b5a-119">The caller can request for additional permissions that are optional (not required to run).</span></span> <span data-ttu-id="e0b5a-120">Diese Anforderung lehnt implizit alle anderen nicht speziell angeforderten Berechtigungen ab.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-120">This request implicitly refuses all other permissions not specifically requested.</span></span> <span data-ttu-id="e0b5a-121">Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-121">This action can only be used within the scope of the assembly.</span></span>|  
|`dclRequestRefuse`|<span data-ttu-id="e0b5a-122">Die Anforderung des Aufrufers für Berechtigungen, die missbraucht werden könnten, wird nicht gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-122">The caller's request for permissions that might be misused will not be granted.</span></span> <span data-ttu-id="e0b5a-123">Diese Aktion kann nur innerhalb des Gültigkeitsbereichs der Assembly verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-123">This action can only be used within the scope of the assembly.</span></span>|  
|`dclPrejitGrant`|<span data-ttu-id="e0b5a-124">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-124">Reserved.</span></span>|  
|`dclPrejitDenied`|<span data-ttu-id="e0b5a-125">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-125">Reserved.</span></span>|  
|`dclNonCasDemand`|<span data-ttu-id="e0b5a-126">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-126">Reserved.</span></span>|  
|`dclNonCasLinkDemand`|<span data-ttu-id="e0b5a-127">Dem unmittelbaren Aufrufer muss die angegebene Berechtigung erteilt worden sein.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-127">The immediate caller is required to have been granted the specified permission.</span></span>|  
|`dclNonCasInheritance`|<span data-ttu-id="e0b5a-128">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-128">Reserved.</span></span>|  
|`dclLinkDemandChoice`|<span data-ttu-id="e0b5a-129">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-129">Reserved.</span></span>|  
|`dclInheritanceDemandChoice`|<span data-ttu-id="e0b5a-130">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-130">Reserved.</span></span>|  
|`dclDemandChoice`|<span data-ttu-id="e0b5a-131">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-131">Reserved.</span></span>|  
|`dclMaximumValue`|<span data-ttu-id="e0b5a-132">Reserviert.</span><span class="sxs-lookup"><span data-stu-id="e0b5a-132">Reserved.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0b5a-133">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e0b5a-133">Requirements</span></span>  
 <span data-ttu-id="e0b5a-134">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b5a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b5a-135">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="e0b5a-135">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="e0b5a-136">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="e0b5a-136">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0b5a-137">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0b5a-137">See also</span></span>

- [<span data-ttu-id="e0b5a-138">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e0b5a-138">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
