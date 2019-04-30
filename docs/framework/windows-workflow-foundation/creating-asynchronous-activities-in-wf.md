---
title: Erstellen von asynchronen Aktivitäten in WF
ms.date: 03/30/2017
ms.assetid: 497e81ed-5eef-460c-ba55-fae73c05824f
ms.openlocfilehash: 5d8659ee57f9bb576cd7066652a294717811432f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945885"
---
# <a name="creating-asynchronous-activities-in-wf"></a>Erstellen von asynchronen Aktivitäten in WF
Das <xref:System.Activities.AsyncCodeActivity>-Objekt stellt eine Basisklasse für Aktivitätsautoren bereit, mit der abgeleitete Aktivitäten asynchrone Ausführungslogik implementieren können. Dies ist nützlich bei benutzerdefinierten Aktivitäten, die asynchrone Aufgaben ausführen müssen, ohne dass der Workflowplanerthread angehalten und Aktivitäten, die parallel ausgeführt werden, bockiert werden. Dieses Thema enthält eine Übersicht zum Erstellen von benutzerdefinierten asynchronen Aktivitäten mit <xref:System.Activities.AsyncCodeActivity>.  
  
## <a name="using-asynccodeactivity"></a>Verwenden von AsyncCodeActivity  
 <xref:System.Activities?displayProperty=nameWithType> bietet benutzerdefinierten Aktivitätsautoren verschiedene Basisklassen, mit denen auf die unterschiedlichen Anforderungen der Aktivitätserstellung eingegangen wird. Jede einzelne davon weist eine bestimmte Semantik auf und stellt einem Workflowautor (und der Aktivitätslaufzeit) einen entsprechenden Vertrag bereit. Ein Aktivität auf Grundlage des <xref:System.Activities.AsyncCodeActivity>-Objekts ist eine Aktivität, die Aufgaben asynchron in Verbindung mit dem Planerthread ausführt und deren Ausführungslogik in verwaltetem Code ausgedrückt wird. Als Ergebnis der Asynchronität kann ein <xref:System.Activities.AsyncCodeActivity>-Objekt möglicherweise während der Ausführung einen Leerlaufpunkt herbeiführen. Aufgrund der flüchtigen Art asynchroner Arbeit erstellt ein <xref:System.Activities.AsyncCodeActivity>-Objekt immer einen nicht persistenten Block für die Dauer der Ausführung der Aktivität. Dadurch wird verhindert, dass die Workflowlaufzeit die Workflowinstanz während der asynchronen Arbeit speichert oder die Workflowinstanz während der Ausführung von asynchronem Code entladen wird.  
  
