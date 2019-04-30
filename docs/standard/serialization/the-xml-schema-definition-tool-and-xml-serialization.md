---
title: Das XML Schema Definition-Tool und die XML-Serialisierung
ms.date: 03/30/2017
helpviewer_keywords:
- Xsd.exe
- XML serialization, XML Schema Definition tool
- XML Schema Definition tool
- serialization, XML Schema Definition tool
ms.assetid: 3c03f855-f931-47ff-bbc6-50c0367a16e4
ms.openlocfilehash: 4c950d84cc95c20c2ae85340a2987ea51bed9570
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62028290"
---
# <a name="the-xml-schema-definition-tool-and-xml-serialization"></a>Das XML Schema Definition-Tool und die XML-Serialisierung
Das XML Schema Definition-Tool ([XML Schema Definition Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)) wird zusammen mit den .NET Framework-Tools als Bestandteil des Windows® Software Development Kit (SDK) installiert. Das Tool ist hauptsächlich für zwei Zwecke vorgesehen:  
  
- Um C#- oder Visual Basic-Klassendateien zu erstellen, die einer bestimmten XML-Schema-Definition (XSD) entsprechen. Das Tool übernimmt ein XML-Schema als Argument und gibt eine Datei mit einer Gruppe von Klassen aus, die dem Schema entsprechen, wenn sie mit <xref:System.Xml.Serialization.XmlSerializer> serialisiert werden. Weitere Informationen zur Verwendung mit dem Tool zum Generieren von Klassen, die einem bestimmten Schema entsprechen, finden Sie unter [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
- So generieren Sie ein XML-Schemadokument aus einer DLL-Datei oder EXE-Datei Um das Schema einer Gruppe von Dateien darzustellen, die Sie erstellt haben oder die mit Attributen verändert wurde, übergeben Sie dem Tool die DLL- oder EXE-Datei als Argument, um das XML-Schema zu generieren. Informationen dazu, wie Sie das Tool zu verwenden, um ein XML-Schemadokument aus einer Reihe von Klassen zu generieren, finden Sie unter [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md).  
  
 Weitere Informationen zu diesem und anderen Tools finden Sie unter [Tools](../../../docs/framework/tools/index.md). Informationen zu den Optionen in diesem Tool finden Sie unter [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataSet>
- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [XML Schema Definition-Tool (Xsd.exe)](../../../docs/standard/serialization/xml-schema-definition-tool-xsd-exe.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Vorgehensweise: Deserialisieren eines Objekts](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
- [Vorgehensweise: Verwenden Sie die XML-Schema Definition-Tool Klassen und XML-Schemadokumente generieren](../../../docs/standard/serialization/xml-schema-def-tool-gen.md)
- [Bindungsunterstützung für XML-Schema](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sh1e66zd(v=vs.100))
