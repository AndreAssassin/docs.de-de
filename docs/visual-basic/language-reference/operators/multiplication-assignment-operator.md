---
title: '*=-Operator (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 47d3239af6ff24501e6babc23c0db4103c477796
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701072"
---
# <a name="-operator-visual-basic"></a>*=-Operator (Visual Basic)
Multipliziert den Wert einer Variablen oder Eigenschaft mit dem Wert eines Ausdrucks und weist das Ergebnis der Variablen oder Eigenschaft zu.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>Teile  
 `variableorproperty`  
 Erforderlich. Eine beliebige numerische Variable oder Eigenschaft.  
  
 `expression`  
 Erforderlich. Ein beliebiger numerischer Ausdruck.  
  
## <a name="remarks"></a>Hinweise  
 Das Element auf der linken Seite des `*=`-Operators kann eine einfache skalare Variable, eine Eigenschaft oder ein Element eines Arrays sein. Die Variable oder [Eigenschaft darf nicht schreibgeschützt sein.](../../../visual-basic/language-reference/modifiers/readonly.md)  
  
 Der `*=`-Operator multipliziert zuerst den Wert des Ausdrucks (auf der rechten Seite des Operators) durch den Wert der Variablen oder Eigenschaft (auf der linken Seite des Operators). Der-Operator weist dann das Ergebnis dieses Vorgangs der Variablen oder der Eigenschaft zu.  
  
## <a name="overloading"></a>Überladen  
 Der [Operator *](../../../visual-basic/language-reference/operators/multiplication-operator.md) kann *überladen*werden. das bedeutet, dass eine Klasse oder Struktur das Verhalten neu definieren kann, wenn ein Operand den Typ dieser Klasse oder Struktur aufweist. Das Überladen des `*`-Operators wirkt sich auf das Verhalten des `*=`-Operators aus. Wenn Ihr Code `*=` für eine Klasse oder Struktur verwendet, die `*` überlastet, stellen Sie sicher, dass Sie das neu definierte Verhalten verstehen. Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der `*=`-Operator verwendet, um eine `Integer`-Variable mit einer Sekunde zu multiplizieren und das Ergebnis der ersten Variablen zuzuweisen.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- [*-Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [Zuweisungsoperatoren](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [Arithmetische Operatoren](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
