---
title: Vom System bereitgestellte Bindungen
description: Erfahren Sie alles zu den vom System bereitgestellten WCF-Bindungen (Windows Communication Foundation).
ms.date: 06/05/2018
helpviewer_keywords:
- bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
ms.openlocfilehash: 3c6c6b628d208aede8c547dcfa66fc189a26ae01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791507"
---
# <a name="system-provided-bindings"></a>Vom System bereitgestellte Bindungen

Bindungen geben den Kommunikationsmechanismus für die Kommunikation mit einem Endpunkt und die zum Herstellen einer Verbindung mit einem Endpunkt erforderlichen Kommunikationsdetails an. Eine Bindung enthält die folgenden Elemente:

- Der Protokollstapel legt die Einstellungen bezüglich Sicherheit, Zuverlässigkeit und Kontextablauf fest, die beim Senden von Nachrichten zum Endpunkt verwendet werden.

- Die Transportebene bestimmt das zugrunde liegende Transportprotokoll, das zum Senden von Nachrichten zum Endpunkt verwendet werden soll, beispielsweise TCP oder HTTP.

- Die Codierung bestimmt die Nachrichtencodierung, die für Nachrichten verwendet werden soll, die an den Endpunkt gesendet werden. Beispielsweise Text/XML, binär, Message Transmission Optimization Mechanism (MTOM).

 In diesem Artikel sind alle vom System bereitgestellten WCF-Bindungen (Windows Communication Foundation) aufgeführt. Wenn keine dieser Bindungen die Kriterien der Anwendung erfüllt, können Sie eine benutzerdefinierte Bindung erstellen. Weitere Informationen zum Erstellen benutzerdefinierter Bindungen finden Sie unter [Benutzerdefinierte Bindungen](./extending/custom-bindings.md).

 Eine sichere und vollständig kompatible Bindung, die das WS-Federationprotokoll unterstützt, ermöglicht es einem Verbund angehörenden Organisationen, Benutzer effizient zu authentifizieren und zu autorisieren.

> [!IMPORTANT]
> Wählen Sie immer eine Bindung aus, die Sicherheitsfunktionen einschließt. Standardmäßig weisen alle Bindungen mit Ausnahme des [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md)-Elements aktivierte Sicherheitsfunktionen auf. Wenn Sie keine sichere Bindung auswählen oder Sicherheitsfunktionen deaktivieren, müssen Sie die Daten auf eine andere Weise schützen, z.&amp;#160;B. durch ein geschütztes Rechenzentrum oder ein isoliertes Netzwerk.

> [!IMPORTANT]
> Verwenden Sie nur dann Duplexverträge mit Bindungen, die keine Sicherheitsfunktionen unterstützen oder bei denen die Sicherheitsfunktionen deaktiviert sind, wenn Sie die Daten auf andere Weise schützen.

Die folgenden Bindungen sind im Lieferumfang von WCF enthalten.

