---
title: Bereich von Standardnamespaces in Visual Basic
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: af868454c9d1dce7d8bf5a1902f64eff8db8780c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710358"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a>Bereich von Standardnamespaces in Visual Basic
Standardnamespaces, wie sie in der XML-Struktur dargestellt werden, befinden sich bei Abfragen nicht innerhalb des gültigen Bereichs. Bei XML, das sich in einem Standardnamespace befindet, müssen Sie weiterhin eine <xref:System.Xml.Linq.XNamespace>-Variable deklarieren und diese Variable mit dem lokalen Namen kombinieren, um einen qualifizierten Namen zu erhalten, der in der Abfrage verwendet werden kann.  
  
 Eines der häufigsten Probleme beim Abfragen von XML-Strukturen besteht darin, dass der Entwickler, wenn die XML-Struktur einen Standardnamespace besitzt, mitunter die Abfrage so schreibt, als würde sich das XML nicht in einem Namespace befinden.  
  
 Der erste Satz von Beispielen in diesem Thema zeigt eine typische Vorgehensweise, bei der XML in einem Standardnamespace geladen, dann jedoch nicht ordnungsgemäß abgefragt wird.  
  
 Der zweite Satz von Beispielen zeigt die notwendigen Korrekturen, die durchgeführt werden müssen, damit XML in einem Namespace abgefragt werden kann.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die ein leeres Resultset zurückgibt.  
  
### <a name="code"></a>Code  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Kommentare  
 Dieses Beispiel liefert das folgende Ergebnis:  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel zeigt die Erstellung von XML in einem Namespace und eine Abfrage, die korrekt codiert ist.  
  
 Im Gegensatz zum falsch codierten Beispiel oben besteht der richtige Ansatz bei der Verwendung Visual Basic darin, einen globalen Standard Namespace zu deklarieren und zu initialisieren. Dadurch werden alle XML-Eigenschaften im Standardnamespace platziert. Weitere Änderungen sind für das ordnungsgemäße Funktionieren des Beispiels nicht erforderlich.  
  
### <a name="code"></a>Code  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a>Kommentare  
 Dieses Beispiel liefert das folgende Ergebnis:  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Namespaces (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)
