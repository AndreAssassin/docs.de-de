---
title: Das aufgabenbasierte asynchrone Programmiermodell (TAP) mit Async und Await (C#)
ms.date: 05/22/2017
ms.assetid: 9bcf896a-5826-4189-8c1a-3e35fa08243a
ms.openlocfilehash: 2fde365acfab3342082e2ca286decc00ca73a19d
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295964"
---
# <a name="task-asynchronous-programming-model"></a>Aufgabenbasiertes asynchrones Programmiermodell
Sie können Leistungsengpässe vermeiden und die Reaktionsfähigkeit der Anwendung insgesamt verbessern, indem Sie asynchrone Programmierung verwenden. Allerdings können herkömmliche Verfahren zum Schreiben von asynchronen Anwendungen kompliziert sein, weshalb es schwierig ist, diese Anwendungen zu schreiben, zu debuggen und zu verwalten.  
  
[C# 5](../../../whats-new/csharp-version-history.md#c-version-50) führte den vereinfachten Ansatz der asynchronen Programmierung ein, der die asynchrone Unterstützung in .NET Framework 4.5 und höher, .NET Core sowie in der Windows-Runtime nutzt. Der Compiler übernimmt die schwierige Arbeit, die zuvor vom Entwickler ausgeführt wurde, und die Anwendung behält eine logische Struktur bei, die synchronem Code ähnelt. So erhalten Sie alle Vorteile der asynchronen Programmierung mit einem Bruchteil des Aufwands.  
  
Dieses Thema enthält eine Übersicht über die Verwendungsmöglichkeiten der asynchronen Programmierung sowie Links zu Supportthemen, die weitere Informationen und Beispiele enthalten.  
  
## <a name="BKMK_WhentoUseAsynchrony"></a> Async verbessert die Reaktionsfähigkeit  
 Asynchronie ist wesentlich für potenziell blockierende Aktivitäten, z.B. Webzugriff. Der Zugriff auf eine Webressource ist manchmal langsam oder verzögert. Wenn eine solche Aktivität innerhalb eines synchronen Prozesses blockiert wird, muss die gesamte Anwendung warten. In einem asynchronen Prozess kann die Anwendung mit anderer Arbeit fortfahren, die nicht von der Webressource abhängig ist, bis die potenziell blockierende Aufgabe beendet ist.  
  
 In der folgenden Tabelle werden typische Bereichen angezeigt, in denen die asynchrone Programmierung die Reaktionsfähigkeit verbessert. Die aufgelisteten APIs von .NET und der Windows-Runtime enthalten Methoden, die die asynchrone Programmierung unterstützen.  
  
| Anwendungsbereich    | .NET-Typen mit asynchronen Methoden     | Windows-Runtime-Typen mit asynchronen Methoden  |
|---------------------|-----------------------------------|-------------------------------------------|
|Webzugriff|<xref:System.Net.Http.HttpClient>|<xref:Windows.Web.Syndication.SyndicationClient>|
|Arbeiten mit Dateien|<xref:System.IO.StreamWriter>ist <xref:System.IO.StreamReader>ist <xref:System.Xml.XmlReader>|<xref:Windows.Storage.StorageFile>|  
|Arbeiten mit Bildern||<xref:Windows.Media.Capture.MediaCapture>ist <xref:Windows.Graphics.Imaging.BitmapEncoder>ist <xref:Windows.Graphics.Imaging.BitmapDecoder>|  
|WCF-Programmierung|[Synchrone und asynchrone Vorgänge](../../../../framework/wcf/synchronous-and-asynchronous-operations.md)||  
  
Asynchronität erweist sich als besonders nützlich bei Prozessen, die durch den UI-Thread ausgeführt werden, da sämtliche auf die Benutzeroberfläche bezogenen Aktivitäten sich gemeinhin diesen Thread teilen. Ist ein Prozess in einer synchronen Anwendung blockiert, werden alle blockiert. Die Anwendung reagiert nicht mehr, und Sie denken möglicherweise, es sei ein Fehler aufgetreten, wenn die Anwendung tatsächlich nur wartet.  
  
 Wenn Sie asynchrone Methoden verwenden, reagiert die Anwendung weiterhin auf die Benutzeroberfläche. Sie können beispielsweise die Fenstergröße ändern, das Fenster minimieren oder die Anwendung schließen, wenn Sie nicht warten möchten, bis sie fertig ist.  
  
 Durch den auf Asynchronie basierenden Ansatz wird eine Entsprechung für die automatische Übertragung an die Liste der Optionen hinzugefügt, die beim Entwerfen von asynchronen Vorgängen zur Auswahl stehen. Sie erhalten also alle Vorteile der herkömmlichen asynchronen Programmierung, der Aufwand des Entwicklers ist jedoch wesentlich geringer.  
  
## <a name="BKMK_HowtoWriteanAsyncMethod"></a> Asynchrone Methoden sind einfacher zu schreiben  
 Die Schlüsselwörter [async](../../../../csharp/language-reference/keywords/async.md) und [await](../../../../csharp/language-reference/keywords/await.md) in C# sind das Kernstück der asynchronen Programmierung. Wenn Sie diese beiden Schlüsselwörter verwenden, können Sie eine asynchrone Methode mithilfe von Ressourcen in .NET Framework, .NET Core oder Windows-Runtime fast genauso einfach erstellen wie eine synchrone Methode. Asynchrone Methoden, die Sie unter Verwendung des Schlüsselworts `async` definieren, werden als *async-Methoden* bezeichnet.  
  
 Das folgende Beispiel zeigt eine Async-Methode. Fast der gesamte Code sollte Ihnen bekannt vorkommen. 
  
 Eine vollständige WPF-Beispieldatei (Windows Presentation Foundation) finden Sie am Ende dieses Themas, und Sie können das Beispiel hier herunterladen: [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c) (Asynchrones Beispiel aus der asynchronen Programmierung mit „async“ und „await“).  
  
```csharp  
async Task<int> AccessTheWebAsync()  
{   
    // You need to add a reference to System.Net.Http to declare client.  
    using (HttpClient client = new HttpClient())  
    {  
        Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com");  
  
        DoIndependentWork();  
  
        string urlContents = await getStringTask;  
  
        return urlContents.Length;  
    }  
}  
```  

 Sie können dem vorherigen Beispiel mehrere Methoden entnehmen. Starten Sie mit der Methodensignatur. Sie enthält den `async`-Modifizierer. Der Rückgabetyp lautet `Task<int>` (weitere Optionen finden Sie im Abschnitt „Rückgabetypen“). Der Methodenname endet auf `Async`. Im Text der Methode gibt `GetStringAsync` einen `Task<string>`-Wert zurück. Das bedeutet, dass Sie `string` (`urlContents`) erhalten, wenn Sie auf die Aufgabe warten (`await`).  Bevor Sie auf die Aufgabe warten, können Sie Arbeiten ausführen, die nicht auf einem `string`-Wert von `GetStringAsync` basieren.  

 Achten Sie besonders auf den `await`-Operator. Er hält `AccessTheWebAsync` an.
 
- `AccessTheWebAsync` kann erst fortgesetzt werden, wenn `getStringTask` abgeschlossen ist.  
- In der Zwischenzeit wird die Steuerung an den Aufrufer von `AccessTheWebAsync` zurückgegeben.  
- Die Steuerung wird hier wieder aufgenommen, sobald `getStringTask` abgeschlossen ist.   
- Der `await`-Operator ruft nun das `string`-Ergebnis von `getStringTask` ab.  

 Die return-Anweisung gibt ein ganzzahliges Ergebnis an. Alle Methoden, die auf `AccessTheWebAsync` warten, rufen den Längenwert ab.  

 Wenn für `AccessTheWebAsync` zwischen dem Aufrufen von `GetStringAsync` und dem Warten auf die Beendigung keine Arbeit ansteht, können Sie den Code durch Aufrufen und Warten in der folgenden Anweisung vereinfachen.  
  
```csharp  
string urlContents = await client.GetStringAsync("https://docs.microsoft.com");  
```  
 
Die folgenden Eigenschaften fassen zusammen, wodurch das vorherige Beispiel sich als eine asynchrone Methode auszeichnet.  
  
-   Die Methodensignatur enthält einen `async`-Modifizierer.  
  
-   Der Name einer Async-Methode endet mit dem Suffix "Async".  
  
-   Der Rückgabetyp ist einer der folgenden Typen:  
  
    -   <xref:System.Threading.Tasks.Task%601> wenn die Methode über eine return-Anweisung verfügt, in der der Operand dem Typ `TResult` angehört.  
  
    -   <xref:System.Threading.Tasks.Task> wenn die Methode keine return-Anweisung hat oder eine return-Anweisung ohne Operanden hat.  
  
    -   `void` wenn Sie einen asynchronen Ereignishandler schreiben.  

    -   Jeder andere Typ, der über eine `GetAwaiter`-Methode verfügt (ab C# 7.0).
  
     Weitere Informationen finden Sie im Abschnitt [Rückgabetypen und Parameter](#BKMK_ReturnTypesandParameters).  
  
-   Die Methode umfasst normalerweise mindestens einen `await`-Ausdruck, der einen Punkt kennzeichnet, an dem die Methode erst nach Abschluss des erwarteten asynchronen Vorgangs fortgesetzt werden kann. In der Zwischenzeit wird die Methode angehalten, und die Steuerung kehrt zum Aufrufer der Methode zurück. Im nächsten Abschnitt dieses Themas wird veranschaulicht, was am Unterbrechungspunkt geschieht.  
  
 In Asynch-Methoden verwenden Sie die bereitgestellten Schlüsselwörter und Typen, um die gewünschten Aktionen anzugeben. Der Compiler übernimmt den Rest, er verfolgt auch, was geschehen muss, wenn die Steuerung zu einem await-Punkt in einer angehaltenen Methode zurückkehrt. Einige Routinenprozesse, beispielsweise Schleifen und Ausnahmebehandlung, sind im herkömmlichen asynchronen Code möglicherweise schwierig zu handhaben. In einer Async-Methode schreiben Sie diese Elemente fast so wie in einer synchronen Lösung, und das Problem ist gelöst.  
  
 Weitere Informationen zur Asynchronität in vorherigen .NET Framework-Versionen finden Sie unter [TPL und herkömmliche asynchrone Programmierung in .NET Framework](../../../../standard/parallel-programming/tpl-and-traditional-async-programming.md).  
  
## <a name="BKMK_WhatHappensUnderstandinganAsyncMethod"></a> Was geschieht in einer asynchronen Methode?  
 Bei der asynchronen Programmierung ist es sehr wichtig zu verstehen, wie die Ablaufsteuerung von Methode zu Methode springt. In dem folgenden Diagramm werden Sie durch den Prozess geführt.  
  
 ![Asynchrones Programm verfolgen](./media/task-asynchronous-programming-model/navigation-trace-async-program.png "NavigationTrace")  
  
 Die Zahlen im Diagramm entsprechen den folgenden Schritten, die beim Klicken auf die Schaltfläche „Start“ durch den Benutzer initiiert werden.
  
1. Ein Ereignishandler ruft die Async-Methode `AccessTheWebAsync` auf und wartet auf sie.  
  
2. `AccessTheWebAsync` erstellt eine <xref:System.Net.Http.HttpClient>-Instanz und ruft die asynchrone Methode <xref:System.Net.Http.HttpClient.GetStringAsync%2A> auf, um den Inhalt einer Website als Zeichenfolge herunterzuladen.  
  
3. In `GetStringAsync` geschieht etwas, durch das die Ausführung angehalten wird. Möglicherweise muss gewartet werden, bis eine Website heruntergeladen oder eine andere blockierende Aktivität ausgeführt wurde. Um blockierende Ressourcen zu vermeiden, übergibt die Methode `GetStringAsync` die Steuerung an ihren Aufrufer `AccessTheWebAsync`.  
  
     `GetStringAsync` gibt <xref:System.Threading.Tasks.Task%601> zurück, wobei `TResult` eine Zeichenfolge ist. `AccessTheWebAsync` weist der `getStringTask`-Variablen die Aufgabe zu. Die Aufgabe stellt den laufenden Prozess für den Aufruf von `GetStringAsync` dar, mit der Festlegung, dass bei Abschluss der Arbeit ein tatsächlicher Zeichenfolgenwert erzeugt wurde.  
  
4. Da `getStringTask` noch nicht abgewartet wurde, kann `AccessTheWebAsync` mit anderer Arbeit fortfahren, die nicht vom Endergebnis von `GetStringAsync` abhängt. Diese Aufgaben werden durch einen Aufruf der synchronen Methode `DoIndependentWork` dargestellt.  
  
5. `DoIndependentWork` ist eine synchrone Methode, die ihre Arbeit ausführt und zu ihrem Aufrufer zurückkehrt.  
  
6. `AccessTheWebAsync` steht keine Arbeit mehr an, die die Methode ohne ein Ergebnis von `getStringTask` ausführen kann. `AccessTheWebAsync` möchte als Nächstes die Länge der heruntergeladenen Zeichenfolge berechnen und zurückgeben, aber die Methode kann diesen Wert erst berechnen, wenn sie über die Zeichenfolge verfügt.  
  
     Daher verwendet `AccessTheWebAsync` einen await-Operator, um die Ausführung anzuhalten und die Steuerung an die Methode zu übergeben, von der `AccessTheWebAsync` aufgerufen wurde. `AccessTheWebAsync` gibt ein `Task<int>`-Element an den Aufrufer zurück. Die Aufgabe stellt eine Zusicherung dar, ein Ganzzahlergebnis zu erzeugen, das die Länge der heruntergeladenen Zeichenfolge ist.  
  
    > [!NOTE]
    >  Wenn `GetStringAsync` (und daher `getStringTask`) abgeschlossen ist, bevor `AccessTheWebAsync` darauf wartet, verbleibt die Steuerung bei `AccessTheWebAsync`. Der Aufwand des Anhaltens und der Rückkehr zu `AccessTheWebAsync` wäre Verschwendung, wenn der aufgerufene asynchrone Prozess (`getStringTask`) bereits abgeschlossen ist und `AccessTheWebSync` nicht auf das Endergebnis warten muss.  
  
     Innerhalb des Aufrufers (der Ereignishandler in diesem Beispiel) wird das Prozessmuster fortgesetzt. Der Aufrufer führt möglicherweise andere Arbeit aus, die nicht von dem Ergebnis von `AccessTheWebAsync` abhängt, bevor er auf dieses Ergebnis wartet, oder der Aufrufer wartet sofort auf das Ergebnis.   Der Ereignishandler wartet auf `AccessTheWebAsync`, und `AccessTheWebAsync` wartet auf `GetStringAsync`.  
  
7. `GetStringAsync` wird abgeschlossen und erstellt ein Zeichenfolgenergebnis. Das Zeichenfolgenergebnis wird von dem Aufruf `GetStringAsync` nicht auf die Art zurückgegeben, die Sie möglicherweise erwarten. (Beachten Sie, dass die Methode bereits in Schritt 3 eine Aufgabe zurückgegeben hat.) Stattdessen wird das Zeichenfolgenergebnis in dem Task gespeichert, der den Abschluss der Methode darstellt: `getStringTask`. Der await-Operator ruft das Ergebnis von `getStringTask` ab. Die Zuweisungsanweisung weist `urlContents` das abgerufene Ergebnis zu.  
  
8. Wenn `AccessTheWebAsync` über das Zeichenfolgenergebnis verfügt, kann die Methode die Länge der Zeichenfolge berechnen. Dann ist die Arbeit von `AccessTheWebAsync` auch abgeschlossen, und der wartende Ereignishandler kann fortfahren. Im vollständigen Beispiel am Ende des Themas können Sie überprüfen, ob der Ereignishandler den Wert des Längenergebnisses abruft und druckt.    
Wenn die asynchrone Programmierung für Sie neu ist, nehmen Sie sich einen Moment Zeit, um den Unterschied zwischen synchronem und asynchronem Verhalten zu untersuchen. Eine synchrone Methode kehrt zum Aufrufer zurück, wenn ihre Arbeit abgeschlossen ist (Schritt 5). Eine asynchrone Methode hingegen gibt einen Aufgabenwert zurück, wenn die Verarbeitung angehalten wird (Schritt 3 und 6). Wenn die asynchrone Methode schließlich ihre Arbeit abgeschlossen hat, wird die Aufgabe als abgeschlossen markiert und das Ergebnis ggf. in der Aufgabe gespeichert.  
  
Weitere Informationen zur Ablaufsteuerung finden Sie unter [Ablaufsteuerung in asynchronen Programmen (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md).  
  
## <a name="BKMK_APIAsyncMethods"></a> API-Async-Methoden  
 Sie fragen sich möglicherweise, wo Methoden wie `GetStringAsync` zu finden sind, die die asynchrone Programmierung unterstützen. .NET Framework 4.5 oder höher und .NET Core enthalten viele Member, die mit `async` und `await` funktionieren. Sie können sie durch das Suffix „Async“ erkennen, das dem Membernamen und dem Rückgabetyp <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> angefügt wird. Beispielsweise enthält die `System.IO.Stream`-Klasse Methoden wie <xref:System.IO.Stream.CopyToAsync%2A>, <xref:System.IO.Stream.ReadAsync%2A> und <xref:System.IO.Stream.WriteAsync%2A> sowie die synchronen Methoden <xref:System.IO.Stream.CopyTo%2A>, <xref:System.IO.Stream.Read%2A> und <xref:System.IO.Stream.Write%2A>.  
  
 Die Windows-Runtime enthält außerdem viele Methoden, die Sie mit `async` und `await` in Windows-Apps verwenden können. Weitere Informationen finden Sie unter [Threading and async programming](/windows/uwp/threading-async/) (Threading und asynchrone Programmierung) für die UWP-Entwicklung, [Asynchronous programming (Windows Store apps)](https://docs.microsoft.com/previous-versions/windows/apps/hh464924(v=win.10)) (Asynchrone Programmierung für Windows Store-Apps) und [Quickstart: Calling asynchronous APIs in C# or Visual Basic](https://docs.microsoft.com/previous-versions/windows/apps/hh452713(v=win.10)) (Schnellstart: Aufrufen von asynchronen APIs in C# oder Visual Basic), wenn Sie frühere Versionen der Windows-Runtime verwenden.  
  
## <a name="BKMK_Threads"></a> Threads  
Async-Methoden sollen nicht blockierende Vorgänge sein. Ein `await`-Ausdruck in einer asynchronen Methode blockiert den aktuellen Thread nicht, während der abgewartete Task ausgeführt wird. Stattdessen registriert der Ausdruck den Rest der Methode als Fortsetzung und gibt die Steuerung an den Aufrufer der Async-Methode zurück.  
  
Durch die Schlüsselwörter `async` und `await` werden keine zusätzlichen Threads erstellt. Async-Methoden erfordern kein Multithreading, da eine Async-Methode nicht in einem eigenen Thread ausgeführt wird. Die Methode wird im aktuellen Synchronisierungskontext ausgeführt und verwendet Zeit im Thread nur, wenn sie aktiv ist. Sie können <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> zur Verschiebung CPU-gebundener Arbeit in einen Hintergrundthread verwenden, aber ein Hintergrundthread nützt nichts bei einem Prozess, der wartet, dass Ergebnisse zur Verfügung gestellt werden.  
  
Der auf Asynchronie basierende Ansatz der asynchronen Programmierung ist vorhandenen Ansätzen in nahezu jedem Fall vorzuziehen. Insbesondere eignet sich dieser Ansatz besser für E/A-gebundene Vorgänge als die <xref:System.ComponentModel.BackgroundWorker>-Klasse, da der Code einfacher und kein Schutz vor Racebedingungen erforderlich ist. In Kombination mit der Methode <xref:System.Threading.Tasks.Task.Run%2A?displayProperty=nameWithType> eignet sich asynchrone Programmierung besser für CPU-gebundene Vorgänge als <xref:System.ComponentModel.BackgroundWorker>, da die asynchrone Programmierung Koordinationsdetails der Ausführung des Codes von der Arbeit trennt, die `Task.Run` an den Threadpool überträgt.  
  
## <a name="BKMK_AsyncandAwait"></a> „async“ und „await“  
 Wenn Sie angeben, dass eine Methode eine asynchrone Methode ist, indem Sie den [async](../../../../csharp/language-reference/keywords/async.md)-Modifizierer verwenden, aktivieren Sie die folgenden zwei Funktionen.  
  
-   Die markierte async-Methode kann [await](../../../../csharp/language-reference/keywords/await.md) verwenden, um Unterbrechungspunkte festzulegen. Der `await`-Operator informiert den Compiler, dass die Async-Methode erst über diesen Punkt hinaus fortgesetzt werden kann, wenn der abgewartete asynchrone Prozess abgeschlossen ist. In der Zwischenzeit kehrt die Steuerung zum Aufrufer der Async-Methode zurück.  
  
     Die Unterbrechung einer async-Methode an einem `await`-Ausdruck stellt keine Beendigung der Methode dar, und `finally`-Blöcke werden nicht ausgeführt.  
  
-   Auf die markierte Async-Methode können auch Methoden warten, die sie aufrufen.  
  
Eine async-Methode enthält in der Regel eine oder mehrere Vorkommen eines `await`-Operators, die Abwesenheit von `await`-Ausdrücken verursacht jedoch keinen Compilerfehler. Wenn eine async-Methode keinen `await`-Operator verwendet, um einen Unterbrechungspunkt zu markieren, wird die Methode ungeachtet des `async`-Modifizierers wie eine synchrone Methode ausgeführt. Der Compiler gibt eine Warnung für solche Methoden aus.  
  
 `async` und `await` sind kontextbezogene Schlüsselwörter. Weitere Informationen und Beispiele finden Sie unter den folgenden Themen:  
  
-   [async](../../../../csharp/language-reference/keywords/async.md)  
  
-   [await](../../../../csharp/language-reference/keywords/await.md)  
  
## <a name="BKMK_ReturnTypesandParameters"></a> Rückgabetypen und Parameter  
Eine async-Methode gibt normalerweise eine <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück. Innerhalb einer async-Methode wird ein `await`-Operator auf einen Task angewendet, der in einem Aufruf einer anderen async-Methode zurückgegeben wurde.  
  
Geben Sie <xref:System.Threading.Tasks.Task%601> als Rückgabetyp an, wenn die Methode eine [`return`](../../../../csharp/language-reference/keywords/return.md)-Anweisung enthält, die einen Operanden vom Typ `TResult` angibt. 
  
Sie verwenden <xref:System.Threading.Tasks.Task> als Rückgabetyp, wenn die Methode keine return-Anweisung hat oder über eine return-Anweisung verfügt, die keinen Operanden zurückgibt.  

Ab C# 7.0 können Sie auch andere Rückgabetypen angeben, vorausgesetzt, der Typ enthält eine `GetAwaiter`-Methode. <xref:System.Threading.Tasks.ValueTask%601> ist ein Beispiel eines solchen Typs. Er ist im NuGet-Paket [System.Threading.Tasks.Extension](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) verfügbar.
  
 Im folgenden Beispiel wird gezeigt, wie Sie eine Methode deklarieren und aufrufen, die <xref:System.Threading.Tasks.Task%601> oder <xref:System.Threading.Tasks.Task> zurückgibt.  
  
```csharp  
// Signature specifies Task<TResult>  
async Task<int> GetTaskOfTResultAsync()  
{  
    int hours = 0;  
    await Task.Delay(0);  
    // Return statement specifies an integer result.  
    return hours;  
}  
  
// Calls to GetTaskOfTResultAsync  
Task<int> returnedTaskTResult = GetTaskOfTResultAsync();  
int intResult = await returnedTaskTResult;  
// or, in a single statement  
int intResult = await GetTaskOfTResultAsync();  
  
// Signature specifies Task  
async Task GetTaskAsync()  
{  
    await Task.Delay(0);  
    // The method has no return statement.    
}  
  
// Calls to GetTaskAsync  
Task returnedTask = GetTaskAsync();  
await returnedTask;  
// or, in a single statement  
await GetTaskAsync();  
```  
  
Jede zurückgegebene Aufgabe stellt derzeit ausgeführte Arbeit dar. Eine Aufgabe kapselt Informationen über den Zustand des asynchronen Prozesses und schließlich entweder das Endergebnis aus dem Prozess oder die Ausnahme, die durch einen Prozessfehler verursacht wird.  
  
Eine asynchrone Methode kann auch den Rückgabetyp `void` aufweisen. Dieser Rückgabetyp wird hauptsächlich zum Definieren von Ereignishandlern verwendet, wobei ein `void`-Rückgabetyp erforderlich ist. Asynchrone Ereignishandler dienen häufig als Ausgangspunkt für asynchrone Programme.  
  
Eine async-Methode, die eine `void`-Rückgabetyp aufweist, kann nicht abgewartet werden, und der Aufrufer einer Methode zur Rückgabe von „void“ kann keine Ausnahmen abfangen, die von der Methode ausgelöst werden.  
  
Eine asynchrone Methode kann keine [in](../../../../csharp/language-reference/keywords/in-parameter-modifier.md)-, [ref](../../../../csharp/language-reference/keywords/ref.md)- oder [out](../../../../csharp/language-reference/keywords/out-parameter-modifier.md)-Parameter deklarieren. Die Methode kann jedoch Methoden aufrufen, die solche Parameter aufweisen. Genauso kann eine async-Methode keinen Wert nach Verweis zurückgeben, obwohl sie Methoden mit ref-Rückgabewerten aufrufen kann. 
  
Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md). Weitere Informationen zum Abfangen von Ausnahmen in async-Methoden finden Sie unter [try-catch](../../../../csharp/language-reference/keywords/try-catch.md). 
  
Asynchrone APIs in der Windows-Runtime-Programmierung weisen einen der folgenden Rückgabetypen auf, die Tasks ähnlich sind:  
  
-   <xref:Windows.Foundation.IAsyncOperation%601>Dies entspricht <xref:System.Threading.Tasks.Task%601>  
  
-   <xref:Windows.Foundation.IAsyncAction>Dies entspricht <xref:System.Threading.Tasks.Task>  
  
-   <xref:Windows.Foundation.IAsyncActionWithProgress%601>  
  
-   <xref:Windows.Foundation.IAsyncOperationWithProgress%602>  

## <a name="BKMK_NamingConvention"></a> Benennungskonvention  
Üblicherweise sollten die Namen von Methoden, die in der Regel awaitable-Typen zurückgeben (wie `Task`, `Task<T>`, `ValueTask`, `ValueTask<T>`), auf „Async“ enden. Methoden, die einen asynchronen Vorgang starten, aber keinen awaitable-Typ zurückgeben, sollten nicht auf „Async“ enden, sondern mit „Begin“, „Start“ oder einem ähnlichen Verb beginnen, sodass eindeutig ist, dass diese Methode nicht das Ergebnis des Vorgangs zurückgibt bzw. auslöst.
  
 Sie können die Konvention ignorieren, wenn ein Ereignis, eine Basisklasse oder ein Schnittstellenvertrag einen anderen Namen vorsieht. Beispielsweise sollten Sie allgemeine Ereignishandler wie `Button1_Click` nicht umbenennen.  
  
## <a name="BKMK_RelatedTopics"></a> Verwandte Themen und Beispiele (Visual Studio)  
  
|Titel|Beschreibung|Beispiel|  
|-----------|-----------------|------------|  
|[Exemplarische Vorgehensweise: Zugreifen auf das Web mit „async“ und „await“ (C#)](../../../../csharp/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)|Zeigt, wie eine synchrone WPF-Projektmappe in eine asynchrone WPF-Projektmappe konvertiert wird. Die Anwendung lädt eine Reihe von Websites herunter.|[Asynchrones Beispiel: Exemplarische Vorgehensweise für den Zugriff auf das Web](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f)|  
|[Vorgehensweise: Erweitern der asynchronen exemplarischen Vorgehensweise mit Task.WhenAll (C#)](../../../../csharp/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)|Fügt der vorherigen exemplarischen Vorgehensweise <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> hinzu. Bei Verwendung von `WhenAll` werden alle Downloads gleichzeitig gestartet.||  
|[Vorgehensweise: Paralleles Erstellen mehrerer Webanforderungen mit „async“ und „await“ (C#)](../../../../csharp/programming-guide/concepts/async/how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await.md)|Veranschaulicht, wie mehrere Aufgaben gleichzeitig gestartet werden.|[Asynchrones Beispiel: Paralleles Erstellen mehrerer Webanforderungen](https://code.msdn.microsoft.com/Async-Make-Multiple-Web-49adb82e)|  
|[Asynchrone Rückgabetypen (C#)](../../../../csharp/programming-guide/concepts/async/async-return-types.md)|Veranschaulicht die Typen, die Async-Methoden zurückgeben können und erklärt, wann die einzelnen Typen geeignet sind.||  
|[Ablaufsteuerung in asynchronen Programmen (C#)](../../../../csharp/programming-guide/concepts/async/control-flow-in-async-programs.md)|Verfolgt die Ablaufsteuerung ausführlich durch eine Reihenfolge von await-Ausdrücken in einem asynchronen Programm.|[Asynchrones Beispiel: Ablaufsteuerung in asynchronen Programmen](https://code.msdn.microsoft.com/Async-Sample-Control-Flow-5c804fc0)|  
|[Feinabstimmung der Async-Anwendung (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)|Zeigt, wie die folgenden Funktionen der asynchronen Lösung hinzugefügt werden:<br /><br /> -   [Eine asynchrone Aufgabe oder Aufgabenliste abbrechen (C#)](../../../../csharp/programming-guide/concepts/async/cancel-an-async-task-or-a-list-of-tasks.md)<br />-   [Asynchrone Aufgaben nach einer Zeitperiode abbrechen (C#)](../../../../csharp/programming-guide/concepts/async/cancel-async-tasks-after-a-period-of-time.md)<br />-   [Verbleibende asynchrone Aufgaben nach Abschluss einer Aufgabe abbrechen (C#)](../../../../csharp/programming-guide/concepts/async/cancel-remaining-async-tasks-after-one-is-complete.md)<br />-   [Mehrere asynchrone Aufgaben starten und nach Abschluss verarbeiten (C#)](../../../../csharp/programming-guide/concepts/async/start-multiple-async-tasks-and-process-them-as-they-complete.md)|[Asynchrones Beispiel: Optimierung Ihrer Anwendung](https://code.msdn.microsoft.com/Async-Fine-Tuning-Your-a676abea)|  
|[Ablaufinvarianz in asynchronen Anwendungen (C#)](../../../../csharp/programming-guide/concepts/async/handling-reentrancy-in-async-apps.md)|Zeigt, wie Fälle gehandhabt werden, in denen ein aktiver asynchroner Vorgang neu gestartet wird, während er ausgeführt wird.||  
|[WhenAny: Überbrückung zwischen .NET Framework und Windows-Runtime](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/jj635140(v=vs.120))|Zeigt, wie zwischen Aufgabentypen in .NET Framework und „IAsyncOperations“ in [!INCLUDE[wrt](~/includes/wrt-md.md)] überbrückt wird, sodass <xref:System.Threading.Tasks.Task.WhenAny%2A> mit einer [!INCLUDE[wrt](~/includes/wrt-md.md)]-Methode verwendet werden kann.|[Asynchrones Beispiel: Überbrückung zwischen .NET und Windows-Runtime („AsTask“ und „WhenAny“)](https://code.msdn.microsoft.com/Async-Sample-Bridging-d6a2f739)|  
|Asynchroner Abbruch: Überbrückung zwischen .NET Framework und Windows-Runtime|Zeigt, wie zwischen Aufgabentypen in .NET Framework und „IAsyncOperations“ in [!INCLUDE[wrt](~/includes/wrt-md.md)] überbrückt wird, sodass <xref:System.Threading.CancellationTokenSource> mit einer [!INCLUDE[wrt](~/includes/wrt-md.md)]-Methode verwendet werden kann.|[Asynchrones Beispiel: Überbrückung zwischen .NET und Windows-Runtime („AsTask“ und „Cancellation“)](https://code.msdn.microsoft.com/Async-Sample-Bridging-9479eca3)|  
|[Using Async for File Access (C#) (Verwenden von Async für Dateizugriff (C#))](../../../../csharp/programming-guide/concepts/async/using-async-for-file-access.md)|Listet die Vorteile der Verwendung von "async" und "await" für den Zugriff auf Dateien auf und veranschaulicht sie.||  
|[Aufgabenbasiertes asynchrones Muster (TAP, Task-based Asynchronous Pattern)](../../../../standard/asynchronous-programming-patterns/task-based-asynchronous-pattern-tap.md)|Beschreibt ein neues Muster für Asynchronie in .NET Framework. Das Muster basiert auf den <xref:System.Threading.Tasks.Task>- und <xref:System.Threading.Tasks.Task%601>-Typen.||  
|[Videos zur asynchronen Programmierung auf Channel 9](https://channel9.msdn.com/search?term=async%20&type=All#pubDate=year&ch9Search&lang-en=en)|Stellt Links zu einer Vielzahl von Videos über die asynchrone Programmierung bereit.||  
  
## <a name="BKMK_CompleteExample"></a> Vollständiges Beispiel  
 Beim folgenden Code handelt es sich um die Datei „MainWindow.xaml.cs“ aus der WPF-Anwendung (Windows Presentation Foundation), die in diesem Thema erläutert wird. Sie können das Beispiel hier herunterladen: [Async Sample: Example from "Asynchronous Programming with Async and Await"](https://code.msdn.microsoft.com/Async-Sample-Example-from-9b9f505c) (Asynchrones Beispiel aus der asynchronen Programmierung mit „async“ und „await“).  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http;  
using System.Net.Http;  
  
namespace AsyncFirstExample  
{  
    public partial class MainWindow : Window  
    {  
        // Mark the event handler with async so you can use await in it.  
        private async void StartButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Call and await separately.  
            //Task<int> getLengthTask = AccessTheWebAsync();  
            //// You can do independent work here.  
            //int contentLength = await getLengthTask;  
  
            int contentLength = await AccessTheWebAsync();  
  
            resultsTextBox.Text +=
                $"\r\nLength of the downloaded string: {contentLength}.\r\n";
        }  
  
        // Three things to note in the signature:  
        //  - The method has an async modifier.   
        //  - The return type is Task or Task<T>. (See "Return Types" section.)  
        //    Here, it is Task<int> because the return statement returns an integer.  
        //  - The method name ends in "Async."  
        async Task<int> AccessTheWebAsync()  
        {   
            // You need to add a reference to System.Net.Http to declare client.  
            using (HttpClient client = new HttpClient())  
            {  
                    // GetStringAsync returns a Task<string>. That means that when you await the  
                    // task you'll get a string (urlContents).  
                    Task<string> getStringTask = client.GetStringAsync("https://docs.microsoft.com");  
  
                    // You can do work here that doesn't rely on the string from GetStringAsync.  
                    DoIndependentWork();  
  
                    // The await operator suspends AccessTheWebAsync.  
                    //  - AccessTheWebAsync can't continue until getStringTask is complete.  
                    //  - Meanwhile, control returns to the caller of AccessTheWebAsync.  
                    //  - Control resumes here when getStringTask is complete.   
                    //  - The await operator then retrieves the string result from getStringTask.  
                    string urlContents = await getStringTask;  
  
                    // The return statement specifies an integer result.  
                    // Any methods that are awaiting AccessTheWebAsync retrieve the length value.  
                    return urlContents.Length;  
            }  
        }  
  
        void DoIndependentWork()  
        {  
            resultsTextBox.Text += "Working . . . . . . .\r\n";  
        }  
    }  
}  
  
// Sample Output:  
  
// Working . . . . . . .  
  
// Length of the downloaded string: 25035.  
```  
  
## <a name="see-also"></a>Siehe auch

- [async](../../../../csharp/language-reference/keywords/async.md)
- [await](../../../../csharp/language-reference/keywords/await.md)
- [Asynchrone Programmierung](../../../../csharp/async.md)
- [async (Übersicht)](../../../../standard/async.md)
