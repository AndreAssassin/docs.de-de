---
title: Optional (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Optional
- vb.optional
helpviewer_keywords:
- Optional keyword [Visual Basic], contexts
- Optional keyword [Visual Basic]
ms.assetid: 4571ce88-a539-4115-b230-54eb277c6aa7
ms.openlocfilehash: 40605d4843bfccf9d2819b3ec6f2ef65f9e9cf9a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661324"
---
# <a name="optional-visual-basic"></a>Optional (Visual Basic)
Gibt an, dass ein Prozedurargument beim Aufrufen der Prozedur ausgelassen werden kann.  
  
## <a name="remarks"></a>Hinweise  
 Für jeden optionalen Parameter verwenden müssen Sie einen konstanten Ausdruck als Standardwert dieses Parameters angeben. Wenn der Ausdruck ergibt [nichts](../../../visual-basic/language-reference/nothing.md), wird der Standardwert des Datentyps Wert als den Standardwert des Parameters verwendet.  
  
 Wenn die Parameterliste einen optionalen Parameter enthält, muss jeder Parameter, die darauf folgt ebenfalls optional sein.  
  
 Der `Optional`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
> [!NOTE]
>  Beim Aufrufen einer Prozedur mit oder ohne optionale Parameter können Sie die Argumente nach Position oder anhand des Namens übergeben. Weitere Informationen finden Sie unter [übergeben von Argumenten nach Position und Name](../../../visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name.md).  
  
> [!NOTE]
>  Sie können auch eine Prozedur mit optionalen Parametern definieren, indem mithilfe der Überladung. Wenn Sie einen optionalen Parameter verfügen, können Sie zwei überladene Versionen der Prozedur, eines, das der Parameter akzeptiert und eine, die nicht definieren. Weitere Informationen finden Sie unter [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine Prozedur mit einem optionalen Parameter.  
  
```  
Public Function FindMatches(ByRef values As List(Of String),  
                            ByVal searchString As String,  
                            Optional ByVal matchCase As Boolean = False) As List(Of String)  
  
    Dim results As IEnumerable(Of String)  
  
    If matchCase Then  
        results = From v In values  
                  Where v.Contains(searchString)  
    Else  
        results = From v In values  
                  Where UCase(v).Contains(UCase(searchString))  
    End If  
  
    Return results.ToList()  
End Function  
```  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie eine Prozedur mit Argumenten, die mit Ihrer Position übergeben und nach Namen übergebenen Argumenten aufgerufen wird. Die Prozedur besitzt zwei optionale Parameter.  
  
 [!code-vb[VbVbalrKeywords#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class8.vb#21)]  
  
## <a name="see-also"></a>Siehe auch

- [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Optionale Parameter](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)
- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
