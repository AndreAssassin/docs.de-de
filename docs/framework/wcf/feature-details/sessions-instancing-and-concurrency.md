---
title: Sitzungen, Instanziierung und Parallelität
ms.date: 03/30/2017
ms.assetid: 50797a3b-7678-44ed-8138-49ac1602f35b
ms.openlocfilehash: a7466d819e15f3bfe8def2d9407dcf2c6e0c7346
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184442"
---
# <a name="sessions-instancing-and-concurrency"></a>Sitzungen, Instanziierung und Parallelität
Eine *Sitzung* ist die Korrelation (d. h. die Beziehung) aller zwischen zwei Endpunkten gesendeter Nachrichten. *Instanziierung* bezieht sich auf die Steuerung der Lebensdauer von benutzerdefinierten Dienstobjekten und den zugehörigen <xref:System.ServiceModel.InstanceContext> -Objekten. *Parallelität* bezeichnet die Kontrolle der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> ausgeführt werden.  
  
 In diesem Thema werden diese Einstellungen, ihre Verwendung und die Interaktion zwischen den Einstellungen beschrieben.  
  
## <a name="sessions"></a>Sitzungen  
 Wenn die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft durch einen Dienstvertrag auf <xref:System.ServiceModel.SessionMode.Required?displayProperty=nameWithType>festgelegt wird, bedeutet dies, dass alle Aufrufe (das heißt der zugrunde liegende Nachrichtenaustausch, durch den die Aufrufe unterstützt werden) Teil derselben Konversation sein müssen. Falls in einem Vertrag angegeben wird, dass Sitzungen zwar erlaubt, aber nicht erforderlich sind, können Clients eine Verbindung herstellen und eine Sitzung aufbauen oder auch nicht. Wird eine Sitzung beendet und eine Nachricht über diesen sitzungsbasierten Kanal gesendet, wird eine Ausnahme ausgelöst.  
  
 WCF-Sitzungen weisen die folgenden konzeptionellen Hauptmerkmale auf:  
  
- Sie werden explizit von der aufrufenden Anwendung initiiert und beendet.  
  
- Die während einer Sitzung gesendeten Nachrichten werden in der Reihenfolge verarbeitet, in der sie empfangen wurden.  
  
- Durch Sitzungen wird eine Gruppe von Nachrichten zu einer Konversation zusammengefasst. Diese Korrelation ist jedoch abstrakt. So werden zum Beispiel bei einem sitzungsbasierten Kanal Nachrichten auf Grundlage einer gemeinsamen Netzwerkverbindung zueinander in Beziehung gesetzt, bei einem anderen Kanal geschieht dies wiederum auf Grundlage eines gemeinsamen Tags im Nachrichtentext. Die Funktionen, die von der Sitzung abgeleitet werden können, sind abhängig von der Art der Korrelation.  
  
- Einer WCF-Sitzung ist kein allgemeiner Datenspeicher zugeordnet.  
  
 Wenn Sie mit <xref:System.Web.SessionState.HttpSessionState?displayProperty=nameWithType> der Klasse in ASP.NET Anwendungen und der darin zur Verfügung gestellten Funktionalität vertraut sind, können Sie die folgenden Unterschiede zwischen dieser Art von Sitzungssitzungen und WCF-Sitzungen feststellen:  
  
- ASP.NET Sitzungen werden immer vom Server initiiert.  
  
- ASP.NET Sitzungen sind implizit ungeordnet.  
  
- ASP.NET Sitzungen bieten einen allgemeinen Datenspeichermechanismus für alle Anforderungen.  
  
 Client- und Dienstanwendungen interagieren auf unterschiedliche Weise mit Sitzungen. Clientanwendungen initiieren Sitzungen und empfangen und verarbeiten dann die innerhalb der Sitzung gesendeten Nachrichten. Dienstanwendungen können Sitzungen als Erweiterungspunkt verwenden, um zusätzliches Verhalten hinzuzufügen. Dies geschieht durch direkte Nutzung von <xref:System.ServiceModel.InstanceContext> oder durch Implementierung eines benutzerspezifischen Instanzenkontextanbieters.  
  
## <a name="instancing"></a>Instanziierung  
 Durch das Instanziierungsverhalten (das über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft festgelegt wird) lässt sich steuern, wie der <xref:System.ServiceModel.InstanceContext> als Antwort auf eingehende Nachrichten erstellt wird. Standardmäßig ist jeder <xref:System.ServiceModel.InstanceContext> einem benutzerdefinierten Dienstobjekt zugeordnet. Dies bedeutet, dass (im Normalfall) auch die Instanziierung benutzerdefinierter Dienstobjekte über die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> -Eigenschaft gesteuert wird. Die <xref:System.ServiceModel.InstanceContextMode> -Enumeration definiert die Instanziierungsmodi.  
  
 Es stehen die folgenden Instanziierungsmodi zur Verfügung:  
  
