---
title: Behandlung nicht verarbeitbarer Nachrichten
ms.date: 03/30/2017
ms.assetid: 8d1c5e5a-7928-4a80-95ed-d8da211b8595
ms.openlocfilehash: fe748ac40f03ed22cacb254ab464a6caf3d27a8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62046436"
---
# <a name="poison-message-handling"></a>Behandlung nicht verarbeitbarer Nachrichten
Ein *für nicht verarbeitbare Nachrichten* ist eine Nachricht, das die maximale Anzahl von Versuchen nicht an der Anwendung überschritten hat. Diese Situation kann auftreten, wenn eine warteschlangenbasierte Anwendung aufgrund der Fehler keine Nachricht verarbeiten kann. Um Zuverlässigkeitsforderungen zu erfüllen, empfängt eine in der Warteschlange stehende Anwendung Nachrichten unter einer Transaktion. Beim Abbrechen der Transaktion, in der eine in der Warteschlange stehende Nachricht empfangen wurde, bleibt die Nachricht in der Warteschlange und wird dann unter einer neuen Transaktion wiederholt. Wenn das Problem, das zum Abbrechen der Transaktion geführt hat, nicht korrigiert wird, kann die empfangende Anwendung in einer Schleife hängen bleiben, in der sie dieselbe Nachricht immer wieder empfängt und abbricht, bis die maximale Anzahl der Zustellversuche überschritten ist. Auf diese Weise entsteht eine nicht verarbeitbare Nachricht.  
  
 Eine Nachricht kann aus vielen Gründen zu einer nicht verarbeitbaren Nachrichten werden. Die häufigsten Ursachen sind anwendungsspezifisch. Wenn beispielsweise eine Anwendung eine Nachricht aus einer Warteschlange liest und dann Datenbankprozesse durchführt, kann es vorkommen, dass von der Anwendung keine Sperre für die Datenbank bewirkt werden kann. Dies führt dann dazu, dass sie die Transaktion abbricht. Da die Datenbanktransaktion abgebrochen wurde, verbleibt die Nachricht in der Warteschlange, wodurch die Nachricht von der Anwendung ein zweites Mal gelesen und ein neuer Versuch gestartet wird, eine Sperrung der Datenbank zu bewirken. Nachrichten können auch nicht verarbeitbar werden, wenn sie ungültige Informationen enthalten. So enthält z. B. eine Bestellung möglicherweise eine ungültige Kundennummer. In diesen Fällen kann die Anwendung die Transaktion freiwillig abbrechen und die Nachricht zwingen, eine nicht verarbeitbare Nachricht zu werden.  
  
 Bei seltenen Gelegenheiten können Nachrichten nicht zur Anwendung weitergeleitet werden. Die Windows Communication Foundation (WCF)-Ebene möglicherweise ein Problem mit der Nachricht, z. B. wenn die Nachricht den falschen Frame, ungültige nachrichtenanmeldeinformationen im Anhang oder einen ungültigen aktionsheader. In diesen Fällen empfängt die Anwendung die Nachricht niemals; trotzdem kann die Nachricht noch zu einer nicht verarbeitbaren Nachricht werden, die manuell verarbeitet werden kann.  
  
## <a name="handling-poison-messages"></a>Behandeln von nicht verarbeitbaren Nachrichten  
 In WCF bietet die Handhabung beschädigter Nachrichten einen Mechanismus für eine empfangende Anwendung zum Umgang mit Nachrichten, die an die Anwendung weitergeleitet werden können oder Nachrichten, die zur Anwendung weitergeleitet werden, aber nicht die aufgrund einer anwendungsspezifischen verarbeitet werden Gründe. Die Konfiguration der Behandlung nicht verarbeitbarer Nachrichten erfolgt in jeder der verfügbaren, in der Warteschlange stehenden Bindungen durch die folgenden Eigenschaften:  
  
