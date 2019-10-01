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
ms.openlocfilehash: d377a77a4a1b4c57e9edd4fbfa364387f1bae479
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699431"
---
# <a name="connectionmanagement-element-network-settings"></a><span data-ttu-id="8865b-102">\<connectionmanagement >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8865b-102">\<connectionManagement> Element (Network Settings)</span></span>
<span data-ttu-id="8865b-103">Gibt die maximale Anzahl von Verbindungen mit einem Netzwerkhost an.</span><span class="sxs-lookup"><span data-stu-id="8865b-103">Specifies the maximum number of connections to a network host.</span></span>  
  
[<span data-ttu-id="8865b-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="8865b-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="8865b-105">&nbsp; @ no__t-1[ **@no__t -4system. net >** ](system-net-element-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="8865b-105">&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)</span></span>  
<span data-ttu-id="8865b-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<connectionmanagement >**</span><span class="sxs-lookup"><span data-stu-id="8865b-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionManagement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8865b-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="8865b-107">Syntax</span></span>  
  
```xml  
<connectionManagement>   
</connectionManagement>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="8865b-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="8865b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="8865b-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8865b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="8865b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="8865b-110">Attributes</span></span>  
 <span data-ttu-id="8865b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="8865b-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="8865b-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8865b-112">Child Elements</span></span>  
  
|<span data-ttu-id="8865b-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="8865b-113">**Element**</span></span>|<span data-ttu-id="8865b-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8865b-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8865b-115">add</span><span class="sxs-lookup"><span data-stu-id="8865b-115">add</span></span>](add-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8865b-116">Fügt der Verbindungsverwaltungsliste eine IP-Adresse oder einen DNS-Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="8865b-116">Adds an IP address or DNS name to the connection management list.</span></span>|  
|[<span data-ttu-id="8865b-117">clear</span><span class="sxs-lookup"><span data-stu-id="8865b-117">clear</span></span>](clear-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8865b-118">Löscht die Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="8865b-118">Clears the connection management list.</span></span>|  
|[<span data-ttu-id="8865b-119">remove</span><span class="sxs-lookup"><span data-stu-id="8865b-119">remove</span></span>](remove-element-for-connectionmanagement-network-settings.md)|<span data-ttu-id="8865b-120">Entfernt eine IP-Adresse oder einen DNS-Namen aus der Verbindungs Verwaltungsliste.</span><span class="sxs-lookup"><span data-stu-id="8865b-120">Removes an IP address or DNS name from the connection management list.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="8865b-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="8865b-121">Parent Elements</span></span>  
  
|<span data-ttu-id="8865b-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="8865b-122">**Element**</span></span>|<span data-ttu-id="8865b-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="8865b-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="8865b-124">system.net</span><span class="sxs-lookup"><span data-stu-id="8865b-124">system.net</span></span>](system-net-element-network-settings.md)|<span data-ttu-id="8865b-125">Enthält Einstellungen, die festlegen, wie Verbindungen zwischen .NET Framework und dem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8865b-125">Contains settings that specify how the .NET Framework connects to the network.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8865b-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8865b-126">Remarks</span></span>  
 <span data-ttu-id="8865b-127">Das `connectionManagement`-Element definiert die maximale Anzahl von Verbindungen mit einem Server oder einer Gruppe von Servern.</span><span class="sxs-lookup"><span data-stu-id="8865b-127">The `connectionManagement` element defines the maximum number of connections to a server or group of servers.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="8865b-128">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="8865b-128">Configuration Files</span></span>  
 <span data-ttu-id="8865b-129">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8865b-129">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="8865b-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8865b-130">Example</span></span>  
 <span data-ttu-id="8865b-131">Im folgenden Beispiel wird eine Anwendung so konfiguriert, dass vier Verbindungen mit dem Server `www.contoso.com` und zwei Verbindungen mit allen anderen Servern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8865b-131">The following example configures an application to use four connections to the server `www.contoso.com` and two connections to all other servers.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="8865b-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8865b-132">See also</span></span>

- <xref:System.Net.ServicePoint>
- <xref:System.Net.ServicePointManager>
- [<span data-ttu-id="8865b-133">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="8865b-133">Network Settings Schema</span></span>](index.md)
