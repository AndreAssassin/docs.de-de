---
title: <defaultProxy> -Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultProxy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy
helpviewer_keywords:
- defaultProxy element
- <defaultProxy> element
ms.assetid: 9d663c4b-07b4-4f6f-9b12-efbd3630354f
ms.openlocfilehash: ce08dadb0fb7b986c0573b1514f9ecbbe2961c3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228341"
---
# <a name="defaultproxy-element-network-settings"></a><span data-ttu-id="7dafd-102">\<DefaultProxy >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="7dafd-102">\<defaultProxy> Element (Network Settings)</span></span>
<span data-ttu-id="7dafd-103">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="7dafd-103">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>  
  
 <span data-ttu-id="7dafd-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="7dafd-104">\<configuration></span></span>  
<span data-ttu-id="7dafd-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="7dafd-105">\<system.net></span></span>  
<span data-ttu-id="7dafd-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="7dafd-106">\<defaultProxy></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dafd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dafd-107">Syntax</span></span>  
  
```xml  
<defaultProxy  
  enabled="true|false"  
  useDefaultCredentials="true|false">  
    <bypasslist>...</bypasslist>  
    <proxy>...</proxy>  
    <module>...</module>  
</defaultProxy>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dafd-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dafd-108">Attributes and Elements</span></span>  
 <span data-ttu-id="7dafd-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dafd-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dafd-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dafd-110">Attributes</span></span>  
  
|**<span data-ttu-id="7dafd-111">Element</span><span class="sxs-lookup"><span data-stu-id="7dafd-111">Element</span></span>**|**<span data-ttu-id="7dafd-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dafd-112">Description</span></span>**|  
|-----------------|---------------------|  
|`enabled`|<span data-ttu-id="7dafd-113">Gibt an, ob ein Webproxy verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7dafd-113">Specifies whether a web proxy is used.</span></span> <span data-ttu-id="7dafd-114">Der Standardwert ist `true`.</span><span class="sxs-lookup"><span data-stu-id="7dafd-114">The default value is `true`.</span></span>|  
|`useDefaultCredentials`|<span data-ttu-id="7dafd-115">Gibt an, ob die Standardanmeldeinformationen für diesen Host für den Zugriff auf den Webproxy verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dafd-115">Specifies whether the default credentials for this host are used to access the web proxy.</span></span> <span data-ttu-id="7dafd-116">Der Standardwert ist `false`.</span><span class="sxs-lookup"><span data-stu-id="7dafd-116">The default value is `false`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dafd-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dafd-117">Child Elements</span></span>  
  
|**<span data-ttu-id="7dafd-118">Element</span><span class="sxs-lookup"><span data-stu-id="7dafd-118">Element</span></span>**|**<span data-ttu-id="7dafd-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dafd-119">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="7dafd-120">bypasslist</span><span class="sxs-lookup"><span data-stu-id="7dafd-120">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="7dafd-121">Gibt einen Satz von regulären Ausdrücken zur Beschreibung der Adressen an, die keinen Proxy verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dafd-121">Provides a set of regular expressions that describe addresses that do not use the proxy.</span></span>|  
|[<span data-ttu-id="7dafd-122">module</span><span class="sxs-lookup"><span data-stu-id="7dafd-122">module</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md)|<span data-ttu-id="7dafd-123">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="7dafd-123">Adds a new proxy module to the application.</span></span>|  
|[<span data-ttu-id="7dafd-124">Proxy</span><span class="sxs-lookup"><span data-stu-id="7dafd-124">proxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/proxy-element-network-settings.md)|<span data-ttu-id="7dafd-125">Definiert einen Proxyserver.</span><span class="sxs-lookup"><span data-stu-id="7dafd-125">Defines a proxy server.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="7dafd-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dafd-126">Parent Elements</span></span>  
  
|**<span data-ttu-id="7dafd-127">Element</span><span class="sxs-lookup"><span data-stu-id="7dafd-127">Element</span></span>**|**<span data-ttu-id="7dafd-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dafd-128">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="7dafd-129">system.net</span><span class="sxs-lookup"><span data-stu-id="7dafd-129">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="7dafd-130">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7dafd-130">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dafd-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dafd-131">Remarks</span></span>  
 <span data-ttu-id="7dafd-132">Wenn das defaultProxy-Element leer ist, werden die Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="7dafd-132">If the defaultProxy element is empty, the proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="7dafd-133">Dieses Verhalten unterscheidet sich von .NET Framework 1.1.</span><span class="sxs-lookup"><span data-stu-id="7dafd-133">This behavior is different from version 1.1 of the .NET Framework.</span></span>  
  
 <span data-ttu-id="7dafd-134">Eine Ausnahme wird ausgelöst, wenn die [Modul](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) Element gibt einen nicht öffentlichen Typ, der Typ nicht abgeleitet ist die <xref:System.Net.IWebProxy> -Klasse, eine Ausnahme vom Standardkonstruktor dieses Objekts aufgetreten ist, oder eine Ausnahme aufgetreten ist zwar das System angegebenen Standardproxys werden abgerufen.</span><span class="sxs-lookup"><span data-stu-id="7dafd-134">An exception is thrown if the [module](../../../../../docs/framework/configure-apps/file-schema/network/module-element-network-settings.md) element specifies a non-public type, the type is not deriving from the <xref:System.Net.IWebProxy> class, an exception from the default constructor of this object occurred, or an exception occurred while retrieving the system-specified default proxy.</span></span> <span data-ttu-id="7dafd-135">Die <xref:System.Exception.InnerException%2A>-Eigenschaft für die Ausnahme muss zusätzliche Informationen zur Fehlerursache enthalten.</span><span class="sxs-lookup"><span data-stu-id="7dafd-135">The <xref:System.Exception.InnerException%2A> property on the exception should have more information about the root cause of the error.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="7dafd-136">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="7dafd-136">Configuration Files</span></span>  
 <span data-ttu-id="7dafd-137">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7dafd-137">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dafd-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dafd-138">Example</span></span>  
 <span data-ttu-id="7dafd-139">Das folgende Beispiel verwendet die Standardeinstellungen des Internet Explorer-Proxys, gibt die Proxyadresse und umgeht den Proxy für lokale und "contoso.com".</span><span class="sxs-lookup"><span data-stu-id="7dafd-139">The following example uses the defaults from the Internet Explorer proxy, specifies the proxy address, and bypasses the proxy for local access and contoso.com.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <proxy  
        usesystemdefault="true"  
        proxyaddress="http://192.168.1.10:3128"  
        bypassonlocal="true"  
      />  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="7dafd-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dafd-140">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="7dafd-141">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="7dafd-141">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
