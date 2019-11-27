---
title: 'Gewusst wie: Zugriff auf untergeordnete XML-Elemente'
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332342"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>Gewusst wie: Zugriff auf untergeordnete XML-Elemente (Visual Basic)
Dieses Beispiel zeigt, wie Sie mithilfe einer untergeordneten Achsen Eigenschaft auf alle untergeordneten XML-Elemente zugreifen können, die einen angegebenen Namen in einem XML-Element aufweisen. Insbesondere wird die <xref:System.Xml.Linq.XElement.Value%2A>-Eigenschaft verwendet, um den Wert des ersten Elements in der Auflistung zu erhalten, das die Eigenschaft `name` untergeordneter Achse zurückgibt. Die Eigenschaft `name` untergeordneter Achse ruft alle untergeordneten Elemente mit dem Namen `phone` im `contact` Objekt ab. In diesem Beispiel wird auch die Eigenschaft `phone` untergeordneter Achse verwendet, um auf alle untergeordneten Elemente mit dem Namen `phone` zuzugreifen, die im `contact`-Objekt enthalten sind.  
  
## <a name="example"></a>Beispiel  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Dieses Beispiel erfordert Folgendes:  
  
- Einen Verweis auf den <xref:System.Xml.Linq>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [Untergeordnete XML-Achseneigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML-Value-Eigenschaft](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [Zugreifen auf XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
