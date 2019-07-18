---
title: Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen
ms.date: 07/20/2015
f1_keywords:
- vbc42324
- bc42324
helpviewer_keywords:
- BC42324
ms.assetid: b5c2c4bd-3b2a-4a73-aaeb-55728eb03b68
ms.openlocfilehash: 3335da503b6fb9c33e44266997cc945214a3a365
ms.sourcegitcommit: e08b319358a8025cc6aa38737854f7bdb87183d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2019
ms.locfileid: "64913072"
---
# <a name="using-the-iteration-variable-in-a-lambda-expression-may-have-unexpected-results"></a>Die Verwendung der Iterationsvariablen in einem Lambda-Ausdruck kann zu unerwarteten Ergebnissen führen
Verwendung der Iterationsvariablen in einem Lambda-Ausdruck möglicherweise unerwartete Ergebnisse. Stattdessen erstellen Sie eine lokale Variable innerhalb der Schleife aus, und weisen Sie diesem den Wert der Iterationsvariablen.  
  
 Diese Warnung wird angezeigt, wenn Sie eine Schleifeniterationsvariablen in einem Lambda-Ausdruck verwenden, die innerhalb der Schleife deklariert ist. Im folgende Beispiel wird z. B. die Warnung angezeigt.  
  
```vb  
For i As Integer = 1 To 10  
    ' The warning is given for the use of i.  
    Dim exampleFunc As Func(Of Integer) = Function() i  
Next  
```  
  
 Das folgende Beispiel zeigt die unerwarteten Ergebnisse, die auftreten können.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            array1(i) = Function() i  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
 Die `For` Schleife erstellt ein Array von Lambda-Ausdrücken, von denen jeder den Wert der Schleifenvariablen Iteration gibt `i`. Bei der Auswertung die Lambda-Ausdrücke in der `For Each` Schleife möglicherweise erwarten, 0, 1, 2, 3 und 4 angezeigt, die nachfolgenden Werte `i` in die `For` Schleife. Stattdessen sehen Sie den endgültigen Wert der `i` fünfmal angezeigt:  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 `5`  
  
 Standardmäßig ist diese Meldung eine Warnung. Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler-ID:** BC42324  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Weisen Sie den Wert für die Iterationsvariable zu einer lokalen Variablen, und verwenden Sie die lokale Variable im Lambda-Ausdruck.  
  
```vb  
Module Module1  
    Sub Main()  
        Dim array1 As Func(Of Integer)() = New Func(Of Integer)(4) {}  
  
        For i As Integer = 0 To 4  
            Dim j = i  
            array1(i) = Function() j  
        Next  
  
        For Each funcElement In array1  
            System.Console.WriteLine(funcElement())  
        Next  
  
    End Sub  
End Module  
```  
  
## <a name="see-also"></a>Siehe auch

- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
