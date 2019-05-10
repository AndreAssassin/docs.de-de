---
title: 'Vorgehensweise: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- embedded expressions [Visual Basic]
- XML literals [Visual Basic], embedded expressions
ms.assetid: 75016fad-0141-42de-8564-5051be29487e
ms.openlocfilehash: ca80ac666e8676e4e58a9741b00125c0126570fa
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598376"
---
# <a name="how-to-embed-expressions-in-xml-literals-visual-basic"></a>Vorgehensweise: Einbetten von Ausdrücken in XML-Literalen (Visual Basic)
Sie können XML-Literale kombinieren, mit eingebetteten Ausdrücken erstellen Sie eine XML-Dokument, Fragment oder Element, das zur Laufzeit erstellten Inhalte enthält. Die folgenden Beispiele veranschaulichen, wie Sie eingebettete Ausdrücke, die zum Auffüllen der Inhalt des Elements, Attribute und Elementnamen zur Laufzeit verwendet wird.  
  
 Die Syntax für einen eingebetteten Ausdruck ist `<%=` `exp` `%>`, dies ist die gleiche Syntax, die [!INCLUDE[vstecasp](~/includes/vstecasp-md.md)] verwendet. Weitere Informationen finden Sie unter [eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md).  
  
 Sie können auch die [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] APIs zum Erstellen [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekte. Weitere Informationen finden Sie unter <xref:System.Xml.Linq.XElement>.  
  
## <a name="procedures"></a>Verfahren  
  
#### <a name="to-insert-text-as-element-content"></a>Zum Einfügen von Text als Inhalt des Elements  
  
- Das folgende Beispiel zeigt, wie Sie den Text einfügen, der in enthalten ist das `contactName` Variable zwischen den öffnenden und schließenden Name-Elementen.  
  
     [!code-vb[VbXMLSamples#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#39)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-as-an-attribute-value"></a>Zum Einfügen von Text als Attributwert  
  
- Das folgende Beispiel zeigt, wie Sie den Text einfügen, der in enthalten ist das `phoneType` Variable als Wert für die `type` Attribut.  
  
     [!code-vb[VbXMLSamples#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#40)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <phone type="home">206-555-0144</phone>  
    </contact>  
    ```  
  
#### <a name="to-insert-text-for-an-element-name"></a>Zum Einfügen von Text für einen Elementnamen  
  
- Das folgende Beispiel zeigt, wie Sie den Text einfügen, der in enthalten ist das `elementName` -Variable als den Namen eines Elements.  
  
     Beim Erstellen von Elementen mit diesem Verfahren, müssen Sie sie schließen die \</ > Tag.  
  
     [!code-vb[VbXMLSamples#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples14.vb#41)]  
  
     Dieses Beispiel erzeugt die folgende Ausgabe:  
  
    ```xml  
    <contact>  
      <name>Patrick Hines</name>  
    </contact>  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Erstellen von XML-Literalen](../../../../visual-basic/programming-guide/language-features/xml/how-to-create-xml-literals.md)
- [Eingebettete Ausdrücke in XML](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
