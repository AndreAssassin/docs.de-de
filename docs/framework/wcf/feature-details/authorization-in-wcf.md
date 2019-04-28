---
title: Autorisierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 26aa445f3136fcb16e2eb9cdce6b245476297dfd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650579"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="80f6c-102">Autorisierung in WCF</span><span class="sxs-lookup"><span data-stu-id="80f6c-102">Authorization in WCF</span></span>
<span data-ttu-id="80f6c-103">Autorisierung ist der Prozess, Zugriff und Rechte für Ressourcen zu steuern, z. B. Dienste oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="80f6c-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="80f6c-104">Die Themen in diesem Abschnitt veranschaulichen Durchführung dieser grundlegenden Aufgaben in Windows Communication Foundation (WCF) in einer Vielzahl von Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="80f6c-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80f6c-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="80f6c-105">In This Section</span></span>  
 [<span data-ttu-id="80f6c-106">Zugriffssteuerungsmechanismen</span><span class="sxs-lookup"><span data-stu-id="80f6c-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="80f6c-107">Bietet eine kurze Übersicht über die Autorisierungsmechanismen in WCF und vorgeschlagenen verwendet.</span><span class="sxs-lookup"><span data-stu-id="80f6c-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="80f6c-108">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="80f6c-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="80f6c-109">Zeigt den Prozess zum Zugriff auf einen Dienst mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="80f6c-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="80f6c-110">Vorgehensweise: Verwenden des ASP.NET-Rollenanbieters mit einem Dienst</span><span class="sxs-lookup"><span data-stu-id="80f6c-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="80f6c-111">Führt durch die Konfiguration eines Diensts, um die Verwendung der Rollenanbieterfunktion von [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="80f6c-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="80f6c-112">Vorgehensweise: Verwenden Sie den Rollenanbieter ASP.NET-Autorisierungs-Manager bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="80f6c-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] <span data-ttu-id="80f6c-113">kann den Autorisierungs-Manager zum Verwalten der Autorisierung für eine Website verwenden.</span><span class="sxs-lookup"><span data-stu-id="80f6c-113">can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="80f6c-114">Auf ähnliche Weise kann WCF nutzen, die [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization-Manager-Kombination für die Autorisierung von Clients.</span><span class="sxs-lookup"><span data-stu-id="80f6c-114">WCF can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="80f6c-115">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="80f6c-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="80f6c-116">Erläutert die Grundlagen des Verwendens der Identitätsmodellinfrastruktur für auf Ansprüche basierende Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="80f6c-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="80f6c-117">Delegierung und Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="80f6c-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="80f6c-118">Erläutert den Unterschied zwischen Delegierung und Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="80f6c-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="80f6c-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="80f6c-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="80f6c-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="80f6c-120">Related Sections</span></span>  
 [<span data-ttu-id="80f6c-121">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="80f6c-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="80f6c-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="80f6c-122">See also</span></span>

- [<span data-ttu-id="80f6c-123">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="80f6c-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="80f6c-124">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="80f6c-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
