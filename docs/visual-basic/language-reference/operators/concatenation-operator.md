---
title: '&amp;Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: aaa7c1b9ab7f6c920180d97b55c3bdeb23f00e02
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592244"
---
# <a name="amp-operator-visual-basic"></a>&amp;Operator (Visual Basic)
Generiert eine Zeichen folgen Verkettung von zwei Ausdrücken.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Erforderlich. Beliebige `String`-oder `Object`-Variable.  
  
 `expression1`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu `String` erweitert wird.  
  
 `expression2`  
 Erforderlich. Jeder Ausdruck mit einem Datentyp, der zu `String` erweitert wird.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Datentyp von `expression1` oder `expression2` nicht `String` ist, aber auf `String` erweitert wird, wird er in `String` konvertiert. Wenn einer der Datentypen nicht zu `String` erweitert wird, generiert der Compiler einen Fehler.  
  
 Der Datentyp von `result` ist `String`. Wenn ein oder beide Ausdrücke zu [Nothing](../../../visual-basic/language-reference/nothing.md) ausgewertet werden oder den Wert <xref:System.DBNull.Value?displayProperty=nameWithType> aufweisen, werden Sie als Zeichenfolge mit dem Wert "" behandelt.  
  
> [!NOTE]
> Der `&`-Operator kann *überladen*werden. Dies bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Wenn Ihr Code diesen Operator für eine solche Klasse oder Struktur verwendet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
> [!NOTE]
> Das kaufmännische und-Zeichen (&) kann auch zum Identifizieren von Variablen als Typ `Long` verwendet werden. Weitere Informationen finden Sie unter [Typzeichen](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md).  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird der `&`-Operator verwendet, um die Verkettung von Zeichen folgen zu erzwingen. Das Ergebnis ist ein Zeichen folgen Wert, der die Verkettung der beiden Zeichen folgen Operanden darstellt.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>Siehe auch

- [&=-Operator](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [Verkettungsoperatoren](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Verkettungs Operatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
