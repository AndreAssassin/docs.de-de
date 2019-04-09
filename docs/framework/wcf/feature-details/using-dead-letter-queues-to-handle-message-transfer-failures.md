---
title: Verwenden von Warteschlangen für unzustellbare Nachrichten zur Handhabung von Nachrichtenübertragungsfehlern
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9e891c6a-d960-45ea-904f-1a00e202d61a
ms.openlocfilehash: 2f15bf569da6127d6c9d27be255590ce3784d7a5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174615"
---
# <a name="using-dead-letter-queues-to-handle-message-transfer-failures"></a>Verwenden von Warteschlangen für unzustellbare Nachrichten zur Handhabung von Nachrichtenübertragungsfehlern
Die Zustellung von in der Warteschlange stehenden Nachrichten kann fehlschlagen. Diese fehlgeschlagenen Nachrichten werden in einer Warteschlange für unzustellbare Nachrichten aufgezeichnet. Das Fehlschlagen der Zustellung kann beispielsweise durch Netzwerkfehler, eine gelöschte Warteschlange, eine volle Warteschlange, einen Authentifizierungsfehler oder eine zu späte Zustellung verursacht werden.  
  
 In der Warteschlange stehende Nachrichten können über lange Zeit hinweg in der Warteschlange verbleiben, wenn die empfangende Anwendung sie nicht umgehend aus der Warteschlange liest. Dieses Verhalten ist möglicherweise nicht für zeitempfindliche Nachrichten geeignet. Zeitempfindliche Nachrichten verfügen über eine Eigenschaft für die Gültigkeitsdauer (Time to Live, TTL), die in der Bindung der Warteschlange festgelegt ist und angibt, wie lange die Nachrichten in der Warteschlange verbleiben können, bevor sie ablaufen. Abgelaufene Nachrichten werden an eine spezielle Warteschlange gesendet und zwar an die Warteschlange für unzustellbare Nachrichten. Nachrichten können auch aus anderen Gründen in einer Warteschlange für unzustellbare Nachrichten platziert werden, z. B. aufgrund des Überschreitens eines Warteschlangenkontingents oder aufgrund eines Authentifizierungsfehlers.  
  
 Im Allgemeinen schreiben Anwendungen Entschädigungslogik, um Nachrichten aus der Warteschlange für unzustellbare Nachrichten sowie Fehlerursachen zu lesen. Die Entschädigungslogik hängt von der Ursache des Fehlers ab. Im Falle eines Authentifizierungsfehlers können Sie beispielsweise das an die Nachricht angehängte Zertifikat korrigieren und die Nachricht anschließend erneut senden. Wenn eine Zustellung fehlgeschlagen ist, weil das Zielwarteschlangenkontingent nicht erreicht wurde, können Sie erneut einen Zustellungsversuch vornehmen, in der Hoffnung, dass das Kontingentproblem behoben wurde.  
  
 Die meisten Warteschlangensysteme haben eine systemweite Warteschlange für unzustellbare Nachrichten, in der alle fehlgeschlagenen Nachrichten dieses Systems gespeichert werden. Message Queuing (MSMQ) bietet zwei systemweite Warteschlangen für unzustellbare Nachrichten: eine transaktionale systemweite Warteschlange für unzustellbare Nachrichten, die Nachrichten speichert, die nicht an die transaktionale Warteschlange gesendet werden konnten, und eine nicht transaktionale Warteschlange für unzustellbare Nachrichten, die Nachrichten speichert, die nicht an die nicht transaktionale Warteschlange gesendet werden konnten. Wenn zwei Clients Nachrichten an zwei verschiedene Dienste senden, und deshalb verschiedene Warteschlangen in WCF denselben MSMQ-Dienst zum Senden von Freigabe sind, ist es möglich, eine Mischung aus Nachrichten in die Systemwarteschlange für unzustellbare Nachrichten zu haben. Dies ist nicht immer optimal. In vielen Fällen (z. B. im Hinblick auf die Sicherheit) ist es nicht ratsam, dass ein Client die Nachrichten eines anderen Clients aus der Warteschlange für unzustellbare Nachrichten liest. Bei einer gemeinsam genutzten Warteschlange für unzustellbare Nachrichten müssen die Clients darüber hinaus die Warteschlange nach von ihnen gesendeten Nachrichten durchsuchen, was je nach Anzahl der Nachrichten in der Warteschlange für unzustellbare Nachrichten viel zu aufwendig sein kann. Aus diesem Grund in WCF`NetMsmqBinding`, `MsmqIntegrationBinding,` und MSMQ auf [!INCLUDE[wv](../../../../includes/wv-md.md)] Geben Sie eine benutzerdefinierte Warteschlange für unzustellbare (auch als anwendungsspezifische Warteschlange für unzustellbare Nachrichten bezeichnet).  
  
 Die benutzerdefinierte Warteschlange für unzustellbare Nachrichten ermöglicht eine Isolation zwischen Clients, die den gleichen MSMQ-Dienst verwenden, um Nachrichten zu senden.  
  
 Auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)], Windows Communication Foundation (WCF) bietet eine systemweite Warteschlange für alle in der Warteschlange Clientanwendungen. Auf [!INCLUDE[wv](../../../../includes/wv-md.md)], WCF stellt eine Warteschlange für unzustellbare Nachrichten für jede in der Warteschlange stehende Clientanwendung bereit.  
  
