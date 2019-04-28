---
title: REM-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3c63c5613b40cb2014c77a0a996e3acb2cc304d4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61783933"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Für erläuternde Hinweise im Quellcode eines Programms verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Teile  
 `comment`  
 Dies ist optional. Der Text eines Kommentars, die Sie einschließen möchten. Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Einfügen einer `REM` Anweisung, die allein in einer Zeile, oder Sie können in einer Zeile, die nach einer anderen Anweisung einfügen. Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein. Wenn sie eine andere Anweisung folgt die `REM` müssen von dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Sie können ein einfaches Anführungszeichen (`'`) anstelle von `REM`. Dies ist "true", gibt an, ob Ihr Kommentar folgt eine weitere Anweisung in der gleichen Zeile oder alleine in einer Zeile.  
  
> [!NOTE]
>  Sie können nicht fortgesetzt werden eine `REM` Anweisung, indem Sie eine Zeilenfortsetzungszeichenfolge (`_`). Sobald ein Kommentar beginnt, untersucht der Compiler nicht die Zeichen für eine besondere Bedeutung. Verwenden Sie für einen mehrzeiligen Kommentar, einen anderen `REM` -Anweisung oder ein Kommentarsymbol (`'`) in jeder Zeile.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die `REM` -Anweisung, die für erläuternde Hinweise in einem Programm verwendet wird. Darüber hinaus wird gezeigt, wie Sie das einfache Anführungszeichen verwendet (`'`) anstelle von `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
