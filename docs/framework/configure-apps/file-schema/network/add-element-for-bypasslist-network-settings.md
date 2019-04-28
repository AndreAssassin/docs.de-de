---
title: <add>-Element für bypasslist (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/add
- http://schemas.microsoft.com/.NetConfiguration/v2.0#add
helpviewer_keywords:
- <bypasslist>, add element
- bypasslist, add element
- <add> element, bypasslist
- add element, bypasslist
ms.assetid: a0b86e28-86b4-4497-abe8-d5fd614c7926
ms.openlocfilehash: 904c8e23f7a09a975a6f3b9322ed6bc4148d9ba4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61674662"
---
# <a name="add-element-for-bypasslist-network-settings"></a><span data-ttu-id="20479-102">\<Hinzufügen >-Element für Bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="20479-102">\<add> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="20479-103">Fügt eine IP-Adresse oder DNS-Namen, der Proxyumgehungsliste enthalten an.</span><span class="sxs-lookup"><span data-stu-id="20479-103">Adds an IP address or DNS name to the proxy bypass list.</span></span>  
  
 <span data-ttu-id="20479-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="20479-104">\<configuration></span></span>  
<span data-ttu-id="20479-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="20479-105">\<system.net></span></span>  
<span data-ttu-id="20479-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="20479-106">\<defaultProxy></span></span>  
<span data-ttu-id="20479-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="20479-107">\<bypasslist></span></span>  
<span data-ttu-id="20479-108">\<add></span><span class="sxs-lookup"><span data-stu-id="20479-108">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20479-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="20479-109">Syntax</span></span>  
  
```xml  
<add   
  address="regular expression"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="20479-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="20479-110">Attributes and Elements</span></span>  
 <span data-ttu-id="20479-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="20479-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="20479-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="20479-112">Attributes</span></span>  
  
|<span data-ttu-id="20479-113">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="20479-113">**Attribute**</span></span>|<span data-ttu-id="20479-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="20479-114">**Description**</span></span>|  
|-------------------|---------------------|  
|<span data-ttu-id="20479-115">**address**</span><span class="sxs-lookup"><span data-stu-id="20479-115">**address**</span></span>|<span data-ttu-id="20479-116">Ein regulärer Ausdruck, ein IP-Adresse oder DNS-Namen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="20479-116">A regular expression describing an IP address or DNS name.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="20479-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20479-117">Child Elements</span></span>  
 <span data-ttu-id="20479-118">Keine</span><span class="sxs-lookup"><span data-stu-id="20479-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="20479-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="20479-119">Parent Elements</span></span>  
  
|<span data-ttu-id="20479-120">**Element**</span><span class="sxs-lookup"><span data-stu-id="20479-120">**Element**</span></span>|<span data-ttu-id="20479-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="20479-121">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="20479-122">bypasslist</span><span class="sxs-lookup"><span data-stu-id="20479-122">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="20479-123">Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="20479-123">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20479-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20479-124">Remarks</span></span>  
 <span data-ttu-id="20479-125">Die `add` -Element fügt reguläre Ausdrücke, die beschreiben, IP-Adressen oder DNS-Servernamen zur Liste der Adressen, die einen Proxyserver zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="20479-125">The `add` element inserts regular expressions describing IP addresses or DNS server names to the list of addresses that bypass a proxy server.</span></span>  
  
 <span data-ttu-id="20479-126">Der Wert des der `address` Attribut sollte sein, einen regulären Ausdruck, der einen Satz von IP-Adressen oder Hostnamen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="20479-126">The value of the `address` attribute should be a regular expression that describes a set of IP addresses or host names.</span></span>  
  
 <span data-ttu-id="20479-127">Sie sollten Vorsicht walten, wenn Sie einen regulären Ausdruck für dieses Element angeben.</span><span class="sxs-lookup"><span data-stu-id="20479-127">You should use caution when specifying a regular expression for this element.</span></span> <span data-ttu-id="20479-128">Der reguläre Ausdruck "[a-Z] +\\.contoso\\.com" entspricht, die jedem host in der Domäne "contoso.com", sondern auch mit jedem Host in der Domäne contoso.com.cpandl.com überein.</span><span class="sxs-lookup"><span data-stu-id="20479-128">The regular expression "[a-z]+\\.contoso\\.com" matches any host in the contoso.com domain, but it also matches any host in the contoso.com.cpandl.com domain.</span></span> <span data-ttu-id="20479-129">Um nur einen Host in der Domäne "contoso.com" zu vergleichen, verwenden Sie ein Ankerelement ("$"): "[a-Z] +\\.contoso\\.com$".</span><span class="sxs-lookup"><span data-stu-id="20479-129">To match only a host in the contoso.com domain, use an anchor ("$"): "[a-z]+\\.contoso\\.com$".</span></span>  
  
 <span data-ttu-id="20479-130">Weitere Informationen zu regulären Ausdrücken finden Sie unter. [Reguläre Ausdrücke von .NET Framework](../../../../../docs/standard/base-types/regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="20479-130">For more information about regular expressions, see .[.NET Framework Regular Expressions](../../../../../docs/standard/base-types/regular-expressions.md).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="20479-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="20479-131">Configuration Files</span></span>  
 <span data-ttu-id="20479-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="20479-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="20479-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="20479-133">Example</span></span>  
 <span data-ttu-id="20479-134">Im folgende Beispiel wird der Umgehungsliste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20479-134">The following example adds two addresses to the bypass list.</span></span> <span data-ttu-id="20479-135">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168. umgangen.</span><span class="sxs-lookup"><span data-stu-id="20479-135">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="20479-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20479-136">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="20479-137">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="20479-137">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
