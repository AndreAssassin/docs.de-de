---
title: ICLRDomainManager-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDomainManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager
helpviewer_keywords:
- ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce53149b92ca40ad50ecbefaf4701940e8567ae5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59103921"
---
# <a name="iclrdomainmanager-interface"></a><span data-ttu-id="a4521-102">ICLRDomainManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a4521-102">ICLRDomainManager Interface</span></span>
<span data-ttu-id="a4521-103">Ermöglicht dem Host an den Anwendungsdomänen-Manager, der zum Initialisieren von der Standardanwendungsdomäne, und klicken Sie zum Angeben von Eigenschaften zur datenquelleninitialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4521-103">Enables the host to specify the application domain manager that will be used to initialize the default application domain, and to specify initialization properties.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4521-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a4521-104">Methods</span></span>  
  
|<span data-ttu-id="a4521-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a4521-105">Method</span></span>|<span data-ttu-id="a4521-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a4521-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4521-107">SetAppDomainManagerType-Methode</span><span class="sxs-lookup"><span data-stu-id="a4521-107">SetAppDomainManagerType Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|<span data-ttu-id="a4521-108">Gibt an, die von abgeleiteten Typ, der <xref:System.AppDomainManager?displayProperty=nameWithType> -Klasse von den Anwendungsdomänen-Manager, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4521-108">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>|  
|[<span data-ttu-id="a4521-109">SetPropertiesForDefaultAppDomain-Methode</span><span class="sxs-lookup"><span data-stu-id="a4521-109">SetPropertiesForDefaultAppDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|<span data-ttu-id="a4521-110">Legt die Eigenschaften, die zum Initialisieren der Standardanwendungsdomäne verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4521-110">Sets properties that will be used to initialize the default application domain.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4521-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a4521-111">Remarks</span></span>  
 <span data-ttu-id="a4521-112">Um eine Instanz dieser Schnittstelle abzurufen, rufen die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) -Methode mit den Typ des Managers IID `IID_ICLRDomainManager`.</span><span class="sxs-lookup"><span data-stu-id="a4521-112">To get an instance of this interface, call the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method with the manager type IID `IID_ICLRDomainManager`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4521-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a4521-113">Requirements</span></span>  
 <span data-ttu-id="a4521-114">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4521-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4521-115">**Header:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="a4521-115">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a4521-116">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="a4521-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="a4521-117">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="a4521-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="a4521-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a4521-118">See also</span></span>

- [<span data-ttu-id="a4521-119">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a4521-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="a4521-120">Hosting</span><span class="sxs-lookup"><span data-stu-id="a4521-120">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
