---
title: 'Vorgehensweise: Deserialisieren eines Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- deserializing objects
- objects, deserializing steps
ms.assetid: 287129c8-035a-4fea-b7b3-4790057ca076
ms.openlocfilehash: e1a960d39319beee1c3c257fcd3ade207de11010
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881140"
---
# <a name="how-to-deserialize-an-object"></a>Vorgehensweise: Deserialisieren eines Objekts
Beim Deserialisieren eines Objekts wird durch das Transportformat festgelegt, ob ein Stream- oder ein Dateiobjekt erstellt wird. Nachdem das Transportformat festgelegt wurde, können Sie je nach Bedarf die <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A>-Methode oder <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode aufrufen.  
  
### <a name="to-deserialize-an-object"></a>So deserialisieren Sie ein Objekt  
  
1. Erstellen Sie ein <xref:System.Xml.Serialization.XmlSerializer>-Objekt unter Verwendung des zu deserialisierenden Objekttyps.  
  
2. Rufen Sie die <xref:System.Xml.Serialization.XmlSerializer.Deserialize%2A>-Methode auf, um ein Replikat des Objekts zu erzeugen. Beim Deserialisieren müssen Sie das zurückgegebene Objekt in den Typ des Originals, umwandeln, wie im folgenden Beispiel gezeigt, die das Objekt aus einer Datei deserialisiert wird (obwohl es auch aus einem Stream deserialisiert werden konnten).  
  
    ```vb  
    Dim myObject As MySerializableClass  
    ' Construct an instance of the XmlSerializer with the type  
    ' of object that is being deserialized.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To read the file, create a FileStream.  
    Dim myFileStream As FileStream = _  
    New FileStream("myFileName.xml", FileMode.Open)  
    ' Call the Deserialize method and cast to the object type.  
    myObject = CType( _  
    mySerializer.Deserialize(myFileStream), MySerializableClass)  
    ```  
  
    ```csharp  
    MySerializableClass myObject;  
    // Construct an instance of the XmlSerializer with the type  
    // of object that is being deserialized.  
    XmlSerializer mySerializer =   
    new XmlSerializer(typeof(MySerializableClass));  
    // To read the file, create a FileStream.  
    FileStream myFileStream =   
    new FileStream("myFileName.xml", FileMode.Open);  
    // Call the Deserialize method and cast to the object type.  
    myObject = (MySerializableClass)   
    mySerializer.Deserialize(myFileStream)  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in die XML-Serialisierung](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [Vorgehensweise: Serialisieren eines Objekts](../../../docs/standard/serialization/how-to-serialize-an-object.md)
