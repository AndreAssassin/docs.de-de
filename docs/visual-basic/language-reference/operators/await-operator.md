---
title: Await-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Await
helpviewer_keywords:
- Await operator [Visual Basic]
- Await [Visual Basic]
ms.assetid: 6b1ce283-e92b-4ba7-b081-7be7b3d37af9
ms.openlocfilehash: d9d50433e3bc24df7cda137a145ab3f0f0302a1f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58841978"
---
# <a name="await-operator-visual-basic"></a>Await-Operator (Visual Basic)
Sie wenden den Operator `Await` auf einen Operanden in einer asynchronen Methode oder einem Lambda-Ausdruck an, um die Ausführung der Methode anzuhalten, bis die erwartete Aufgabe ausgeführt wurde. Die Aufgabe stellt derzeit ausgeführte Arbeit dar.  
  
 Die Methode in der `Await` wird verwendet, muss ein [Async](../../../visual-basic/language-reference/modifiers/async.md) Modifizierer. Eine solche mit dem `Async`-Modifizierer definierte Methode, die in der Regel mindestens einen `Await`-Ausdruck enthält, wird als *async-Methode* bezeichnet.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt. Eine Einführung in die asynchrone Programmierung, finden Sie unter [asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 In der Regel die Aufgabe, die auf die Sie anwenden der `Await` Operator ist der Rückgabewert eines Aufrufs an eine Methode, die implementiert die [Task-Based Asynchronous Pattern](https://go.microsoft.com/fwlink/?LinkId=204847), d. h. eine <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.  
  
 Im folgenden Code gibt die <xref:System.Net.Http.HttpClient>-Methode <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A>`getContentsTask`, eine `Task(Of Byte())` zurück. Die Aufgabe enthält das Versprechen, das tatsächliche Bytearray zu erzeugen, wenn die Operation abgeschlossen ist. Der Operator `Await` wird auf `getContentsTask` angewendet, um die Ausführung in `SumPageSizesAsync` anzuhalten, bis `getContentsTask` abgeschlossen wurde. In der Zwischenzeit wird die Steuerung wieder an den Aufrufer von `SumPageSizesAsync` übergeben. Wenn `getContentsTask` beendet ist, wird der `Await`-Ausdruck in ein Bytearray ausgewertet.  
  
```vb  
Private Async Function SumPageSizesAsync() As Task  
  
    ' To use the HttpClient type in desktop apps, you must include a using directive and add a   
    ' reference for the System.Net.Http namespace.  
    Dim client As HttpClient = New HttpClient()   
    ' . . .   
    Dim getContentsTask As Task(Of Byte()) = client.GetByteArrayAsync(url)  
    Dim urlContents As Byte() = Await getContentsTask  
  
    ' Equivalently, now that you see how it works, you can write the same thing in a single line.  
    'Dim urlContents As Byte() = Await client.GetByteArrayAsync(url)  
    ' . . .  
End Function  
```  
  
> [!IMPORTANT]
>  Das vollständige Beispiel finden Sie unter [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können das Beispiel aus den [Codebeispielen für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) der Microsoft-Website herunterladen. Das Beispiel befindet sich im AsyncWalkthrough_HttpClient-Projekt.  
  
 Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task(Of TResult)` zurückgibt, ist der Typ des `Await`-Ausdrucks TResult. Wenn `Await` auf das Ergebnis eines Methodenaufrufs angewendet wird, der eine `Task` zurückgibt, gibt der `Await`-Ausdruck keinen Wert zurück. Der Unterschied wird im folgenden Beispiel veranschaulicht.  
  
```vb  
' Await used with a method that returns a Task(Of TResult).  
Dim result As TResult = Await AsyncMethodThatReturnsTaskTResult()  
  
' Await used with a method that returns a Task.  
Await AsyncMethodThatReturnsTask()  
```  
  
 Ein `Await`-Ausdruck oder eine Await-Anweisung blockiert nicht den Thread, auf dem sie ausgeführt wird. Stattdessen wird damit verursacht, dass der Compiler den Rest der asynchronen Methode nach dem `Await`-Ausdruck als Fortsetzung der erwarteten Aufgabe registriert. Die Steuerung wird dann wieder an den Aufrufer der Async-Methode übergeben. Wenn die Aufgabe abgeschlossen ist, löst sie ihre Fortsetzung aus, und die Ausführung der asynchronen Methode wird da fortgesetzt, wo sie angehalten wurde.  
  
 Ein `Await`-Ausdruck kann nur im Text einer unmittelbar einschließenden Methode oder eines Lambda-Ausdrucks auftreten, die oder der durch einen `Async`-Modifizierer gekennzeichnet ist. Der Begriff *"await"* dient als Schlüsselwort nur in diesem Kontext. In anderen Kontexten wird er als Bezeichner interpretiert. In der asynchronen Methode oder einen Lambda-Ausdruck ein `Await` Ausdruck kann nicht in einem Abfrageausdruck auftreten, der `catch` oder `finally` -Block eine [versuchen Sie es... Catch... Schließlich](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md) -Anweisung, in der Steuerelement-Schleifenausdruck der ein `For` oder `For Each` Schleife oder im Text einer [SyncLock](../../../visual-basic/language-reference/statements/synclock-statement.md) Anweisung.  
  
## <a name="exceptions"></a>Ausnahmen  
 Die meisten asynchronen Methoden geben einen <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601> zurück. Die Eigenschaften der zurückgegebenen Aufgabe enthalten Informationen über den Status und Verlauf, z. B. ob die Aufgabe abgeschlossen ist, ob die asynchrone Methode eine Ausnahme verursacht hat oder abgebrochen wurde, und was das Endergebnis ist. Der Operator `Await` greift auf diese Eigenschaften zu.  
  
 Wenn Sie auf eine asynchrone Methode warten, die eine Aufgabe zurückgibt und eine Ausnahme verursacht, löst der Operator `Await` die Ausnahme erneut aus.  
  
 Wenn Sie eine asynchrone Methode erwarten, die eine Aufgabe zurückgibt und abgebrochen wird, löst der Operator `Await` erneut eine <xref:System.OperationCanceledException> aus.  
  
 Eine einzelne Aufgabe, die einen Fehlerzustand aufweist, kann verschiedene Ausnahmen auslösen.  Beispielsweise kann die Aufgabe das Ergebnis eines Aufrufs an <xref:System.Threading.Tasks.Task.WhenAll%2A?displayProperty=nameWithType> sein. Wenn Sie auf eine solche Aufgabe warten, löst die await-Operation nur eine der Ausnahmen erneut aus. Sie können jedoch nicht vorhersagen, welche der Ausnahmen erneut ausgelöst wird.  
  
 Beispiele für die Fehlerbehandlung in asynchronen Methoden finden Sie in [testen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Windows Forms-Beispielen wird die Verwendung von `Await` in einer asynchronen Methode, `WaitAsynchronouslyAsync`, veranschaulicht. Vergleichen Sie das Verhalten der Methode mit dem Verhalten von `WaitSynchronously`. Ohne einen `Await`-Operator wird `WaitSynchronously` trotz der Verwendung des `Async`-Modifizierers in der Definition und in einem Aufruf von <xref:System.Threading.Thread.Sleep%2A?displayProperty=nameWithType> im Text synchron ausgeführt.  
  
```vb  
Private Async Sub Button1_Click(sender As Object, e As EventArgs) Handles Button1.Click  
    ' Call the method that runs asynchronously.  
    Dim result As String = Await WaitAsynchronouslyAsync()  
  
    ' Call the method that runs synchronously.  
    'Dim result As String = Await WaitSynchronously()  
  
    ' Display the result.  
    TextBox1.Text &= result  
End Sub  
  
' The following method runs asynchronously. The UI thread is not  
' blocked during the delay. You can move or resize the Form1 window   
' while Task.Delay is running.  
Public Async Function WaitAsynchronouslyAsync() As Task(Of String)  
    Await Task.Delay(10000)  
    Return "Finished"  
End Function  
  
' The following method runs synchronously, despite the use of Async.  
' You cannot move or resize the Form1 window while Thread.Sleep  
' is running because the UI thread is blocked.  
Public Async Function WaitSynchronously() As Task(Of String)  
    ' Import System.Threading for the Sleep method.  
    Thread.Sleep(10000)  
    Return "Finished"  
End Function  
```  
  
## <a name="see-also"></a>Siehe auch

- [Asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
- [Async](../../../visual-basic/language-reference/modifiers/async.md)
