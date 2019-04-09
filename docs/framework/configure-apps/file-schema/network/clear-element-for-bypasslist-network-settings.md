---
title: <clear> -Element für Bypasslist (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/bypasslist/clear
- http://schemas.microsoft.com/.NetConfiguration/v2.0#clear
helpviewer_keywords:
- clear element, bypasslist
- <clear> element, bypasslist
- <bypasslist>, clear element
- bypasslist, clear element
ms.assetid: 301584ca-a914-4100-b180-3b288d3b099e
ms.openlocfilehash: 7499d15f1d57887ffc3e78b83ed686c0c0f46cf4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203521"
---
# <a name="clear-element-for-bypasslist-network-settings"></a><span data-ttu-id="af29a-102">\<clear >-Element für Bypasslist (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="af29a-102">\<clear> Element for bypasslist (Network Settings)</span></span>
<span data-ttu-id="af29a-103">Löscht der Proxyumgehungsliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="af29a-103">Clears the proxy bypass list.</span></span>  
  
 <span data-ttu-id="af29a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af29a-104">\<configuration></span></span>  
<span data-ttu-id="af29a-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="af29a-105">\<system.net></span></span>  
<span data-ttu-id="af29a-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="af29a-106">\<defaultProxy></span></span>  
<span data-ttu-id="af29a-107">\<bypasslist></span><span class="sxs-lookup"><span data-stu-id="af29a-107">\<bypasslist></span></span>  
<span data-ttu-id="af29a-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="af29a-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af29a-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="af29a-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af29a-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="af29a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af29a-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="af29a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af29a-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="af29a-112">Attributes</span></span>  
 <span data-ttu-id="af29a-113">Keine</span><span class="sxs-lookup"><span data-stu-id="af29a-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="af29a-114">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af29a-114">Child Elements</span></span>  
 <span data-ttu-id="af29a-115">Keine</span><span class="sxs-lookup"><span data-stu-id="af29a-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af29a-116">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="af29a-116">Parent Elements</span></span>  
  
|**<span data-ttu-id="af29a-117">Element</span><span class="sxs-lookup"><span data-stu-id="af29a-117">Element</span></span>**|**<span data-ttu-id="af29a-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="af29a-118">Description</span></span>**|  
|-----------------|---------------------|  
|[<span data-ttu-id="af29a-119">bypasslist</span><span class="sxs-lookup"><span data-stu-id="af29a-119">bypasslist</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/bypasslist-element-network-settings.md)|<span data-ttu-id="af29a-120">Bietet eine Reihe von regulären Ausdrücken, die Adressen beschreiben, die einen Proxy nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="af29a-120">Provides a set of regular expressions that describe addresses that do not use a proxy.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af29a-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="af29a-121">Remarks</span></span>  
 <span data-ttu-id="af29a-122">Die `clear` Element löscht alle Einträge in der Umgehungsliste aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="af29a-122">The `clear` element clears all entries from the bypass list.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="af29a-123">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="af29a-123">Configuration Files</span></span>  
 <span data-ttu-id="af29a-124">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af29a-124">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af29a-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af29a-125">Example</span></span>  
 <span data-ttu-id="af29a-126">Das folgende Beispiel löscht die Bypass-Liste und klicken Sie dann die Bypass-Liste zwei Adressen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="af29a-126">The following example clears the bypass list and then adds two addresses to the bypass list.</span></span> <span data-ttu-id="af29a-127">Die erste umgeht den Proxy für alle Server in der Domäne "contoso.com"; die zweite wird der Proxy für alle Server, dessen IP-Adresse beginnt, mit 192.168. umgangen.</span><span class="sxs-lookup"><span data-stu-id="af29a-127">The first bypasses the proxy for all servers in the contoso.com domain; the second bypasses the proxy for all servers whose IP address begins with 192.168.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <bypasslist>  
         <clear/>  
        <add address="[a-z]+\.contoso\.com$" />  
        <add address="192\.168\.\d{1,3}\.\d{1,3}" />  
      </bypasslist>  
    </defaultProxy>  
  </system.net>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="af29a-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af29a-128">See also</span></span>

- <xref:System.Net.WebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="af29a-129">Netzwerkeinstellungsschema</span><span class="sxs-lookup"><span data-stu-id="af29a-129">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
