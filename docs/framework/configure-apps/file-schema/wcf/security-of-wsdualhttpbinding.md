---
title: <security> von <wsDualHttpBinding>
ms.date: 03/30/2017
ms.assetid: 869c05e7-4ebe-467d-95ab-c8f8de4e6b9e
ms.openlocfilehash: b6a1c952b1ae65c8fb6f17237b5c15f3a8d4844a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399752"
---
# <a name="security-of-wsdualhttpbinding"></a>\<Sicherheits > von \<WSDualHttpBinding >
Definiert die Sicherheitsfunktionen der [ \<WSDualHttpBinding->](wsdualhttpbinding.md).  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WSDualHttpBinding->** ](wsdualhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security mode="Message/None">
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           negotiateServiceCredential="Boolean"/>
</security>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|Modus|Optionale. Gibt den angewendeten Sicherheitstyp an. Der Standardwert ist `Message`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSDualHttpSecurityMode>.|  
  
## <a name="mode-attribute"></a>Mode-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|None|Die Sicherheitsfunktionen sind deaktiviert.|  
|Meldung|Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<message>](message-of-wsdualhttpbinding.md)|Definiert die Einstellungen für die Sicherheit auf Nachrichtenebene. Dieses Element ist vom Typ <xref:System.ServiceModel.MessageSecurityOverHttp>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../misc/binding.md)|Definiert alle Bindungsfunktionen der [ \<WSDualHttpBinding->](wsdualhttpbinding.md).|  
  
## <a name="remarks"></a>Hinweise  
 Eine Dualbindung macht die IP-Adresse des Clients für den Dienst verfügbar. Der Client sollte Sicherheitseinstellungen verwenden, um sicherzustellen, dass nur Verbindungen zu vertrauenswürdigen Diensten hergestellt werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.WSDualHttpSecurity>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
