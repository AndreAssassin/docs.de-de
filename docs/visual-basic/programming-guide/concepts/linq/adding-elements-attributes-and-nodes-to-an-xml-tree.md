---
title: Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
ms.openlocfilehash: 35d3bdb27342dd7a871778ad4749db4d6849bd60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814315"
---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a>Hinzufügen von Elementen, Attributen und Knoten zu einer XML-Struktur (Visual Basic)
Sie können einer vorhandenen XML-Struktur Inhalt (Elemente, Attribute, Kommentare, Verarbeitungsanweisungen, Text und CDATA) hinzufügen.  
  
## <a name="methods-for-adding-content"></a>Methoden zum Hinzufügen von Inhalt  
 Die folgenden Methoden fügen einem <xref:System.Xml.Linq.XElement> oder einem <xref:System.Xml.Linq.XDocument> untergeordneten Inhalt hinzu:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.Add%2A>|Fügt Inhalt am Ende des untergeordneten Inhalts des <xref:System.Xml.Linq.XContainer> hinzu.|  
|<xref:System.Xml.Linq.XContainer.AddFirst%2A>|Fügt Inhalt vor dem untergeordneten Inhalt des <xref:System.Xml.Linq.XContainer> hinzu.|  
  
 Die folgenden Methoden fügen Inhalt als nebengeordnete Knoten eines <xref:System.Xml.Linq.XNode> hinzu. Der Knoten, dem Sie am häufigsten nebengeordneten Inhalt hinzufügen, ist <xref:System.Xml.Linq.XElement>, obwohl Sie gültigen nebengeordneten Inhalt auch anderen Knotentypen hinzufügen können, z. B. <xref:System.Xml.Linq.XText> oder <xref:System.Xml.Linq.XComment>.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.AddAfterSelf%2A>|Fügt Inhalt nach dem <xref:System.Xml.Linq.XNode> hinzu.|  
|<xref:System.Xml.Linq.XNode.AddBeforeSelf%2A>|Fügt Inhalt vor dem <xref:System.Xml.Linq.XNode> hinzu.|  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel erstellt zwei XML-Strukturen und ändert dann eine der beiden Strukturen:  
  
### <a name="code"></a>Code  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
```  
  
### <a name="comments"></a>Kommentare  
 Dieser Code erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Ändern von XML-Bäumen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