## <a name="specifying-use-of-the-dead-letter-queue"></a>Angeben der Verwendung der Warteschlange für unzustellbare Nachrichten  
 Eine Warteschlange für unzustellbare Nachrichten befindet sich im Warteschlangen-Manager der sendenden Anwendung. Sie speichert Nachrichten, die abgelaufen sind oder nicht zugestellt werden konnten.  
  
 Die Bindung weist die folgenden Eigenschaften für eine Warteschlange für unzustellbare Nachrichten auf:  
  
-   <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>  
  
-   <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A>  
  
## <a name="reading-messages-from-the-dead-letter-queue"></a>Lesen von Nachrichten aus der Warteschlange für unzustellbare Nachrichten  
 Eine Anwendung, die Nachrichten aus einer Warteschlange für unzustellbare Nachrichten liest, ist ähnlich wie ein WCF-Dienst, der aus einer Anwendungswarteschlange, mit Ausnahme der folgenden geringfügige Unterschiede liest:  
  
-   Zum Lesen von Nachrichten aus einer transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI (Uniform Resource Identifier) folgendes Format aufweisen: net.msmq://localhost/system$;DeadXact.  
  
-   Zum Lesen von Nachrichten aus einer nicht transaktionalen Systemwarteschlange für unzustellbare Nachrichten muss der URI folgendes Format aufweisen: net.msmq://localhost/system$;DeadLetter.  
  
-   Um eine benutzerdefinierte Warteschlange für unzustellbare Nachrichten gelesen werden, der URI muss von der Form: Net.msmq://localhost/private/ sein\<*Custom-Dlq-Name*>, in denen *Custom-Dlq-Name* ist der Name des benutzerdefinierten Dead Letter-Warteschlange.  
  
 Weitere Informationen dazu, wie Sie die Adresse von Warteschlangen finden Sie unter [Dienstendpunkte und Adressieren von Warteschlangen](../../../../docs/framework/wcf/feature-details/service-endpoints-and-queue-addressing.md).  
  
 Der WCF-Stapel auf dem Empfänger mit Adressen, die der Dienst überwacht die mit der Adresse für die Nachricht übereinstimmt. Wenn die Adressen übereinstimmen, wird die Nachricht weitergeleitet; stimmen sie nicht überein, wird die Nachricht nicht weitergeleitet. Dies kann Probleme beim Lesen aus der Warteschlange für unzustellbare Nachrichten verursachen, da die Nachrichten in der Warteschlange in der Regel an den Dienst und nicht an den Dienst der Warteschlange für unzustellbare Nachrichten adressiert sind. Daher muss der Dienst, der aus der Warteschlange für unzustellbare Nachrichten liest, einen Adressfilter `ServiceBehavior` installieren, der den Stapel auffordert, alle Nachrichten in der Warteschlange unabhängig vom Adressaten abzugleichen. Genau genommen müssen Sie dem Dienst, der die Nachrichten aus der Warteschlange für unzustellbare Nachrichten liest, ein `ServiceBehavior` mit dem Parameter <xref:System.ServiceModel.AddressFilterMode.Any> hinzufügen.  
  
