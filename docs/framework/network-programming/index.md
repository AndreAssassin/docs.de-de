---
title: Netzwerkprogrammierung in .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- Networking
- Internet
- Internet, .NET Framework Internet services
- Network Resources
ms.assetid: 8d455610-67a0-4fa8-a62f-7747064a9256
ms.openlocfilehash: 74084b8eef46f700733ad44e04cf8b3811456b85
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642411"
---
# <a name="network-programming-in-the-net-framework"></a>Netzwerkprogrammierung in .NET Framework
Das Microsoft .NET Framework stellt eine mehrschichtige, erweiterbare und verwaltete Implementierung von Internetdiensten zur Verfügung. Die Internetdienste können schnell und auf einfache Weise in Anwendungen integriert werden. Ihre Netzwerkanwendungen können austauschbare Protokolle einsetzten, um neue Internetprotokolle automatisch zu verwenden, oder eine verwaltete Implementierung der Windows Socket-Schnittstelle benutzen, um auf Socketebene mit dem Netzwerk zu arbeiten.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Einführung in austauschbare Protokolle](../../../docs/framework/network-programming/introducing-pluggable-protocols.md)  
 Beschreibt, wie auf eine Internetressource ohne Berücksichtigung des benötigten Zugriffsprotokolls zugegriffen werden kann.  
  
 [Requesting Data (Anfordern von Daten)](../../../docs/framework/network-programming/requesting-data.md)  
 Erläutert, wie austauschbare Protokolle verwendet werden, um Daten von Internetressourcen herunterzuladen oder um Daten hochzuladen.  
  
 [Programmieren austauschbarer Protokolle](../../../docs/framework/network-programming/programming-pluggable-protocols.md)  
 Erklärt, wie protokollspezifische Klassen verwendet werden, um austauschbare Protokolle zu implementieren.  
  
 [Verwenden von Anwendungsprotokollen](../../../docs/framework/network-programming/using-application-protocols.md)  
 Beschreibt Programmierungsanwendungen, die Netzwerkprotokolle wie TCP, UDP und HTTP nutzen.  
  
 [Internetprotokoll Version 6](../../../docs/framework/network-programming/internet-protocol-version-6.md)  
 Beschreibt die Vorteile der Internetprotokollversion 6 (IPv6) gegenüber der aktuellen Version der Internetprotokollsammlung (IPv4) sowie Adressierung, Routing, automatische Konfiguration, Aktivierung und Deaktivierung von IPv6.  
  
 [Konfigurieren von Internetanwendungen](../../../docs/framework/network-programming/configuring-internet-applications.md)  
 Erläutert, wie die .NET Framework-Konfigurationsdateien verwendet werden, um Internetanwendungen zu konfigurieren.  
  
 [Netzwerkablaufverfolgung in .NET Framework](../../../docs/framework/network-programming/network-tracing.md)  
 Erklärt, wie die Netzwerkablaufverfolgung verwendet wird, um Informationen über Methodenaufrufe und den Netzwerkdatenverkehr abzurufen, der von einer Anwendung generiert wird.  
  
 [Cacheverwaltung für Netzwerkanwendungen](../../../docs/framework/network-programming/cache-management-for-network-applications.md)  
 Beschreibt, wie das Zwischenspeichern für Anwendungen verwendet wird, die die Klassen <xref:System.Net.WebClient?displayProperty=nameWithType>, <xref:System.Net.WebRequest?displayProperty=nameWithType>und <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> verwenden.  
  
 [Security in Network Programming (Sicherheit in der Netzwerkprogrammierung)](../../../docs/framework/network-programming/security-in-network-programming.md)  
 Beschreibt, wie die standardmäßigen Internetsicherheits- und Authentifizierungstechniken verwendet werden.  
  
 [Bewährte Methoden für System.Net-Klassen](../../../docs/framework/network-programming/best-practices-for-system-net-classes.md)  
 Stellt Tipps und Tricks bereit, mit denen Sie Ihre Internetanwendungen optimal ausnutzen.  
  
 [Zugreifen auf das Internet über einen Proxy](../../../docs/framework/network-programming/accessing-the-internet-through-a-proxy.md)  
 Beschreibt, wie Proxys konfiguriert werden.  
  
 [NetworkInformation](../../../docs/framework/network-programming/networkinformation.md)  
 Beschreibt, wie Informationen über Netzwerkereignisse, Änderungen, Statistiken und Eigenschaften erfasst werden und erläutert, wie Sie mithilfe der <xref:System.Net.NetworkInformation.Ping?displayProperty=nameWithType> -Klasse bestimmen, ob ein Remotehost erreichbar ist.  
  
 [Änderungen am System.Uri-Namespace in Version 2.0](../../../docs/framework/network-programming/changes-to-the-system-uri-namespace-in-version-2-0.md)  
 Beschreibt mehrere Änderungen, die an der <xref:System.Uri?displayProperty=nameWithType> -Klasse in Version 2.0 vorgenommen wurden, um falsches Verhalten zu korrigieren und um Benutzerfreundlichkeit und Sicherheit zu erhöhen.  
  
 [International Resource Identifier-Unterstützung in System.Uri](../../../docs/framework/network-programming/international-resource-identifier-support-in-system-uri.md)  
 Beschreibt Erweiterungen der <xref:System.Uri?displayProperty=nameWithType> -Klasse in Version 3.5, 3.0 SP1 und 2.0 SP1 zur Unterstützung von International Resource Identifiers (IRI) und Internationalized Domain Name (IDN).  
  
 [Erweiterungen der Socketleistung in Version 3.5](../../../docs/framework/network-programming/socket-performance-enhancements-in-version-3-5.md)  
 Beschreibt die Erweiterungen für die <xref:System.Net.Sockets.Socket?displayProperty=nameWithType> -Klasse in Version 3.5, 3.0 SP1 und 2.0 SP1, durch die ein alternatives asynchrones Muster bereitgestellt wird, das von spezialisierten Socketanwendungen mit hoher Leistung verwendet werden kann.  
  
 [Peer Name Resolution-Protokoll (PNRP)](../../../docs/framework/network-programming/peer-name-resolution-protocol.md)  
 Beschreibt die Unterstützung, die in Version 3.5 hinzugefügt wurde, um das Peer Name Resolution-Protokoll (PNRP) zu unterstützen, ein serverloses und dynamisches Protokoll zu Registrierung und Auflösung von Namen. Diese neuen Funktionen werden durch den <xref:System.Net.PeerToPeer?displayProperty=nameWithType> -Namespace unterstützt.  
  
 [Peer-to-Peer-Zusammenarbeit](../../../docs/framework/network-programming/peer-to-peer-collaboration.md)  
 Beschreibt die Unterstützung, die in Version 3.5 hinzugefügt wurde, um Peer-zu-Peer-Zusammenarbeit auf Grundlage von PNRP zu ermöglichen. Diese neuen Funktionen werden durch den <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType> -Namespace unterstützt.  
  
 [Änderungen an der NTLM-Authentifizierung für „HttpWebRequest“ in Version 3.5 SP1](../../../docs/framework/network-programming/changes-to-ntlm-authentication-for-httpwebrequest-in-version-3-5-sp1.md)  
 Beschreibt Sicherheitsänderungen, die in Version 3.5 SP1 vorgenommen wurden und beeinflussen, wie die integrierte Windows-Authentifizierung durch <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>und verwandte Klassen im System.Net-Namespace behandelt wird.  
  
 [Integrierte Windows-Authentifizierung mit erweitertem Schutz](../../../docs/framework/network-programming/integrated-windows-authentication-with-extended-protection.md)  
 Beschreibt Erweiterungen für verbesserten Schutz, die beeinflussen, wie die integrierte Windows-Authentifizierung durch <xref:System.Net.HttpWebRequest?displayProperty=nameWithType>, <xref:System.Net.HttpListener?displayProperty=nameWithType>, <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>, <xref:System.Net.Security.SslStream?displayProperty=nameWithType>, <xref:System.Net.Security.NegotiateStream?displayProperty=nameWithType>und verwandte Klassen im Namespace <xref:System.Net?displayProperty=nameWithType> und in verwandten Namespaces behandelt wird.  
  
 [NAT-Durchlauf mit IPv6 und Teredo](../../../docs/framework/network-programming/nat-traversal-using-ipv6-and-teredo.md)  
 Beschreibt die Erweiterungen, die dem Namespace <xref:System.Net?displayProperty=nameWithType>, <xref:System.Net.NetworkInformation?displayProperty=nameWithType>und <xref:System.Net.Sockets?displayProperty=nameWithType> hinzugefügt wurden, um NAT-Durchdringung mit IPv6 und Teredo zu unterstützen.  
  
 [Netzwerkisolation für Windows Store-Apps](../../../docs/framework/network-programming/network-isolation-for-windows-store-apps.md)  
 Beschreibt die Auswirkungen der Netzwerkisolation, wenn Klassen aus den Namespaces <xref:System.Net>, <xref:System.Net.Http>und <xref:System.Net.Http.Headers> in [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -Apps verwendet werden.  
  
 [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)  
 Links zu herunterladbaren Beispielen für Netzwerkprogrammierung, in denen Klassen aus den Namespaces <xref:System.Net>, <xref:System.Net.Cache>, <xref:System.Net.Configuration>, <xref:System.Net.Mail>, <xref:System.Net.Mime>, <xref:System.Net.NetworkInformation>, <xref:System.Net.PeerToPeer>, <xref:System.Net.Security>, <xref:System.Net.Sockets> verwendet werden.  
  
## <a name="reference"></a>Referenz  
 <xref:System.Net?displayProperty=nameWithType>  
 Stellt für viele der Protokolle, die gegenwärtig in Netzwerken verwendet werden, eine einfache Programmierschnittstelle bereit. Die Klassen <xref:System.Net.WebRequest?displayProperty=nameWithType> und <xref:System.Net.WebResponse?displayProperty=nameWithType> in diesem Namespace sind die Grundlage für austauschbare Protokolle.  
  
 <xref:System.Net.Cache?displayProperty=nameWithType>  
 Definiert die Typen und Enumerationen, mit denen Cacherichtlinien für Ressourcen definiert werden, die mithilfe der Klassen <xref:System.Net.WebRequest?displayProperty=nameWithType> und <xref:System.Net.HttpWebRequest?displayProperty=nameWithType> abgerufen werden.  
  
 <xref:System.Net.Configuration?displayProperty=nameWithType>  
 Klassen, die von Anwendungen verwendet werden, um programmgesteuert auf die Konfigurationseinstellungen für die System.Net-Namespaces zuzugreifen und diese Einstellungen zu aktualisieren.  
  
 <xref:System.Net.Http?displayProperty=nameWithType>  
 Klassen, die eine Programmierschnittstelle für moderne HTTP-Anwendungen zur Verfügung stellen.  
  
 <xref:System.Net.Http.Headers?displayProperty=nameWithType>  
 Bietet Unterstützung für Auflistungen von HTTP-Headern, die vom <xref:System.Net.Http?displayProperty=nameWithType> -Namespace verwendet werden.  
  
 <xref:System.Net.Mail?displayProperty=nameWithType>  
 Klassen zum Erstellen und Senden von E-Mail-Nachrichten mithilfe des SMTP-Protokolls.  
  
 <xref:System.Net.Mime?displayProperty=nameWithType>  
 Definiert Typen, die verwendet werden, um MIME-Header (Multipurpose Internet Mail Exchanges) darzustellen, die von Klassen im <xref:System.Net.Mail?displayProperty=nameWithType> -Namespace verwendet werden.  
  
 <xref:System.Net.NetworkInformation?displayProperty=nameWithType>  
 Klassen, um programmgesteuert Informationen über Netzwerkereignisse, Änderungen, Statistiken und Eigenschaften zu erfassen.  
  
 <xref:System.Net.PeerToPeer?displayProperty=nameWithType>  
 Stellt eine verwaltete PNRP-Implementierung (Peer Name Resolution-Protokoll) für Entwickler zur Verfügung.  
  
 <xref:System.Net.PeerToPeer.Collaboration?displayProperty=nameWithType>  
 Stellt für Entwickler eine verwaltete Implementierung der Schnittstelle für die Peer-zu-Peer-Zusammenarbeit zur Verfügung.  
  
 <xref:System.Net.Security?displayProperty=nameWithType>  
 Klassen, die Netzwerkstreams für die sichere Kommunikation zwischen Hosts zur Verfügung stellen.  
  
 <xref:System.Net.Sockets?displayProperty=nameWithType>  
 Stellt eine verwaltete Implementierung der Winsock-Schnittstelle (Windows Sockets) für Entwickler zur Verfügung, die den Zugriff auf das Netzwerk kontrollieren müssen.  
  
 <xref:System.Net.WebSockets?displayProperty=nameWithType>  
 Stellt eine verwaltete Implementierung der WebSocket-Schnittstelle für Entwickler zur Verfügung.  
  
 <xref:System.Uri?displayProperty=nameWithType>  
 Stellt eine Objektdarstellung eines URIs (Uniform Resource Identifier) und einfachen Zugriff auf die Teile des URIs bereit.  
  
 <xref:System.Security.Authentication.ExtendedProtection?displayProperty=nameWithType>  
 Stellt Unterstützung für die Authentifizierung mit erweiterten Schutz für Anwendungen zur Verfügung.  
  
 <xref:System.Security.Authentication.ExtendedProtection.Configuration?displayProperty=nameWithType>  
 Stellt Unterstützung für die Konfiguration der Authentifizierung mit erweitertem Schutz für Anwendungen zur Verfügung.  
  
## <a name="see-also"></a>Siehe auch

- [Bewährte Methoden für Transport Layer Security (TLS) mit .NET Framework](../../../docs/framework/network-programming/tls.md)
- [Themen zur Vorgehensweise bei der Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-how-to-topics.md)
- [Beispiele zur Netzwerkprogrammierung](../../../docs/framework/network-programming/network-programming-samples.md)
- [Netzwerkbeispiele für .NET in der MSDN Code Gallery](https://code.msdn.microsoft.com/Wiki/View.aspx?ProjectName=nclsamples)
- [HttpClient Sample (HttpClient-Beispiel)](https://go.microsoft.com/fwlink/?LinkId=242550)
