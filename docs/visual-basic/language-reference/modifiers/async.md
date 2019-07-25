---
title: Async (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Async
helpviewer_keywords:
- Async [Visual Basic]
- Async keyword [Visual Basic]
ms.assetid: 1be8b4b5-9689-41b5-bd33-b906bfd53bc5
ms.openlocfilehash: cf2c62878e8902afa9455c789d41393b73110172
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68434058"
---
# <a name="async-visual-basic"></a>Async (Visual Basic)
Der `Async` -Modifizierer gibt an, dass die von ihm modifizierte Methode oder der [Lambda-Ausdruck](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md) asynchron ist. Solche Methoden werden als *Async-Methoden*bezeichnet.  
  
 Mit einer Async-Methode können Aufgaben mit potenziell langer Laufzeit auf einfache Weise ausgeführt werden, ohne den Thread des Aufrufers zu blockieren. Der Aufrufer einer Async-Methode kann seine Arbeit fortsetzen, ohne auf die Fertigstellung der Async-Methode zu warten.  
  
> [!NOTE]
>  Die Schlüsselwörter `Async` und `Await` wurden in Visual Studio 2012 eingeführt. Eine Einführung in die asynchrone Programmierung finden Sie unter [asynchrone Programmierung mit Async und warten](../../../visual-basic/programming-guide/concepts/async/index.md).  
  
 Im folgenden Beispiel wird die Struktur einer asynchronen Methode veranschaulicht. Laut Konvention enden die Namen von asynchrone Methoden mit "Async."  
  
```vb  
Public Async Function ExampleMethodAsync() As Task(Of Integer)  
    ' . . .  
  
    ' At the Await expression, execution in this method is suspended and,  
    ' if AwaitedProcessAsync has not already finished, control returns  
    ' to the caller of ExampleMethodAsync. When the awaited task is   
    ' completed, this method resumes execution.   
    Dim exampleInt As Integer = Await AwaitedProcessAsync()  
  
    ' . . .  
  
    ' The return statement completes the task. Any method that is   
    ' awaiting ExampleMethodAsync can now get the integer result.  
    Return exampleInt  
End Function  
```  
  
 In der Regel enthält eine durch das `Async` -Schlüsselwort geänderte Methode mindestens einen [Erwartungs Ausdruck oder](../../../visual-basic/language-reference/modifiers/async.md) eine-Anweisung. Die Methode wird bis zum ersten `Await`-Ausdruck synchron ausgeführt. Dann wird die Methode angehalten, bis die erwartete Aufgabe abgeschlossen ist. In der Zwischenzeit wird die Steuerung zum Aufrufer der Methode zurückgegeben. Wenn die Methode keinen `Await`-Ausdruck oder keine Await-Anweisung enthält, wird die Methode nicht angehalten und wie eine synchrone Methode ausgeführt. Mit einer Compilerwarnung werden Sie auf alle Async-Methoden hingewiesen, die kein `Await` enthalten, da dies möglicherweise auf einen Fehler hindeutet. Weitere Informationen finden Sie unter [Compilerfehler](../../../visual-basic/language-reference/error-messages/because-this-call-is-not-awaited-the-current-method-continues-to-run.md).  
  
 Das Schlüsselwort `Async` ist ein nicht reserviertes Schlüsselwort. Es ist ein Schlüsselwort, wenn eine Methode oder ein Lambdaausdruck geändert wird. In allen anderen Kontexten wird es als Bezeichner interpretiert.  
  
## <a name="return-types"></a>Rückgabetypen  
 Eine Async-Methode ist entweder eine [unter](../../../visual-basic/programming-guide/language-features/procedures/sub-procedures.md) Prozedur oder eine [Funktions](../../../visual-basic/programming-guide/language-features/procedures/function-procedures.md) Prozedur, die den <xref:System.Threading.Tasks.Task> Rückgabetyp oder <xref:System.Threading.Tasks.Task%601>aufweist. Die-Methode kann keine [ByRef](../../../visual-basic/language-reference/modifiers/byref.md) -Parameter deklarieren.  
  
 Sie geben `Task(Of TResult)` für den Rückgabetyp einer Async-Methode an, wenn die [Return](../../../visual-basic/language-reference/statements/return-statement.md) -Anweisung der Methode einen Operanden vom Typ TResult aufweist. `Task` wird verwendet, falls kein sinnvoller Wert zurückgegeben wird, wenn die Methode abgeschlossen ist. Das bedeutet, dass ein Aufruf der Methode eine `Task` zurückgibt, aber wenn die `Task` abgeschlossen ist, erzeugt eine `Await`-Anweisung, die `Task` erwartet, keinen Ergebniswert.  
  
 Asynchrone Unterroutinen werden hauptsächlich verwendet, um Ereignishandler zu definieren, in denen eine `Sub` Prozedur erforderlich ist. Der Aufrufer einer Async-Unterroutine kann diese nicht erwarten und keine Ausnahmen auffangen, die von der Methode ausgelöst werden.  
  
 Weitere Informationen und Beispiele finden Sie unter [Asynchrone Rückgabetypen](../../../visual-basic/programming-guide/concepts/async/async-return-types.md).  
  
## <a name="example"></a>Beispiel  
 In den folgenden Beispielen werden ein asynchroner Ereignishandler, ein asynchroner Lambda-Ausdruck und eine asynchrone Methode dargestellt. Ein vollständiges Beispiel, das diese Elemente verwendet, [finden Sie unter Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md). Sie können den Code der exemplarischen Vorgehensweise unter [Codebeispiele für Entwickler](https://code.msdn.microsoft.com/Async-Sample-Accessing-the-9c10497f) herunterladen.  
  
```vb  
' An event handler must be a Sub procedure.  
Async Sub button1_Click(sender As Object, e As RoutedEventArgs) Handles button1.Click  
    textBox1.Clear()  
    ' SumPageSizesAsync is a method that returns a Task.  
    Await SumPageSizesAsync()  
    textBox1.Text = vbCrLf & "Control returned to button1_Click."  
End Sub  
  
' The following async lambda expression creates an equivalent anonymous  
' event handler.  
AddHandler button1.Click, Async Sub(sender, e)  
                              textBox1.Clear()  
                              ' SumPageSizesAsync is a method that returns a Task.  
                              Await SumPageSizesAsync()  
                              textBox1.Text = vbCrLf & "Control returned to button1_Click."  
                          End Sub  
  
' The following async method returns a Task(Of T).  
' A typical call awaits the Byte array result:  
'      Dim result As Byte() = Await GetURLContents("https://msdn.com")  
Private Async Function GetURLContentsAsync(url As String) As Task(Of Byte())  
  
    ' The downloaded resource ends up in the variable named content.  
    Dim content = New MemoryStream()  
  
    ' Initialize an HttpWebRequest for the current URL.  
    Dim webReq = CType(WebRequest.Create(url), HttpWebRequest)  
  
    ' Send the request to the Internet resource and wait for  
    ' the response.  
    Using response As WebResponse = Await webReq.GetResponseAsync()  
        ' Get the data stream that is associated with the specified URL.  
        Using responseStream As Stream = response.GetResponseStream()  
            ' Read the bytes in responseStream and copy them to content.    
            ' CopyToAsync returns a Task, not a Task<T>.  
            Await responseStream.CopyToAsync(content)  
        End Using  
    End Using  
  
    ' Return the result as a byte array.  
    Return content.ToArray()  
End Function  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.AsyncStateMachineAttribute>
- [Await-Operator](../../../visual-basic/language-reference/operators/await-operator.md)
- [Asynchrone Programmierung mit Async und Await](../../../visual-basic/programming-guide/concepts/async/index.md)
- [Exemplarische Vorgehensweise: Zugreifen auf das Web mit Async und Await](../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)
