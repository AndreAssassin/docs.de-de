---
title: Custom Element for SingleTagSectionHandler element
ms.date: 05/01/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/sectionName
helpviewer_keywords:
- custom element
ms.assetid: e62056c6-b351-40eb-afc0-cc13fc44e45e
author: guardrex
ms.author: mairaw
ms.openlocfilehash: bfc2a916e37ac27d45746eb268912b3752f4d80f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705297"
---
# <a name="custom-element-for-singletagsectionhandler"></a>Custom Element for SingleTagSectionHandler element

Definiert die Einstellungen in einem benutzerdefinierten Konfigurationsabschnitt, der durch definiert ist eine \<Abschnitt >-Element und verwendet die <xref:System.Configuration.SingleTagSectionHandler> Klasse.

[**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md)   
&nbsp;&nbsp;*\<sectionName>*

## <a name="syntax"></a>Syntax

```xml
<sectionName key="value" key2="value2" ... />
```

## <a name="attributes"></a>Attribute

Attribute und Attributwerte sind benutzerdefiniert.

## <a name="parent-element"></a>Übergeordnetes Element

|     | Beschreibung |
| --- | ----------- |
| [**\<configuration>**](~/docs/framework/configure-apps/file-schema/configuration-element.md) | Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei. |

## <a name="child-elements"></a>Untergeordnete Elemente

Keiner

## <a name="remarks"></a>Hinweise

Die  **\<SectionName >** Element ist ein benutzerdefiniertes Element, das definiert, indem eine [  **\<Abschnitt >** ](~/docs/framework/configure-apps/file-schema/section-element.md) -Tag in die [  **\<ConfigSections >** ](~/docs/framework/configure-apps/file-schema/configsections-element-for-configuration.md) Element. Gibt zurück, das Konfigurationssystem eine <xref:System.Collections.IDictionary> Objekt beim Aufrufen <xref:System.Configuration.Configuration.GetSection(System.String)?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Das folgende Beispiel deklariert ein benutzerdefiniertes Element namens  **\<SampleSection >** , das Lesen von Einstellungen enthält die <xref:System.Configuration.SingleTagSectionHandler> Klasse:

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

Dieses Element kann in der Anwendungskonfigurationsdatei, Konfigurationsdatei des Computers verwendet werden (*"Machine.config"*), und *"Web.config"* Dateien, die nicht auf Anwendungsebene Verzeichnis sind.

## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema für .NET Framework](~/docs/framework/configure-apps/file-schema/index.md)
