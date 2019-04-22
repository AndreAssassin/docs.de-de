---
title: Klonen oder Anfügen (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3c3bd105-c9d3-49bd-875b-27ab4e8bc7a3
ms.openlocfilehash: 59ffedfdbb2820683f1e6cc232154688f5c29fc8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832293"
---
# <a name="cloning-vs-attaching-visual-basic"></a>Klonen oder Anfügen (Visual Basic)
Beim Hinzufügen von <xref:System.Xml.Linq.XNode> (inklusive <xref:System.Xml.Linq.XElement>)-Objekten oder <xref:System.Xml.Linq.XAttribute>-Objekten zu einer neuen Struktur werden die Objekte einfach an die XML-Struktur angefügt, falls der neue Inhalt kein übergeordnetes Element besitzt. Wenn der neue Inhalt bereits ein übergeordnetes Element besitzt und Bestandteil einer anderen XML-Struktur ist, wird er geklont. Der neu geklonte Inhalt wird dann an die XML-Struktur angefügt.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt das Verhalten, wenn Sie einer Struktur ein übergeordnetes Element und ein Element ohne übergeordnetes Element hinzufügen:  
  
```vb  
' Create a tree with a child element.  
Dim xmlTree1 As XElement = _  
    <Root>  
        <Child1>1</Child1>  
    </Root>  
  
' Create an element that is not parented.  
Dim child2 As XElement = <Child2>2</Child2>  
  
' Create a tree and add Child1 and Child2 to it.  
Dim xmlTree2 As XElement = _  
    <Root>  
        <%= xmlTree1.<Child1>(0) %>  
        <%= child2 %>  
    </Root>  
  
' Compare Child1 identity.  
Console.WriteLine("Child1 was {0}", _  
    IIf(xmlTree1.Element("Child1") Is xmlTree2.Element("Child1"), _  
    "attached", "cloned"))  
  
' Compare Child2 identity.  
Console.WriteLine("Child2 was {0}", _  
    IIf(child2 Is xmlTree2.Element("Child2"), _  
    "attached", "cloned"))  
```  
  
 Dieses Beispiel erzeugt die folgende Ausgabe:  
  
```  
Child1 was cloned  
Child2 was attached  
```  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von XML-Strukturen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
