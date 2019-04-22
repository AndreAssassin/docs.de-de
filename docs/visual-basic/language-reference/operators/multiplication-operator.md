---
title: '* -Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*
helpviewer_keywords:
- arithmetic operators [Visual Basic], multiplication
- operators [Visual Basic], multiplication
- '* operator [Visual Basic]'
- multiplication operator [Visual Basic], syntax
- math operators [Visual Basic]
ms.assetid: 2b210382-99da-4195-89ba-b1d06f5e89ad
ms.openlocfilehash: 09b95585325b05c0b7925c4c1c9e123f45791e10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828952"
---
# <a name="-operator-visual-basic"></a>*-Operator (Visual Basic)
Multipliziert zwei Zahlen miteinander.  
  
## <a name="syntax"></a>Syntax  
  
```  
number1 * number2  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`number1`|Erforderlich. Ein beliebiger numerischer Ausdruck.|  
|`number2`|Erforderlich. Ein beliebiger numerischer Ausdruck.|  
  
## <a name="result"></a>Ergebnis  
 Das Ergebnis ist das Produkt der `number1` und `number2`.  
  
## <a name="supported-types"></a>Unterstützte Typen  
 Alle numerischen Typen, einschließlich der Typen ohne Vorzeichen und Gleitkommatypen und `Decimal`.  
  
## <a name="remarks"></a>Hinweise  
 Der Datentyp des Ergebnisses, hängt von den Typen der Operanden ab. Die folgende Tabelle zeigt, wie der Datentyp des Ergebnisses bestimmt wird.  
  
|Datentypen der Operanden|Der Ergebnisdatentyp|  
|---|---|  
|Beide Ausdrücke sind ganzzahlige Datentypen ([SByte](../../../visual-basic/language-reference/data-types/sbyte-data-type.md), [Byte](../../../visual-basic/language-reference/data-types/byte-data-type.md), [kurze](../../../visual-basic/language-reference/data-types/short-data-type.md), [UShort](../../../visual-basic/language-reference/data-types/ushort-data-type.md), [Ganzzahl](../../../visual-basic/language-reference/data-types/integer-data-type.md), [UInteger](../../../visual-basic/language-reference/data-types/uinteger-data-type.md), [lange](../../../visual-basic/language-reference/data-types/long-data-type.md), [ULong](../../../visual-basic/language-reference/data-types/ulong-data-type.md))|Einen numerischen Datentyp aufweisen, die für die Datentypen der entsprechenden `number1` und `number2`. Finden Sie in den Tabellen "Ganzzahlarithmetik" in [Datentypen von Operatorergebnissen Daten](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md).|  
|Beide Ausdrücke sind [Decimal](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|`Decimal`|  
|Beide Ausdrücke sind [einzelne](../../../visual-basic/language-reference/data-types/single-data-type.md)|`Single`|  
|Einer der Ausdrücke ist ein Gleitkomma-Datentyp (`Single` oder [doppelte](../../../visual-basic/language-reference/data-types/double-data-type.md)) jedoch nicht beides `Single` (Hinweis `Decimal` ist kein Gleitkommadatentyp)|`Double`|  
  
 Wenn ein Ausdruck ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird er als 0 (null) behandelt.  
  
## <a name="overloading"></a>Überladen  
 Die `*` Operator möglich *überladen*, was bedeutet, dass eine Klasse oder Struktur sein Verhalten definieren kann, wenn ein Operand den Typ der Klasse oder Struktur hat. Wenn Ihr Code dieser Operator für diese eine Klasse oder Struktur verwendet, achten Sie darauf, dass Sie verstehen, dass das neu definierte Verhalten. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `*` Operator zum Multiplizieren zweier Zahlen. Das Ergebnis ist das Produkt der beiden Operanden.  
  
 [!code-vb[VbVbalrOperators#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [* =-Operator](../../../visual-basic/language-reference/operators/multiplication-assignment-operator.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Arithmetische Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
