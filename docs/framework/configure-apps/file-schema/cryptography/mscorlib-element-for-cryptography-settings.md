---
title: <mscorlib> -Element für Kryptografieeinstellungen
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#mscorlib
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/mscorlib
helpviewer_keywords:
- mscorlib element
- <mscorlib> element
ms.assetid: d549668f-31f1-4b92-8021-a9135c09ca3c
ms.openlocfilehash: ec328bc4c63bd4754c6f975ac03e610718304245
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165151"
---
# <a name="mscorlib-element-for-cryptography-settings"></a>\<"mscorlib" >-Element für Kryptografieeinstellungen
Enthält die [ \<CryptographySettings >-Element](../../../../../docs/framework/configure-apps/file-schema/cryptography/cryptographysettings-element.md).  
  
 \<configuration>  
\<mscorlib>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
      <mscorlib>   
</mscorlib>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`cryptographySettings`|Enthält Kryptografieeinstellungen.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`configuration`|Das Stammelement in jeder von den Common Language Runtime- und .NET Framework-Anwendungen verwendeten Konfigurationsdatei.|  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der  **\<"mscorlib" >** Element auf eine kryptografischen Klasse verweisen und die Runtime zu konfigurieren. Sie können dann an die Zeichenfolge "RSA" übergeben der <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A?displayProperty=nameWithType> -Methode und die Verwendung der <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create%2A> -Methode zur Rückgabe einer `MyCryptoRSAClass` Objekt.  
  
```xml  
<configuration>  
   <mscorlib>  
      <cryptographySettings>  
         <cryptoNameMapping>  
            <cryptoClasses>  
               <cryptoClass   MyCryptoRSA="MyCryptoRSAClass, MyAssembly  
                  Culture=neutral, PublicKeyToken=a5d015c7d5a0b012,  
                  Version=1.0.0.0"/>  
            </cryptoClasses>  
            <nameEntry name="RSA" class="MyCryptoRSA"/>  
            <nameEntry name="System.Security.Cryptography.AsymmetricAlgorithm"  
                       class="MyCryptoRSA"/>  
         </cryptoNameMapping>  
      </cryptographySettings>  
   </mscorlib>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Cryptography.CryptoConfig.CreateFromName%2A>
- <xref:System.Security.Cryptography>
- [Konfigurationsdateischema](../../../../../docs/framework/configure-apps/file-schema/index.md)
- [Schema für Kryptografieeinstellungen](../../../../../docs/framework/configure-apps/file-schema/cryptography/index.md)
- [Kryptografische Dienste](../../../../../docs/standard/security/cryptographic-services.md)
- [Konfigurieren kryptografischer Klassen](../../../../../docs/framework/configure-apps/configure-cryptography-classes.md)
