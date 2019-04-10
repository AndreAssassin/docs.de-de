---
title: Asynchronous Programming with Async and Await (Visual Basic) (Asynchrone Programmierung mit Async und Await (Visual Basic))
ms.date: 07/20/2015
ms.assetid: bd7e462b-583b-4395-9c36-45aa9e61072c
ms.openlocfilehash: 8593275371fcd97db2357211c3e221839b878527
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59324720"
---
# <a name="asynchronous-programming-with-async-and-await-visual-basic"></a>Asynchronous Programming with Async and Await (Visual Basic) (Asynchrone Programmierung mit Async und Await (Visual Basic))
Sie können Leistungsengpässe vermeiden und die Reaktionsfähigkeit der Anwendung insgesamt verbessern, indem Sie asynchrone Programmierung verwenden. Allerdings können herkömmliche Verfahren zum Schreiben von asynchronen Anwendungen kompliziert sein, weshalb es schwierig ist, diese Anwendungen zu schreiben, zu debuggen und zu verwalten.  
  
 Visual Studio 2012 führte den vereinfachten Ansatz der asynchronen Programmierung ein, der die asynchrone Unterstützung in .NET Framework 4.5 und höher sowie in der Windows-Runtime nutzt. Der Compiler übernimmt die schwierige Arbeit, die zuvor vom Entwickler ausgeführt wurde, und die Anwendung behält eine logische Struktur bei, die synchronem Code ähnelt. So erhalten Sie alle Vorteile der asynchronen Programmierung mit einem Bruchteil des Aufwands.  
  
 Dieses Thema enthält eine Übersicht über die Verwendungsmöglichkeiten der asynchronen Programmierung sowie Links zu Supportthemen, die weitere Informationen und Beispiele enthalten.  
  
## <a name="BKMK_WhentoUseAsynchrony"></a> Async verbessert die Reaktionsfähigkeit  
 Asynchronie ist wesentlich für potenziell blockierende Aktivitäten, z. B. wenn die Anwendung auf das Internet zugreift. Der Zugriff auf eine Webressource ist manchmal langsam oder verzögert. Wenn eine solche Aktivität innerhalb eines synchronen Prozesses blockiert wird, muss die gesamte Anwendung warten. In einem asynchronen Prozess kann die Anwendung mit anderer Arbeit fortfahren, die nicht von der Webressource abhängig ist, bis die potenziell blockierende Aufgabe beendet ist.  
  
 In der folgenden Tabelle werden typische Bereichen angezeigt, in denen die asynchrone Programmierung die Reaktionsfähigkeit verbessert. Die aufgelisteten APIs von .NET Framework 4.5 und der Windows-Runtime enthalten Methoden, die die asynchrone Programmierung unterstützen.  
  
|Anwendungsbereich|Unterstützende APIs, die asynchrone Methoden enthalten|  
|----------------------|------------------------------------------------|  
|Webzugriff|<xref:System.Net.Http.HttpClient>, <xref:Windows.Web.Syndication.SyndicationClient>|  
|Arbeiten mit Dateien|<xref:Windows.Storage.StorageFile>, <xref:System.IO.StreamWriter>, <xref:System.IO.StreamReader>, <xref:System.Xml.XmlReader>|  
|Arbeiten mit Bildern|<xref:Windows.Media.Capture.MediaCapture>ist <xref:Windows.Graphics.Imaging.BitmapEncoder>ist <xref:Windows.Graphics.Imaging.BitmapDecoder>|  
|WCF-Programmierung|[Synchrone und asynchrone Vorgänge](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)|  
|||  
  
 Asynchronität erweist sich als besonders nützlich bei Prozessen, die durch den UI-Thread ausgeführt werden, da sämtliche auf die Benutzeroberfläche bezogenen Aktivitäten sich gemeinhin diesen Thread teilen. Ist ein Prozess in einer synchronen Anwendung blockiert, werden alle blockiert. Die Anwendung reagiert nicht mehr, und Sie denken möglicherweise, es sei ein Fehler aufgetreten, wenn die Anwendung tatsächlich nur wartet.  
  
 Wenn Sie asynchrone Methoden verwenden, reagiert die Anwendung weiterhin auf die Benutzeroberfläche. Sie können beispielsweise die Fenstergröße ändern, das Fenster minimieren oder die Anwendung schließen, wenn Sie nicht warten möchten, bis sie fertig ist.  
  
 Durch den auf Asynchronie basierenden Ansatz wird eine Entsprechung für die automatische Übertragung an die Liste der Optionen hinzugefügt, die beim Entwerfen von asynchronen Vorgängen zur Auswahl stehen. Sie erhalten also alle Vorteile der herkömmlichen asynchronen Programmierung, der Aufwand des Entwicklers ist jedoch wesentlich geringer.  
  
