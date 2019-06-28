---
title: <Library> (Element (.NET Native)
ms.date: 03/30/2017
ms.assetid: f642276b-33fb-4a81-b882-8808c31ba69e
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce001ed25d7704301d7f809887a445e3492e93fc
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67422536"
---
# <a name="library-element-net-native"></a>\<Library > (Element (.NET Native)
Definiert die Assembly, die Typen und Typmember enthält, deren Metadaten zur Laufzeit für die Reflektion verfügbar sind.  
  
 \<Directives>-Element  
\<Library>-Element  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<Library Name="assembly_name" />  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`Name`|Erforderliches Attribut. Gibt den Namen einer Assembly an. Untergeordnete Elemente dieses `<Library>`-Elements definieren die Laufzeitreflektionsrichtlinie für Typen und Typmember in dieser Assembly.|  
  
## <a name="name-attribute"></a>Namensattribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|*assembly_name*|Der einfache Name der Assembly ohne Dateierweiterung. Dieses Attribut entspricht der <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType>-Eigenschaft. Der Name einer Assembly namens Extensions.dll lautet beispielsweise "Extensions". Im Abschnitt „Hinweise“ ist eine besondere Form von *assembly_name* beschrieben, die den bedingten Einschluss von Metadaten aus der Assembly unterstützt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Assembly>](../../../docs/framework/net-native/assembly-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einer bestimmten Assembly an.|  
|[\<Namespace>](../../../docs/framework/net-native/namespace-element-net-native.md)|Wendet die Richtlinie auf alle Typen in einem bestimmten Namespace an.|  
|[\<Type>](../../../docs/framework/net-native/type-element-net-native.md)|Wendet die Richtlinie auf einen bestimmten Typ, z. B. eine Klasse oder Struktur, an.|  
|[\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)|Wendet die Richtlinie auf einen konstruierten generischen Typ an. Zum Beispiel kann ein [\<TypeInstantiation>](../../../docs/framework/net-native/typeinstantiation-element-net-native.md)-Element verwendet werden, um Richtlinien für einen `List<String>`-Typ zu definieren.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)|Das Stammelement einer Laufzeitanweisungsdatei.|  
  
## <a name="remarks"></a>Hinweise  
 Das [\<Directives>](../../../docs/framework/net-native/directives-element-net-native.md)-Element kann null (0), ein oder mehrere `<Library>`-Elemente enthalten.  
  
 Das `<Library>`-Element dient als Container für die Definition der Programmelemente, deren Metadaten zur Laufzeit benötigt werden. Dieses Element drückt keine Richtlinie aus. Zur Kompilierzeit durchsuchen die Compilertools nur die im `<Library>`-Element bezeichnete Bibliothek nach Programmelementen, die durch seine untergeordneten Elemente identifiziert werden. Im Gegensatz dazu durchsuchen Compilertools alle Bibliotheken, auch die .NET Framework-Kernbibliotheken, nach Programmelementen, die durch untergeordnete Elemente des [\<Application>](../../../docs/framework/net-native/application-element-net-native.md)-Elements identifiziert werden.  
  
 `<Library>`-Direktiven können bedingt verwendet werden. Wenn der Name des der `<Library>` Element beginnt und endet mit einem Sternchen (\*), wird die `<Library>` Richtlinie wirkt sich nur dann, wenn die app zwischen den Sternchen angegebene Assembly verwiesen wird. Beispielsweise gilt die folgende laufzeitanweisung nur dann, wenn die Utilities.dll-Assembly von der app verwiesen wird.  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
  <Library Name="*Utilities*">  
   ...  
  </Library>  
</Directives>  
```  
  
## <a name="see-also"></a>Siehe auch

- [\<Anwendung > Element](../../../docs/framework/net-native/application-element-net-native.md)
- [\<Directives >-Element](../../../docs/framework/net-native/directives-element-net-native.md)
- [Runtime Directives (rd.xml) Configuration File Reference (Referenz zur Laufzeitanweisungs-Konfigurationsdatei (rd.xml))](../../../docs/framework/net-native/runtime-directives-rd-xml-configuration-file-reference.md)
- [Elemente der Laufzeitanweisung](../../../docs/framework/net-native/runtime-directive-elements.md)
