---
title: Schema für Kryptografieeinstellungen
ms.date: 03/30/2017
helpviewer_keywords:
- configuration schema [.NET Framework], cryptography
- elements [.NET Framework], cryptography
- schema configuration settings
- cryptography, settings schema
- cryptography, mapping algorithm names
- configuration sections [.NET Framework]
- configuration settings [.NET Framework], cryptography
ms.assetid: 1f55050a-b2a3-4868-a3c0-da20826150f3
ms.openlocfilehash: 00b04cc2175f4bb4cc0b74602cd3c26f4a4e342f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59184456"
---
# <a name="cryptography-settings-schema"></a>Schema für Kryptografieeinstellungen
Das Schema für Kryptografieeinstellungen enthält Elemente, die angeben, wie die Anzeigenamen von Algorithmen Klassen zugeordnet werden, die Kryptografiealgorithmen implementieren.  
  
 [**\<configuration>**](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)  
  
 [**\<mscorlib>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)  
  
 [**\<cryptographySettings>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)  
  
 [**\<cryptoNameMapping>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)  
  
 [**\<cryptoClasses>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)  
  
 [**\<cryptoClass>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)  
  
 [**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)  
  
 [**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)  
  
 [**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[**\<cryptoClasses**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclasses-element.md)|Enthält eine Liste von Kryptografieklassen, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet sind.|  
|[**\<cryptoClass**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptoclass-element.md)|Enthält eine Kryptografieklasse, die einem Anzeigenamen im Element **\<nameEntry>** zugeordnet ist.|  
|[**\<cryptographySettings**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md)|Enthält Kryptografieeinstellungen.|  
|[**\<cryptoNameMapping**>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|[**\<"mscorlib" >** -Element für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/mscorlib-element-for-cryptography-settings.md)|Enthält das Element **\<cryptographySettings>**.|  
|[**\<nameEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/nameentry-element.md)|Ordnet einen Klassennamen dem Anzeigenamen eines Algorithmus zu. Dadurch kann eine Klasse über viele Anzeigenamen verfügen.|  
|[**\<oidEntry>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidentry-element.md)|Ordnet einen ASN.1-Objektbezeichner (OID) einem Anzeigenamen zu.|  
|[**\<oidMap>**](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Enthält die ASN.1-OID-Zuordnungen zu Klassen.|  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)
