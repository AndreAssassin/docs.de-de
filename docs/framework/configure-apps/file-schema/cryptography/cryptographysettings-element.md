---
title: <cryptographySettings>-Element
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib/cryptographySettings
- http://schemas.microsoft.com/.NetConfiguration/v2.0#cryptographySettings
helpviewer_keywords:
- cryptographySettings element
- <cryptographySettings> element
ms.assetid: 6201b7da-bcb7-49f7-b9f5-ba1fe05573b9
ms.openlocfilehash: ec3a5a73caa901a21e22dbec7500af9153e01ef4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61705219"
---
# <a name="cryptographysettings-element"></a>\<CryptographySettings >-Element
Enthält Kryptografieeinstellungen.  
  
 \<configuration>  
\<mscorlib>  
\<cryptographySettings>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <cryptographySettings>   
</cryptographySettings>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<cryptoNameMapping>](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptonamemapping-element.md)|Enthält die Zuordnung von Klassen zu den Anzeigenamen.|  
|[\<oidMap>](../../../../../docs/framework/configure-apps/file-schema/cryptography/oidmap-element.md)|Enthält die ASN. 1-Objekt-ID (OID)-Zuordnungen zu Klassen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
|`mscorlib`|Enthält die `cryptographySettings` Element.|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie mithilfe der  **\<CryptographySettings >** Element namenszuordnungen Kryptografie und OID-Zuordnungen enthalten. In diesem Beispiel wird die Laufzeit, damit <xref:System.Security.Cryptography.HashAlgorithm.Create%2A?displayProperty=nameWithType> gibt eine `MyHashClass` Objekt und die `MyCryptoClass` Zuordnungen, die die Objekt-ID 1.3.36.2.1 Klasse.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyHash="MyHashClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
               <cryptoClass   MyCrypto="MyCryptoClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="System.Security.Cryptography.HashAlgorithm"  
                       class="MyHash"/>  
         </cryptoNameMapping>  
         <oidMap>  
            <oidEntry OID="1.3.36.3.2.1"   name="MyCryptoClass"/>  
         </oidMap>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Cryptography Settings Schema (Schema für Kryptografieeinstellungen)](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [Cryptographic Services](../../../../../docs/standard/security/cryptographic-services.md)
