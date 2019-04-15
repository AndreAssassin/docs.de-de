---
title: Proxykonfiguration
ms.date: 06/18/2018
helpviewer_keywords:
- Networking
- adaptive proxies
- static proxies
- Network Resources
- Internet, proxy configuration
- proxies
- network, proxy configuration
- proxies, configuring
ms.assetid: 353c0a8b-4cee-44f6-8e65-60e286743df9
ms.openlocfilehash: c6b3808a2d73070cc07b31eb0fca7ca9d6af8cdb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59200544"
---
# <a name="proxy-configuration"></a><span data-ttu-id="fe88c-102">Proxykonfiguration</span><span class="sxs-lookup"><span data-stu-id="fe88c-102">Proxy Configuration</span></span>
<span data-ttu-id="fe88c-103">Ein Proxyserver verarbeitet Clientanforderungen für Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="fe88c-103">A proxy server handles client requests for resources.</span></span> <span data-ttu-id="fe88c-104">Ein Proxy kann eine angeforderte Ressource aus dem Cache zurückgeben oder die Anforderung an den Server weiterleiten, auf dem sich die Ressource befindet.</span><span class="sxs-lookup"><span data-stu-id="fe88c-104">A proxy can return a requested resource from its cache or forward the request to the server where the resource resides.</span></span> <span data-ttu-id="fe88c-105">Proxys können die Netzwerkleistung durch Reduzierung der Anzahl der an Remote-Server gesendeten Anforderungen verbessern.</span><span class="sxs-lookup"><span data-stu-id="fe88c-105">Proxies can improve network performance by reducing the number of requests sent to remote servers.</span></span> <span data-ttu-id="fe88c-106">Proxys können auch verwendet werden, um den Zugriff auf Ressourcen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="fe88c-106">Proxies can also be used to restrict access to resources.</span></span>  
  
