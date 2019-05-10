---
title: Sicherheit Overview1
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, security
- WCF, security
ms.assetid: f478c80d-792d-4e7a-96bd-a2ff0b6f65f9
ms.openlocfilehash: 5e2b81a3ca7ab2c266218c3e32d22e0ebf67bf6a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64586778"
---
# <a name="security-overview"></a>Übersicht über die Sicherheit
Windows Communication Foundation (WCF) ist eine SOAP-Nachrichten basierende verteilte Programmierplattform, und Sichern von Nachrichten zwischen Clients und Diensten ist wichtig, um Daten zu schützen. WCF bietet eine vielseitige und interoperable Plattform für den Austausch sicherer Nachrichten auf Grundlage der vorhandenen Sicherheitsinfrastruktur und der anerkannten Sicherheitsstandards für SOAP-Nachrichten.  
  
> [!NOTE]
>  Ein umfassendes Handbuch zu WCF-Sicherheit, finden Sie unter [WCF Security Guidance](https://go.microsoft.com/fwlink/?LinkID=158912).  
  
 WCF verwendet Konzepte sind bekannt, wenn Sie sichere, verteilte Anwendungen mit vorhandenen Technologien wie HTTPS und unter Windows erstellt haben integrierte Sicherheit oder mit Benutzernamen und Kennwörtern zum Authentifizieren von Benutzern. WCF nicht nur vorhandene Sicherheitsinfrastrukturen integriert, sondern erweitert auch verteilte Sicherheit über nur-Windows-Domänen unter Verwendung von sicheren SOAP-Nachrichten. Erwägen Sie die WCF eine Implementierung vorhandener Sicherheitsmechanismen mit dem großen Vorteil der Verwendung von SOAP als zusätzliches vorhandenen Protokolle. Beispielsweise verfügen Anmeldeinformationen zur Identifizierung eines Clients oder Diensts, wie Benutzername, Kennwort oder X.509-Zertifikate, über interoperable XML-basierte SOAP-Profile. Mithilfe dieser Profile werden Nachrichten durch Nutzen offener Spezifikationen wie digitalen XML-Signaturen und XML-Verschlüsselung sicher ausgetauscht. Eine Liste der Spezifikationen, finden Sie unter [unterstützte Webdienstprotokolle vom System-provided Interoperabilitätsbindungen](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md).  
  
 Eine andere Parallele ist das Component Object Model (COM) auf der Windows-Plattform, mit dem sichere verteilte Anwendungen aktiviert werden. COM besitzt einen komplexen Sicherheitsmechanismus, in dem der Sicherheitskontext zwischen Komponenten übergehen kann; dieser Mechanismus gewährleistet Integrität, Vertraulichkeit und Authentifizierung. Jedoch ermöglicht COM nicht Cross-Platform, sicheres messaging wie WCF. Mithilfe von WCF, können Sie erstellen, Dienste und Clients, die von Windows-Domänen über das Internet erstrecken. Die interoperablen Nachrichten von WCF sind unverzichtbar für die Erstellung dynamischer, überzeugt sind geschäftsorientierte Dienste, mit denen die Sicherheit Ihrer Informationen.  
  
## <a name="windows-communication-foundation-security-benefits"></a>Vorzüge der Windows Communication Foundation-Sicherheit  
 WCF ist eine verteilte Programmierplattform, die basierend auf der SOAP-Nachrichten. Mithilfe von WCF, können Sie Anwendungen diese Funktion sowohl als Dienste auch als Dienstclients erstellen und Verarbeiten von Nachrichten aus einer unbegrenzten Anzahl von anderen Webdiensten und Clients erstellen. In einer derartigen verteilten Anwendung können Nachrichten zwischen Knoten, durch Firewalls, im Internet und durch zahlreiche SOAP-Vermittler fließen. Dies führt zu einer Vielzahl von Nachrichtensicherheitsrisiken. Die folgenden Beispiele veranschaulichen einige häufigen Bedrohungen, die WCF-Sicherheit kann verringern, beim Austauschen von Nachrichten zwischen Entitäten:  
  
- Beobachtung des Netzwerkverkehrs zum Erhalt vertraulicher Informationen. In einem Onlinebanking-Szenario fordert ein Client die Übertragung von Geldmitteln von einem Konto zu einem anderen an. Ein böswilliger Benutzer fängt die Nachricht ab und gelangt dadurch in den Besitz der Kontonummer und des Kennworts. Später überträgt er vom kompromittierten Konto Geldmittel.  
  
- Nicht autorisierte Entitäten, die ohne Wissen des Clients als Dienste fungieren. In diesem Szenario fungiert ein böswilliger Benutzer (die nicht autorisierte Person) als Onlinedienst und fängt Nachrichten vom Client ab, um an vertrauliche Informationen zu gelangen. Dann verwendet der böswillige Benutzer die gestohlenen Daten, um Geldmittel vom kompromittierten Konto zu übertragen. Dieser Angriff wird auch bezeichnet ein *Phishing-Angriff*.  
  
- Vom Aufrufenden nicht beabsichtigte Ergebnisse aufgrund von Nachrichtenänderung. Beispielsweise ermöglicht die Änderung der Nummer eines Kontos, auf das ein Betrag eingezahlt wird, die Übertragung der Geldmittel auf ein nicht autorisiertes Konto.  
  
- Durch Hackermanipulation mehrfach ausgeführte Aktionen. Beispielsweise verschickt ein Hacker mehrmals die gleiche Bestellung. Beispielsweise erhält ein Onlinebuchladen Hunderte von Bestellungen und schickt die Bücher an einen Kunden, der diese Bücher nicht bestellt hat.  
  
- Unmöglichkeit einer Clientauthentifizierung durch einen Dienst. In diesem Fall kann der Dienst nicht gewährleisten, dass die Transaktion von der richtigen Person ausgeführt wurde.  
  
 Zusammenfassung: Übertragungssicherheit bietet folgende Gewährleistungen:  
  
- Dienstendpunkt-Authentifizierung (Empfänger)  
  
- Clientprinzipal-Authentifizierung (Initiator)  
  
- Nachrichtenintegrität  
  
- Nachrichtenvertraulichkeit  
  
- Wiederholungserkennung  
  
### <a name="integration-with-existing-security-infrastructures"></a>Integration in vorhandene Sicherheitsinfrastrukturen  
 Oftmals verfügen Webdienstbereitstellungen bereits über Sicherheitslösungen, beispielsweise Secure Sockets Layer (SSL) oder das Kerberos-Protokoll. Einige nutzen eine bereits zur Verfügung stehende Sicherheitsinfrastruktur; so verwenden Windows-Domänen beispielsweise Active Directory. Häufig ist eine Integration in diese vorhandenen Technologien erforderlich, während neuere Technologien bewertet und übernommen werden müssen.  
  
 WCF-Sicherheit ist in vorhandene transportsicherheitsmodelle integriert und kann vorhandene Infrastrukturen für neuere übertragungssicherheitsmodelle basierend auf der SOAP-nachrichtensicherheit nutzen.  
  
### <a name="integration-with-existing-authentication-models"></a>Integration in vorhandene Authentifizierungsmodelle  
 Ein wichtiger Bestandteil jedes Kommunikationssicherheitsmodells ist die Fähigkeit zur Identifizierung und Authentifizierung von Entitäten in der Kommunikation. Diese Entitäten in der Kommunikation verwenden "digitale Identitäten" oder Anmeldeinformationen, um sich bei den kommunizierenden Peers zu authentifizieren. Im Zuge der Entwicklung verteilter Kommunikationsplattformen wurden verschiedene Modelle für Anmeldeinformations-Authentifizierung und verwandte Sicherheitsmodelle implementiert. Beispielsweise ist das Angeben eines Benutzernamens und Kennworts eine weit verbreitete Methode zur Identifizierung von Benutzern im Internet. In Intranets setzt sich die Verwendung eines Kerberos-Domänencontrollers zur Sicherung von Benutzer- und Dienstauthentifizierung durch. In bestimmten Szenarien, wie beim Kontakt zweier Geschäftspartner, können Zertifikate zur gegenseitigen Authentifizierung verwendet werden.  
  
 Im Bereich der Webdienste, in denen derselbe Dienst unter Umständen sowohl internen Unternehmenskunden als auch externen Partnern oder Internetkunden zur Verfügung steht, ist es wichtig, dass die Infrastruktur eine Integration in diese vorhandenen Sicherheitsauthentifizierungsmodelle ermöglicht. WCF-Sicherheit unterstützt eine Vielzahl von Anmeldeinformationstypen (Authentifizierungsmodelle), einschließlich:  
  
- Anonymer Aufrufer  
  
- Anmeldeinformationen für Benutzernamenclient  
  
- Anmeldeinformationen für Zertifikatclient  
  
- Windows (sowohl Kerberos-Protokoll als auch NT LanMan [NTLM]).  
  
### <a name="standards-and-interoperability"></a>Standards und Interoperabilität  
 In einer Welt mit umfangreichen vorhandenen Bereitstellungen ist Homogenität selten. Zwischen verteilten Berechnungs-/Kommunikationsplattformen und den Technologien anderer Anbieter müssen Interaktionen möglich sein. Ebenso muss auch Sicherheit interoperabel sein.  
  
 Um interoperable Sicherheitssysteme verwenden zu können, haben Unternehmen aus der Webdienstbranche verschiedene Standards entwickelt. Insbesondere im Hinblick auf Sicherheit müssen einige wichtige Standards vorgeschlagen werden: WS-Security: SOAP-Nachrichtensicherheit (von der Standardisierungsorganisation OASIS akzeptiert und früher als WS-Sicherheit), WS-Trust, WS-SecureConversation und WS-SecurityPolicy.  
  
 WCF unterstützt eine Vielzahl von Interoperabilitätsszenarien von Bedeutung. Die <xref:System.ServiceModel.BasicHttpBinding>-Klasse bezieht sich auf das Basic Security Profile (BSP), und die <xref:System.ServiceModel.WSHttpBinding>-Klasse bezieht sich auf die aktuellen Sicherheitsstandards (zum Beispiel WS-Security 1.1 und WS-SecureConversation). Durch diese Standards einhalten, kann WCF-Sicherheit zusammenarbeiten und integrieren in Web Services, die von Betriebssystemen und Plattformen als Microsoft Windows gehostet werden.  
  
## <a name="wcf-security-functional-areas"></a>WCF-Sicherheit &amp;#8211; Funktionsbereiche  
 WCF-Sicherheit ist in drei funktionale Bereiche unterteilt: übertragungssicherheit, Zugriffssteuerung und Überwachung. In den folgenden Abschnitten finden Sie eine kurze Erläuterung dieser Bereiche und Links auf weitere Informationen.  
  
### <a name="transfer-security"></a>Übertragungssicherheit  
 Übertragungssicherheit umfasst drei Hauptsicherheitsfunktionen: Integrität, Vertraulichkeit und Authentifizierung. *Integrität* ist die Möglichkeit, um festzustellen, ob eine Nachricht manipuliert wurde. *Vertraulichkeit* ist die Möglichkeit, eine Nachricht lesbar zu machen als den vorgesehenen Empfänger; beibehalten. Dies wird durch Kryptografie erreicht. *Authentifizierung* ist die Möglichkeit, eine beanspruchte Identität zu überprüfen. Durch die Kombination dieser drei Funktionen wird sichergestellt, dass Nachrichten sicher zwischen verschiedenen Punkten übertragen werden.  
  
#### <a name="transport-and-message-security-modes"></a>Transport- und Nachrichtensicherheitsmodi  
 Hauptsächlich zwei Mechanismen zum Implementieren von übertragungssicherheit in WCF verwendet werden: *Transport* Sicherheitsmodus und *Nachricht* Sicherheitsmodus.  
  
- *Sicherheitsmodus "Transport"* verwendet ein Protokoll auf Transportebene, wie z. B. HTTPS, um übertragungssicherheit zu erreichen. Der Transportmodus besitzt den Vorteil seiner großen Verbreitung, der Verfügbarkeit auf zahlreichen Plattformen und seiner geringeren rechnerischen Komplexität. Der Modus besitzt jedoch den Nachteil, dass Nachrichten nur von Punkt zu Punkt (Point-to-Point) gesichert werden.  
  
- *Sicherheitsmodus "Nachricht"*, auf der anderen Seite, wird WS-Sicherheit (und andere Spezifikationen) zum Implementieren von übertragungssicherheit. Da die Nachrichtensicherheit direkt für die SOAP-Nachrichten übernommen wird und zusammen mit den Anwendungsdaten in den SOAP-Umschlägen enthalten ist, besitzt sie den Vorteil der Unabhängigkeit von Transportprotokollen, der größeren Erweiterbarkeit und der Gewährleistung von End-to-End-Sicherheit (im Vergleich zu Point-to-Point); der Modus hat den Nachteil deutlich langsamer als der Transportsicherheitsmodus zu sein, da das XML-Format der SOAP-Nachrichten verarbeitet werden muss.  
  
 Weitere Informationen zu diesen Unterschieden finden Sie unter [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md).  
  
 Ein dritter Sicherheitsmodus verwendet beide zuvor beschriebenen Modi und vereint deren Vorteile. Dieser Modus wird als `TransportWithMessageCredential` bezeichnet. In diesem Modus wird die Nachrichtensicherheit zum Authentifizieren des Clients verwendet, wohingegen die Transportsicherheit zum Authentifizieren des Servers und zum Sicherstellen von Nachrichtenvertraulichkeit und -integrität dient. Daher ist der `TransportWithMessageCredential`-Sicherheitsmodus beinahe so schnell wie der Transportsicherheitsmodus und ermöglicht die Erweiterbarkeit der Clientauthentifizierung auf dieselbe Weise wie die Nachrichtensicherheit. Im Gegensatz zum Nachrichtensicherheitsmodus bietet dieser Modus keine vollständige End-to-End-Sicherheit.  
  
### <a name="access-control"></a>Zugriffssteuerung  
 *Steuerung des Zugriffs* ist auch bekannt als Autorisierung. *Autorisierung* können verschiedenen Benutzern unterschiedliche Rechte zum Anzeigen von Daten haben. Da die Dateien der Personalabteilung eines Unternehmens vertrauliche Mitarbeiterdaten enthalten, sind nur Abteilungsleiter zum Einsehen der Mitarbeiterdaten berechtigt. Zudem können Ableitungsleiter nur Daten für ihre direkten Berichte anzeigen. In diesem Fall basiert die Zugriffssteuerung sowohl auf der Rolle ("Abteilungsleiter") als auch auf der speziellen Identität des Abteilungsleiters (dadurch wird ein anderer Abteilungsleiter an der Einsicht in die Unterlagen eines Mitarbeiters gehindert).  
  
 In WCF Zugriffssteuerungsfunktionen durch Integration in die common Language Runtime (CLR) bereitgestellt werden <xref:System.Security.Permissions.PrincipalPermissionAttribute> und über einen Satz von APIs, die als bezeichnet die *Identitätsmodell*. Weitere Informationen zur Zugriffssteuerung und anspruchsbasierte Autorisierung finden Sie unter [Erweitern von Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md).  
  
### <a name="auditing"></a>Überwachung  
 *Überwachung* ist die Protokollierung von Sicherheitsereignissen in das Windows-Ereignisprotokoll. Sie können sicherheitsbezogene Ereignisse protokollieren, z. B. Authentifizierungsfehler (oder erfolgreiche Authentifizierungen). Weitere Informationen finden Sie unter [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md). Ausführliche Informationen zur Programmierung, finden Sie unter [Vorgehensweise: Überwachen von Sicherheitsereignissen](../../../../docs/framework/wcf/feature-details/how-to-audit-wcf-security-events.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Security.Permissions.PrincipalPermissionAttribute>
- [Sichern von Diensten](../../../../docs/framework/wcf/securing-services.md)
- [Häufige Sicherheitsszenarien](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)
- [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)
- [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [Authentifizierung](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
- [Autorisierung](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)
- [Verbund und ausgestellte Token](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [Überwachung](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)
- [Sicherheitsleitfaden und bewährte Methoden](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)
- [Konfigurieren von Diensten mit Konfigurationsdateien](../../../../docs/framework/wcf/configuring-services-using-configuration-files.md)
- [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)
- [Übersicht über die Endpunkterstellung](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [Erweitern der Sicherheit](../../../../docs/framework/wcf/extending/extending-security.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
