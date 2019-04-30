---
title: Kovarianz und Kontravarianz (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
ms.openlocfilehash: 241b8f5864b6e9b3e1caddde25d032a24e4d0bb7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022012"
---
# <a name="covariance-and-contravariance-visual-basic"></a>Kovarianz und Kontravarianz (Visual Basic)
Kovarianz und Kontravarianz in Visual Basic ermöglichen die implizite Referenzkonvertierung für Arraytypen, Delegattypen und generische Typargumente. Die Kovarianz behält die Zuweisungskompatibilität bei und die Kontravarianz kehrt sie um.  
  
 Der folgende Code veranschaulicht den Unterschied zwischen Zuweisungskompatibilität, Kovarianz und Kontravarianz.  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 Die Kovarianz für Arrays ermöglicht die implizite Konvertierung eines Arrays mit einem stärker abgeleiteten Typ zu einem Array mit einem schwächer abgeleiteten Typ. Dieser Vorgang ist jedoch nicht typsicher, wie im folgenden Codebeispiel gezeigt wird.  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 Die Unterstützung von Kovarianz und Kontravarianz für Methodengruppen ermöglicht es, Methodensignaturen mit Delegattypen abzugleichen. Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz). Weitere Informationen finden Sie unter [Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Using Variance in Delegates (Visual Basic) (Verwenden von Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
 Im folgenden Codebeispiel wird die Unterstützung von Methodengruppen durch Kovarianz und Kontravarianz veranschaulicht.  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 In .NET Framework 4 oder höher, wird Visual Basic unterstützt die Kovarianz und Kontravarianz in generischen Schnittstellen und Delegaten und ermöglicht die implizite Konvertierung von generischen Typparametern. Weitere Informationen finden Sie unter [Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) und [Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
 Das folgende Codebeispiel zeigt die implizite Verweiskonvertierung bei generischen Schnittstellen.  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 Generische Schnittstellen oder Delegate werden als *variant* bezeichnet, wenn deren generische Parameter als kovariant oder kontravariant deklariert sind. Visual Basic ermöglicht es Ihnen, eigene variante Schnittstellen oder Delegate zu erstellen. Weitere Informationen finden Sie unter [Creating Variant Generic Interfaces (Visual Basic) (Erstellen von varianten generischen Schnittstellen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) und [Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|Erläutert Ko- und Kontravarianz in generischen Schnittstellen und enthält eine Liste der Varianten generischen Schnittstellen in .NET Framework.|  
|[Creating Variant Generic Interfaces (Visual Basic) (Erstellen varianter generischer Schnittstellen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|Zeigt, wie benutzerdefinierte variante Schnittstellen erstellt werden.|  
|[Using Variance in Interfaces for Generic Collections (Visual Basic) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei <xref:System.Collections.Generic.IEnumerable%601>- und <xref:System.IComparable%601>-Schnittstellen bei der Wiederverwendung Ihres Codes helfen kann.|  
|[Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|Erläutert Ko- und Kontravarianz in generischen und nicht generischen Delegaten und stellt eine Liste von varianten generischen Delegaten im .NET Framework bereit.|  
|[Using Variance in Delegates (Visual Basic) (Verwenden von Varianz in Delegaten (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz in nicht generischen Delegaten verwendet werden kann, um Methodensignaturen mit Delegattypen abzugleichen.|  
|[Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|Zeigt, wie die Unterstützung durch Kovarianz und Kontravarianz bei `Func`- und `Action`-Delegaten bei der Wiederverwendung Ihres Codes helfen kann.|
