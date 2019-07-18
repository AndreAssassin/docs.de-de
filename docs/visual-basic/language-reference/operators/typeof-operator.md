---
title: TypeOf-Operator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- TypeOf
- vb.TypeOf
helpviewer_keywords:
- types [Visual Basic], compatible
- comparison operators [Visual Basic]
- TypeOf...Is expression
- data types [Visual Basic], compatible
- TypeOf operator [Visual Basic]
- compatible data types [Visual Basic]
ms.assetid: 33f65296-659a-4b9a-9a29-c2a91cff68b2
ms.openlocfilehash: e5cb1ddc130a8b1913f30b0d20d27941005dd9d3
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063253"
---
# <a name="typeof-operator-visual-basic"></a>TypeOf-Operator (Visual Basic)
Überprüft, ob der Laufzeittyp des Ausdrucks Ergebnis kompatiblen Typ ist mit dem angegebenen Typ.
  
## <a name="syntax"></a>Syntax  
  
```  
result = TypeOf objectexpression Is typename  
```  
  
```  
result = TypeOf objectexpression IsNot typename  
```  
  
## <a name="parts"></a>Teile  
 `result`  
 Wird zurückgegeben. Ein `Boolean`-Wert.  
  
 `objectexpression`  
 Erforderlich. Jeder Ausdruck, der als ein Verweistyp ausgewertet wird.  
  
 `typename`  
 Erforderlich. Ein beliebiger Datentypname.  
  
## <a name="remarks"></a>Hinweise  
 Der `TypeOf`-Operator bestimmt, ob der Laufzeittyp von `objectexpression` mit `typename` kompatibel ist. Die Kompatibilität hängt von der Typkategorie von `typename` ab. Die folgende Tabelle zeigt, wie die Kompatibilität bestimmt wird.  
  
|Typkategorie von `typename`|Kompatibilitätskriterium|  
|---------------------------------|-----------------------------|  
|Klasse|`objectexpression` ist vom Typ `typename` oder erbt von `typename`|  
|Struktur|`objectexpression` ist vom Typ `typename`|  
|Interface|`objectexpression` implementiert `typename` oder erbt von einer Klasse, die `typename` implementiert|  
  
 Wenn der Laufzeittyp von `objectexpression` das Kompatibilitätskriterium erfüllt, ist `result``True`. Andernfalls lautet `result` `False`.  Wenn `objectexpression` null ist, dann gibt `TypeOf`...`Is``False` zurück, und ...`IsNot` gibt `True` zurück.  
  
 `TypeOf` wird immer mit dem Schlüsselwort `Is` verwendet, um einen `TypeOf`...`Is`-Ausdruck zu erstellen, oder mit dem Schlüsselwort `IsNot`, um einen `TypeOf`...`IsNot`-Ausdruck zu erstellen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden `TypeOf`...`Is`-Ausdrücke zum Testen der Typkompatibilität von zwei Objektverweisvariablen mit verschiedenen Datentypen verwendet.  
  
 [!code-vb[VbVbalrOperators#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#39)]  
  
 Die Variable `refInteger` verfügt über einen Laufzeittyp von `Integer`. Sie ist mit `Integer`, jedoch nicht mit `Double` kompatibel. Die Variable `refForm` verfügt über einen Laufzeittyp von <xref:System.Windows.Forms.Form>. Sie ist mit <xref:System.Windows.Forms.Form> kompatibel, da es sich hierbei um ihren Typ handelt, sowie mit <xref:System.Windows.Forms.Control>, da <xref:System.Windows.Forms.Form> von <xref:System.Windows.Forms.Control> erbt, und mit <xref:System.ComponentModel.IComponent>, da <xref:System.Windows.Forms.Form> von <xref:System.ComponentModel.Component> erbt, welche wiederum <xref:System.ComponentModel.IComponent> implementiert. `refForm` ist jedoch mit <xref:System.Windows.Forms.Label> nicht kompatibel.  
  
## <a name="see-also"></a>Siehe auch

- [Is-Operator](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot-Operator](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md)
- [Operator Precedence in Visual Basic (Operatorrangfolge in Visual Basic)](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [Nach Funktionalität sortierte Operatoren](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Operatoren und Ausdrücke](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
