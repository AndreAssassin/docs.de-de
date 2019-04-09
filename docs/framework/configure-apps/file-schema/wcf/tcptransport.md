---
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: 6c5bb61f234c8d5b8ffc5e16195a2cb50022d142
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166165"
---
# <a name="tcptransport"></a>\<tcpTransport>
Definiert einen TCP-Transport, der von einem Kanal zum Übertragen von Nachrichten für eine benutzerdefinierte Bindung verwendet werden kann.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<tcpTransport>  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpopint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|channelInitializationTimeout|Ruft das Zeitlimit zum Initialisieren eines Kanals ab, der akzeptiert werden soll, oder legt das Limit fest.  Die maximale Zeit in Sekunden, in der sich der Kanal im Initialisierungsstatus befinden kann, bevor die Verbindung getrennt wird. Dieses Kontingent umfasst die Zeit, die eine TCP-Verbindung ausführen kann, um sich über das .NET Message Framing-Protokoll zu authentifizieren. Ein Client muss vorab einige Daten senden, bevor der Server über genügend Informationen zum Ausführen der Authentifizierung verfügt. Der Standardwert ist 30 Sekunden.|  
|connectionBufferSize|Ruft die Puffergröße ab, oder legt die Puffergröße fest, die zum Übertragen eines Teils der serialisierten Nachricht vom Client oder Dienst verwendet wird.|  
|hostNameComparisonMode|Ruft einen Wert ab oder legt einen Wert fest, der angibt, ob der Hostname zum Erreichen des Diensts bei übereinstimmendem URI verwendet werden soll.|  
|listenBacklog|Die maximale Anzahl der Verbindungsanforderungen in der Warteschlange, die für einen Webdienst ausstehen können. Das `connectionLeaseTimeout`-Attribut beschränkt die Zeit, die ein Client wartet, bevor eine Verbindungsausnahme ausgelöst wird. Dies ist eine Eigenschaft auf Socketebene, die die maximale Anzahl der in der Warteschlange eingereihten Verbindungsanforderungen steuert, die für einen Webdienst ausstehend sein können. Wenn ListenBacklog zu niedrig ist, wird WCF keine Anforderungen mehr und neue Verbindungen aus diesem Grund löschen, bis der Server einige der vorhandenen Verbindungen in der Warteschlange bestätigt. Der Standardwert ist 16 * Anzahl der Prozessoren.|  
|manualAddressing|Ruft einen Wert ab, der angibt, ob eine manuelle Adressierung der Nachricht erforderlich ist, oder legt diesen fest.|  
|maxBufferPoolSize|Ruft die maximale Größe von Pufferpools ab, die vom Transport verwendet werden, oder legt diese fest.|  
|maxBufferSize|Ruft die maximale Größe des zu verwendenden Puffers ab oder legt diese fest. Bei Streamingnachrichten sollte dieser Wert mindestens die maximale Größe der Nachrichten-Header aufweisen, die im gepufferten Modus gelesen werden.|  
|maxOutputDelay|Ruft das maximale Zeitintervall ab, oder legt das maximale Zeitintervall fest, das als Teil einer Nachricht oder als vollständige Nachricht im Arbeitsspeicher gepuffert bleiben kann, bevor sie versendet wird.|  
|maxPendingAccepts|Ruft die maximale Anzahl ausstehender asynchroner Annahmevorgänge ab, die für die Verarbeitung beim Dienst eingehender Verbindungen zur Verfügung stehen, oder legt die maximale Anzahl fest.|  
|maxPendingConnections|Ruft die maximale Anzahl an Verbindungen ab, die zum Verteilen auf dem Dienst bereitstehen, oder legt sie fest.|  
|maxReceivedMessageSize|Ruft die maximal zulässige Größe der Nachrichten ab, die empfangen werden können, und legt diese fest.|  
|portSharingEnabled|Ein boolescher Wert, der angibt, ob die TCP-Anschlussfreigabe für diese Verbindung aktiviert ist. Wenn dies `false` ist, verwendet jede Bindung ihren eigenen Anschluss. Die Standardeinstellung ist `false`.<br /><br /> Diese Einstellung ist nur für Dienste relevant. Auf Clients hat dies keine Auswirkung.<br /><br /> Bei Verwendung dieser Einstellung muss der Windows Communication Foundation (WCF)-TCP-Anschlussfreigabedienst aktiviert werden, indem der Starttyp auf Manuell oder Automatisch gesetzt wird.|  
|teredoEnabled|Ein boolescher Wert, der angibt, ob das Teredo-Protokoll aktiviert ist, das zur Adressierung von Clients hinter einer Firewall verwendet wird. Die Standardeinstellung ist `false`.<br /><br /> Mit dieser Eigenschaft wird das Teredo-Protokoll für das zugrunde liegende TCP-Socket aktiviert. Weitere Informationen finden Sie unter [Überblick zu Teredo](https://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Diese Eigenschaft kann nur unter [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] und unter [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)] verwendet werden. [!INCLUDE[wv](../../../../../includes/wv-md.md)] verfügt über eine computerweite Konfigurationsoption für Teredo, sodass diese Eigenschaft unter Vista ignoriert. Um das Teredo-Protokoll verwenden zu können, müssen der Client und die Dienstcomputer über den IPv6-Stapel von Microsoft verfügen und ordnungsgemäß konfiguriert sein. Weitere Informationen zum Konfigurieren von Teredo finden Sie unter [Überblick zu Teredo](https://go.microsoft.com/fwlink/?LinkId=95339). Weitere Informationen finden Sie unter [Windows Server 2003 Technology Centers](https://go.microsoft.com/fwlink/?LinkId=49888).|  
|transferMode|Ruft einen Wert ab, oder legt einen Wert fest, der angibt, ob die Nachrichten bei verbindungsorientiertem Transport gepuffert oder per Stream übertragen werden.|  
|connectionPoolSettings|Gibt zusätzliche Verbindungspooleinstellungen für eine Named Pipe-Bindung an.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Dieser Transport verwendet URIs im Format "net.tcp://hostname:port/path". Andere URI-Komponenten sind optional.  
  
 Das `tcpTransport`-Element stellt den Startpunkt für das Erstellen einer benutzerdefinierten Bindung dar, die das TCP-Transportprotokoll implementiert. Dieser Transport ist für die Kommunikation zwischen WCF und WCF optimiert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Transportprotokolle](../../../../../docs/framework/wcf/feature-details/transports.md)
- [Wählen eines Transports](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [Bindungen](../../../../../docs/framework/wcf/bindings.md)
- [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
