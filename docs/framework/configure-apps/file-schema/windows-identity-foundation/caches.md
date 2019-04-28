---
title: <caches>
ms.date: 03/30/2017
ms.assetid: 4651091b-3a20-40d8-b293-4408c0710143
author: BrucePerlerMS
ms.openlocfilehash: b1d04280ef993297102d446ba5a7db54e8404dd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61750786"
---
# <a name="caches"></a><span data-ttu-id="c30fa-101">\<caches></span><span class="sxs-lookup"><span data-stu-id="c30fa-101">\<caches></span></span>
<span data-ttu-id="c30fa-102">Registriert die Caches für Sitzungstoken und Erkennung von tokenwiederholungen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c30fa-102">Registers the caches used for session tokens and token replay detection.</span></span>  
  
 <span data-ttu-id="c30fa-103">\<system.identityModel></span><span class="sxs-lookup"><span data-stu-id="c30fa-103">\<system.identityModel></span></span>  
<span data-ttu-id="c30fa-104">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c30fa-104">\<identityConfiguration></span></span>  
<span data-ttu-id="c30fa-105">\<caches></span><span class="sxs-lookup"><span data-stu-id="c30fa-105">\<caches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c30fa-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c30fa-106">Syntax</span></span>  
  
```xml  
<system.identityModel>  
  <identityConfiguration>  
    <caches>  
    </caches>  
  </identityConfiguration>  
</system.identityModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c30fa-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c30fa-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c30fa-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c30fa-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c30fa-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c30fa-109">Attributes</span></span>  
 <span data-ttu-id="c30fa-110">Keiner</span><span class="sxs-lookup"><span data-stu-id="c30fa-110">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c30fa-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c30fa-111">Child Elements</span></span>  
  
|<span data-ttu-id="c30fa-112">Element</span><span class="sxs-lookup"><span data-stu-id="c30fa-112">Element</span></span>|<span data-ttu-id="c30fa-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c30fa-113">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c30fa-114">\<sessionSecurityTokenCache></span><span class="sxs-lookup"><span data-stu-id="c30fa-114">\<sessionSecurityTokenCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/sessionsecuritytokencache.md)|<span data-ttu-id="c30fa-115">Registriert ein Zwischenspeicher für Sitzungstoken mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="c30fa-115">Registers a cache for session tokens with a service or a security token handler collection.</span></span>|  
|[<span data-ttu-id="c30fa-116">\<tokenReplayCache></span><span class="sxs-lookup"><span data-stu-id="c30fa-116">\<tokenReplayCache></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/tokenreplaycache.md)|<span data-ttu-id="c30fa-117">Registriert einen tokenwiederholungscache mit einem Dienst oder ein Sicherheitstoken-Handlerauflistung an.</span><span class="sxs-lookup"><span data-stu-id="c30fa-117">Registers a token replay cache with a service or a security token handler collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c30fa-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c30fa-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c30fa-119">Element</span><span class="sxs-lookup"><span data-stu-id="c30fa-119">Element</span></span>|<span data-ttu-id="c30fa-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c30fa-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c30fa-121">\<identityConfiguration></span><span class="sxs-lookup"><span data-stu-id="c30fa-121">\<identityConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/identityconfiguration.md)|<span data-ttu-id="c30fa-122">Gibt die identitätseinstellungen der Servicelevel.</span><span class="sxs-lookup"><span data-stu-id="c30fa-122">Specifies service-level identity settings.</span></span>|  
|[<span data-ttu-id="c30fa-123">\<securityTokenHandlerConfiguration></span><span class="sxs-lookup"><span data-stu-id="c30fa-123">\<securityTokenHandlerConfiguration></span></span>](../../../../../docs/framework/configure-apps/file-schema/windows-identity-foundation/securitytokenhandlerconfiguration.md)|<span data-ttu-id="c30fa-124">Stellt die Konfiguration für eine Auflistung der Tokenhandler.</span><span class="sxs-lookup"><span data-stu-id="c30fa-124">Provides configuration for a collection of security token handlers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c30fa-125">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c30fa-125">Remarks</span></span>  
 <span data-ttu-id="c30fa-126">Ein `<caches>` Element kann angegeben werden, auf der Dienstebene unter der `<identityConfiguration>` Element oder die Sicherheitsstufe für die Auflistung von Tokenhandler unter der `<securityTokenHandlerConfiguration>` Element.</span><span class="sxs-lookup"><span data-stu-id="c30fa-126">A `<caches>` element can be specified at the service level under the `<identityConfiguration>` element or on the security token handler collection level under the `<securityTokenHandlerConfiguration>` element.</span></span> <span data-ttu-id="c30fa-127">Einstellungen für eine Auflistung der Tokenhandler überschreiben jene, die für den Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="c30fa-127">Settings on a token handler collection override those specified on the service.</span></span>  
  
 <span data-ttu-id="c30fa-128">Die `<caches>` Element wird dargestellt, durch die <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c30fa-128">The `<caches>` element is represented by the <xref:System.IdentityModel.Configuration.IdentityModelCachesElement> class.</span></span> <span data-ttu-id="c30fa-129">Die konfigurierten Caches werden durch dargestellt die <xref:System.IdentityModel.Configuration.IdentityModelCaches> Klasse.</span><span class="sxs-lookup"><span data-stu-id="c30fa-129">The configured caches are represented by the <xref:System.IdentityModel.Configuration.IdentityModelCaches> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c30fa-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c30fa-130">Example</span></span>  
 <span data-ttu-id="c30fa-131">Das folgende XML zeigt die Konfiguration eines benutzerdefinierten Cache zum Speichern von Sicherheitstoken für die Sitzung (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span><span class="sxs-lookup"><span data-stu-id="c30fa-131">The following XML shows the configuration of a custom cache for holding session security tokens (<xref:System.IdentityModel.Tokens.SessionSecurityToken>).</span></span> <span data-ttu-id="c30fa-132">Die Konfiguration stammt aus dem `ClaimsAwareWebFarm` Beispiel.</span><span class="sxs-lookup"><span data-stu-id="c30fa-132">The configuration is taken from the `ClaimsAwareWebFarm` sample.</span></span>  
  
```xml  
<caches>  
  <sessionSecurityTokenCache type="CacheLibrary.SharedSessionSecurityTokenCache, CacheLibrary">  
    <!--cacheServiceAddress points to the centralized session security token cache service running in the web farm.-->  
    <cacheServiceAddress url="http://localhost:4161/SessionSecurityTokenCacheService.svc" />  
  </sessionSecurityTokenCache>  
</caches>  
```
