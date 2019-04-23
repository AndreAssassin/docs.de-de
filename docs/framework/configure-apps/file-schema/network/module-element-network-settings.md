---
title: <module>-Element (Netzwerkeinstellungen)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#module
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/defaultProxy/module
helpviewer_keywords:
- module element
- <module> element
ms.assetid: 10318725-9666-4d65-ab61-b94c64e59f13
ms.openlocfilehash: 0d108f2350d82666e3dc24f0f6854fe64ea4755f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59084114"
---
# <a name="module-element-network-settings"></a><span data-ttu-id="206aa-102">\<Modul >-Element (Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="206aa-102">\<module> Element (Network Settings)</span></span>
<span data-ttu-id="206aa-103">Fügt der Anwendung ein neues Proxymodul hinzu.</span><span class="sxs-lookup"><span data-stu-id="206aa-103">Adds a new proxy module to the application.</span></span>  
  
 <span data-ttu-id="206aa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="206aa-104">\<configuration></span></span>  
<span data-ttu-id="206aa-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="206aa-105">\<system.net></span></span>  
<span data-ttu-id="206aa-106">\<defaultProxy></span><span class="sxs-lookup"><span data-stu-id="206aa-106">\<defaultProxy></span></span>  
<span data-ttu-id="206aa-107">\<module></span><span class="sxs-lookup"><span data-stu-id="206aa-107">\<module></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="206aa-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="206aa-108">Syntax</span></span>  
  
```xml  
<module   
  type="type_fullname, assembly_fullname"   
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="206aa-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="206aa-109">Attributes and Elements</span></span>  
 <span data-ttu-id="206aa-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="206aa-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="206aa-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="206aa-111">Attributes</span></span>  
  
|<span data-ttu-id="206aa-112">**Attribut**</span><span class="sxs-lookup"><span data-stu-id="206aa-112">**Attribute**</span></span>|<span data-ttu-id="206aa-113">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="206aa-113">**Description**</span></span>|  
|-------------------|---------------------|  
|`type`|<span data-ttu-id="206aa-114">Den vollqualifizierten Typnamen (angegeben durch die <xref:System.Type.FullName%2A> Eigenschaft) und den Assemblynamen (erkennbar die <xref:System.Reflection.Assembly.FullName%2A> Eigenschaft), getrennt durch ein Komma, die der Proxy implementiert.</span><span class="sxs-lookup"><span data-stu-id="206aa-114">The fully qualified type name (indicated by the <xref:System.Type.FullName%2A> property) and the assembly name (indicated by the <xref:System.Reflection.Assembly.FullName%2A> property), separated by a comma, that implements the proxy.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="206aa-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="206aa-115">Child Elements</span></span>  
 <span data-ttu-id="206aa-116">Keine</span><span class="sxs-lookup"><span data-stu-id="206aa-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="206aa-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="206aa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="206aa-118">**Element**</span><span class="sxs-lookup"><span data-stu-id="206aa-118">**Element**</span></span>|<span data-ttu-id="206aa-119">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="206aa-119">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="206aa-120">defaultProxy</span><span class="sxs-lookup"><span data-stu-id="206aa-120">defaultProxy</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings.md)|<span data-ttu-id="206aa-121">Konfiguriert den HTTP-Proxyserver (Hypertext Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="206aa-121">Configures the Hypertext Transfer Protocol (HTTP) proxy server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="206aa-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="206aa-122">Remarks</span></span>  
 <span data-ttu-id="206aa-123">Die `module` Element registriert Proxyklassen, implementieren die <xref:System.Net.IWebProxy> Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="206aa-123">The `module` element registers proxy classes that implement the <xref:System.Net.IWebProxy> interface.</span></span> <span data-ttu-id="206aa-124">Nach dem Registrieren der Proxyklasse `module` zum Anfordern von Informationen über die unterstützten Proxy verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="206aa-124">After registering the proxy class, `module` can be used to request information through the supported proxy.</span></span>  
  
 <span data-ttu-id="206aa-125">Der Wert für die `type` Attribut sollte sein, den Klassennamen des Moduls und den Namen der entsprechenden Dynamic Link Library (DLL).</span><span class="sxs-lookup"><span data-stu-id="206aa-125">The value for the `type` attribute should be the class name of the module and the name of its corresponding Dynamic Link Library (DLL).</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="206aa-126">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="206aa-126">Configuration Files</span></span>  
 <span data-ttu-id="206aa-127">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="206aa-127">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="206aa-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="206aa-128">Example</span></span>  
 <span data-ttu-id="206aa-129">Das folgende Beispiel registriert eine benutzerdefinierten Proxy-Klasse.</span><span class="sxs-lookup"><span data-stu-id="206aa-129">The following example registers a custom proxy class.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <defaultProxy>  
      <module  
        type="Test.CustomWebProxy, TestProxy, Version=2.0.3600.0, Culture=neutral, PublicKeyToken=b23a5c561934e385"  
      />  
    </defaultProxy>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="206aa-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="206aa-130">See also</span></span>

- <xref:System.Net.IWebProxy?displayProperty=nameWithType>
- [<span data-ttu-id="206aa-131">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="206aa-131">Network Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