## <a name="BKMK_HowtoWriteanAsyncMethod"></a> Async-Methoden sind einfacher zu schreiben  
 Die Schlüsselwörter [Async](../../../../visual-basic/language-reference/modifiers/async.md) und [Await](../../../../visual-basic/language-reference/modifiers/async.md) in Visual Basic sind der Kern der asynchronen Programmierung. Wenn Sie diese beiden Schlüsselwörter verwenden, können Sie eine asynchrone Methode mithilfe von Ressourcen in .NET Framework oder Windows-Runtime fast genauso einfach erstellen wie eine synchrone Methode. Asynchrone Methoden, die Sie unter Verwendung von `Async` und `Await` definieren, werden als async-Methoden bezeichnet.  
  
 Das folgende Beispiel zeigt eine Async-Methode. Fast der gesamte Code sollte Ihnen bekannt vorkommen. Die Kommentare rufen die von Ihnen hinzugefügten Funktionen auf, um die Asynchronie zu erstellen.  
  
 Eine vollständige WPF-Beispieldatei (Windows Presentation Foundation) finden Sie am Ende dieses Themas, und Sie können das Beispiel hier herunterladen: [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c) (Asynchrones Beispiel aus der asynchronen Programmierung mit „async“ und „await“).  
  
```vb  
' Three things to note in the signature:  
'  - The method has an Async modifier.   
'  - The return type is Task or Task(Of T). (See "Return Types" section.)  
'    Here, it is Task(Of Integer) because the return statement returns an integer.  
'  - The method name ends in "Async."  
Async Function AccessTheWebAsync() As Task(Of Integer)  
  
    ' You need to add a reference to System.Net.Http to declare client.  
    Dim client As HttpClient = New HttpClient()  
  
    ' GetStringAsync returns a Task(Of String). That means that when you await the  
    ' task you'll get a string (urlContents).  
    Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
  
    ' You can do work here that doesn't rely on the string from GetStringAsync.  
    DoIndependentWork()  
  
    ' The Await operator suspends AccessTheWebAsync.  
    '  - AccessTheWebAsync can't continue until getStringTask is complete.  
    '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
    '  - Control resumes here when getStringTask is complete.   
    '  - The Await operator then retrieves the string result from getStringTask.  
    Dim urlContents As String = Await getStringTask  
  
    ' The return statement specifies an integer result.  
    ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
    Return urlContents.Length  
End Function  
```  
  
 Wenn für `AccessTheWebAsync` zwischen dem Aufrufen von `GetStringAsync` und dem Warten auf die Beendigung keine Arbeit ansteht, können Sie den Code durch Aufrufen und Warten in der folgenden Anweisung vereinfachen.  
  
```vb  
Dim urlContents As String = Await client.GetStringAsync()  
```  
  
 Die folgenden Eigenschaften fassen zusammen, wodurch das vorherige Beispiel sich als eine asynchrone Methode auszeichnet.  
  
-   Die Methodensignatur enthält einen `Async`-Modifizierer.  
  
-   Der Name einer Async-Methode endet mit dem Suffix "Async".  
  
