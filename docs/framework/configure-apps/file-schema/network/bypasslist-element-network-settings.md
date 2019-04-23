---
title: <bypasslist>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#bypasslist
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist
helpviewer_keywords:
- bypasslist element
- <bypasslist> element
ms.assetid: 124446b7-abb1-4e5e-a492-b64398f268f1
ms.openlocfilehash: d3d986dae478f49504dae21b9f39574b7887b4d2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202221"
---
# <a name="bypasslist-element-network-settings"></a><span data-ttu-id="01752-102">\<BypassList >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="01752-102">\<bypasslist> Element (Network Settings)</span></span>
<span data-ttu-id="01752-103">Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="01752-103">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>  
  
 <span data-ttu-id="01752-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="01752-104">\<configuration></span></span>  
<span data-ttu-id="01752-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="01752-105">\<system.net></span></span>  
<span data-ttu-id="01752-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="01752-106">\<defaultProxy></span></span>  
<span data-ttu-id="01752-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="01752-107">\<bypasslist></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01752-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="01752-108">Syntax</span></span>  
  
```xml  
<bypasslist>   
</bypasslist>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="01752-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="01752-109">Attributes and Elements</span></span>  
 <span data-ttu-id="01752-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="01752-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="01752-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="01752-111">Attributes</span></span>  
 <span data-ttu-id="01752-112">Keine</span><span class="sxs-lookup"><span data-stu-id="01752-112">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="01752-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01752-113">Child Elements</span></span>  
  
|<span data-ttu-id="01752-114">**Element**</span><span class="sxs-lookup"><span data-stu-id="01752-114">**Element**</span></span>|<span data-ttu-id="01752-115">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01752-115">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01752-116">add</span><span class="sxs-lookup"><span data-stu-id="01752-116">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-bypasslist-network-settings.md)|<span data-ttu-id="01752-117">Fügt eine IP-Adresse oder DNS-Namen, der Proxyumgehungsliste enthalten an.</span><span class="sxs-lookup"><span data-stu-id="01752-117">Adds an IP address or DNS name to the proxy bypass list.</span></span>|  
|[<span data-ttu-id="01752-118">clear</span><span class="sxs-lookup"><span data-stu-id="01752-118">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-bypasslist-network-settings.md)|<span data-ttu-id="01752-119">Löscht die Bypass-Liste.</span><span class="sxs-lookup"><span data-stu-id="01752-119">Clears the bypass list.</span></span>|  
|[<span data-ttu-id="01752-120">remove</span><span class="sxs-lookup"><span data-stu-id="01752-120">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-bypasslist-network-settings.md)|<span data-ttu-id="01752-121">Entfernt eine IP-Adresse oder DNS-Namen, aus der Proxyumgehungsliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="01752-121">Removes an IP address or DNS name from the proxy bypass list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="01752-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="01752-122">Parent Elements</span></span>  
  
|<span data-ttu-id="01752-123">**Element**</span><span class="sxs-lookup"><span data-stu-id="01752-123">**Element**</span></span>|<span data-ttu-id="01752-124">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01752-124">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="01752-125">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="01752-125">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="01752-126">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="01752-126">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01752-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="01752-127">Remarks</span></span>  
 <span data-ttu-id="01752-128">Die Bypass-Liste enthält reguläre Ausdrücke, die URIs beschreiben, <xref:System.Net.WebRequest> Instanzen, die direkt anstelle von über den Proxyserver zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="01752-128">The bypass list contains regular expressions that describe URIs that <xref:System.Net.WebRequest> instances access directly instead of through the proxy server.</span></span>  
  
 <span data-ttu-id="01752-129">Sie sollten Vorsicht walten, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="01752-129">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="01752-130">Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein.</span><span class="sxs-lookup"><span data-stu-id="01752-130">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="01752-131">Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie ein Ankerelement ("$"): "[a-Z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="01752-131">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="01752-132">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="01752-132">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="01752-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="01752-133">Configuration Files</span></span>  
 <span data-ttu-id="01752-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01752-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="01752-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="01752-135">Example</span></span>  
 <span data-ttu-id="01752-136">Im folgende Beispiel wird der Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="01752-136">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="01752-137">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, deren IP-Adressen beginnen mit 192.168. umgangen.</span><span class="sxs-lookup"><span data-stu-id="01752-137">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP addresses begin with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="01752-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="01752-138">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="01752-139">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="01752-139">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
