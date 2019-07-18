---
title: Zugreifen auf XML in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756961"
---
# <a name="accessing-xml-in-visual-basic"></a>Zugreifen auf XML in Visual Basic
Visual Basic bietet XML-Achseneigenschaften für den Zugriff auf und die berichtsnavigation [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] Strukturen. Diese Eigenschaften verwenden eine spezielle Syntax, um Elemente und Attribute zugreifen, indem Sie die XML-Namen angeben können.  
  
 Die folgende Tabelle enthält die Sprachfunktionen, die Ihnen den Zugriff auf XML-Elemente und Attribute in Visual Basic ermöglichen.  
  
### <a name="xml-axis-properties"></a>XML-Achseneigenschaften  
  
|Beschreibung der Eigenschaft|Beispiel|Beschreibung|  
|--------------------------|-------------|-----------------|  
|*Child-Achse*|`contact.<phone>`|Ruft alle `phone` Elemente, die untergeordneten Elemente sind die `contact` Element.|  
|*Attribute-Achse*|`phone.@type`|Ruft alle `type` Attribute der `phone` Element.|  
|*descendant-Achse*|`contacts...<name>`|Ruft alle `name` Bestandteile der `contacts` Element, unabhängig davon, wie viele Ebenen in der Hierarchie, die sie auftreten.|  
|*erweiterungsindizierer*|`contacts...<name>(0)`|Ruft das erste `name` Element aus der Sequenz.|  
|*value*|`contacts...<name>.Value`|Ruft eine Zeichenfolgendarstellung des ersten Objekts in der Sequenz oder `Nothing` , wenn die Sequenz leer ist.|  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Access-XML-Nachfolgerelemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 Zeigt, wie für eine descendant-Achse-Eigenschaft den Zugriff auf alle XML-Elemente, die einen angegebenen Namen aufweisen und unter einem angegebenen XML-Element enthalten sind.  
  
 [Vorgehensweise: Zugriff auf XML-untergeordnete Elemente](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 Veranschaulicht, wie einer untergeordneten Achseneigenschaft auf alle untergeordneten XML-Elemente, die einen angegebenen Namen in ein XML-Element aufweisen.  
  
 [Vorgehensweise: Die XML-Attribute zuzugreifen](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 Veranschaulicht, wie ein Attributachseneigenschaft zu verwenden, um alle XML-Attribute zuzugreifen, die einen angegebenen Namen in ein XML-Element aufweisen.  
  
 [Vorgehensweise: Deklarieren und Verwenden von XML-Namespace-Präfixe](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 Zeigt, wie ein XML-Namespacepräfix zu deklarieren und zu erstellen und Zugreifen auf XML-Elemente verwenden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [XML-Achseneigenschaften](../../../../visual-basic/language-reference/xml-axis/index.md)  
 Enthält Links zu Abschnitten beschreiben die verschiedenen Eigenschaften der XML-Zugriff.  
  
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 Bietet eine Einführung zur Verwendung [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.  
  
 [Erstellen von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 Bietet eine Einführung in die Verwendung von XML-Literale in Visual Basic.  
  
 [Bearbeiten von XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 Enthält Links zu Abschnitten zum Laden und Ändern von XML in Visual Basic.  
  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 Enthält Links zu Abschnitten, die beschreibt, wie mit [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.