## <a name="adaptive-proxies"></a><span data-ttu-id="fe88c-107">Adaptive Proxys</span><span class="sxs-lookup"><span data-stu-id="fe88c-107">Adaptive Proxies</span></span>  
 <span data-ttu-id="fe88c-108">Im .NET Framework gibt es zwei Grundtypen von Proxys: adaptive und statische.</span><span class="sxs-lookup"><span data-stu-id="fe88c-108">In the .NET Framework, proxies come in two varieties: adaptive and static.</span></span> <span data-ttu-id="fe88c-109">Adaptive Proxys ändern Sie ihre Einstellungen, wenn sich die Konfiguration ändert.</span><span class="sxs-lookup"><span data-stu-id="fe88c-109">Adaptive proxies adjust their settings when the network configuration changes.</span></span> <span data-ttu-id="fe88c-110">Wenn z. B. ein Laptop-Benutzer eine DFÜ-Netzwerkverbindung gestartet hat, würde ein adaptiver Proxy diese Änderung erkennen, das neue Konfigurationsskript entdecken und ausführen und die Einstellungen entsprechend anpassen.</span><span class="sxs-lookup"><span data-stu-id="fe88c-110">For example, if a laptop user starts a dialup network connection, an adaptive proxy would recognize this change, discover and run its new configuration script, and adjust its settings appropriately.</span></span>  
  
 <span data-ttu-id="fe88c-111">Adaptive Proxys werden durch ein Konfigurationsskript konfiguriert (siehe [Automatische Proxyerkennung](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span><span class="sxs-lookup"><span data-stu-id="fe88c-111">Adaptive proxies are configured by a configuration script (see [Automatic Proxy Detection](../../../docs/framework/network-programming/automatic-proxy-detection.md)).</span></span> <span data-ttu-id="fe88c-112">Das Skript generiert eine Reihe von Anwendungsprotokollen und ein Proxy für jedes Protokoll.</span><span class="sxs-lookup"><span data-stu-id="fe88c-112">The script generates a set of application protocols and a proxy for each protocol.</span></span>  
  
 <span data-ttu-id="fe88c-113">Änderungen in der Netzwerkumgebung erfordern, dass das System einen neuen Satz von Proxys verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe88c-113">Changes in the network environment may require that the system use a new set of proxies.</span></span> <span data-ttu-id="fe88c-114">Wenn eine Netzwerkverbindung ausfällt oder eine neue Netzwerkverbindung initialisiert wird, muss das System die entsprechende Quelle des Konfigurationsskripts in der neuen Umgebung erkennen und das neue Skript ausführen.</span><span class="sxs-lookup"><span data-stu-id="fe88c-114">If a network connection goes down or a new network connection is initialized, the system must discover the appropriate source of the configuration script in the new environment and run the new script.</span></span>  
  
 <span data-ttu-id="fe88c-115">Sie können das Attribut `usesystemdefault` des Elements [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) in der Konfigurationsdatei verwenden.</span><span class="sxs-lookup"><span data-stu-id="fe88c-115">You can use the `usesystemdefault` attribute of the [`<proxy>`](../configure-apps/file-schema/network/proxy-element-network-settings.md) element in your configuration file.</span></span> <span data-ttu-id="fe88c-116">Das `usesystemdefault`-Attribut steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Proxyumgehungsliste und lokale Proxyumgehung) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollten.</span><span class="sxs-lookup"><span data-stu-id="fe88c-116">The `usesystemdefault` attribute controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="fe88c-117">Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe88c-117">If this value is set to `true`, the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="fe88c-118">Wenn der Wert auf `false` oder gar nicht festgelegt ist, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fe88c-118">If this value is `false` or not set, the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="fe88c-119">Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fe88c-119">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>  
  
 <span data-ttu-id="fe88c-120">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fe88c-120">The following example shows a typical adaptive proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
      <proxy usesystemdefault="false" />
    </defaultProxy>  
</system.net>  
```  
  
## <a name="static-proxies"></a><span data-ttu-id="fe88c-121">Statische Proxys</span><span class="sxs-lookup"><span data-stu-id="fe88c-121">Static Proxies</span></span>  
 <span data-ttu-id="fe88c-122">Statische Proxys werden in der Regel explizit von einer Anwendung konfiguriert, oder wenn eine Konfigurationsdatei von einer Anwendung oder vom System aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fe88c-122">Static proxies are usually configured explicitly by an application, or when a configuration file is invoked by an application or the system.</span></span> <span data-ttu-id="fe88c-123">Statische Proxys sind in Netzwerken nützlich, in denen die Topologie sich nur selten verändert, wie z. B. bei einem Desktop-Computer, der mit einem Unternehmensnetzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="fe88c-123">Static proxies are useful in networks in which the topology changes infrequently, such as a desktop computer connected to a corporate network.</span></span>  
  
 <span data-ttu-id="fe88c-124">Mehrere Optionen steuern, wie ein statischer Proxy arbeitet.</span><span class="sxs-lookup"><span data-stu-id="fe88c-124">Several options control how a static proxy operates.</span></span> <span data-ttu-id="fe88c-125">Sie können Folgendes angeben:</span><span class="sxs-lookup"><span data-stu-id="fe88c-125">You can specify the following:</span></span>  
  
-   <span data-ttu-id="fe88c-126">Die Proxy-Adresse.</span><span class="sxs-lookup"><span data-stu-id="fe88c-126">The address of the proxy.</span></span>  
  
-   <span data-ttu-id="fe88c-127">Gibt an, ob der Proxy für lokale Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe88c-127">Whether the proxy should be bypassed for local addresses.</span></span>  
  
-   <span data-ttu-id="fe88c-128">Gibt an, ob der Proxy für eine Gruppe von Adressen umgangen werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe88c-128">Whether the proxy should be bypassed for a set of addresses.</span></span>  
  
 <span data-ttu-id="fe88c-129">Die folgende Tabelle zeigt die Konfigurationsoptionen für einen statischen Proxy.</span><span class="sxs-lookup"><span data-stu-id="fe88c-129">The following table shows the configuration options for a static proxy.</span></span>  
  
|<span data-ttu-id="fe88c-130">Attribut-, Eigenschafts- oder Konfigurationseinstellung</span><span class="sxs-lookup"><span data-stu-id="fe88c-130">Attribute, property, or configuration file setting</span></span>|<span data-ttu-id="fe88c-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe88c-131">Description</span></span>|  
|--------------------------------------------------------|-----------------|  
|`proxyaddress` <span data-ttu-id="fe88c-132">oder</span><span class="sxs-lookup"><span data-stu-id="fe88c-132">or</span></span> <xref:System.Net.WebProxy.Address>|<span data-ttu-id="fe88c-133">Die Adresse des Proxyservers, der verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="fe88c-133">The address of the proxy to use.</span></span>|  
|`bypassonlocal` <span data-ttu-id="fe88c-134">oder</span><span class="sxs-lookup"><span data-stu-id="fe88c-134">or</span></span> <xref:System.Net.WebProxy.BypassProxyOnLocal>|<span data-ttu-id="fe88c-135">Steuert, ob der Proxy für lokale Adressen umgangen wird.</span><span class="sxs-lookup"><span data-stu-id="fe88c-135">Controls whether the proxy is bypassed for local addresses.</span></span>|  
|`bypasslist` <span data-ttu-id="fe88c-136">oder</span><span class="sxs-lookup"><span data-stu-id="fe88c-136">or</span></span> <xref:System.Net.WebProxy.BypassArrayList>|<span data-ttu-id="fe88c-137">Beschreibt mit regulären Ausdrücken eine Reihe von Adressen, die den Proxyserver umgehen.</span><span class="sxs-lookup"><span data-stu-id="fe88c-137">Describes, with regular expressions, a set of addresses that bypass the proxy.</span></span>|  
|`usesystemdefault`|<span data-ttu-id="fe88c-138">Steuert, ob die statischen Proxyeinstellungen (Proxy-Adresse, Bypass-Liste und Bypass auf lokal) aus den Proxy-Einstellungen für den Benutzer im Internet Explorer gelesen werden sollte.</span><span class="sxs-lookup"><span data-stu-id="fe88c-138">Controls whether the static proxy settings (proxy address, bypass list, and bypass on local) should be read from the Internet Explorer proxy settings for the user.</span></span> <span data-ttu-id="fe88c-139">Wenn dieser Wert auf `true` festgelegt wird, werden die statischen Proxyeinstellungen von Internet Explorer verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe88c-139">If this value is set to `true`, then the static proxy settings from Internet Explorer will be used.</span></span> <span data-ttu-id="fe88c-140">Wenn dieser Wert in .NET Framework 2.0 auf `true` festgelegt wird, werden die Proxyeinstellungen von Internet Explorer nicht von anderen Proxyeinstellungen in der Konfigurationsdatei überschrieben.</span><span class="sxs-lookup"><span data-stu-id="fe88c-140">On .NET Framework 2.0 when this value is set to `true`, the Internet Explorer proxy settings are not overridden by other proxy settings in the configuration file.</span></span> <span data-ttu-id="fe88c-141">Auf dem .NET Framework 1.1 können die Internet Explorer-Proxy-Einstellungen von anderen Proxy-Einstellungen in der Konfigurationsdatei überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="fe88c-141">On .NET Framework 1.1, the Internet Explorer proxy settings can be overridden by other proxy settings in the configuration file.</span></span><br /><br /> <span data-ttu-id="fe88c-142">Wenn dieser Wert auf `false` oder gar nicht festgelegt wird, können die statischen Proxyeinstellungen in der Konfiguration angegeben werden. Sie überschreiben dann die Proxyeinstellungen von Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="fe88c-142">If this value is `false` or not set, then the static proxy settings can be specified in the configuration and will override the Internet Explorer proxy settings.</span></span> <span data-ttu-id="fe88c-143">Dieser Wert muss auch auf `false` oder gar nicht festgelegt werden, damit adaptive Proxys aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="fe88c-143">This value must also be set to `false` or not set for adaptive proxies to be enabled.</span></span>|  
  
 <span data-ttu-id="fe88c-144">Das folgende Beispiel zeigt eine typische adaptive Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="fe88c-144">The following example shows a typical static proxy configuration.</span></span>  
  
```xml  
<system.net>  
    <defaultProxy>  
        <proxy  proxyaddress="http://proxy.contoso.com:3128"  
                bypassonlocal="true"  
        />  
        <bypasslist>  
            <add address="[a-z]+.blueyonderairlines.com$" />  
        </bypasslist>  
    </defaultProxy>  
</system.net>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fe88c-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe88c-145">See also</span></span>

- <xref:System.Net.WebProxy>
- <xref:System.Net.GlobalProxySelection>
- [<span data-ttu-id="fe88c-146">Automatische Proxyerkennung</span><span class="sxs-lookup"><span data-stu-id="fe88c-146">Automatic Proxy Detection</span></span>](../../../docs/framework/network-programming/automatic-proxy-detection.md)
