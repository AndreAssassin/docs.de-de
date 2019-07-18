---
title: 'Einblicke in den CustomPeerResolverService: Clientregistrierungen'
ms.date: 03/30/2017
ms.assetid: 40236953-a916-4236-84a6-928859e1331a
ms.openlocfilehash: 3d1e1c6493da54bc3ae0e74a33985da59382ea52
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64619782"
---
# <a name="inside-the-custompeerresolverservice-client-registrations"></a>Einblicke in den CustomPeerResolverService: Clientregistrierungen
Jeder Knoten im Netz veröffentlicht seine Endpunktinformationen für den Resolverdienst durch die `Register`-Funktion. Der Resolverdienst speichert diese Informationen als Registrierungsdatensatz. Dieser Datensatz enthält einen eindeutigen Bezeichner (RegistrationID) sowie Endpunktinformationen (PeerNodeAddress) für den Knoten.  
  
## <a name="stale-records-and-expiration-time"></a>Veraltete Datensätze und Ablaufzeit  
 Idealerweise ruft ein Knoten beim Verlassen des Netzes die `Unregister`- Funktion auf, wodurch der Registrierungseintrag vom Resolverdienst entfernt wird. Manchmal werden Knoten jedoch geschlossen oder nicht verfügbar, bevor `Unregister` aufgerufen wurde. Dadurch bleibt ein veralteter Registrierungsdatensatz zurück.  
  
 Veraltete Datensätze im Resolverdienst können zu fehlerhaften Verbindungen führen. Erhält ein Knoten beim Versuch, eine Verbindung mit einem Netz herzustellen, veraltete Verbindungsinformationen vom Resolverdienst, dauert es ggf. länger, bis er eine erfolgreiche Verknüpfung zu dem Netz herstellen kann. Veraltete Datensätze belegen zudem Speicherplatz. Ohne effizienten Bereinigungsprozess kann ein Überlauf des Zwischenspeichers auftreten, in dem die Registrierungen gespeichert werden, was den Absturz des Resolverdiensts zur Folge haben kann.  
  
 Der <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> versieht jeden Datensatz mit einer Ablaufzeit (DateTime) und speichert diese Information zusammen mit dem Datensatz. Anhand der Ablaufzeit werden veraltete Datensätze durch den Dienst erkannt. Eine solche Vorgehensweise empfiehlt sich auch bei benutzerdefinierten Implementierungen.  
  
## <a name="refreshinterval-and-cleanupinterval"></a>RefreshInterval und CleanupInterval  
 Mit der `RefreshInterval`-Eigenschaft des <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> wird die Gültigkeitsdauer von Registrierungsdatensätzen in der Registrierungssuchtabelle des Diensts definiert. Ist die für diese Eigenschaft angegebene Zeit für einen bestimmten Datensatz abgelaufen, ist dieser Datensatz veraltet und wird zum Löschen markiert.  
  
 Mithilfe der `CleanupInterval`-Eigenschaft des <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> wird dem Dienst mitgeteilt, wie häufig veraltete Registrierungsdatensätze gesucht und gelöscht werden sollen. Das `CleanupInterval` sollte auf eine Zeit festgelegt werden, die mindestens dem für den Dienst festgelegten `RefreshInterval` entspricht.  
  
 Wenn Sie einen eigenen Resolverdienst implementieren möchten, müssen Sie eine Wartungsfunktion zum Entfernen veralteter Registrierungsdatensätze schreiben. Dafür stehen verschiedene Möglichkeiten zur Verfügung:  
  
- **Regelmäßige Wartung**: Legen Sie einen Zeitgeber, wechseln in regelmäßigen Abständen aus, und führen Ihre Datenspeicher, um alte Datensätze zu löschen. Dieser Ansatz wird vom <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService> verwendet.  
  
- **Passives löschen**: Statt aktiv nach veralteten Datensätzen suchen, in regelmäßigen Abständen, können Sie identifizieren und veraltete Datensätze löschen, wenn Ihr Dienst bereits eine andere Funktion ausgeführt wird. Dadurch erhöht sich zwar möglicherweise die Antwortzeit für Anforderungen der Resolverclients, andererseits wird in diesem Fall kein Timer benötigt. Darüber hinaus ist diese Methode möglicherweise effizienter, wenn voraussichtlich nur wenige Knoten das Netz ohne Aufruf von `Unregister` verlassen.  
  
## <a name="registrationlifetime-and-refresh"></a>RegistrationLifetime und Refresh  
 Wenn sich ein Knoten bei einem Resolverdienst registriert, erhält er vom Dienst ein <xref:System.ServiceModel.PeerResolvers.RegisterResponseInfo>-Objekt. Dieses Objekt besitzt eine `RegistrationLifetime`-Eigenschaft, mit der dem Knoten die verbleibende Zeit bis zum Ablauf der Registrierung und damit bis zur Entfernung durch den Resolverdienst angegeben wird. Beispiel: Beträgt die `RegistrationLifetime` zwei Minuten, muss durch den Knoten in weniger als zwei Minuten ein Aufruf von `Refresh` erfolgen, damit der Datensatz nicht als veraltet gilt und gelöscht wird. Erhält der Resolverdienst eine `Refresh`-Anforderung, sucht er den Datensatz und setzt die Ablaufzeit zurück. Durch die Refresh-Anforderung wird ein <xref:System.ServiceModel.PeerResolvers.RefreshResponseInfo>-Objekt mit einer `RegistrationLifetime`-Eigenschaft zurückgegeben.  
  
## <a name="see-also"></a>Siehe auch

- [Peerresolver](../../../../docs/framework/wcf/feature-details/peer-resolvers.md)
