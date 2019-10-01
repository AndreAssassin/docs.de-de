---
title: <remove>-Element für schemeSettings (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 4095ba51-de20-4f87-b562-018abe422c91
ms.openlocfilehash: 0dc8c6111157ba1f23d4a0449bee8f6626027e23
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697851"
---
# <a name="remove-element-for-schemesettings-uri-settings"></a><span data-ttu-id="d3705-102">\<remove >-Element für SchemeSettings (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3705-102">\<remove> Element for schemeSettings (Uri Settings)</span></span>
<span data-ttu-id="d3705-103">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="d3705-103">Removes a scheme setting for a scheme name.</span></span>  
  
[<span data-ttu-id="d3705-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d3705-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d3705-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d3705-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="d3705-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<schemesettings >** ](schemesettings-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="d3705-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<schemeSettings>**](schemesettings-element-uri-settings.md)</span></span>  
<span data-ttu-id="d3705-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="d3705-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3705-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="d3705-108">Syntax</span></span>  
  
```xml  
<remove
  name="http|https"
/>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d3705-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d3705-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d3705-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3705-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d3705-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="d3705-111">Attributes</span></span>  
  
|<span data-ttu-id="d3705-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="d3705-112">Attribute</span></span>|<span data-ttu-id="d3705-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3705-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d3705-114">NAME</span><span class="sxs-lookup"><span data-stu-id="d3705-114">name</span></span>|<span data-ttu-id="d3705-115">Der Name des Schemas, für das diese Einstellung gilt.</span><span class="sxs-lookup"><span data-stu-id="d3705-115">The scheme name for which this setting applies.</span></span> <span data-ttu-id="d3705-116">Die einzigen unterstützten Werte sind Name = "http" und Name = "https".</span><span class="sxs-lookup"><span data-stu-id="d3705-116">The only supported values are name="http" and name="https".</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d3705-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3705-117">Child Elements</span></span>  
 <span data-ttu-id="d3705-118">Keine</span><span class="sxs-lookup"><span data-stu-id="d3705-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d3705-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d3705-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d3705-120">Element</span><span class="sxs-lookup"><span data-stu-id="d3705-120">Element</span></span>|<span data-ttu-id="d3705-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d3705-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d3705-122">\<schemeSettings>-Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3705-122">\<schemeSettings> Element (Uri Settings)</span></span>](schemesettings-element-uri-settings.md)|<span data-ttu-id="d3705-123">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="d3705-123">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3705-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d3705-124">Remarks</span></span>  
 <span data-ttu-id="d3705-125">Standardmäßig werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung die Prozentwerte für Prozent codierte Pfad Trennzeichen aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="d3705-125">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="d3705-126">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="d3705-126">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d3705-127">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="d3705-127">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="d3705-128">Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="d3705-128">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="d3705-129">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType>-Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="d3705-129">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="d3705-130">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d3705-130">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="d3705-131">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="d3705-131">Configuration Files</span></span>  
 <span data-ttu-id="d3705-132">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d3705-132">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d3705-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d3705-133">Example</span></span>  
 <span data-ttu-id="d3705-134">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, mit der alle Schema Einstellungen für das http-Schema entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d3705-134">The following example shows a configuration used by the <xref:System.Uri> class that removes any scheme settings for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <remove name="http"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d3705-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d3705-135">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="d3705-136">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="d3705-136">Network Settings Schema</span></span>](index.md)
