---
title: <basicHttpContextBinding>
ms.date: 03/30/2017
ms.assetid: 39b16b82-4ec6-4eff-8031-67e026870961
ms.openlocfilehash: 0f4bde41bdd37580d946af3195540082d3647e7a
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400635"
---
# <a name="basichttpcontextbinding"></a>\<basicHttpContextBinding>
Angeben einer Bindung, die Kontext für den Austausch von <xref:System.ServiceModel.BasicHttpBinding> bietet, indem HTTP-Cookies als Austauschmechanismus aktiviert werden.  
  
[ **\<configuration>** ](../configuration-element.md)\
&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<BasicHttpContextBinding->**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<basicHttpContextBinding>
  <binding allowCookies="Boolean"
           bypassProxyOnLocal="Boolean"
           closeTimeout="TimeSpan"
           envelopeVersion="None/Soap11/Soap12"
           hostNameComparisonMode="StrongWildCard/Exact/WeakWildcard"
           maxBufferPoolSize="Integer"
           maxBufferSize="Integer"
           maxReceivedMessageSize="Integer"
           messageEncoding="Text/Mtom"
           name="String"
           openTimeout="TimeSpan"
           proxyAddress="URI"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           textEncoding="UnicodeFffeTextEncoding/Utf16TextEncoding/Utf8TextEncoding"
           transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse"
           useDefaultWebProxy="Boolean">
    <security mode="None/Transport/Message/TransportWithMessageCredential/TransportCredentialOnly">
      <transport clientCredentialType="None/Basic/Digest/Ntlm/Windows/Certificate"
                 proxyCredentialType="None/Basic/Digest/Ntlm/Windows"
                 realm="String" />
      <message algorithmSuite="Aes128/Aes192/Aes256/Rsa15Aes128/ Rsa15Aes256/TripleDes"
               clientCredentialType="UserName/Certificate" />
    </security>
    <readerQuotas maxArrayLength="Integer"
                  maxBytesPerRead="Integer"
                  maxDepth="Integer"
                  maxNameTableCharCount="Integer"
                  maxStringContentLength="Integer" />
  </binding>
