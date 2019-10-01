---
title: Teilausdruck (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic], sub expression
- Sub Expression [Visual Basic]
- subroutines [Visual Basic], sub expressions
ms.assetid: 36b6bfd1-6539-4d8f-a5eb-6541a745ffde
ms.openlocfilehash: 2330b410f54b54d8f6cb7d8ad6f9b39a3f4d31bc
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701336"
---
# <a name="sub-expression-visual-basic"></a>Teilausdruck (Visual Basic)
Deklariert die Parameter und den Code, die einen Lambda Ausdruck für die Unterroutine definieren.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Sub ( [ parameterlist ] ) statement  
- or -  
Sub ( [ parameterlist ] )  
  [ statements ]  
End Sub  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`parameterlist`|Optional. Eine Liste der Namen der lokalen Variablen, die die Parameter der Prozedur darstellen. Die Klammern müssen auch dann vorhanden sein, wenn die Liste leer ist. Weitere Informationen finden Sie unter [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md).|  
|`statement`|Erforderlich. Eine einzelne Anweisung.|  
|`statements`|Erforderlich. Eine Liste von-Anweisungen.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Lambda-Ausdruck* ist eine Unterroutine, die keinen Namen hat und eine oder mehrere-Anweisungen ausführt. Sie können einen Lambda-Ausdruck überall dort verwenden, wo Sie einen Delegattyp verwenden können, außer als Argument für `RemoveHandler`. Weitere Informationen zu Delegaten und zur Verwendung von Lambda-Ausdrücken mit Delegaten finden Sie unter [delegatanweisung](../../../visual-basic/language-reference/statements/delegate-statement.md) und [gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).  
  
## <a name="lambda-expression-syntax"></a>Lambdaausdruckssyntax  
 Die Syntax eines Lambda-Ausdrucks ähnelt der einer Standard Unterroutine. Die Unterschiede lauten wie folgt:  
  
- Ein Lambda-Ausdruck weist keinen Namen auf.  
  
- Ein Lambda-Ausdruck kann keinen Modifizierer aufweisen, wie z. b. `Overloads` oder `Overrides`.  
  
- Der Text eines einzeiligen Lambda Ausdrucks muss eine-Anweisung und kein Ausdruck sein. Der Text kann aus einem aufzurufenden Teil Prozedur-, aber keinem Aufrufvorgang einer Funktions Prozedur bestehen.  
  
- In einem Lambda-Ausdruck müssen entweder alle Parameter über bestimmte Datentypen verfügen, oder alle Parameter müssen abgeleitet werden.  
  
- Optionale Parameter und `ParamArray`-Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
- Generische Parameter sind in Lambda-Ausdrücken nicht zulässig.  
  
## <a name="example"></a>Beispiel  
 Im folgenden finden Sie ein Beispiel für einen Lambda-Ausdruck, der einen Wert in die Konsole schreibt. Das Beispiel zeigt die einzeilige und die mehrzeilige Lambda-Ausdruckssyntax für eine Unterroutine. Weitere Beispiele finden Sie unter [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbVbalrLambdas#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Lambda-Ausdrücke](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
- [Anweisungen](../../../visual-basic/programming-guide/language-features/statements.md)
- [Gelockerte Delegatenkonvertierung](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
