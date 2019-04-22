---
title: Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
ms.date: 07/20/2015
f1_keywords:
- bc36550
- vbc36550
helpviewer_keywords:
- BC36550
ms.assetid: 4387a51f-733c-45d7-abdb-eb64d4f51078
ms.openlocfilehash: a4561359e4d7cb0f6ebe44a5deb09b3374556ed8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58826183"
---
# <a name="extension-attribute-can-be-applied-only-to-module-sub-or-function-declarations"></a>Das Extension-Attribut darf nur in Module-, Sub- oder Function-Deklarationen verwendet werden
Die einzige Möglichkeit zum Erweitern von eines Datentyps in Visual Basic ist eine Erweiterungsmethode in einem Standardmodul definieren. Die Erweiterungsmethode möglich ein `Sub` Prozedur oder ein `Function` Verfahren. Alle Erweiterungsmethoden müssen mit dem Extension-Attribut markiert werden `<Extension()>`, aus der <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> Namespace. Optional kann ein Modul, eine Erweiterungsmethode enthält, auf die gleiche Weise gekennzeichnet werden. Keine andere Verwendung der das Extension-Attribut ist ungültig.  
  
 **Fehler-ID:** BC36550  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie das Extension-Attribut.  
  
-   Entwerfen Sie die Erweiterung als eine Methode, in ein einschließendes Modul definiert.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine `Print` -Methode für die `String` -Datentyp.  
  
```  
Imports StringUtility  
Imports System.Runtime.CompilerServices  
Namespace StringUtility  
    <Extension()>   
    Module StringExtensions  
        <Extension()>   
        Public Sub Print (ByVal str As String)  
            Console.WriteLine(str)  
        End Sub  
    End Module  
End Namespace  
```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Attribute](../../../visual-basic/programming-guide/concepts/attributes/index.md)
- [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