</basicHttpContextBinding>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`allowCookies`|Ein boolescher Wert, der angibt, ob der Client Cookies akzeptiert und für zukünftige Anfragen propagiert. Die Standardeinstellung ist `false`.<br /><br /> Sie können diese Eigenschaft verwenden, wenn Sie mit ASMX-Webdiensten interagieren, die Cookies verwenden. Auf diese Weise können Sie sicherstellen, dass die vom Server zurückgegebenen Cookies automatisch bei allen zukünftigen Clientanforderungen für diesen Dienst kopiert werden.|  
|`bypassProxyOnLocal`|Ein boolescher Wert, der angibt, ob der Proxyserver bei lokalen Adressen umgangen werden soll. Die Standardeinstellung ist `false`.<br /><br /> Eine Internetressource gilt als lokal, wenn sie über eine lokale Adresse verfügt. Eine lokale Adresse befindet, befindet sich auf demselben Computer, der lokalen LAN oder Intranet und wird erkannt werden, anhand des fehlenden Punkts (.) wie in den URIs " http://webserver/ "und" http://localhost/ ".<br /><br /> Durch dieses Attribut wird festgelegt, ob mit BasicHttpBinding konfigurierte Endpunkte den Proxyserver zum Zugreifen auf lokale Ressourcen verwenden. Wenn dieses Attribut `true` ist, wird bei Anforderungen lokaler Internetressourcen der Proxyserver nicht verwendet. Ist dieses Attribut auf `true` festgelegt, sollten Sie den Hostnamen anstatt localhost verwenden, wenn die Clients bei der Kommunikation mit Diensten auf demselben Computer einen Proxy nutzen sollen.<br /><br /> Wenn dieses Attribut `false` ist, werden alle Internetanforderungen über den Proxyserver ausgeführt.|  
|`closeTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Schließvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`envelopeVersion`|Gibt die SOAP-Version an, die für Nachrichten verwendet wird, die von dieser Bindung verarbeitet werden. Der einzig gültige Wert ist Soap11.|  
|`hostNameComparisonMode`|Gibt den HTTP-Hostnamen-Vergleichsmodus an, der verwendet wird, um URIs zu analysieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HostNameComparisonMode> und gibt an, ob beim Abgleich des URI der Hostname zum Erreichen des Dienstes verwendet wird. Der Standardwert lautet <xref:System.ServiceModel.HostNameComparisonMode.StrongWildcard>, wodurch der Hostname beim Abgleich ignoriert wird.|  
|`maxBufferPoolSize`|Eine ganze Zahl, die die maximale Speicherkapazität der Nachrichtenpuffer angibt, die Nachrichten aus dem Kanal empfangen. Der Standardwert ist 524288 (0x80000) Bytes.<br /><br /> Der Puffer-Manager reduziert den Pufferaufwand durch Verwendung eines Pufferpools. Puffer sind zur Verarbeitung von Nachrichten durch den Dienst erforderlich, wenn sie aus dem Kanal eintreffen. Wenn die Speicherkapazität des Pufferpools zur Verarbeitung der Nachrichten nicht ausreicht, muss der Puffer-Manager zusätzliche Speicherkapazität aus dem CLR-Heap zuweisen. Dadurch wird die Auslastung der Garbage Collection erhöht. Eine umfangreiche Zuweisung aus dem CLR-Heap der Garbage Collection weist darauf hin, dass die Größe des Pufferpools nicht ausreichend ist und dass die Leistung durch eine größere Zuweisung infolge einer Erhöhung der des maximalen Grenzwerts, der durch dieses Attribut angegeben wird, verbessert werden kann.|  
|`maxBufferSize`|Eine ganze Zahl, die die maximale Größe eines Puffers in Bytes angibt, in dem Nachrichten gespeichert werden, während sie für einen mit dieser Bindung konfigurierten Endpunkt verarbeitet werden. Der Standardwert ist 65.536 Bytes.|  
|`maxReceivedMessageSize`|Eine positive ganze Zahl, die die maximale Nachrichtengröße in Bytes einschließlich Header definiert, die in einem für diese Bindung konfigurierten Kanal beim Nachrichtenempfang zulässig ist. Der Absender erhält einen SOAP-Fehler, wenn die Nachricht zu groß für den Empfänger ist. Der Empfänger verwirft die Nachricht und erstellt einen Eintrag des Ereignisses im Ablaufverfolgungsprotokoll. Der Standardwert beträgt 65.536 Bytes.|  
|`messageEncoding`|Definiert den Encoder, der verwendet wird, um die SOAP-Nachricht zu codieren. Folgende Werte sind gültig:<br /><br /> Text Verwenden Sie einen Textnachrichten Encoder.<br />MTOM Verwenden Sie einen MTOM-Encoder (Message Transmission Organization Mechanism 1,0).<br /><br /> Der Standardwert ist Text. Dieses Attribut ist vom Typ <xref:System.ServiceModel.WSMessageEncoding>.|  
|`messageVersion`|Gibt die Nachrichtenversion an, die von den Clients und Diensten verwendet wird, die mit der Bindung konfiguriert wurden. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Channels.MessageVersion>.|  
|`name`|Eine Zeichenfolge, die den Konfigurationsnamen der Bindung enthält. Dieser Wert sollte eindeutig sein, da er von der Bindung zur Identifizierung verwendet wird. Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren. Außerdem kommt dieser Name bei den Bindungen eines Typs nur einmal vor. Ab [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] müssen Bindungen und Verhalten keinen Namen aufweisen. Weitere Informationen zur Standardkonfiguration und zu den namenlosen Bindungen und Verhalten finden Sie unter [vereinfachte Konfiguration](../../../wcf/simplified-configuration.md) und [vereinfachte Konfiguration für WCF-Dienste](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|`namespace`|Gibt den XML-Namespace der Bindung an. Der Standardwert ist „http://tempuri.org/Bindings“. Jede Bindung hat ein `name`-Attribut und ein `namespace`-Attribut, die die Bindung in den Metadaten des Diensts eindeutig identifizieren.|  
|`openTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Öffnungsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`proxyAddress`|Ein URI, der die Adresse des HTTP-Proxys enthält. Wenn `useSystemWebProxy` auf `true` festgelegt ist, muss diese Einstellung `null` lauten. Die Standardeinstellung ist `null`.|  
|`receiveTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Empfangsvorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:10:00.|  
|`sendTimeout`|Ein <xref:System.TimeSpan>-Wert, der das Zeitintervall für den Abschluss eines Sendevorgangs angibt. Dieser Wert muss größer oder gleich <xref:System.TimeSpan.Zero> sein. Der Standardwert ist 00:01:00.|  
|`textEncoding`|Legt die Zeichensatzkodierung fest, die zum Ausgeben von Nachrichten über die Bindung verwendet werden soll. Folgende Werte sind gültig:<br /><br /> BigEndianUnicode Unicode bigEndian-Codierung.<br />Unicode- 16-Bit-Codierung.<br />UTF8 8-Bit-Codierung<br /><br /> Der Standard ist UTF8. Dieses Attribut ist vom Typ <xref:System.Text.Encoding>.|  
|`transferMode`|Ein gültiger <xref:System.ServiceModel.TransferMode>-Wert, der angibt, ob Nachrichten bei einer Anforderung oder Antwort gepuffert oder per Stream übertragen werden.|  
|`useDefaultWebProxy`|Ein boolescher Wert, der angibt, ob der automatisch konfigurierte HTTP-Proxy des Systems bei Verfügbarkeit verwendet werden soll. Die Standardeinstellung ist `true`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|Definiert die Sicherheitseinstellungen für die Bindung. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>.|  
|[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|Definiert die Beschränkungen der Komplexität von SOAP-Nachrichten, die von Endpunkten verarbeitet werden können, die mit dieser Bindung konfiguriert wurden. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Dieses Element enthält eine Auflistung von standardmäßigen und benutzerdefinierten Bindungen.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Bindungselement bietet einen Schutzgrad und einen Austauschmechanismus als Teil des Kontextes für eine `BasicHttpBinding`.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.BasicHttpContextBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpContextBindingElement>
- <xref:System.ServiceModel.Channels.ContextBindingElement>
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](../../../misc/binding.md)
- [\<basicHttpBinding>](basichttpbinding.md)