-   Der Rückgabetyp ist einer der folgenden Typen:  
  
    -   <xref:System.Threading.Tasks.Task%601> Wenn die Methode eine return-Anweisung in der der Operand den Typ TResult aufweist.  
  
    -   <xref:System.Threading.Tasks.Task> Wenn die Methode keine return-Anweisung oder eine return-Anweisung ohne Operanden hat.  
  
    -   [Sub](../../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md), wenn Sie einen asynchronen Ereignishandler schreiben.  
  
     Weitere Informationen finden Sie unter „Rückgabetypen und Parameter“ weiter unten in diesem Thema.  
  
-   Die Methode umfasst normalerweise mindestens einen await-Ausdruck, der einen Punkt kennzeichnet, an dem die Methode erst nach Abschluss des erwarteten Vorgangs fortgesetzt werden kann. In der Zwischenzeit wird die Methode angehalten, und die Steuerung kehrt zum Aufrufer der Methode zurück. Im nächsten Abschnitt dieses Themas wird veranschaulicht, was am Unterbrechungspunkt geschieht.  
  
 In Asynch-Methoden verwenden Sie die bereitgestellten Schlüsselwörter und Typen, um die gewünschten Aktionen anzugeben. Der Compiler übernimmt den Rest, er verfolgt auch, was geschehen muss, wenn die Steuerung zu einem await-Punkt in einer angehaltenen Methode zurückkehrt. Einige Routinenprozesse, beispielsweise Schleifen und Ausnahmebehandlung, sind im herkömmlichen asynchronen Code möglicherweise schwierig zu handhaben. In einer Async-Methode schreiben Sie diese Elemente fast so wie in einer synchronen Lösung, und das Problem ist gelöst.  
  
 Weitere Informationen zur Asynchronität in vorherigen .NET Framework-Versionen finden Sie unter [TPL und herkömmliche asynchrone Programmierung in .NET Framework](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Was geschieht in einer asynchronen Methode?  
 Bei der asynchronen Programmierung ist es sehr wichtig zu verstehen, wie die Ablaufsteuerung von Methode zu Methode springt. In dem folgenden Diagramm werden Sie durch den Prozess geführt.  
  
 ![Diagramm, das die Nachverfolgung eines asynchronen Programms zeigt.](./media/index/navigation-trace-async-program.png)  
  
 Die Zahlen im Diagramm entsprechen den folgenden Schritten.  
  
1. Ein Ereignishandler ruft die Async-Methode `AccessTheWebAsync` auf und wartet auf sie.  
  
2. `AccessTheWebAsync` erstellt eine <xref:System.Net.Http.HttpClient> -Instanz und ruft die <xref:System.Net.Http.HttpClient.GetStringAsync%2A> asynchrone Methode, um den Inhalt einer Website als Zeichenfolge herunterzuladen.  
  
3. In `GetStringAsync` geschieht etwas, durch das die Ausführung angehalten wird. Möglicherweise muss gewartet werden, bis eine Website heruntergeladen oder eine andere blockierende Aktivität ausgeführt wurde. Um blockierende Ressourcen zu vermeiden, übergibt die Methode `GetStringAsync` die Steuerung an ihren Aufrufer `AccessTheWebAsync`.  
  
     `GetStringAsync` Gibt eine <xref:System.Threading.Tasks.Task%601> TResult eine Zeichenfolge ist und `AccessTheWebAsync` weist die Aufgabe der `getStringTask` Variable. Die Aufgabe stellt den laufenden Prozess für den Aufruf von `GetStringAsync` dar, mit der Festlegung, dass bei Abschluss der Arbeit ein tatsächlicher Zeichenfolgenwert erzeugt wurde.  
  
4. Da `getStringTask` noch nicht abgewartet wurde, kann `AccessTheWebAsync` mit anderer Arbeit fortfahren, die nicht vom Endergebnis von `GetStringAsync` abhängt. Diese Aufgaben werden durch einen Aufruf der synchronen Methode `DoIndependentWork` dargestellt.  
  
5. `DoIndependentWork` ist eine synchrone Methode, die ihre Arbeit ausführt und zu dessen Aufrufer zurück.  
  
6. `AccessTheWebAsync` ist nicht genügend Arbeit, die dies, ohne ein Ergebnis von tun kann `getStringTask`. `AccessTheWebAsync` möchte als Nächstes berechnen und Zurückgeben der Länge der heruntergeladenen Zeichenfolge ist, aber die Methode können diesen Wert nicht berechnen, bis die Methode die Zeichenfolge ist.  
  
     Daher verwendet `AccessTheWebAsync` einen await-Operator, um die Ausführung anzuhalten und die Steuerung an die Methode zu übergeben, von der `AccessTheWebAsync` aufgerufen wurde. `AccessTheWebAsync` Gibt eine `Task<int>` (`Task(Of Integer)` in Visual Basic) an den Aufrufer. Die Aufgabe stellt eine Zusicherung dar, ein Ganzzahlergebnis zu erzeugen, das die Länge der heruntergeladenen Zeichenfolge ist.  
  
    > [!NOTE]
    >  Wenn die Methode `GetStringAsync` (und daher `getStringTask`) abgeschlossen ist, bevor `AccessTheWebAsync` auf sie wartet, verbleibt die Steuerung bei `AccessTheWebAsync`. Der Aufwand des Anhaltens und der Rückkehr zu `AccessTheWebAsync` wäre Verschwendung, wenn der aufgerufene asynchrone Prozess (`getStringTask`) bereits abgeschlossen ist und "AccessTheWebSync" nicht auf das Endergebnis warten muss.  
  
     Innerhalb des Aufrufers (der Ereignishandler in diesem Beispiel) wird das Prozessmuster fortgesetzt. Der Aufrufer führt möglicherweise andere Arbeit aus, die nicht von dem Ergebnis von `AccessTheWebAsync` abhängt, bevor er auf dieses Ergebnis wartet, oder der Aufrufer wartet sofort auf das Ergebnis.   Der Ereignishandler wartet auf `AccessTheWebAsync`, und `AccessTheWebAsync` wartet auf `GetStringAsync`.  
  
7. `GetStringAsync` Schließt ein, und erstellt ein Zeichenfolgenergebnis. Das Zeichenfolgenergebnis wird von dem Aufruf `GetStringAsync` nicht auf die Art zurückgegeben, die Sie möglicherweise erwarten. (Beachten Sie, dass die Methode bereits in Schritt 3 eine Aufgabe zurückgegeben hat.) Stattdessen wird das Zeichenfolgenergebnis in dem Task gespeichert, der den Abschluss der Methode darstellt: `getStringTask`. Der await-Operator ruft das Ergebnis von `getStringTask` ab. Die Zuweisungsanweisung weist `urlContents` das abgerufene Ergebnis zu.  
  
8. Wenn `AccessTheWebAsync` über das Zeichenfolgenergebnis verfügt, kann die Methode die Länge der Zeichenfolge berechnen. Dann ist die Arbeit von `AccessTheWebAsync` auch abgeschlossen, und der wartende Ereignishandler kann fortfahren. Im vollständigen Beispiel am Ende des Themas können Sie überprüfen, ob der Ereignishandler den Wert des Längenergebnisses abruft und druckt.  
  
 Wenn die asynchrone Programmierung für Sie neu ist, nehmen Sie sich einen Moment Zeit, um den Unterschied zwischen synchronem und asynchronem Verhalten zu untersuchen. Eine synchrone Methode kehrt zum Aufrufer zurück, wenn ihre Arbeit abgeschlossen ist (Schritt 5). Eine asynchrone Methode hingegen gibt einen Aufgabenwert zurück, wenn die Verarbeitung angehalten wird (Schritt 3 und 6). Wenn die asynchrone Methode schließlich ihre Arbeit abgeschlossen hat, wird die Aufgabe als abgeschlossen markiert und das Ergebnis ggf. in der Aufgabe gespeichert.  
  
 Weitere Informationen zur Ablaufsteuerung finden Sie unter [Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="BKMK_APIAsyncMethods"></a> API-Async-Methoden  
 Sie fragen sich möglicherweise, wo Methoden wie `GetStringAsync` zu finden sind, die die asynchrone Programmierung unterstützen. .NET Framework 4.5 oder höher enthält viele Member, die mit `Async` und `Await` funktionieren. Sie können diese Member durch das Suffix "Async" erkennen, das dem Membernamen und dem Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> angefügt wird. Beispielsweise enthält die `System.IO.Stream`-Klasse Methoden wie <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> und <xref:System.IO.Stream.WriteAsync%2A> sowie die synchronen Methoden <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> und <xref:System.IO.Stream.Write%2A>.  
  
 Die Windows-Runtime enthält außerdem viele Methoden, die Sie mit `Async` und `Await` in Windows-Apps verwenden können. Weitere Informationen und Beispielmethoden finden Sie unter [Aufrufen von asynchronen APIs in C# oder Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic), [asynchrone Programmierung (Windows-Runtime-apps)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)), und ["whenany": Für die Überbrückung zwischen .NET Framework und die Windows-Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120)).  
  
## <a name="BKMK_Threads"></a> Threads  
 Async-Methoden sollen nicht blockierende Vorgänge sein. Ein `Await`-Ausdruck in einer asynchronen Methode blockiert den aktuellen Thread nicht, während der abgewartete Task ausgeführt wird. Stattdessen registriert der Ausdruck den Rest der Methode als Fortsetzung und gibt die Steuerung an den Aufrufer der Async-Methode zurück.  
  
 Durch die Schlüsselwörter `Async` und `Await` werden keine zusätzlichen Threads erstellt. Async-Methoden erfordern kein Multithreading, da eine Async-Methode nicht in einem eigenen Thread ausgeführt wird. Die Methode wird im aktuellen Synchronisierungskontext ausgeführt und verwendet Zeit im Thread nur, wenn sie aktiv ist. Sie können <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> zur Verschiebung CPU-gebundener Arbeit in einen Hintergrundthread verwenden, aber ein Hintergrundthread nützt nichts bei einem Prozess, der wartet, dass Ergebnisse zur Verfügung gestellt werden.  
  
 Der auf Asynchronie basierende Ansatz der asynchronen Programmierung ist vorhandenen Ansätzen in nahezu jedem Fall vorzuziehen. Dieser Ansatz ist besser als <xref:System.ComponentModel.BackgroundWorker> für e/A-gebundene Vorgänge daran, dass der Code einfacher ist und nicht zum Schutz vor Racebedingungen. In Kombination mit <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> eignet sich asynchrone Programmierung besser für CPU-gebundene Vorgänge als <xref:System.ComponentModel.BackgroundWorker>, da die asynchrone Programmierung Koordinationsdetails der Ausführung des Codes von der Arbeit trennt, die `Task.Run` an den Threadpool überträgt.  
  
## <a name="BKMK_AsyncandAwait"></a> Async und Await  
 Wenn Sie angeben, dass eine Methode eine Async-Methode ist, indem Sie einen [Async](../../../../visual-basic/language-reference/modifiers/async.md)-Modifizierer verwenden, aktivieren Sie die folgenden zwei Funktionen.  
  
-   Die markierte Async-Methode kann [Await](../../../../visual-basic/language-reference/operators/await-operator.md) verwenden, um Unterbrechungspunkte festzulegen. Der await-Operator informiert den Compiler, dass die Async-Methode erst über diesen Punkt hinaus fortgesetzt werden kann, wenn der abgewartete asynchrone Prozess abgeschlossen ist. In der Zwischenzeit kehrt die Steuerung zum Aufrufer der Async-Methode zurück.  
  
     Die Unterbrechung einer async-Methode an einem `Await`-Ausdruck stellt keine Beendigung der Methode dar, und `Finally`-Blöcke werden nicht ausgeführt.  
  
-   Auf die markierte Async-Methode können auch Methoden warten, die sie aufrufen.  
  
 Eine async-Methode enthält in der Regel eine oder mehrere Vorkommen eines `Await`-Operators, die Abwesenheit von `Await`-Ausdrücken verursacht jedoch keinen Compilerfehler. Wenn eine async-Methode keinen `Await`-Operator verwendet, um einen Unterbrechungspunkt zu markieren, wird die Methode ungeachtet des `Async`-Modifizierers wie eine synchrone Methode ausgeführt. Der Compiler gibt eine Warnung für solche Methoden aus.  
  
 `Async` und `Await` sind Kontextbezogene Schlüsselwörter. Weitere Informationen und Beispiele finden Sie unter den folgenden Themen:  
  
-   [Async](../../../../visual-basic/language-reference/modifiers/async.md)  
  
-   [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md)  
  
## <a name="BKMK_ReturnTypesandParameters"></a> Rückgabetypen und Parameter  
 In .NET Framework gibt eine asynchrone Methode in der Regel <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück. Innerhalb einer async-Methode wird ein `Await`-Operator auf einen Task angewendet, der in einem Aufruf einer anderen async-Methode zurückgegeben wurde.  
  
 Sie geben <xref:System.Threading.Tasks.Task%601> als Rückgabetyp an, wenn die Methode eine [Rückgabeanweisung](../../../../visual-basic/language-reference/statements/return-statement.md) enthält, die einen Operanden des Typs `TResult` angibt.  
  
 Sie verwenden `Task` als Rückgabetyp, wenn die Methode keine return-Anweisung hat oder über eine return-Anweisung verfügt, die keinen Operanden zurückgibt.  
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine Methode deklarieren und aufrufen, die <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task> zurückgibt.  
  
```vb  
' Signature specifies Task(Of Integer)  
Async Function TaskOfTResult_MethodAsync() As Task(Of Integer)  
  
    Dim hours As Integer  
    ' . . .  
    ' Return statement specifies an integer result.  
    Return hours  
End Function  
  
' Calls to TaskOfTResult_MethodAsync  
Dim returnedTaskTResult As Task(Of Integer) = TaskOfTResult_MethodAsync()  
Dim intResult As Integer = Await returnedTaskTResult  
' or, in a single statement  
Dim intResult As Integer = Await TaskOfTResult_MethodAsync()  
  
' Signature specifies Task  
Async Function Task_MethodAsync() As Task  
  
    ' . . .  
    ' The method has no return statement.  
End Function  
  
' Calls to Task_MethodAsync  
Task returnedTask = Task_MethodAsync()  
Await returnedTask  
' or, in a single statement  
Await Task_MethodAsync()  
```  
  
 Jede zurückgegebene Aufgabe stellt derzeit ausgeführte Arbeit dar. Eine Aufgabe kapselt Informationen über den Zustand des asynchronen Prozesses und schließlich entweder das Endergebnis aus dem Prozess oder die Ausnahme, die durch einen Prozessfehler verursacht wird.  
  
 Eine asynchrone Methode kann auch eine `Sub`-Methode sein. Dieser Rückgabetyp wird hauptsächlich zum Definieren von Ereignishandlern verwendet, bei denen ein Rückgabetyp erforderlich ist. Asynchrone Ereignishandler dienen häufig als Ausgangspunkt für asynchrone Programme.  
  
 Eine asynchrone Methode, bei der es sich um eine `Sub`-Prozedur handelt, kann nicht abgewartet werden, und der Aufrufer kann keine Ausnahmen erfassen, die die Methode auswirft.  
  
 Mit einer asynchronen Methode können keine [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)-Parameter deklariert, jedoch Methoden aufgerufen werden, die solche Parameter aufweisen.  
  
 Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md). Weitere Informationen zum Auffangen von Ausnahmen in async-Methoden finden Sie unter [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) (Try...Catch...Finally-Anweisung).  
  
 Asynchrone APIs in der Windows-Runtime-Programmierung weisen einen der folgenden Rückgabetypen auf, die Tasks ähnlich sind:  
  
-   <xref:Windows.Foundation.IAsyncOperation%601>, entspricht <xref:System.Threading.Tasks.Task%601>  
  
-   <xref:Windows.Foundation.IAsyncAction>, entspricht <xref:System.Threading.Tasks.Task>  
  
-   <xref:Windows.Foundation.IAsyncActionWithProgress%601>  
  
-   <xref:Windows.Foundation.IAsyncOperationWithProgress%602>  
  
 Weitere Informationen und ein Beispiel finden Sie unter [aufrufen asynchroner APIs in c# oder Visual Basic](/windows/uwp/threading-async/call-asynchronous-apis-in-csharp-or-visual-basic).  
  
## <a name="BKMK_NamingConvention"></a> Benennungskonvention  
 Gemäß der Konvention fügen Sie die Zeichenfolge „Async“ an die Namen von Methoden an, die einen `Async`-Modifizierer besitzen.  
  
 Sie können die Konvention ignorieren, wenn ein Ereignis, eine Basisklasse oder ein Schnittstellenvertrag einen anderen Namen vorsieht. Beispielsweise sollten Sie allgemeine Ereignishandler wie `Button1_Click` nicht umbenennen.  
  
## <a name="BKMK_RelatedTopics"></a> Verwandte Themen und Beispiele (Visual Studio)  
  
|Titel|Beschreibung|Beispiel|  
|-----------|-----------------|------------|  
|[Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|Zeigt, wie eine synchrone WPF-Projektmappe in eine asynchrone WPF-Projektmappe konvertiert wird. Die Anwendung lädt eine Reihe von Websites herunter.|[ASYNC-Beispiel: Accessing the Web Walkthrough](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|  
|[Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Fügt der vorherigen exemplarischen Vorgehensweise <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> hinzu. Bei Verwendung von `WhenAll` werden alle Downloads gleichzeitig gestartet.||  
|[Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit Async und Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Veranschaulicht, wie mehrere Aufgaben gleichzeitig gestartet werden.|[ASYNC-Beispiel: Paralleles erstellen Sie mehrerer Webanforderungen](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|  
|[Asynchrone Rückgabetypen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/async-return-types.md)|Veranschaulicht die Typen, die Async-Methoden zurückgeben können und erklärt, wann die einzelnen Typen geeignet sind.||  
|[Ablaufsteuerung in asynchronen Programmen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/control-flow-in-async-programs.md)|Verfolgt die Ablaufsteuerung ausführlich durch eine Reihenfolge von await-Ausdrücken in einem asynchronen Programm.|[ASYNC-Beispiel: Ablaufsteuerung in asynchronen Programmen](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|  
|[Feinabstimmung der Async-Anwendung (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/fine-tuning-your-async-application.md)|Zeigt, wie die folgenden Funktionen der asynchronen Lösung hinzugefügt werden:<br /><br /> -   [Cancel an Async Task or a List of Tasks (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md) (Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (Visual Basic))<br />-   [Cancel Async Tasks after a Period of Time (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md) (Asynchrone Aufgaben nach einer Zeitperiode abbrechen (Visual Basic))<br />-   [Cancel Remaining Async Tasks after One Is Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md) (Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (Visual Basic))<br />-   [Start Multiple Async Tasks and Process Them As They Complete (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md) (Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (Visual Basic))|[ASYNC-Beispiel: Feinabstimmung der Anwendung](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|  
|[Umgang mit Ablaufinvarianz in asynchronen Anwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|Zeigt, wie Fälle gehandhabt werden, in denen ein aktiver asynchroner Vorgang neu gestartet wird, während er ausgeführt wird.||  
|[WhenAny: Überbrückung zwischen .NET Framework und Windows-Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|Zeigt, wie zwischen Aufgabentypen in .NET Framework und „IAsyncOperations“ in [!INCLUDE[wrt](~/includes/wrt-md.md)] überbrückt wird, sodass <xref:System.Threading.Tasks.Task.WhenAny%2A> mit einer [!INCLUDE[wrt](~/includes/wrt-md.md)]-Methode verwendet werden kann.|[ASYNC-Beispiel: Für die Überbrückung zwischen .NET und Windows-Runtime ("astask" und "whenany")](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|  
|Asynchroner Abbruch: Überbrückung zwischen .NET Framework und Windows-Runtime|Zeigt, wie zwischen Aufgabentypen in .NET Framework und „IAsyncOperations“ in [!INCLUDE[wrt](~/includes/wrt-md.md)] überbrückt wird, sodass <xref:System.Threading.CancellationTokenSource> mit einer [!INCLUDE[wrt](~/includes/wrt-md.md)]-Methode verwendet werden kann.|[ASYNC-Beispiel: Für die Überbrückung zwischen .NET und Windows-Runtime ("AsTask" & "Cancellation")](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|  
|[Using Async for File Access (Visual Basic) (Verwenden von Async für Dateizugriff (Visual Basic))](../../../../visual-basic/programming-guide/concepts/async/using-async-for-file-access.md)|Listet die Vorteile der Verwendung von "async" und "await" für den Zugriff auf Dateien auf und veranschaulicht sie.||  
|[Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Beschreibt ein neues Muster für Asynchronie in .NET Framework. Das Muster basiert auf den <xref:System.Threading.Tasks.Task>- und <xref:System.Threading.Tasks.Task%601>-Typen.||  
|[Videos zur asynchronen Programmierung auf Channel 9](https://channel9.msdn.com/search?term=async+&type=All)|Stellt Links zu einer Vielzahl von Videos über die asynchrone Programmierung bereit.||  
  
## <a name="BKMK_CompleteExample"></a> Vollständiges Beispiel  
 Bei dem folgenden Code handelt es sich um die Datei „MainWindow.xaml.vb“ aus der WPF-Anwendung (Windows Presentation Foundation), die in diesem Thema erläutert wird. Sie können das Beispiel hier herunterladen: [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c) (Asynchrones Beispiel aus der asynchronen Programmierung mit „async“ und „await“).  
  
```vb  
' Add an Imports statement and a reference for System.Net.Http  
Imports System.Net.Http  
  
Class MainWindow  
  
    ' Mark the event handler with async so you can use Await in it.  
    Private Async Sub StartButton_Click(sender As Object, e As RoutedEventArgs)  
  
        ' Call and await separately.  
        'Task<int> getLengthTask = AccessTheWebAsync();  
        '' You can do independent work here.  
        'int contentLength = await getLengthTask;  
  
        Dim contentLength As Integer = Await AccessTheWebAsync()  
  
        ResultsTextBox.Text &=  
            String.Format(vbCrLf & "Length of the downloaded string: {0}." & vbCrLf, contentLength)  
    End Sub  
  
    ' Three things to note in the signature:  
    '  - The method has an Async modifier.   
    '  - The return type is Task or Task(Of T). (See "Return Types" section.)  
    '    Here, it is Task(Of Integer) because the return statement returns an integer.  
    '  - The method name ends in "Async."  
    Async Function AccessTheWebAsync() As Task(Of Integer)  
  
        ' You need to add a reference to System.Net.Http to declare client.  
        Dim client As HttpClient = New HttpClient()  
  
        ' GetStringAsync returns a Task(Of String). That means that when you await the  
        ' task you'll get a string (urlContents).  
        Dim getStringTask As Task(Of String) = client.GetStringAsync("https://msdn.microsoft.com")  
  
        ' You can do work here that doesn't rely on the string from GetStringAsync.  
        DoIndependentWork()  
  
        ' The Await operator suspends AccessTheWebAsync.  
        '  - AccessTheWebAsync can't continue until getStringTask is complete.  
        '  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
        '  - Control resumes here when getStringTask is complete.   
        '  - The Await operator then retrieves the string result from getStringTask.  
        Dim urlContents As String = Await getStringTask  
  
        ' The return statement specifies an integer result.  
        ' Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
        Return urlContents.Length  
    End Function  
  
    Sub DoIndependentWork()  
        ResultsTextBox.Text &= "Working . . . . . . ." & vbCrLf  
    End Sub  
End Class  
  
' Sample Output:  
  
' Working . . . . . . .  
  
' Length of the downloaded string: 41763.  
```  
  
## <a name="see-also"></a>Siehe auch

- [Await-Operator](../../../../visual-basic/language-reference/operators/await-operator.md)
- [Async](../../../../visual-basic/language-reference/modifiers/async.md)
