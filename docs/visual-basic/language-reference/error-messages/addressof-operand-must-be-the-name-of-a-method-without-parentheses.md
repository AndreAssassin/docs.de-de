---
title: Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).
ms.date: 07/20/2015
f1_keywords:
- vbc30577
- bc30577
helpviewer_keywords:
- BC30577
ms.assetid: c2c55640-5c61-4e66-97a4-4322020c6001
ms.openlocfilehash: b8c67c2390df91c6a4af66e020365544e6bf369b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61751630"
---
# <a name="addressof-operand-must-be-the-name-of-a-method-without-parentheses"></a>Der AddressOf-Operand muss dem Namen einer Methode entsprechen (ohne Klammern).
Der `AddressOf` -Operator erstellt eine Delegatinstanz einer Prozedur, die auf eine bestimmte Prozedur verweist. Die Syntax lautet wie folgt aus.  
  
 `AddressOf` `procedurename`  
  
 Runden Klammern Folgendes Argument `AddressOf`, wo keine erforderlich sind.  
  
 **Fehler-ID:** BC30577  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Entfernen Sie die Klammern um die folgenden Argument `AddressOf`.  
  
2. Stellen Sie sicher, dass das Argument den Namen einer Methode ist.  
  
## <a name="see-also"></a>Siehe auch

- [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)
- [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)
