---
title: Peerresolver
ms.date: 03/30/2017
ms.assetid: d86d12a1-7358-450f-9727-b6afb95adb9c
ms.openlocfilehash: 0547bb37b03235c61f43cec365551438f7931ad1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909915"
---
# <a name="peer-resolvers"></a>Peerresolver
Um eine Verbindung mit einem Mesh herzustellen, erfordert ein Peerknoten die IP-Adressen anderer Knoten. IP-Adressen werden bezogen, indem eine Verbindung zu einem Auflösungsdienst hergestellt wird, der die Netz-ID annimmt und eine Liste von Adressen zurückgibt, die mit dieser bestimmten Netz-ID registrierten Knoten entsprechen. Der Resolver behält eine Liste registrierter Adressen bei, die durch Registrierung jedes Knotens im Mesh mit dem Dienst erstellt wird.  
  
 Mithilfe der `Resolver`-Eigenschaft der <xref:System.ServiceModel.NetPeerTcpBinding> können Sie den zu verwendenden PeerResolver-Dienst angeben.  
  
## <a name="supported-peer-resolvers"></a>Unterstützte Peerresolver  
 Peerkanal unterstützt zwei Arten von Resolvern: Peer Name Resolution-Protokoll (PNRP) und benutzerdefinierte Auflösungs Dienste.  
  
 Standardmäßig verwendet Peerkanal den PNRP-Peerresolverdienst, um Peers und Nachbarn im Netz zu ermitteln. Für Situationen/Plattformen, in denen PNRP nicht verfügbar oder nicht realisierbar ist, bietet Windows Communication Foundation (WCF) einen alternativen serverbasierten Ermittlungs <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>Dienst (). Sie können auch explizit einen benutzerdefinierten Resolverdienst definieren. Schreiben Sie hierzu eine Klasse, die die <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract>-Schnittstelle implementiert.  
  
### <a name="peer-name-resolution-protocol-pnrp"></a>Peer Name Resolution-Protokoll (PNRP)  
 PNRP, der Standardresolver für [!INCLUDE[wv](../../../../includes/wv-md.md)], ist ein verteilter, serverloser Namensauflösungsdienst. PNRP kann auch auf [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)] verwendet werden, indem das Advanced Networking Pack installiert wird. Zwei Clients., auf denen die gleiche Version von PNRP ausgeführt wird, können sich mithilfe dieses Protokolls suchen, falls sie bestimmte Voraussetzungen erfüllen (wie das Fehlen einer dazwischen stehenden Unternehmens-Firewall). Die mit [!INCLUDE[wv](../../../../includes/wv-md.md)] gelieferte Version von PNRP ist neuer als die im Advanced Networking Pack enthaltene Version. Suchen Sie im Microsoft Download Center nach Updates auf PNRP für [!INCLUDE[wxpsp2](../../../../includes/wxpsp2-md.md)].  
  
### <a name="custom-resolver-services"></a>Benutzerdefinierte Auflösungsdienste  
 Wenn der PNRP-Dienst nicht verfügbar ist oder Sie die vollständige Kontrolle über die Netzstruktur benötigen, können Sie einen benutzerdefinierten, serverbasierten Resolverdienst verwenden. Dieser Dienst kann durch Schreiben einer Resolverklasse, die die <xref:System.ServiceModel.PeerResolvers.IPeerResolverContract>-Schnittstelle implementiert, oder durch Verwenden der im Lieferumfang enthaltenen Standardimplementierung <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> explizit definiert werden.  
  
 Bei der Standardimplementierung des Dienstes laufen die Clientregistrierungen nach einer bestimmten Zeit ab, wenn der Client die Registrierung nicht explizit aktualisiert. Clients, die den Auflösungsdienst verwenden, benötigen eine bestimmte obere Begrenzung für die Client-Server-Wartezeit, um die Registrierung rechtzeitig erfolgreich aktualisieren zu können. Dies schließt ein, ein entsprechendes Aktualisierungstimeout (`RefreshInterval`) für den Auflösungsdienst auszuwählen. (Weitere Informationen finden [Sie unter in "CustomPeerResolverService": Client Registrierungen](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md).)  
  
 Auch muss der Anwendungsautor die Sicherung der Verbindung zwischen Clients und dem benutzerdefinierten Resolverdienst berücksichtigen. Sie können dazu die Sicherheitseinstellungen der <xref:System.ServiceModel.NetTcpBinding> verwenden, über die Clients eine Verbindung zum Auflösungsdienst herstellen. Anmeldeinformationen müssen (sofern verwendet) für die zum Erstellen von Peerkanal verwendete `ChannelFactory` angegeben werden. Diese Anmeldeinformationen werden an die zum Erstellen von Kanälen für den benutzerdefinierten Resolver verwendete `ChannelFactory` übergeben.  
  
> [!NOTE]
> Bei der Verwendung lokaler und provisorischer Netzwerke mit einem benutzerdefinierten Resolver wird dringend empfohlen, dass Anwendungen, die verbindungslokale oder provisorische Netzwerke nutzen oder unterstützen, Logik einfügen, die für das Herstellen einer Verbindung eine einzelne verbindungslokale Adresse auswählt. Dadurch werden möglicherweise durch Computer mit mehreren verbindungslokalen Adressen verursachte Probleme verhindert. In Übereinstimmung damit unterstützt Peerkanal nur die Verwendung jeweils einer einzelnen verbindungslokalen Adresse. Sie können diese Adresse mit der `ListenIpAddress`-Eigenschaft der <xref:System.ServiceModel.NetPeerTcpBinding> angeben.  
  
 Eine Demonstration der Implementierung eines benutzerdefinierten Konflikt Lösers finden Sie unter [Peer Channel Custom Peerresolver](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751466(v=vs.90)).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Innerhalb von CustomPeerResolverService: Client Registrierungen](../../../../docs/framework/wcf/feature-details/inside-the-custompeerresolverservice-client-registrations.md)  
  
## <a name="see-also"></a>Siehe auch

- [Peerkanalbegriffe](../../../../docs/framework/wcf/feature-details/peer-channel-concepts.md)
- [Peerkanalsicherheit](../../../../docs/framework/wcf/feature-details/peer-channel-security.md)
- [Erstellen einer Peerkanalanwendung](../../../../docs/framework/wcf/feature-details/building-a-peer-channel-application.md)
