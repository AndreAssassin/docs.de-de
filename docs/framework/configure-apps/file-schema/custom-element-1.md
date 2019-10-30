---
title: Benutzerdefiniertes Element für SingleTagSectionHandler
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ac2d01121e81b545556fb082fa7b82c31cccf9da
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73118837"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Benutzerdefiniertes Element für SingleTagSectionHandler

Definiert Einstellungen in einem benutzerdefinierten Konfigurations Abschnitt, der von einem \<Abschnitt >-Element definiert wird und die <xref:System.Configuration.SingleTagSectionHandler>-Klasse verwendet.

[ **\<configuration>** ](configuration-element.md)   
&nbsp;&nbsp; *\<sectionName >*

## <a name="syntax"></a>Syntax

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Attribute

Attribute und Attributwerte sind Benutzer definiert.

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [ **\<configuration>** ](configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Das **\<sectionName >** -Element ist ein benutzerdefiniertes Element, das durch einen [ **\<Abschnitt >** ](section-element.md) -Tag im\<Element > [**configabschnitts**](configsections-element-for-configuration.md) definiert wird. Das Konfigurationssystem gibt ein <xref:System.Collections.IDictionary> Objekt zurück, wenn Sie <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>aufgerufen haben.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein benutzerdefiniertes Element namens **\<sampleSection >** deklariert, das die von der <xref:System.Configuration.SingleTagSectionHandler>-Klasse gelesenen Einstellungen enthält:

```xml
<configuration>
  <configSections>
    <section name="sampleSection" 
             type="System.Configuration.SingleTagSectionHandler" />
  </configSections>
  <sampleSection setting1="Value1" 
                 setting2="value two" 
                 setting3="third value" />
</configuration>
```

## <a name="configuration-file"></a>Konfigurationsdatei

Dieses Element kann in der Anwendungs Konfigurationsdatei, in der Computer Konfigurationsdatei (*Machine. config*) und in den *Web. config* -Dateien verwendet werden, die sich nicht auf der Ebene des Anwendungs Verzeichnisses befinden.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdatei Schema für die .NET Framework](index.md)
