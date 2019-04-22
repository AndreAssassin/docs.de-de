---
title: <connectionManagement>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/connectionManagement
- http://schemas.microsoft.com/.NetConfiguration/v2.0#connectionManagement
helpviewer_keywords:
- <connectionManagement> element
- connectionManagement element
ms.assetid: bedccaab-12a2-4511-8f67-e961f249aec6
ms.openlocfilehash: 4412fe30bfb8dcb3d7576df18cb2a472463d935c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59125184"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="68ec3-102">\<ConnectionManagement >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="68ec3-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="68ec3-103">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="68ec3-103">Specifies the maximum number of connections to a network host.</span></span>  
  
 <span data-ttu-id="68ec3-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="68ec3-104">\<configuration></span></span>  
<span data-ttu-id="68ec3-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="68ec3-105">\<system.net></span></span>  
<span data-ttu-id="68ec3-106">\<connectionManagement></span><span class="sxs-lookup"><span data-stu-id="68ec3-106">\<connectionManagement></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68ec3-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="68ec3-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="68ec3-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="68ec3-108">Attributes and Elements</span></span>  
 <span data-ttu-id="68ec3-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="68ec3-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="68ec3-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="68ec3-110">Attributes</span></span>  
 <span data-ttu-id="68ec3-111">Keine</span><span class="sxs-lookup"><span data-stu-id="68ec3-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="68ec3-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68ec3-112">Child Elements</span></span>  
  
|<span data-ttu-id="68ec3-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="68ec3-113">**Element**</span></span>|<span data-ttu-id="68ec3-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="68ec3-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="68ec3-115">add</span><span class="sxs-lookup"><span data-stu-id="68ec3-115">add</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="68ec3-116">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="68ec3-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="68ec3-117">clear</span><span class="sxs-lookup"><span data-stu-id="68ec3-117">clear</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="68ec3-118">Löscht der Verbindungsverwaltungsliste an.</span><span class="sxs-lookup"><span data-stu-id="68ec3-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="68ec3-119">remove</span><span class="sxs-lookup"><span data-stu-id="68ec3-119">remove</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="68ec3-120">Entfernt aus der Verbindungsverwaltungsliste eine IP-Adresse oder DNS-Namen.</span><span class="sxs-lookup"><span data-stu-id="68ec3-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="68ec3-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="68ec3-121">Parent Elements</span></span>  
  
|<span data-ttu-id="68ec3-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="68ec3-122">**Element**</span></span>|<span data-ttu-id="68ec3-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="68ec3-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="68ec3-124">system.net</span><span class="sxs-lookup"><span data-stu-id="68ec3-124">system.net</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/system-net-element-network-settings.md)|<span data-ttu-id="68ec3-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="68ec3-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="68ec3-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="68ec3-126">Remarks</span></span>  
 <span data-ttu-id="68ec3-127">Die `connectionManagement` Element definiert die maximale Anzahl von Verbindungen mit einem Server oder eine Gruppe von Servern.</span><span class="sxs-lookup"><span data-stu-id="68ec3-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="68ec3-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="68ec3-128">Configuration Files</span></span>  
 <span data-ttu-id="68ec3-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="68ec3-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="68ec3-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="68ec3-130">Example</span></span>  
 <span data-ttu-id="68ec3-131">Im folgenden Beispiel wird eine Anwendung für die Verwendung von vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern.</span><span class="sxs-lookup"><span data-stu-id="68ec3-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <connectionManagement>  
      <add address = "http://www.contoso.com" maxconnection = "4" />  
      <add address = "*" maxconnection = "2" />  
    </connectionManagement>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="68ec3-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="68ec3-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="68ec3-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="68ec3-133">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