### <a name="asynccodeactivity-methods"></a>AsyncCodeActivity-Methoden  
 Aktivitäten, die vom <xref:System.Activities.AsyncCodeActivity>-Objekt ableiten, können asynchrone Ausführungslogik erstellen, indem sie die <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A>-Methode und die <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>-Methode mit benutzerdefiniertem Code überschreiben. Wenn diese Methoden von der Laufzeit aufgerufen werden, wird <xref:System.Activities.AsyncCodeActivityContext> an sie übergeben. <xref:System.Activities.AsyncCodeActivityContext> kann ein aktivitätsautor zu gemeinsam genutzten Zustands <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> /  <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> im Kontext des <xref:System.Activities.AsyncCodeActivityContext.UserState%2A> Eigenschaft. Im folgenden Beispiel generiert eine `GenerateRandom`-Aktivität eine Zufallszahl auf asynchrone Weise.  
  
 [!code-csharp[CFX_ActivityExample#8](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#8)]  
  
 Die vorangehende Beispielaktivität wird von <xref:System.Activities.AsyncCodeActivity%601> abgeleitet und verfügt über ein erhöhtes `OutArgument<int>` mit dem Namen `Result`. Der von der `GetRandom`-Methode zurückgegebene Wert wird extrahiert und von der <xref:System.Activities.AsyncCodeActivity%601.EndExecute%2A>-Überschreibung zurückgegeben. Dieser Wert wird als `Result`-Wert festgelegt. Asynchrone Aktivitäten, die kein Ergebnis zurückgeben, sollten von <xref:System.Activities.AsyncCodeActivity> abgeleitet werden. Im folgenden Beispiel wird eine `DisplayRandom`-Aktivität definiert, die von <xref:System.Activities.AsyncCodeActivity> abgeleitet wird. Diese Aktivität entspricht der `GetRandom`-Aktivität, aber statt ein Ergebnis zurückzugeben, wird eine Meldung in der Konsole angezeigt.  
  
 [!code-csharp[CFX_ActivityExample#11](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#11)]  
  
 Da es keinen Rückgabewert gibt, verwendet `DisplayRandom` zum Aufrufen des zugehörigen Delegaten ein <xref:System.Action>-Element statt eines <xref:System.Func%602>-Elements, und der Delegat gibt keinen Wert zurück.  
  
 Die <xref:System.Activities.AsyncCodeActivity> stellt außerdem eine <xref:System.Activities.AsyncCodeActivity.Cancel%2A>-Überschreibung bereit. Während <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> und <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> erforderliche Überschreibungen darstellen, ist <xref:System.Activities.AsyncCodeActivity.Cancel%2A> optional und kann überschrieben werden, damit die Aktivität ihren ausstehenden asynchronen Zustand bereinigen kann, wenn sie abgebrochen wird. Wenn eine Bereinigung möglich ist und `AsyncCodeActivity.ExecutingActivityInstance.IsCancellationRequested` auf `true` festgelegt ist, sollte die Aktivität <xref:System.Activities.AsyncCodeActivityContext.MarkCanceled%2A> aufrufen. Alle von dieser Methode ausgelösten Ausnahmen wirken sich fatal auf die Workflowinstanz aus.  
  
 [!code-csharp[CFX_ActivityExample#10](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#10)]  
  
### <a name="invoking-asynchronous-methods-on-a-class"></a>Aufrufen von asynchronen Methoden für eine Klasse  
 Viele der Klassen in [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] stellen asynchrone Funktionalität bereit, und diese Funktionalität kann asynchron mit einer <xref:System.Activities.AsyncCodeActivity>-basierten Aktivität aufgerufen werden. Im folgenden Beispiel wird eine Aktivität erstellt, die erstellt asynchron eine Datei mit den <xref:System.IO.FileStream> Klasse.  
  
 [!code-csharp[CFX_ActivityExample#12](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#12)]  
  
### <a name="sharing-state-between-the-beginexecute-and-endexecute-methods"></a>Gemeinsame Zustandsverwendung durch die BeginExecute-Methode und die EndExecute-Methode  
 Im vorherigen Beispiel wurde auf das <xref:System.IO.FileStream>-Objekt, das in <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> erstellt wurde, in <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> zugegriffen. Dies ist möglich, weil die `file`-Variable in der <xref:System.Activities.AsyncCodeActivityContext.UserState%2A?displayProperty=nameWithType>-Eigenschaft in <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> übergeben wurde. Dies ist die richtige Methode zum gemeinsamen Verwenden des Zustands zwischen <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> und <xref:System.Activities.AsyncCodeActivity.EndExecute%2A>. Es ist unzulässig, eine Membervariable in der abgeleiteten Klasse (in diesem Fall `FileWriter`) zu verwenden, um einen gemeinsamen Zustand für <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> und <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> zu verwenden, da auf das Aktivitätsobjekt von mehreren Aktivitätsinstanzen verwiesen werden kann. Der Versuch, eine Membervariable zu verwenden, um einen Zustand gemeinsam zu verwenden, kann dazu führen, dass Werte einer <xref:System.Activities.ActivityInstance> Werte einer anderen <xref:System.Activities.ActivityInstance> überschreiben oder nutzen.  
  
### <a name="accessing-argument-values"></a>Zugreifen auf Argumentwerte  
 Die Umgebung eines <xref:System.Activities.AsyncCodeActivity>-Objekts besteht aus den Argumenten, die für die Aktivität definiert sind. Diese Argumente zugegriffen werden können, aus der <xref:System.Activities.AsyncCodeActivity.BeginExecute%2A> / <xref:System.Activities.AsyncCodeActivity.EndExecute%2A> -überschreibungen mit dem <xref:System.Activities.AsyncCodeActivityContext> Parameter. Im Delegaten kann nicht auf die Argumente zugegriffen werden. Die Argumentwerte oder andere gewünschte Daten können jedoch mithilfe seiner Parameter an den Delegaten übergeben werden. Im folgenden Beispiel wird eine Aktivität definiert, die Zufallszahlen generiert. Die Aktivität ruft ihre inklusive obere Begrenzung aus ihrem `Max`-Argument ab. Der Wert des Arguments wird an den asynchronen Code übergeben, sobald der Delegat aufgerufen wird.  
  
 [!code-csharp[CFX_ActivityExample#9](~/samples/snippets/csharp/VS_Snippets_CFX/CFX_ActivityExample/cs/Program.cs#9)]  
  
### <a name="scheduling-actions-or-child-activities-using-asynccodeactivity"></a>Planen von Aktionen oder untergeordneten Aktivitäten mithilfe von AsyncCodeActivity  
 Von <xref:System.Activities.AsyncCodeActivity> abgeleitete benutzerdefinierte Aktivitäten ermöglichen das asynchrone Arbeiten am Workflowthread, bieten aber keine Möglichkeit, untergeordnete Aktivitäten oder Aktionen zu planen. Das asynchrone Verhalten kann jedoch integriert werden, indem untergeordnete Aktivitäten bei der Zusammensetzung geplant werden. Eine asynchrone Aktivität kann erstellt und dann mit einer abgeleiteten <xref:System.Activities.Activity>-Aktivität oder <xref:System.Activities.NativeActivity>-Aktivität zusammengestellt werden, um Unterstützung für asynchrones Verhalten und die Planung untergeordneter Aktivitäten oder Aktionen bereitzustellen. Beispielsweise könnte eine Aktivität erstellt werden, die von <xref:System.Activities.Activity> abgeleitet ist und als Implementierung über <xref:System.Activities.Statements.Sequence> verfügt, die asynchrone Aktivität sowie die anderen Aktivitäten enthält, die die Logik der Aktivität implementieren. Weitere Beispiele für das Verfassen von Aktivitäten mit <xref:System.Activities.Activity> und <xref:System.Activities.NativeActivity>, finden Sie unter [Vorgehensweise: Erstellen einer Aktivität](how-to-create-an-activity.md) und [Optionen Erstellung von Aktivitäten](activity-authoring-options-in-wf.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Action>
- <xref:System.Func%602>