|Bindung|Konfigurationselement|Beschreibung|
|-------------|---------------------------|-----------------|
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md)|Eine Bindung, die sich für die Kommunikation mit Webdiensten eignet, die mit WS-Basic Profile kompatibel sind, beispielsweise auf ASP.NET-Webdiensten (ASMX) basierende Dienste. Diese Bindung verwendet HTTP als Transport und Text/XML als Standardnachrichtencodierung.|
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die sich für Nicht-Duplexdienstverträge eignet.|
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die für Duplexdienstverträge oder für die Kommunikation über SOAP-Vermittler geeignet ist.|
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Eine sichere und vollständig kompatible Bindung, die das WS-Verbundsprotokoll unterstützt, die es einem Verbund angehörenden Organisationen ermöglicht, Benutzer effizient zu authentifizieren und zu autorisieren.|
|<xref:System.ServiceModel.NetHttpBinding>|[\<netHttpBinding>](../configure-apps/file-schema/wcf/nethttpbinding.md)|Eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet.|
|<xref:System.ServiceModel.NetHttpsBinding>|[\<netHttpsBinding>](../configure-apps/file-schema/wcf/nethttpsbinding.md)|Eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte sichere Bindung, die standardmäßig die binäre Codierung verwendet.|
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)|Eine sichere und optimierte Bindung, die sich für die computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../configure-apps/file-schema/wcf/netnamedpipebinding.md)|Eine sichere, zuverlässige und optimierte Bindung, die sich für die Kommunikation zwischen WCF-Anwendungen auf einem Computer eignet.|
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../configure-apps/file-schema/wcf/netmsmqbinding.md)|Eine der Warteschlange hinzugefügte Bindung, die sich für eine computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet.|
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../configure-apps/file-schema/wcf/netpeertcpbinding.md)|Eine Bindung, die eine sichere Kommunikation zwischen mehreren Computern ermöglicht.|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Eine Bindung, die sich für eine computerübergreifende Kommunikation zwischen einer WCF-Anwendung und vorhandenen Message Queuing-Anwendungen eignet.|
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding>](../configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Eine Bindung, die sich für die Kommunikation mit Webdiensten eignet, die mit WS-Basic Profile kompatibel sind, und so die Verwendung von HTTP-Cookies zum Austauschen von Kontext ermöglicht.|
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding>](../configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Eine sichere und optimierte Bindung, die sich für die computerübergreifende Kommunikation zwischen WCF-Anwendungen eignet und so die Verwendung von SOAP-Headern zum Austauschen von Kontext ermöglicht.|
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../configure-apps/file-schema/wcf/webhttpbinding.md)|Eine Bindung, die zum Konfigurieren von Endpunkten für WCF-Webdienste verwendet wird, die durch HTTP-Anforderungen und nicht durch SOAP-Nachrichten bereitgestellt werden.|
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding>](../configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Eine sichere und vollständig kompatible Bindung, die sich für Nicht-Duplexdienstverträge eignet und so die Verwendung von SOAP-Headern zum Austauschen von Kontext ermöglicht.|
|<xref:System.ServiceModel.UdpBinding>|[\<udpBinding>](../configure-apps/file-schema/wcf/udpbinding.md)|Eine Bindung, die verwendet werden soll, wenn eine große Menge einfacher Nachrichten an eine große Anzahl von Clients gleichzeitig gesendet werden soll.|

 In der folgenden Tabelle sind die Funktionen der einzelnen vom System bereitgestellten Bindungen dargestellt. Die Bindungen sind in den Tabellenspalten angegeben. Die Funktionen werden in den Zeilen aufgelistet und in der zweiten Tabelle beschrieben. In der folgenden Tabelle werden die im Zusammenhang mit Bindungen verwendeten Abkürzungen erklärt. Zur Auswahl einer Bindung ermitteln Sie, welche Spalte in den Zeilen alle Funktionen enthält, die Sie benötigen.

|Bindung|Interoperabilität|Sicherheit (Standard)|Sitzung<br />(Standard)|Transaktionen|Duplex|Codierung (Standard)|Streaming<br />(Standard)|
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Keine), Transport, Nachricht, Gemischt|(Keine)|(Keine)|n/v|Text, (MTOM)|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.WSHttpBinding>|WS|Transport, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung, Sicherheitssitzung|(Keine), Ja|n/v|(Text), MTOM|Nein|
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Nachricht), Keine|(Zuverlässige Sitzung), Sicherheitssitzung|(Keine), Ja|Ja|(Text), MTOM|Nein|
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Nachricht), Gemischt, Keine|(Keine), zuverlässige Sitzung, Sicherheitssitzung|(Keine), Ja|Nein|(Text), MTOM|Nein|
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(Keine), Transport, Nachricht, TransportWithMessageCredential, TransportCredentialOnly|Siehe den Hinweis unten.|Keiner|Siehe den Hinweis unten.|(Binär), Text, MTOM|Ja (gepuffert)|
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Transport), TransportWithMessageCredential|Siehe den Hinweis unten.|Keiner|Siehe den Hinweis unten.|(Binär), Text, MTOM|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transport), Nachricht, Keine, Gemischt|(Transport), zuverlässige Sitzung, Sicherheitssitzung|(Keine), Ja|Ja|Binär|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transport), Keine|Keine, (Transport)|(Keine), Ja|Ja|Binär|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Nachricht, (Transport), Keine|Keine, (Transport)|Keine, (Ja)|Nein|Binär|Nein|
|<xref:System.ServiceModel.NetPeerTcpBinding>|Peer|(Transport)|(Keine)|(Keine)|Ja||Nein|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Transport)|(Keine)|Keine, (Ja)|n/v|n/v|Nein|
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(Keine), Transport, Nachricht, Gemischt|(Keine)|(Keine)|n/v|Text, (MTOM)|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transport), Nachricht, Keine, Gemischt|(Transport), zuverlässige Sitzung, Sicherheitssitzung|(Keine), Ja|Ja|Binär|Ja<br />(gepuffert)|
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Transport, (Nachricht), Gemischt|(Keine), zuverlässige Sitzung, Sicherheitssitzung|(Keine), Ja|n/v|Text, (MTOM)|Nein|
|<xref:System.ServiceModel.UdpBinding> <br /><br /> **Hinweis**:  Interoperabilität lässt sich durch Implementieren der SOAP-über-UDP-Standardspezifikation erzielen, die von dieser Bindung implementiert wird.|.NET|(Keine)|(Keine)|(Keine)|n/v|(Text)|Nein|

