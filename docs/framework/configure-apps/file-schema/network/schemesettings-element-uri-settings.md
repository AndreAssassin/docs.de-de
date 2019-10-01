---
title: <schemeSettings>-Element (URI-Einstellungen)
ms.date: 03/30/2017
ms.assetid: 0ae45c6e-8c4c-4c0d-8b9f-a93824648890
ms.openlocfilehash: 498aef77a1dfd8cffcac73b704b8d1bb6df5d165
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697768"
---
# <a name="schemesettings-element-uri-settings"></a><span data-ttu-id="85a85-102">\<schemesettings > Element (URI-Einstellungen)</span><span class="sxs-lookup"><span data-stu-id="85a85-102">\<schemeSettings> Element (Uri Settings)</span></span>
<span data-ttu-id="85a85-103">Gibt an, ob <xref:System.Uri> auf bestimmte Schemen analysiert wird.</span><span class="sxs-lookup"><span data-stu-id="85a85-103">Specifies how a <xref:System.Uri> will be parsed for specific schemes.</span></span>  
  
[<span data-ttu-id="85a85-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="85a85-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="85a85-105">&nbsp; @ no__t-1[ **\<uri >** ](uri-element-uri-settings.md)</span><span class="sxs-lookup"><span data-stu-id="85a85-105">&nbsp;&nbsp;[**\<uri>**](uri-element-uri-settings.md)</span></span>  
<span data-ttu-id="85a85-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<schemesettings >**</span><span class="sxs-lookup"><span data-stu-id="85a85-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<schemeSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a85-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="85a85-107">Syntax</span></span>  
  
```xml  
<schemeSettings>   
</schemeSettings>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="85a85-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="85a85-108">Attributes and Elements</span></span>  
 <span data-ttu-id="85a85-109">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="85a85-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="85a85-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="85a85-110">Attributes</span></span>  
 <span data-ttu-id="85a85-111">None</span><span class="sxs-lookup"><span data-stu-id="85a85-111">None</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="85a85-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85a85-112">Child Elements</span></span>  
  
|<span data-ttu-id="85a85-113">**Element**</span><span class="sxs-lookup"><span data-stu-id="85a85-113">**Element**</span></span>|<span data-ttu-id="85a85-114">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="85a85-114">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="85a85-115">add</span><span class="sxs-lookup"><span data-stu-id="85a85-115">add</span></span>](add-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="85a85-116">Fügt eine Schema Einstellung für einen Schema Namen hinzu.</span><span class="sxs-lookup"><span data-stu-id="85a85-116">Adds a scheme setting for a scheme name.</span></span>|  
|[<span data-ttu-id="85a85-117">clear</span><span class="sxs-lookup"><span data-stu-id="85a85-117">clear</span></span>](clear-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="85a85-118">Löscht alle vorhandenen Schema Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="85a85-118">Clears all existing scheme settings.</span></span>|  
|[<span data-ttu-id="85a85-119">remove</span><span class="sxs-lookup"><span data-stu-id="85a85-119">remove</span></span>](remove-element-for-schemesettings-uri-settings.md)|<span data-ttu-id="85a85-120">Entfernt eine Schema Einstellung für einen Schema Namen.</span><span class="sxs-lookup"><span data-stu-id="85a85-120">Removes a scheme setting for a scheme name.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="85a85-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="85a85-121">Parent Elements</span></span>  
  
|<span data-ttu-id="85a85-122">**Element**</span><span class="sxs-lookup"><span data-stu-id="85a85-122">**Element**</span></span>|<span data-ttu-id="85a85-123">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="85a85-123">**Description**</span></span>|  
|-----------------|---------------------|  
|[<span data-ttu-id="85a85-124">uri</span><span class="sxs-lookup"><span data-stu-id="85a85-124">uri</span></span>](uri-element-uri-settings.md)|<span data-ttu-id="85a85-125">Enthält Einstellungen, die angeben, wie die .NET Framework Webadressen verarbeitet, die mithilfe von URIs (Uniform Resource Identifier) ausgedrückt werden.</span><span class="sxs-lookup"><span data-stu-id="85a85-125">Contains settings that specify how the .NET Framework handles web addresses expressed using uniform resource identifiers (URIs).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85a85-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="85a85-126">Remarks</span></span>  
 <span data-ttu-id="85a85-127">Standardmäßig werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse vor dem Ausführen der Pfad Komprimierung die Prozentwerte für Prozent codierte Pfad Trennzeichen aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="85a85-127">By default, the <xref:System.Uri?displayProperty=nameWithType> class un-escapes percent encoded path delimiters before executing path compression.</span></span> <span data-ttu-id="85a85-128">Dies wurde als Sicherheitsmechanismus gegen Angriffe wie die folgende implementiert:</span><span class="sxs-lookup"><span data-stu-id="85a85-128">This was implemented as a security mechanism against attacks like the following:</span></span>  
  
 `http://www.contoso.com/..%2F..%2F/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="85a85-129">Wenn dieser URI an Module übermittelt wird, die Prozent codierte Zeichen nicht ordnungsgemäß verarbeiten, kann dies dazu führen, dass der folgende Befehl vom Server ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="85a85-129">If this URI gets passed down to modules not handling percent encoded characters correctly, it could result in the following command being executed by the server:</span></span>  
  
 `c:\Windows\System32\cmd.exe /c dir c:\`  
  
 <span data-ttu-id="85a85-130">Aus diesem Grund werden von der <xref:System.Uri?displayProperty=nameWithType>-Klasse zunächst Pfad Trennzeichen aufgehoben, und anschließend wird die Pfad Komprimierung angewendet.</span><span class="sxs-lookup"><span data-stu-id="85a85-130">For this reason, <xref:System.Uri?displayProperty=nameWithType> class first un-escapes path delimiters and then applies path compression.</span></span> <span data-ttu-id="85a85-131">Das Ergebnis der Übergabe der obigen bösartigen URL an den <xref:System.Uri?displayProperty=nameWithType>-Klassenkonstruktor führt zum folgenden URI:</span><span class="sxs-lookup"><span data-stu-id="85a85-131">The result of passing the malicious URL above to <xref:System.Uri?displayProperty=nameWithType> class constructor results in the following URI:</span></span>  
  
 `http://www.microsoft.com/Windows/System32/cmd.exe?/c+dir+c:\`  
  
 <span data-ttu-id="85a85-132">Dieses Standardverhalten kann so geändert werden, dass keine Escapezeichen für Prozent codierte Pfad Trennzeichen verwendet werden, indem die SchemeSettings-Konfigurationsoption für ein bestimmtes Schema verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="85a85-132">This default behavior can be modified to not un-escape percent encoded path delimiters using the schemeSettings configuration option for a specific scheme.</span></span>  
  
## <a name="configuration-files"></a><span data-ttu-id="85a85-133">Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="85a85-133">Configuration Files</span></span>  
 <span data-ttu-id="85a85-134">Dieses Element kann in der Anwendungskonfigurationsdatei oder in der Computerkonfigurationsdatei ("Machine.config") verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="85a85-134">This element can be used in the application configuration file or the machine configuration file (Machine.config).</span></span>  
  
## <a name="example"></a><span data-ttu-id="85a85-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="85a85-135">Example</span></span>  
 <span data-ttu-id="85a85-136">Das folgende Beispiel zeigt eine Konfiguration, die von der <xref:System.Uri>-Klasse verwendet wird, um das Escapezeichen für Prozent codierte Pfad Trennzeichen für das http-Schema zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="85a85-136">The following example shows a configuration used by the <xref:System.Uri> class to support not escaping percent-encoded path delimiters for the http scheme.</span></span>  
  
```xml  
<configuration>  
  <uri>  
    <schemeSettings>  
      <add name="http" genericUriParserOptions="DontUnescapePathDotsAndSlashes"/>  
    </schemeSettings>  
  </uri>  
</configuration>  
```  
  
## <a name="element-information"></a><span data-ttu-id="85a85-137">Elementinformationen</span><span class="sxs-lookup"><span data-stu-id="85a85-137">Element Information</span></span>  
  
|||
|-|-|  
|<span data-ttu-id="85a85-138">Namespace</span><span class="sxs-lookup"><span data-stu-id="85a85-138">Namespace</span></span>|<span data-ttu-id="85a85-139">System</span><span class="sxs-lookup"><span data-stu-id="85a85-139">System</span></span>|  
|<span data-ttu-id="85a85-140">Schemaname</span><span class="sxs-lookup"><span data-stu-id="85a85-140">Schema Name</span></span>||  
|<span data-ttu-id="85a85-141">Validierungsdatei</span><span class="sxs-lookup"><span data-stu-id="85a85-141">Validation File</span></span>||  
|<span data-ttu-id="85a85-142">Kann leer sein</span><span class="sxs-lookup"><span data-stu-id="85a85-142">Can be Empty</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="85a85-143">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85a85-143">See also</span></span>

- <xref:System.Configuration.SchemeSettingElement?displayProperty=nameWithType>
- <xref:System.Configuration.SchemeSettingElementCollection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection?displayProperty=nameWithType>
- <xref:System.Configuration.UriSection.SchemeSettings%2A?displayProperty=nameWithType>
- <xref:System.GenericUriParserOptions?displayProperty=nameWithType>
- <xref:System.Uri?displayProperty=nameWithType>
- [<span data-ttu-id="85a85-144">Network Settings Schema (Schema für Netzwerkeinstellungen)</span><span class="sxs-lookup"><span data-stu-id="85a85-144">Network Settings Schema</span></span>](index.md)
