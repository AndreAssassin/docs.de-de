---
title: Schema für App-Einstellungen
ms.date: 05/01/2017
helpviewer_keywords:
- schema app settings
- app settings, schema [Windows Forms]
- Windows Forms, app settings schema
- configuration schema [.NET Framework], app settings
ms.assetid: 99347d62-3ea5-40b6-bfec-c31431011422
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: d02f9f952c0ca7651d27571111a2d29f3d1130fe
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69921302"
---
# <a name="app-settings-schema"></a>Schema für App-Einstellungen

Dieses Thema enthält benutzerdefinierte Anwendungseinstellungen, z.B. Dateipfade, URLs für den XML-Webdienst oder andere benutzerdefinierte Konfigurationsinformationen für eine Anwendung.

[ **\<configuration>** ](../configuration-element.md)   
&nbsp;&nbsp;[ **\<appSettings>** ](appsettings-element-for-configuration.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<add>** ](add-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<clear>** ](clear-element-for-appsettings.md)   
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<remove>** ](remove-element-for-appsettings.md)

| Element | Beschreibung |
| ------- | ----------- |
| [ **\<appSettings>** ](appsettings-element-for-configuration.md) | Enthält die Tags **\<add>** , **\<clear>** und **\<remove>** zur Steuerung von App-Einstellungen. Verfügt über ein optionales **file**-Attribut. |
| [ **\<add>** ](add-element-for-appsettings.md) | Definiert eine Einstellung. Untergeordnetes Element von **\<appSettings>** . Erfordert **key**- und **value**-Attribute. |
| [ **\<clear>** ](clear-element-for-appsettings.md) | Löscht alle Einstellungen. Untergeordnetes Element von **\<appSettings>** . Besitzt keine Attribute. |
| [ **\<remove>** ](remove-element-for-appsettings.md) | Entfernt eine Einstellung. Untergeordnetes Element von **\<appSettings>** . Erfordert ein **key**-Attribut. |

## <a name="appsettings-element"></a>\<appSettings>-Element

Dieses Element enthält die Tags **\<add>** , **\<clear>** und **\<remove>** zur Steuerung von Anwendungseinstellungen. Es definiert ein optionales Attribut für **file**.

## <a name="add-element"></a>\<add>-Element

Fügt der Auflistung der Anwendungseinstellungen eine benutzerdefinierte Anwendungseinstellung als Name/Wertpaar hinzu. Es definiert Attribute für **key** und **value**

## <a name="clear-element"></a>\<clear>-Element

Entfernt alle Verweise auf geerbte benutzerdefinierte Anwendungseinstellung und lässt nur die Verweise zu, die durch **\<add>** -Elemente hinzugefügt werden, die dem **\<clear>** -Element folgen. Es definiert keine Attribute.

## <a name="remove-element"></a>\<remove>-Element

Entfernt einen Verweis auf eine geerbte benutzerdefinierte Anwendungseinstellung aus der Auflistung der Anwendungseinstellungen. Definiert ein Attribut für **key**.

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt eine externe Anwendungseinstellungsdatei (*custom.config*), die eine benutzerdefinierte Anwendungseinstellung definiert.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<appSettings>
  <add key="MyCustomSetting" value="MyCustomSettingValue" />
</appSettings>
```

Das folgende Beispiel zeigt eine Anwendungskonfigurationsdatei, die die Einstellung in der externen Einstellungsdatei verarbeitet und eine eigene Anwendungseinstellung festlegt.

```xml
<configuration>
  <appSettings file="custom.config">
    <add key="ApplicationName" value="MyApplication" />
  </appSettings>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über Anwendungseinstellungen](../../../winforms/advanced/application-settings-overview.md)
- [Architektur der Anwendungseinstellungen](../../../winforms/advanced/application-settings-architecture.md)
