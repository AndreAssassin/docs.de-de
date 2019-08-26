---
title: Validierung eines XML-Schemas (XSD) mit "XmlSchemaSet"
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
ms.assetid: 359b10eb-ec05-4cc6-ac96-c2b060afc4de
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bdcfe785d6f5f81d721acd45eebb580b08b2d14
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916076"
---
# <a name="xml-schema-xsd-validation-with-xmlschemaset"></a>Validierung eines XML-Schemas (XSD) mit "XmlSchemaSet"
XML-Dokumente können anhand eines XSD-Schemas (XML Schema Definition Language) in einem <xref:System.Xml.Schema.XmlSchemaSet> validiert werden.  
  
## <a name="validating-xml-documents"></a>Validierung von XML-Dokumenten  
 XML-Dokumente werden von der <xref:System.Xml.XmlReader.Create%2A>-Methode der <xref:System.Xml.XmlReader>-Klasse validiert. Wenn Sie ein XML-Dokument validieren möchten, müssen Sie ein <xref:System.Xml.XmlReaderSettings>-Objekt erstellen, das ein XSD-Schema (XML Schema Definition) enthält, mit dem das XML-Dokument validiert wird.  
  
> [!NOTE]
> Der <xref:System.Xml.Schema>-Namespace enthält Erweiterungsmethoden, die bei Verwendung von [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) und [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md) ein einfaches Validieren einer XML-Struktur anhand einer XSD-Datei ermöglichen. Weitere Informationen zum Validieren von XML-Dokumenten mit LINQ to XML finden Sie unter [How to: Überprüfen mit XSD (LINQ to XML) (C#)](../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md) und [ Überprüfen mit XSD (LINQ to XML) (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md).  
  
 Um einem <xref:System.Xml.Schema.XmlSchemaSet> ein einzelnes Schema oder mehrere Schemas (als <xref:System.Xml.Schema.XmlSchemaSet>) hinzuzufügen, muss eines von beiden als Parameter an die <xref:System.Xml.Schema.XmlSchemaSet.Add%2A>-Methode des <xref:System.Xml.Schema.XmlSchemaSet> übergeben werden. Beachten Sie beim Validieren von Dokumenten, dass der Namespace des Dokuments dem Zielnamespace des Schemas im Schemasatz entsprechen muss.  
  
 Es folgt ein Beispiel für ein XML-Dokument.  
  
 [!code-xml[XSDInference Examples#5](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xml#5)]  
  
 Im Folgenden wird das Schema dargestellt, das das XML-Dokument validiert.  
  
 [!code-xml[XSDInference Examples#6](../../../../samples/snippets/xml/VS_Snippets_Data/XSDInference Examples/XML/contosoBooks.xsd#6)]  
  
 Im folgenden Codebeispiel wird das oben genannte Schema der <xref:System.Xml.Schema.XmlSchemaSet><xref:System.Xml.XmlReaderSettings.Schemas%2A>-Eigenschaft des <xref:System.Xml.XmlReaderSettings>-Objekts hinzugefügt. Das <xref:System.Xml.XmlReaderSettings>-Objekt wird als Parameter an die <xref:System.Xml.XmlReader.Create%2A>-Methode des <xref:System.Xml.XmlReader>-Objekts übergeben, das das oben genannte XML-Dokument validiert.  
  
 Die <xref:System.Xml.XmlReaderSettings.ValidationType%2A>-Eigenschaft des <xref:System.Xml.XmlReaderSettings>-Objekts wird auf `Schema` festgelegt, um die Validierung des XML-Dokuments durch die <xref:System.Xml.XmlReader.Create%2A>-Methode des <xref:System.Xml.XmlReader>-Objekts zu erzwingen. Dem <xref:System.Xml.Schema.ValidationEventHandler>-Objekt wird ein <xref:System.Xml.XmlReaderSettings> hinzugefügt, der alle <xref:System.Xml.Schema.XmlSeverityType.Warning>- oder <xref:System.Xml.Schema.XmlSeverityType.Error>-Ereignisse behandelt, die von während der Validierung des XML-Dokuments und des Schemas gefundenen Fehlern ausgelöst werden.  
  
 [!code-cpp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/cpp/VS_Snippets_Data/XmlSchemaSetOverall Example/CPP/xmlschemasetexample.cpp#1)]
 [!code-csharp[XmlSchemaSetOverall Example#1](../../../../samples/snippets/csharp/VS_Snippets_Data/XmlSchemaSetOverall Example/CS/xmlschemasetexample.cs#1)]
 [!code-vb[XmlSchemaSetOverall Example#1](../../../../samples/snippets/visualbasic/VS_Snippets_Data/XmlSchemaSetOverall Example/VB/xmlschemasetexample.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [„XmlSchemaSet“ zur Kompilierung von Schemas](../../../../docs/standard/data/xml/xmlschemaset-for-schema-compilation.md)
- [Arbeiten mit XML-Schemata](../../../../docs/standard/data/xml/working-with-xml-schemas.md)