> [!IMPORTANT]
> <xref:System.ServiceModel.NetHttpBinding> ist eine für die Nutzung von HTTP- oder WebSocket-Diensten entwickelte Bindung, die standardmäßig die binäre Codierung verwendet. Die <xref:System.ServiceModel.NetHttpBinding> erkennt, ob sie mit einem Anforderung-Antwort-Vertrag oder einem Duplexvertrag verwendet wird, und ändert das Verhalten entsprechend, indem HTTP für Anforderung-Antwort und WebSockets für Duplex verwendet werden. Dieses Verhalten kann überschrieben werden, mithilfe der <xref:System.ServiceModel.Channels.WebSocketTransportUsage> Bindung festlegen: WhenDuplex: Dies ist der Standardwert, der das oben beschriebene Verhalten aufweist. Never: Verhindert die Verwendung von WebSockets. Der Versuch, einen Duplexvertrag mit dieser Einstellung zu verwenden, löst eine Ausnahme aus. Always: Erzwingt die Verwendung von WebSockets sogar für Anforderung-Antwort-Verträge. NetHttpBinding unterstützt zuverlässige Sitzungen im HTTP-Modus und WebSocket-Modus. Im WebSocket-Modus werden Sitzungen vom Transport bereitgestellt.

 Die in der vorstehenden Tabelle aufgeführten Funktionen werden in der folgenden Tabelle erläutert.

|Feature|Beschreibung|
|-------------|-----------------|
|Interoperabilitätstyp|Benennt das Protokoll oder die Technologie, mit dem bzw. der in der Bindung die Zusammenarbeit sichergestellt wird.|
|Sicherheit|Gibt an, wie der Kanal geschützt wird.<br />– None: Die SOAP-Nachricht ist nicht gesichert, und der Client ist nicht authentifiziert.<br />-Transport: Sicherheitsanforderungen werden auf der Transportebene erfüllt.<br />-Meldung: Sicherheitsanforderungen werden auf der Nachrichtenebene erfüllt.<br />-Gemischt: Ansprüche werden in der Nachricht übertragen; Anforderungen an Integrität und Vertraulichkeit werden der Transportebene erfüllt.|
|Sitzung|Gibt an, ob die betreffende Bindung Sitzungsverträge unterstützt.|
|Transaktionen|Gibt an, ob Transaktionen ermöglicht werden.|
|Duplex|Gibt an, ob Duplexverträge unterstützt werden. Beachten Sie, dass diese Funktion in der Bindung Unterstützung für Sitzungen erfordert.|
|Codierung|Gibt das Übertragungsformat der Nachricht an. Zulässige Werte sind:<br />– Text: beispielsweise UTF-8.<br />– Binär<br />-Message Transmission Optimization Mechanism (MTOM): Eine Methode für die effiziente Codierung binärer XML-Elemente innerhalb des Kontexts eines SOAP-Umschlags.|
|Streaming|Gibt an, ob Streaming für eingehende und ausgehende Nachrichten unterstützt wird. Der Wert wird mithilfe der `TransferMode`-Eigenschaft für die Bindung festgelegt. Zulässige Werte sind:<br />- <xref:System.ServiceModel.TransferMode.Buffered>: Die Anforderungs- und Antwortnachrichten werden gepuffert.<br />- <xref:System.ServiceModel.TransferMode.Streamed>: Die Anforderungs- und Antwortnachrichten werden per Stream übertragen.<br />- <xref:System.ServiceModel.TransferMode.StreamedRequest>: Die Anforderungsnachricht wird per Stream übertragen, und die Antwortnachricht wird gepuffert.<br />- <xref:System.ServiceModel.TransferMode.StreamedResponse>: Die Anforderungsnachricht wird gepuffert, und die Antwortnachricht wird per Stream übertragen.|

## <a name="see-also"></a>Siehe auch

- [Übersicht über die Endpunkterstellung](endpoint-creation-overview.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](using-bindings-to-configure-services-and-clients.md)
- [Einfache WCF-Programmierung](basic-wcf-programming.md)
