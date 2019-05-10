---
title: Leerzeichen in XML-Literalen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: 903928087d5ad9c51040ba6bf65639f44d8c7dd6
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64627440"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>Leerzeichen in XML-Literalen (Visual Basic)
Visual Basic-Compiler bindet nur die signifikanten Leerzeichen aus einem XML-Literal, wenn er erstellt eine [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt. Bedeutungslose Leerzeichen sind nicht integriert.  
  
## <a name="significant-and-insignificant-white-space"></a>Erhebliche und nicht signifikanter Leerraum  
 Leerzeichen in XML-Literale sind wichtig, nur in drei Bereichen:  
  
- Wenn sie sich in einem Attributwert sind.  
  
- Wenn sie sind Bestandteil des Textinhalts eines Elements und der Text auch andere Zeichen enthält.  
  
- Wenn sie sich in einem eingebetteten Ausdruck für den Textinhalt des Elements sind.  
  
 Andernfalls der Compiler behandelt Leerzeichen als nicht signifikant und schließt Sie nicht der [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Objekt für das Literal.  
  
 Um nicht signifikante Leerraum in einem XML-literal einschließen möchten, verwenden Sie einen eingebetteten Ausdruck an, der ein Zeichenfolgenliteral mit den Leerraum enthält.  
  
> [!NOTE]
>  Wenn die `xml:space` Attribut wird in einem XML-Elementliteral angezeigt, in Visual Basic-Compiler umfasst das Attribut in der <xref:System.Xml.Linq.XElement> -Objekt, aber das Hinzufügen dieses Attributs ändert sich nicht darauf aus, wie der Compiler Leerzeichen behandelt.  
  
## <a name="examples"></a>Beispiele  
 Das folgende Beispiel enthält zwei XML-Elemente, äußere und innere. Beide Elemente enthalten Leerzeichen in ihren Textinhalt. Der Leerraum in das äußere Element ist unbedeutend, da sie nur aus Leerzeichen und ein XML-Element enthält. Der Leerraum in das innere Element ist von Bedeutung, da er Leerzeichen und Text enthält.  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 Wenn ausführen, zeigt dieser Code den folgenden Text ein.  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
