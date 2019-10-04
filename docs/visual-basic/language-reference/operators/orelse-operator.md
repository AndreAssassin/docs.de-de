---
title: OrElse-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- OrElse
- vb.OrElse
helpviewer_keywords:
- short-circuiting
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], disjunction
- short-circuit evaluation
- OrElse operator [Visual Basic]
ms.assetid: 253803d8-05b0-47d7-b213-abd222847779
ms.openlocfilehash: 8290e642db3ec76a931bdd2febe427309457bc86
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835246"
---
# <a name="orelse-operator-visual-basic"></a>OrElse-Operator (Visual Basic)
Führt eine kurze, inklusive logische Disjunktion für zwei Ausdrücke aus.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 OrElse expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression1`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
 `expression2`  
 Erforderlich. Beliebiger `Boolean` -Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Eine logische Operation wird als *Kurzschluss* bezeichnet, wenn der kompilierte Code die Auswertung eines Ausdrucks abhängig vom Ergebnis eines anderen Ausdrucks umgehen kann. Wenn das Ergebnis des ersten ausgewerteten Ausdrucks das Endergebnis des Vorgangs bestimmt, muss der zweite Ausdruck nicht ausgewertet werden, da er das Endergebnis nicht ändern kann. Kurzschluss kann die Leistung verbessern, wenn der umgangen-Ausdruck Komplex ist, oder wenn er Prozedur Aufrufe umfasst.  
  
 Wenn ein oder beide Ausdrücke zu `True` ausgewertet werden, ist `result` `True`. In der folgenden Tabelle wird veranschaulicht, wie `result` bestimmt wird.  
  
|Wenn `expression1` ist|Und `expression2` ist|Der Wert von `result` ist|  
|-------------------------|--------------------------|------------------------------|  
|`True`|(nicht ausgewertet)|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
## <a name="data-types"></a>Datentypen  
 Der `OrElse`-Operator ist nur für den [booleschen Datentyp](../../../visual-basic/language-reference/data-types/boolean-data-type.md)definiert. Visual Basic konvertiert jeden Operanden nach Bedarf in `Boolean`, bevor der Ausdruck ausgewertet wird. Wenn Sie das Ergebnis einem numerischen Typ zuweisen, wird Visual Basic von `Boolean` in diesen Typ konvertiert, sodass `False` `0` und `True` `-1` ist.
Weitere Informationen finden Sie unter [boolesche Typkonvertierungen](../data-types/boolean-data-type.md#type-conversions).
  
## <a name="overloading"></a>Überladen  
 Der [OR-Operator](../../../visual-basic/language-reference/operators/or-operator.md) und der [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md) können *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur ihr Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen der Operatoren `Or` und `IsTrue` wirkt sich auf das Verhalten des Operators `OrElse` aus. Wenn Ihr Code `OrElse` für eine Klasse oder Struktur verwendet, die `Or` und `IsTrue` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `OrElse`-Operator verwendet, um eine logische Disjunktion für zwei Ausdrücke auszuführen. Das Ergebnis ist ein `Boolean`-Wert, der angibt, ob einer der beiden Ausdrücke True ist. Wenn der erste Ausdruck `True` ist, wird der zweite Ausdruck nicht ausgewertet.  
  
 [!code-vb[VbVbalrOperators#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#37)]  
  
 Im vorangehenden Beispiel werden die Ergebnisse `True`, `True` und `False` erstellt. Bei der Berechnung von `firstCheck` wird der zweite Ausdruck nicht ausgewertet, da der erste Wert bereits `True` ist. Der zweite Ausdruck wird jedoch in der Berechnung von `secondCheck` ausgewertet.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `If`... `Then`-Anweisung gezeigt, die zwei Prozedur Aufrufe enthält. Wenn der erste Aufruf `True` zurückgibt, wird die zweite Prozedur nicht aufgerufen. Dies kann zu unerwarteten Ergebnissen führen, wenn die zweite Prozedur wichtige Aufgaben durchführt, die immer ausgeführt werden sollten, wenn dieser Code Abschnitt ausgeführt wird.  
  
 [!code-vb[VbVbalrOperators#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#38)]  
  
## <a name="see-also"></a>Siehe auch

- [Logische/bitweise Operatoren (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Or-Operator](../../../visual-basic/language-reference/operators/or-operator.md)
- [IsTrue-Operator](../../../visual-basic/language-reference/operators/istrue-operator.md)
- [Logische und bitweise Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
