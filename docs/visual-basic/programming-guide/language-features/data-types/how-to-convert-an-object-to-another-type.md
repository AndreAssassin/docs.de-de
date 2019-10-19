---
title: 'Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- objects [Visual Basic], converting
ms.assetid: 60cb5fc7-7ba4-4ab5-9c24-480fa12ddcdc
ms.openlocfilehash: 39083fc55d30e24c357ec162a15466f81655f4c8
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582326"
---
# <a name="how-to-convert-an-object-to-another-type-in-visual-basic"></a>Gewusst wie: Konvertieren eines Objekts in einen anderen Typ in Visual Basic
Sie konvertieren eine `Object` Variable in einen anderen Datentyp, indem Sie ein Konvertierungs Schlüsselwort wie die [CType-Funktion](../../../../visual-basic/language-reference/functions/ctype-function.md)verwenden.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Object` Variable in eine `Integer` und eine `String` konvertiert.  
  
```vb  
Public Sub objectConversion(ByVal anObject As Object)  
    Dim anInteger As Integer  
    Dim aString As String  
    anInteger = CType(anObject, Integer)  
    aString = CType(anObject, String)  
End Sub  
```  
  
 Wenn Sie wissen, dass der Inhalt einer `Object` Variablen einen bestimmten Datentyp hat, ist es besser, die Variable in diesen Datentyp zu konvertieren. Wenn Sie die `Object` Variable weiterhin verwenden, werden entweder *Boxing* und *Unboxing* (bei einem Werttyp) oder eine *späte Bindung* (für einen Verweistyp) verursacht. Diese Vorgänge erfordern eine zusätzliche Ausführungszeit und machen die Leistung langsamer.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Einen Verweis auf den <xref:System?displayProperty=nameWithType>-Namespace  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Object>
- [Typkonvertierungen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Implizite und explizite Konvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
- [Konvertierungen zwischen Zeichenfolgen und anderen Typen](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [Arraykonvertierungen](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Datentypen](../../../../visual-basic/language-reference/data-types/index.md)
- [Typkonvertierungsfunktionen](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