- `ReceiveRetryCount`. Ein Ganzzahlwert, die die maximale Anzahl der Neuversuche für den Versand einer Nachricht von der Anwendungswarteschlange zu der Anwendung angibt. Der Standardwert ist 5. Dieser Wert ist in Fällen ausreichend, in denen eine sofortige Wiederholung das Problem behebt, beispielsweise wenn ein temporärer Deadlock für eine Datenbank vorliegt.  
  
- `MaxRetryCycles`. Ein Ganzzahlwert, der die maximale Anzahl der Wiederholungszyklen angibt. Ein Wiederholungszyklus umfasst die Übertragung einer Nachricht von der Anwendungswarteschlange zur untergeordneten Wiederholungswarteschlange und – nach einer konfigurierbaren Verzögerung – die Rückübertragung der Nachricht aus der untergeordneten Wiederholungswarteschlange zur Anwendungswarteschlange, um einen erneuten Zustellversuch zu unternehmen. Der Standardwert ist 2. In [!INCLUDE[wv](../../../../includes/wv-md.md)] erfolgen maximal (`ReceiveRetryCount` +1) * (`MaxRetryCycles` + 1) Versuche. `MaxRetryCycles` wird für [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] ignoriert.  
  
- `RetryCycleDelay`. Die Verzögerungszeit für Wiederholungszyklen. Der Standardwert ist 30 Minuten. `MaxRetryCycles` und `RetryCycleDelay` bieten gemeinsam einen Mechanismus zur Behandlung des Problems, wenn eine Wiederholung nach einer periodischen Verzögerung das Problem behebt. Damit wird z. B. ein gesperrtes Rowset bei einem in SQL Server anstehenden Transaktionscommit behandelt.  
  
- `ReceiveErrorHandling`. Eine Enumeration, die angibt, welche Aktion für eine Nachricht erfolgen soll, deren Zustellung auch nach der maximalen Anzahl von Wiederholungen fehlgeschlagen ist. Die Werte können „Fehler“, „Ablegen“, „Ablehnen“ und „Verschieben“ sein. Die Standardoption ist "Fehler".  
  
- Fehler. Diese Option sendet einen Fehler an den Listener, der bewirkt hat, dass der `ServiceHost` fehlerhaft agiert. Die Nachricht muss durch einen externen Mechanismus aus der Anwendungswarteschlange entfernt werden, bevor die Anwendung mit der Verarbeitung von Nachrichten aus der Warteschlange fortfahren kann.  
  
- Ablage. Diese Option legt die nicht verarbeitbare Nachricht ab, und die Nachricht wird der Anwendung nie zugestellt. Wenn die Eigenschaft `TimeToLive` der Nachricht zu diesem Zeitpunkt bereits abgelaufen ist, kann die Nachricht in der Warteschlange für unzustellbare Nachrichten des Absenders angezeigt werden. Andernfalls wird die Nachricht nirgendwo angezeigt. Diese Option gibt an, dass vom Benutzer keine Aktion für den Fall angegeben wurde, dass die Nachricht verloren geht.  
  
- Ablehnen. Diese Option ist nur in [!INCLUDE[wv](../../../../includes/wv-md.md)] verfügbar. Damit wird das Message Queuing (MSMQ) angewiesen, eine negative Bestätigung mit dem Hinweis, dass die Anwendung die Nachricht nicht empfangen kann, an den sendenden Warteschlangen-Manager zu senden. Die Nachricht wird in die Warteschlange für unzustellbare Nachrichten des sendenden Warteschlangen-Managers eingefügt.  
  
