---
title: Implements-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Implements
- Implements
helpviewer_keywords:
- Implements statement [Visual Basic], syntax
- Implements statement [Visual Basic]
- interface implementation [Visual Basic], Implements statement
ms.assetid: 1fafb83f-f55a-4215-8ea9-681e8622613d
ms.openlocfilehash: 1f0c6b052ead303e0b43465dac2067422abc4ef8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61637738"
---
# <a name="implements-statement"></a>Implements-Anweisung
Gibt an, mindestens eine weitere Schnittstellen oder Schnittstellenmember, die in der Klasse implementiert werden müssen oder Strukturdefinition, die in der sie angezeigt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
Implements interfacename [, ...]  
-or-  
Implements interfacename.interfacemember [, ...]  
```  
  
## <a name="parts"></a>Teile  
 `interfacename`  
 Erforderlich. Eine Schnittstelle, deren Eigenschaften, Prozeduren und Ereignisse werden von den entsprechenden Elementen in der Klasse oder Struktur implementiert werden.  
  
 `interfacemember`  
 Erforderlich. Der Member einer Schnittstelle, das implementiert wird.  
  
## <a name="remarks"></a>Hinweise  
 Eine Schnittstelle ist eine Sammlung von Prototypen, die die Member (Eigenschaften, Prozeduren und Ereignisse) darstellen die Schnittstelle kapselt. Schnittstellen enthalten nur die Deklarationen für Member. implementieren diese Member, Klassen und Strukturen. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Die `Implements` Anweisung muss unmittelbar folgen der `Class` oder `Structure` Anweisung.  
  
 Wenn Sie eine Schnittstelle implementieren, müssen Sie alle in der Schnittstelle deklarierten Member implementieren. Das auslassen jedes Element gilt ein Syntaxfehler aufgetreten. Um einen einzelnen Member zu implementieren, geben Sie die [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md) Schlüsselwort (unterscheidet sich von der `Implements` Anweisung) Wenn Sie das Element in der Klasse oder Struktur deklarieren. Weitere Informationen finden Sie unter [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Klassen können [Private](../../../visual-basic/language-reference/modifiers/private.md) Implementierungen von Eigenschaften und Prozeduren, aber diese Member sind nur durch umwandeln, die eine Instanz der implementierenden Klasse in eine Variable deklariert wird, der den Typ der Schnittstelle zugegriffen werden kann.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie mit der `Implements` Anweisung, um die Member einer Schnittstelle zu implementieren. Es definiert eine Schnittstelle, die mit dem Namen `ICustomerInfo` mit einem Ereignis, eine Eigenschaft und einer Prozedur. Die Klasse `customerInfo` implementiert alle in der Schnittstelle definierten Member.  
  
 [!code-vb[VbVbalrStatements#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#33)]  
  
 Beachten Sie, dass die Klasse `customerInfo` verwendet die `Implements` Anweisung in einer separaten Quellcodezeile, um anzugeben, dass die Klasse, alle Member implementiert der `ICustomerInfo` Schnittstelle. Klicken Sie dann auf jedes Element in der Klasse verwendet die `Implements` -Schlüsselwort als Teil der Element-Deklaration, um anzugeben, dass sie diesen Schnittstellenmember implementiert.  
  
## <a name="example"></a>Beispiel  
 Die beiden folgenden Verfahren zeigen, wie Sie die Schnittstelle implementiert, die im vorherigen Beispiel verwenden können. Um die Implementierung zu testen, fügen Sie diese Prozeduren, um Ihr Projekt, und rufen die `testImplements` Verfahren.  
  
 [!code-vb[VbVbalrStatements#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#34)]  
  
## <a name="see-also"></a>Siehe auch

- [Implements](../../../visual-basic/language-reference/statements/implements-clause.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
