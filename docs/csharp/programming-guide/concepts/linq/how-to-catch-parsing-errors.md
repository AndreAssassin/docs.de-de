---
title: 'Vorgehensweise: Erfassen von Fehlern bei der Analyse (C#)'
ms.date: 07/20/2015
ms.assetid: bfb612d4-5605-48ef-8c93-915cf9d5dcfb
ms.openlocfilehash: 094485b24cdccee7898bd0344aa7c100e26bf4e9
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487486"
---
# <a name="how-to-catch-parsing-errors-c"></a>Vorgehensweise: Erfassen von Fehlern bei der Analyse (C#)
In diesem Thema wird gezeigt, wie nicht wohlgeformter oder ungültiger XML-Code erkannt werden kann.  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] wird mithilfe von <xref:System.Xml.XmlReader> implementiert. Wenn nicht wohlgeformter oder ungültiger XML-Code an [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] übergeben wird, löst die zugrunde liegende <xref:System.Xml.XmlReader>-Klasse eine Ausnahme aus. Die verschiedenen Methoden, die XML analysieren, z.B. <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, fangen die Ausnahme nicht ab. Die Ausnahme kann dann von Ihrer Anwendung abgefangen werden.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code versucht, ungültiges XML zu analysieren:  
  
```csharp  
try {  
    XElement contacts = XElement.Parse(  
        @"<Contacts>  
            <Contact>  
                <Name>Jim Wilson</Name>  
            </Contact>  
          </Contcts>");  
  
    Console.WriteLine(contacts);  
}  
catch (System.Xml.XmlException e)  
{  
    Console.WriteLine(e.Message);  
}  
```  
  
 Wenn Sie diesen Code ausführen, wird die folgende Ausnahme ausgelöst:  
  
```  
The 'Contacts' start tag on line 1 does not match the end tag of 'Contcts'. Line 5, position 13.  
```  
  
 Weitere Informationen zu den Ausnahmen, von denen Sie ausgehen können, dass sie von den Methoden <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>, <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType> und <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType> ausgelöst werden, finden Sie in der <xref:System.Xml.XmlReader>-Dokumentation.  
  