- Verschieben. Diese Option ist nur in [!INCLUDE[wv](../../../../includes/wv-md.md)] verfügbar. Damit wird die nicht verarbeitbare Nachricht in eine Warteschlange für potenziell schädliche Nachrichten verschoben, sodass sie später durch eine Anwendung zur Behandlung nicht verarbeitbarer Nachrichten verarbeitet werden kann. Die Warteschlange für potenziell schädliche Nachrichten ist eine untergeordnete Warteschlange der Anwendungswarteschlange. Eine Anwendung für die Handhabung beschädigter Nachrichten kann es sich um einen WCF-Dienst sein, der Nachrichten aus der Warteschlange für nicht verarbeitbare liest. Die Warteschlange für nicht verarbeitbare ist eine Unterwarteschlange der Anwendungswarteschlange und kann als net.msmq:// adressiert werden\<*Computername*>/*ApplicationQueue*; poison, wobei  *Computername* ist der Name des Computers, auf dem die Warteschlange befindet, und die *ApplicationQueue* ist der Name der anwendungsspezifischen Warteschlange.  
  
 Im Folgenden ist die maximale Anzahl von für eine Nachricht durchgeführten Übermittlungsversuchen dargestellt:  
  
- ((ReceiveRetryCount+1) * (MaxRetryCycles + 1)) auf [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
- (ReceiveRetryCount+1) auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)].  
  
