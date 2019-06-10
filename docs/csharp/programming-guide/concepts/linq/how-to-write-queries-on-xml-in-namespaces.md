---
title: 'Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)'
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: d33ecc22d8eb6ea4a08b56fbed6b6b437a5e3216
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66484633"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a>Vorgehensweise: Schreiben von Abfragen für XML in Namespaces (C#)
Wenn Sie eine Abfrage für XML in einem Namespace schreiben möchten, müssen Sie <xref:System.Xml.Linq.XName>-Objekte verwenden, die den richtigen Namespace enthalten.  
  
 In C# besteht der am häufigsten verwendete Ansatz darin, einen <xref:System.Xml.Linq.XNamespace> mit einer Zeichenfolge zu initialisieren, die den URI enthält, und dann mithilfe der Additionsoperatorüberladung den Namespace mit dem lokalen Namen zu kombinieren.  
  
 Die erste Gruppe der Beispiele in diesem Thema zeigt,wie Sie eine XML-Struktur in einem Standardnamespace erstellen. Die zweite Gruppe der Beispiele zeigt, wie Sie eine XML-Struktur in einem Namespace mit einem Präfix erstellen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Standardnamespace befindet. Anschließend ruft das Beispiel eine Auflistung der Elemente ab.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a>Beispiel  
 In C# schreiben Sie Abfragen auf die gleiche Weise. Dies gilt unabhängig davon, ob Sie Abfragen für eine XML-Struktur schreiben, die einen Namespace mit einem Präfix verwendet, oder für eine XML-Struktur mit einem Standardnamespace.  
  
 Das folgende Beispiel erstellt eine XML-Struktur, die sich in einem Namespace mit einem Präfix befindet. Anschließend ruft das Beispiel eine Auflistung der Elemente ab.  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a>Siehe auch

- [Working with XML Namespaces (C#) (Arbeiten mit XML-Namespaces (C#))](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)