- <xref:System.ServiceModel.InstanceContextMode.PerCall>: Für jede Clientanforderung wird ein neuer <xref:System.ServiceModel.InstanceContext> (und damit auch ein neues Dienstobjekt) erstellt.  
  
- <xref:System.ServiceModel.InstanceContextMode.PerSession>: Für jede neue Clientsitzung wird ein neuer <xref:System.ServiceModel.InstanceContext> (und damit auch ein neues Dienstobjekt) erstellt und für die Lebensdauer dieser Sitzung aufrechterhalten, wofür eine Bindung erforderlich ist, die Sitzungen unterstützt.  
  
- <xref:System.ServiceModel.InstanceContextMode.Single>: Alle Clientanforderungen werden während der Lebensdauer der Anwendung von einem <xref:System.ServiceModel.InstanceContext> (und damit einem Dienstobjekt) verarbeitet.  
  
 Das folgende Codebeispiel zeigt den Standard- <xref:System.ServiceModel.InstanceContextMode> -Wert ( <xref:System.ServiceModel.InstanceContextMode.PerSession> ), der explizit für eine Dienstklasse festgelegt wird.  
  
```csharp  
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]
public class CalculatorService : ICalculatorInstance
{
    ...  
}  
```  
  
 Durch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft wird gesteuert, wie oft der <xref:System.ServiceModel.InstanceContext> freigegeben wird. Die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> -Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.ReleaseServiceInstanceOnTransactionComplete%2A?displayProperty=nameWithType> -Eigenschaft bestimmen dagegen, wann das Dienstobjekt freigegeben wird.  
  
### <a name="well-known-singleton-services"></a>Bekannte Singleton-Dienste  
 Gelegentlich ist eine Variante für einzelne Instanzendienstobjekte nützlich: Sie können selbst ein Dienstobjekt und den Diensthost, der dieses Objekt verwendet, erstellen. Hierfür müssen Sie auch die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft auf <xref:System.ServiceModel.InstanceContextMode.Single> festlegen, damit keine Ausnahme ausgelöst wird, sobald der Diensthost geöffnet wird.  
  
 Verwenden Sie zum Erstellen eines solchen Diensts den <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Object%2CSystem.Uri%5B%5D%29?displayProperty=nameWithType> -Konstruktor. Dieser stellt eine Alternative zur Implementierung eines benutzerdefinierten <xref:System.ServiceModel.Dispatcher.IInstanceContextInitializer?displayProperty=nameWithType> dar, wenn Sie eine bestimmte Objektinstanz für einen Singleton-Dienst bereitstellen möchten. Sie können diese Überladung verwenden, wenn der Dienstimplementierungstyp schwer zu konstruieren ist (z. B. wenn kein parameterloser öffentlicher Konstruktor implementiert wird).  
  
 Beachten Sie, dass einige Features, die sich auf das Instancing-Verhalten von Windows Communication Foundation (WCF) beziehen, unterschiedlich funktionieren, wenn diesem Konstruktor ein Objekt bereitgestellt wird. So zeigt zum Beispiel der Aufruf von <xref:System.ServiceModel.InstanceContext.ReleaseServiceInstance%2A?displayProperty=nameWithType> keine Wirkung, wenn eine Singleton-Objektinstanz bereitgestellt wird. Dementsprechend werden auch alle anderen Instanzfreigabemechanismen ignoriert. Der <xref:System.ServiceModel.ServiceHost> verhält sich immer so, als ob die <xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A?displayProperty=nameWithType> -Eigenschaft für alle Vorgänge auf <xref:System.ServiceModel.ReleaseInstanceMode.None?displayProperty=nameWithType> festgelegt ist.  
  
### <a name="sharing-instancecontext-objects"></a>Freigeben von InstanceContext-Objekten  
 Sie können auch steuern, welcher sitzungsbasierte Kanal oder Aufruf dem <xref:System.ServiceModel.InstanceContext> -Objekt zugeordnet wird, indem Sie diese Zuordnung selbst vornehmen.  
  
## <a name="concurrency"></a>Parallelität  
 Bei der Parallelität handelt es sich um die Steuerung der Anzahl von Threads, die gleichzeitig in einem <xref:System.ServiceModel.InstanceContext> aktiv sind. Sie können diese Anzahl über <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A?displayProperty=nameWithType> in Verbindung mit der <xref:System.ServiceModel.ConcurrencyMode> -Enumeration bestimmen.  
  
 Es stehen die folgenden drei Parallelitätsmodi zur Verfügung:  
  
- <xref:System.ServiceModel.ConcurrencyMode.Single>: Jeder Instanzkontext darf höchstens über jeweils einen Thread verfügen, der im Instanzkontext Nachrichten verarbeitet. Falls weitere Threads diesen Instanzkontext verwenden möchten, werden sie so lange blockiert, bis der ursprüngliche Thread den Instanzkontext verlässt.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Multiple>: Jede Dienstinstanz kann über mehrere Threads verfügen, die Nachrichten gleichzeitig verarbeiten. Für diesen Parallelitätsmodus muss die Dienstimplementierung threadsicher sein.  
  