> [!NOTE]
>  Für eine Nachricht, die erfolgreich zugestellt wird, werden keine Wiederholungen durchgeführt.  
  
 Zur Nachverfolgung, wie oft das Lesen einer Nachricht versucht wurde, verfügt [!INCLUDE[wv](../../../../includes/wv-md.md)] über eine dauerhafte Nachrichteneigenschaft, die die Anzahl der Abbrüche zählt, und über eine Verschiebungszähleigenschaft, die zählt, wie oft die Nachricht zwischen der Anwendungswarteschlange und den untergeordneten Warteschlangen verschoben wurde. Der WCF-Kanal verwendet diese zum Berechnen der empfangswiederholungsanzahl und der wiederholungszyklusanzahl. Auf [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)], die abbruchanzahl im Arbeitsspeicher verwaltet wird, die von der WCF-Kanal und wird zurückgesetzt, wenn die Anwendung ein Fehler auftritt. Darüber hinaus kann der WCF-Kanal enthalten, dass die abbruchanzahl für bis zu 256 Nachrichten im Arbeitsspeicher zu einem beliebigen Zeitpunkt. Wenn eine 257. Nachricht gelesen wird, dann wird die Abbruchanzahl der ältesten Nachricht zurückgesetzt.  
  
 Die Abbruchanzahl- und Verschiebungsanzahleigenschaften stehen dem Dienstvorgang durch den Vorgangskontext zur Verfügung. Im folgenden Codebeispiel wird der Zugriff darauf veranschaulicht.  
  
 [!code-csharp[S_UE_MSMQ_Poison#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/service.cs#1)]  
  
 WCF stellt zwei in der Warteschlange stehende standardbindungen bereit:  
  
- <xref:System.ServiceModel.NetMsmqBinding>. Ein [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] Bindung geeignet ist, zum Ausführen warteschlangenbasierter Kommunikation mit anderen WCF-Endpunkten.  
  
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>. Eine Bindung, die zur Kommunikation mit vorhandenen Message Queuing-Anwendungen geeignet ist.  
  
> [!NOTE]
>  Sie können Eigenschaften in diesen Bindungen basierend auf den Anforderungen von den WCF-Dienst ändern. Der gesamte Mechanismus zur Behandlung nicht verarbeitbarer Nachrichten ist zur empfangenden Anwendung lokal. Der Prozess ist für die sendende Anwendung unsichtbar, es sei denn, die empfangende Anwendung beendet den Vorgang und sendet eine negative Bestätigung an den Absender zurück. In diesem Fall wird die Nachricht in die Warteschlange für unzustellbare Nachrichten des Absenders verschoben.  
  
## <a name="best-practice-handling-msmqpoisonmessageexception"></a>Bewährte Methode: Handling MsmqPoisonMessageException  
 Wenn der Dienst feststellt, dass eine Nachricht nicht verarbeitbar ist, löst der Warteschlangentransport eine <xref:System.ServiceModel.MsmqPoisonMessageException> aus, die die `LookupId` der nicht verarbeitbaren Nachricht enthält.  
  
 Eine empfangende Anwendung kann die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle implementieren, um alle Fehler zu behandeln, die die Anwendung erfordert. Weitere Informationen finden Sie unter [erweitern-Steuerelement über Fehlerbehandlung und Berichterstellung](../../../../docs/framework/wcf/samples/extending-control-over-error-handling-and-reporting.md).  
  
 Die Anwendung erfordert möglicherweise eine bestimmte automatische Behandlung von nicht verarbeitbaren Nachrichten, mit der die nicht verarbeitbaren Nachrichten in eine entsprechende Warteschlange verschoben werden, sodass der Dienst auf die restlichen Nachrichten in der Warteschlange zugreifen kann. Das einzige Szenario, in dem der Fehlerbehandlungsmechanismus zum Abhören auf Ausnahmen für nicht verarbeitbare Nachrichten verwendet werden kann, liegt vor, wenn die <xref:System.ServiceModel.Configuration.MsmqBindingElementBase.ReceiveErrorHandling%2A>-Einstellung auf <xref:System.ServiceModel.ReceiveErrorHandling.Fault> festgelegt ist. Das Beispiel der nicht verarbeitbaren Nachricht für Message Queuing 3.0 veranschaulicht dieses Verhalten. Im Folgenden werden die Schritte zur Behandlung nicht verarbeitbarer Nachrichten, einschließlich empfohlener Vorgehensweisen, umrissen:  
  
1. Stellen Sie sicher, dass die Einstellungen für nicht verarbeitbare Nachrichten den Anforderungen Ihrer Anwendung entsprechen. Stellen Sie bei der Arbeit mit diesen Einstellungen sicher, dass Ihnen die Unterschiede zwischen den Message Queuing-Fähigkeiten in [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] bekannt sind.  
  
2. Implementieren Sie falls erforderlich den `IErrorHandler`, um Fehler mit nicht verarbeitbaren Nachrichten zu behandeln. Das das Festlegen von `ReceiveErrorHandling` auf `Fault` einen manuellen Mechanismus zum Verschieben der nicht verarbeitbaren Nachricht aus der Warteschlange oder zum Korrigieren eines Problems mit externen Abhängigkeiten erfordert, besteht die typische Nutzung darin, den `IErrorHandler` zu implementieren, wenn `ReceiveErrorHandling` auf `Fault` festgelegt ist, wie im folgenden Code gezeigt:  
  
     [!code-csharp[S_UE_MSMQ_Poison#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/poisonerrorhandler.cs#2)]  
  
3. Erstellen Sie ein `PoisonBehaviorAttribute`, das das Dienstverhalten verwenden kann. Das Verhalten installiert den `IErrorHandler` auf dem Verteiler. Siehe nachstehendes Codebeispiel.  
  
     [!code-csharp[S_UE_MSMQ_Poison#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/s_ue_msmq_poison/cs/poisonbehaviorattribute.cs#3)]  
  
4. Stellen Sie sicher, dass der Dienst mit dem Verhaltensattribut für nicht verarbeitbare Nachrichten kommentiert wird.  

 Wenn außerdem das `ReceiveErrorHandling` auf `Fault` festgelegt ist, tritt beim `ServiceHost` ein Fehler auf, wenn dieser auf die nicht verarbeitbare Nachricht stößt. Sie können sich dem Fehlerereignis zuwenden und den Dienst herunterfahren, Korrekturmaßnahmen treffen und neu starten. Beispielsweise kann die `LookupId` in der <xref:System.ServiceModel.MsmqPoisonMessageException>, die an den `IErrorHandler` weitergegeben wurde, notiert werden. Tritt nun beim Diensthost ein Fehler auf, können Sie die `System.Messaging`-API verwenden, um die Nachricht mithilfe der `LookupId` aus der Warteschlange zu empfangen, die Nachricht aus der Warteschlange zu entfernen und die Nachricht in einem externen Speicher oder einer anderen Warteschlange zu speichern. Sie können dann den `ServiceHost` neu starten, um die normale Verarbeitung fortzusetzen. Die [Nachrichtenbehandlung nicht verarbeitbarer Nachrichten in MSMQ 4.0](../../../../docs/framework/wcf/samples/poison-message-handling-in-msmq-4-0.md) veranschaulicht dieses Verhalten.  
  
## <a name="transaction-time-out-and-poison-messages"></a>Transaktionstimeout und nicht verarbeitbare Nachrichten  
 Eine Klasse von Fehlern kann zwischen dem Wartenschlangentransportkanal und dem Benutzercode auftreten. Diese Fehler können durch Zwischenschichten erkannt werden, beispielsweise die Nachrichtensicherheitsschicht oder die Dienstverteilungslogik. So stellen beispielsweise ein in der SOAP-Sicherheitsschicht erkanntes fehlendes X.509-Zertifikat und eine fehlende Aktion Fälle dar, in denen die Nachricht nicht an die Anwendung verteilt wird. In diesem Fall wird die Nachricht durch das Dienstmodell wieder abgelegt. Da die Nachricht in einer Transaktion gelesen wird und ein Ergebnis für diese Transaktion nicht geliefert werden kann, kommt es letztlich zum Timeout der Transaktion, sie wird abgebrochen, und die Nachricht wird wieder in die Warteschlange zurückgestellt. Mit anderen Worten: Für eine bestimmte Fehlerklasse führt die Transaktion keinen sofortigen Abbruch durch, sondern wartet, bis es zum Timeout der Transaktion kommt. Sie können das Transaktionstimeout für einen Dienst mit <xref:System.ServiceModel.ServiceBehaviorAttribute> ändern.  
  
 Um das Transaktionstimeout auf einer computerweiten Basis zu ändern, modifizieren Sie die machine.config-Datei und legen das entsprechende Transaktionstimeout fest. Wichtig: Die Transaktion wird in Abhängigkeit vom festgelegten Transaktionstimeout schließlich abgebrochen, wieder in der Warteschlange platziert, und die Abbruchanzahl wird erhöht. Schließlich wird die Nachricht nicht verarbeitbar, und die richtige Disposition wird entsprechend den Benutzereinstellungen gewählt.  
  
## <a name="sessions-and-poison-messages"></a>Sitzungen und nicht verarbeitbare Nachrichten  
 Eine Sitzung durchläuft die gleichen Wiederholungsprozeduren und Prozeduren zur Behandlung nicht verarbeitbarer Nachrichten wie eine einzelne Nachricht. Die zuvor aufgeführten Eigenschaften für nicht verarbeitbare Nachrichten gelten auch für die ganze Sitzung, d. h., dass die gesamte Sitzung wiederholt wird und schließlich in einer Warteschlange für potenziell schädliche Nachrichten oder in der Absenderwarteschlange für unzustellbare Nachrichten platziert wird, wenn die Nachricht abgelehnt wird.  
  
## <a name="batching-and-poison-messages"></a>Batchverarbeitung und nicht verarbeitbare Nachrichten  
 Wenn eine Nachricht zu einer nicht verarbeitbaren Nachricht wird und Teil eines Batches ist, wird für den gesamten Batch ein Rollback durchgeführt, und der Kanal kehrt zum Lesen einzelner Nachrichten zurück. Weitere Informationen zur Batchverarbeitung finden Sie unter [Batchverarbeitung von Nachrichten in einer Transaktion](../../../../docs/framework/wcf/feature-details/batching-messages-in-a-transaction.md)  
  
## <a name="poison-message-handling-for-messages-in-a-poison-queue"></a>Behandlung nicht verarbeitbarer Nachrichten für Nachrichten in einer Warteschlange für potenziell schädliche Nachrichten  
 Die Behandlung nicht verarbeitbarer Nachrichten ist nicht damit beendet, dass eine Nachricht in die Warteschlange für potenziell schädliche Nachrichten eingefügt wird. Die Nachrichten in der Warteschlange für potenziell schädliche Nachrichten müssen immer noch gelesen und behandelt werden. Beim Lesen von Nachrichten aus der endgültigen Warteschlange für potenziell schädliche Nachrichten können Sie eine Teilmenge der Einstellungen zur Behandlung nicht verarbeitbarer Nachrichten verwenden. Die anwendbaren Einstellungen sind `ReceiveRetryCount` und `ReceiveErrorHandling`. Sie können `ReceiveErrorHandling` auf "Drop", "Reject" oder "Fault" festlegen. `MaxRetryCycles` wird ignoriert, und es wird eine Ausnahme ausgelöst, wenn `ReceiveErrorHandling` auf {3&amp;amp;gt;Move&amp;amp;lt;3} festgelegt wird.  
  
## <a name="windows-vista-windows-server-2003-and-windows-xp-differences"></a>Unterschiede zwischen Windows Vista, Windows Server 2003 und Windows XP  
 Wie bereits oben erwähnt, sind in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht alle Einstellungen für die Behandlung nicht verarbeitbarer Nachrichten anwendbar. Die folgenden Hauptunterschiede zwischen dem Message Queuing in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], [!INCLUDE[wxp](../../../../includes/wxp-md.md)] und [!INCLUDE[wv](../../../../includes/wv-md.md)] sind für die Behandlung nicht verarbeitbarer Nachrichten relevant:  
  
- Message Queuing in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt untergeordnete Warteschlangen, während [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] keine untergeordneten Warteschlangen unterstützen. Untergeordnete Warteschlangen werden zur Behandlung nicht verarbeitbarer Nachrichten verwendet. Die Wiederholungswarteschlangen und die Warteschlange für potenziell schädliche Nachrichten sind untergeordnete Warteschlangen der Anwendungswarteschlange, die basierend auf den Einstellungen für die Behandlung nicht verarbeitbarer Nachrichten erstellt wird. Die Eigenschaft `MaxRetryCycles` bestimmt, wie viele untergeordnete Wiederholungwarteschlangen erstellt werden sollen. Deshalb werden bei der Ausführung unter [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] oder unter [!INCLUDE[wxp](../../../../includes/wxp-md.md)] die `MaxRetryCycles` ignoriert, und `ReceiveErrorHandling.Move` wird nicht zugelassen.  
  
- Message Queuing in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt die negative Bestätigung, während [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] dies nicht tun. Eine negative Bestätigung vom empfangenden Warteschlangen-Manager bewirkt, dass der sendende Warteschlangen-Manager die abgelehnte Nachricht in die Warteschlange für unzustellbare Nachrichten einstellt. Damit ist `ReceiveErrorHandling.Reject` in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht zulässig.  
  
- Message Queuing in [!INCLUDE[wv](../../../../includes/wv-md.md)] unterstützt eine Nachrichteneigenschaft, die zählt, wie oft die Nachrichtenzustellung versucht wird. Diese Abbruchanzahleigenschaft ist in [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] und [!INCLUDE[wxp](../../../../includes/wxp-md.md)] nicht verfügbar. WCF verwaltet die abbruchanzahl im Arbeitsspeicher, sodass es möglich, dass diese Eigenschaft nicht auf einen genauen Wert enthalten kann, wenn dieselbe Nachricht von mehr als ein WCF-Dienst in einer Farm gelesen wird.  
  
## <a name="see-also"></a>Siehe auch

- [Warteschlangenübersicht](../../../../docs/framework/wcf/feature-details/queues-overview.md)
- [Unterschiede zwischen den Warteschlangenfunktionen in Windows Vista, Windows Server 2003 und Windows XP](../../../../docs/framework/wcf/feature-details/diff-in-queue-in-vista-server-2003-windows-xp.md)
- [Angeben und Behandeln von Fehlern in Verträgen und Diensten](../../../../docs/framework/wcf/specifying-and-handling-faults-in-contracts-and-services.md)