## <a name="poison-message-handling-from-the-dead-letter-queue"></a>Die Handhabung von beschädigten Nachrichten aus der Warteschlange für unzustellbare Nachrichten  
 Die Handhabung beschädigter Nachrichten ist für Warteschlangen für unzustellbare Nachrichten verfügbar. Dabei gelten bestimmte Voraussetzungen. Da beim Lesen aus der Systemwarteschlange für unzustellbare Nachrichten keine untergeordneten Warteschlangen erstellt werden können, kann `ReceiveErrorHandling` nicht auf `Move` festgelegt werden. Beachten Sie, dass Sie beim Lesen aus einer benutzerdefinierten Warteschlange für unzustellbare Nachrichten untergeordnete Warteschlangen nutzen können und dass `Move` daher eine gültige Disposition für die beschädigte Nachricht ist.  
  
 Wenn `ReceiveErrorHandling` beim Lesen aus der benutzerdefinierten Warteschlange für unzustellbare Nachrichten auf `Reject` eingestellt ist, wird die beschädigte Nachricht in der Systemwarteschlange für unzustellbare Nachrichten platziert. Beim Lesen aus der Systemwarteschlange für unzustellbare Nachrichten wird die Nachricht abgelegt (gelöscht). Ein Ausschluss aus einer Systemwarteschlange für unzustellbare Nachrichten in MSMQ legt die Nachricht ab (löscht sie).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie eine Warteschlange für unzustellbare Nachrichten erstellt und für die Verarbeitung abgelaufener Nachrichten verwendet wird. Das Beispiel basiert auf dem Beispiel in [Vorgehensweise: Exchange in der Warteschlange Nachrichten mit wcd-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md). Im folgenden Beispiel wird dargestellt, wie der Clientcode auf den Dienst für die Auftragsverarbeitung geschrieben wird, der für jede Anwendung eine Warteschlange für unzustellbare Nachrichten verwendet. Im Beispiel wird auch gezeigt, wie Nachrichten aus der Warteschlange für unzustellbare Nachrichten verarbeitet werden.  
  
 Der folgende Code ist für einen Client, der eine Warteschlange für unzustellbare Nachrichten für jede Anwendung angibt.  
  
 [!code-csharp[S_DeadLetter#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/client.cs#1)]
 [!code-vb[S_DeadLetter#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/client.vb#1)]  
  
 Der folgende Code ist für die Clientkonfigurationsdatei.  

 Der folgende Code ist für einen Dienst, der Nachrichten aus einer Warteschlange für unzustellbare Nachrichten verarbeitet.  
  
 [!code-csharp[S_DeadLetter#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_deadletter/cs/dlservice.cs#3)]
 [!code-vb[S_DeadLetter#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/s_deadletter/vb/dlservice.vb#3)]  
  
 Der folgende Code ist für die Dienstkonfigurationsdatei für die Warteschlange für unzustellbare Nachrichten.  

## <a name="see-also"></a>Siehe auch

- [Warteschlangenübersicht](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Vorgehensweise: Austauschen von Nachrichten in einer Warteschlange mit WCF-Endpunkten](../../../../docs/framework/wcf/feature-details/how-to-exchange-queued-messages-with-wcf-endpoints.md)
- [Behandlung nicht verarbeitbarer Nachrichten](../../../../docs/framework/wcf/feature-details/poison-message-handling.md)