- <xref:System.ServiceModel.ConcurrencyMode.Reentrant>: Jede Dienstinstanz verarbeitet jeweils nur eine Nachricht, akzeptiert jedoch eintrittsinvariante Aufrufe. Der Dienst akzeptiert diese Aufrufe nur, wenn er über ein WCF-Clientobjekt ausruft.  
  
> [!NOTE]
> Das Schreiben von Code, bei dem problemlos mehr als ein Thread verwendet wird, kann sich als sehr schwierig erweisen. Stellen Sie sicher, dass Ihr Dienst ordnungsgemäß mit den Modi <xref:System.ServiceModel.ConcurrencyMode.Multiple> bzw. <xref:System.ServiceModel.ConcurrencyMode.Reentrant> arbeiten kann, bevor Sie diese Werte verwenden. Weitere Informationen finden Sie unter <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>.  
  
 Die Parallelität steht mit dem Instanziierungsmodus in Beziehung. Beim <xref:System.ServiceModel.InstanceContextMode.PerCall> Instancing ist Parallelität nicht relevant, da jede <xref:System.ServiceModel.InstanceContext> Nachricht von einem neuen verarbeitet wird <xref:System.ServiceModel.InstanceContext>und daher nie mehr als ein Thread im aktiv ist.  
  
 Das folgende Codebeispiel zeigt, wie die <xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A> -Eigenschaft auf den Wert <xref:System.ServiceModel.ConcurrencyMode.Multiple>festgelegt wird.  
  
```csharp
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]
public class CalculatorService : ICalculatorConcurrency
{
    ...  
}  
```  
  
## <a name="sessions-interact-with-instancecontext-settings"></a>Interaktion von Sitzungen und InstanceContext-Einstellungen  
 Sitzungen und der <xref:System.ServiceModel.InstanceContext> interagieren je nach Kombination des Werts der <xref:System.ServiceModel.SessionMode> -Enumeration in einem Vertrag und der <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft der Dienstimplementierung, durch die die Zuordnung zwischen Kanälen und bestimmten Dienstobjekten gesteuert wird.  
  
 Die folgende Tabelle enthält eine Übersicht über die Ergebnisse eines eingehenden Kanals, der Sitzungen je nach Kombination der Werte für die <xref:System.ServiceModel.ServiceContractAttribute.SessionMode%2A?displayProperty=nameWithType> -Eigenschaft und die <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A?displayProperty=nameWithType> -Eigenschaft eines Diensts unterstützt oder nicht unterstützt.  
  
|InstanceContextMode-Wert|<xref:System.ServiceModel.SessionMode.Required>|<xref:System.ServiceModel.SessionMode.Allowed>|<xref:System.ServiceModel.SessionMode.NotAllowed>|  
|-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|  
|PerCall|- Verhalten mit sessionful Kanal: Eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Anruf.<br />- Verhalten mit sitzungslosem Kanal: Eine Ausnahme wird ausgelöst.|- Verhalten mit sessionful Kanal: Eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Anruf.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden Anruf.|- Verhalten mit sessionful Channel: Eine Ausnahme wird ausgelöst.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden Anruf.|  
|PerSession|- Verhalten mit Sessionful Channel: Eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Kanal.<br />- Verhalten mit sitzungslosem Kanal: Eine Ausnahme wird ausgelöst.|- Verhalten mit Sessionful Channel: Eine Sitzung und <xref:System.ServiceModel.InstanceContext> für jeden Kanal.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden Anruf.|- Verhalten mit sessionful Channel: Eine Ausnahme wird ausgelöst.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden Anruf.|  
|Single|- Verhalten mit sessionful Channel: <xref:System.ServiceModel.InstanceContext> Eine Sitzung und eine für alle Anrufe.<br />- Verhalten mit sitzungslosem Kanal: Eine Ausnahme wird ausgelöst.|- Verhalten mit sessionful Channel: Eine Sitzung und <xref:System.ServiceModel.InstanceContext> für das erstellte oder benutzerdefinierte Singleton.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für das erstellte oder benutzerdefinierte Singleton.|- Verhalten mit sessionful Channel: Eine Ausnahme wird ausgelöst.<br />- Verhalten mit sitzungslosem Kanal: Ein <xref:System.ServiceModel.InstanceContext> für jeden erstellten Singleton oder für das benutzerdefinierte Singleton.|  
  
## <a name="see-also"></a>Weitere Informationen

- [Verwenden von Sitzungen](../../../../docs/framework/wcf/using-sessions.md)
- [Vorgehensweise: Erstellen eines Diensts, der Sitzungen erfordert](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-that-requires-sessions.md)
- [Gewusst wie: Steuern der Dienstinstanzierung](../../../../docs/framework/wcf/feature-details/how-to-control-service-instancing.md)
- [Parallelität](../../../../docs/framework/wcf/samples/concurrency.md)
- [Instanziierung](../../../../docs/framework/wcf/samples/instancing.md)
- [Sitzung](../../../../docs/framework/wcf/samples/session.md)
