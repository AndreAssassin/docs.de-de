---
title: Übersicht über die XElement-Klasse (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 52331fcd-6023-4d19-b423-7b24f2d86ded
ms.openlocfilehash: 7fbe1cc484ea3482bc455c161783bd7a4513d0bd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783616"
---
# <a name="xelement-class-overview-visual-basic"></a>Übersicht über die XElement-Klasse (Visual Basic)
Die <xref:System.Xml.Linq.XElement>-Klasse ist eine der wichtigsten Klassen in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]. Sie stellt ein XML-Element dar. Diese Klasse kann zum Erstellen von Elementen, zum Ändern des Inhalts des Elements, zum Hinzufügen, Ändern oder Löschen untergeordneter Elemente, zum Hinzufügen von Attributen zu einem Element oder zum Serialisieren des Inhalts eines Elements in Textform verwendet werden. Die Klasse kann auch mit anderen Klassen in <xref:System.Xml?displayProperty=nameWithType> zusammenarbeiten, wie <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> und <xref:System.Xml.Xsl.XslCompiledTransform>.  
  
## <a name="xelement-functionality"></a>"XElement"-Funktionalität  
 In diesem Thema wird die von der <xref:System.Xml.Linq.XElement>-Klasse bereitgestellte Funktionalität beschrieben.  
  
### <a name="constructing-xml-trees"></a>Konstruieren von XML-Strukturen  
 Für das Konstruieren von XML-Strukturen stehen Ihnen verschiedene Möglichkeiten zur Verfügung. So können Sie z. B. Folgendes tun:  
  
- XML-Strukturen in Code konstruieren Weitere Informationen finden Sie unter [Creating XML Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md).  
  
- XML aus verschiedenen Quellen, wie <xref:System.IO.TextReader>, Textdateien oder Internetadressen (URLs), analysieren Weitere Informationen finden Sie unter [Analysieren von XML (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md).  
  
- einen <xref:System.Xml.XmlReader> verwenden, um die Struktur aufzufüllen Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XNode.ReadFrom%2A>.  
  
- mit der <xref:System.Xml.XmlWriter>-Methode einen Writer erstellen, den Writer an das Modul übergeben und dann den in den <xref:System.Xml.Linq.XContainer.CreateWriter%2A> geschriebenen Inhalt zum Auffüllen der XML-Struktur verwenden, sofern ein Modul vorhanden ist, das Inhalt in einen <xref:System.Xml.XmlWriter> schreiben kann  
  
 Die verbreitetste Variante, eine XML-Struktur zu erstellen, sieht aber wie folgt aus:  
  
```vb  
Dim contacts As XElement = _  
    <Contacts>  
        <Contact>  
            <Name>Patrick Hines</Name>  
            <Phone>206-555-0144</Phone>  
            <Address>  
                <Street1>123 Main St</Street1>  
                <City>Mercer Island</City>  
                <State>WA</State>  
                <Postal>68042</Postal>  
            </Address>  
        </Contact>  
    </Contacts>  
```  
  
 Bei einer weiteren häufig verwendeten Technik zum Erstellen einer XML-Struktur wird die XML-Struktur anhand der Ergebnisse einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage aufgefüllt, wie im folgenden Beispiel dargestellt wird:  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element>1</Element>  
        <Element>2</Element>  
        <Element>3</Element>  
        <Element>4</Element>  
        <Element>5</Element>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child>1</Child>  
        <Child>2</Child>  
        <%= From el In srcTree.Elements() _  
            Where el.Value > 2 _  
            Select el %>  
    </Root>  
Console.WriteLine(xmlTree)  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
### <a name="serializing-xml-trees"></a>Serialisieren von XML-Strukturen  
 Sie können die XML-Struktur in eine <xref:System.IO.File>, in einen <xref:System.IO.TextWriter> oder in einen <xref:System.Xml.XmlWriter> serialisieren.  
  
 Weitere Informationen finden Sie unter [Serialisieren von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md).  
  
### <a name="retrieving-xml-data-via-axis-methods"></a>Abrufen von XML-Daten über Achsenmethoden  
 Mit Achsenmethoden können Sie Attribute, untergeordnete Elemente, Nachfolgerelemente und Vorgängerelemente abrufen. [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen verwenden Achsenmethoden und bieten verschiedene flexible und leistungsstarke Möglichkeiten zum Navigieren durch eine XML-Struktur und zu deren Verarbeitung.  
  
 Weitere Informationen finden Sie unter [LINQ to XML-Achsen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md).  
  
### <a name="querying-xml-trees"></a>Abfragen von XML-Strukturen  
 Sie können [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen schreiben, die Daten aus einer XML-Struktur abrufen.  
  
 Weitere Informationen finden Sie unter [Abfragen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md).  
  
### <a name="modifying-xml-trees"></a>Ändern von XML-Strukturen  
 Sie können ein Element auf unterschiedliche Weise ändern, z. B. durch Ändern seines Inhalts oder seiner Attribute. Sie können ein Element auch aus seinem übergeordneten Element entfernen.  
  
 Weitere Informationen finden Sie unter [Ändern von XML-Bäumen (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md).  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to XML Programming Overview (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
