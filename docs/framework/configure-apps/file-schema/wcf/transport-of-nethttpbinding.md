---
title: <transport> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 521aaf3913a1d30d10a674b71d4d98affcabc296
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399338"
---
# <a name="transport-of-nethttpbinding"></a>\<Transport > von \<"netthttpbinding" >
Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> "netthttpbinding"** ](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheits >** ](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Transport >**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<netHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|clientCredentialType|: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.  Die Standardeinstellung ist `None`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen. Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt. Der Standardwert ist eine leere Zeichenfolge.|  
|policyEnforcement|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
|protectionScenario|Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|None|Nachrichten werden nicht während der Übertragung gesichert.|  
|Einfach|Gibt die Standardauthentifizierung an.|  
|Digest|Gibt die Digestauthentifizierung an.|  
|Ntlm|Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.|  
|Windows|Gibt die integrierte Windows-Authentifizierung an.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType-Attribut  
  
|Wert|Description|  
|-----------|-----------------|  
|None|-Nachrichten werden während der Übertragung nicht gesichert.|  
|Einfach|Gibt die Standard Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.|  
|Digest|Gibt die Digest-Authentifizierung gemäß RFC 2617 – http-Authentifizierung an: Standard-und Digestauthentifizierung.|  
|Ntlm|Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.|  
|Windows|Gibt die integrierte Windows-Authentifizierung an.|  
|Zertifikat|Führt die Clientauthentifizierung mit einem Zertifikat aus. Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 None  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|Definiert die Sicherheitsfunktionen für die [ \<> "netthttpbinding](nethttpbinding.md)".|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht. Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
