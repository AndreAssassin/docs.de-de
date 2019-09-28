---
title: Partial (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: acfe47f52ede289093b3554a7dd190ef3f0e2c80
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592115"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)
Gibt an, dass eine Typdeklaration eine partielle Definition des Typs ist.  
  
 Mit dem `Partial`-Schlüsselwort können Sie die Typdefinition auf mehrere Deklarationen aufteilen. Sie können beliebig viele partielle Deklarationen in beliebig vielen verschiedenen Quelldateien verwenden. Alle Deklarationen müssen jedoch in der gleichen Assembly und dem gleichen Namespace enthalten sein.  
  
> [!NOTE]
> Visual Basic unterstützt *partielle Methoden*, die in der Regel in partiellen Klassen implementiert werden. Weitere Informationen finden Sie unter [partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) und [unter Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attrlist`|Optional. Liste der Attribute, die für diesen Typ gelten. Sie müssen die [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern (`< >`) einschließen.|  
|`accessmodifier`|Optional. Gibt an, welcher Code auf diesen Typ zugreifen kann. Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Optional. Siehe [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Optional. Siehe [notvererbt able](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Erforderlich. Der Name dieses Typs. Muss mit dem Namen übereinstimmen, der in allen anderen partiellen Deklarationen desselben Typs definiert ist.|  
|`Of`|Optional. Gibt an, dass dies ein generischer Typ ist. Weitere Informationen finden Sie [unter generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Erforderlich, wenn Sie [verwenden.](../../../visual-basic/language-reference/statements/of-clause.md) Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Optional. Siehe [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie `Inherits` verwenden. Der Name der Klasse oder Schnittstelle, von der diese Klasse abgeleitet wird.|  
|`Implements`|Optional. Siehe [implementierende Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie `Implements` verwenden. Die Namen der von diesem Typ implementierten Schnittstellen.|  
|`variabledeclarations`|Optional. Anweisungen, die zusätzliche Variablen und Ereignisse für den Typ definieren.|  
|`proceduredeclarations`|Optional. Anweisungen, die zusätzliche Prozeduren für den Typ deklarieren und definieren.|  
|`End Class` oder `End Structure`|Beendet diese partielle `Class`- oder `Structure`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Visual Basic verwendet partielle Klassendefinitionen, um in jeweils eigenen Quelldateien generierten Code von Code zu trennen, der vom Benutzer erstellt wurde. Zum Beispiel definiert der **Windows Form-Designer** partielle Klassen für Steuerelemente, z.B. <xref:System.Windows.Forms.Form>. Sie sollten den generierten Code in diesen Steuerelementen nicht ändern.  
  
 Beim Erstellen eines partiellen Typs gelten alle Regeln für die Erstellung von Klassen, Strukturen, Schnittstellen und Modulen, beispielsweise diejenigen für die Verwendung und Vererbung von Modifizierern.  
  
## <a name="best-practices"></a>Bewährte Methoden  
  
- Normalerweise wird die Entwicklung eines einzelnen Typs nicht auf zwei oder mehr Deklarationen aufgeteilt. In der Regel benötigen Sie das `Partial`-Schlüsselwort daher nicht.  
  
- Zur besseren Lesbarkeit sollte jede partielle Deklaration eines Typs das `Partial`-Schlüsselwort enthalten. Der Compiler gestattet den Wegfall des Schlüsselworts nur bei höchstens einer partiellen Deklaration. Fällt es bei mehr als einer Deklaration weg, tritt ein Fehler auf.  
  
## <a name="behavior"></a>Verhalten  
  
- **Union von Deklarationen.** Der Compiler behandelt den Typ als die Union all seiner partiellen Deklarationen. Jeder Modifizierer aus jeder partiellen Definition wird auf den gesamten Typ angewendet, und jeder Member aus jeder partiellen Definition steht dem gesamten Typ zur Verfügung.  
  
- **Die Typerweiterung ist für partielle Typen in Modulen nicht zulässig.** Wenn eine partielle Definition in einem Modul enthalten ist, ist automatisch keine Typerweiterung für diesen Typ möglich. In einem solchen Fall kann eine Reihe partieller Definitionen zu unerwarteten Ergebnissen und sogar zu Compilerfehlern führen. Weitere Informationen finden Sie unter [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
 Das `Partial`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Definition der `sampleClass`-Klasse auf zwei Deklarationen aufgeteilt, die jeweils eine andere `Sub`-Prozedur definieren.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Die beiden partiellen Definitionen aus dem vorhergehenden Beispiel können in derselben Quelldatei oder in zwei unterschiedlichen Quelldateien enthalten sein.  
  
## <a name="see-also"></a>Siehe auch

- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Typerweiterung](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Partielle Methoden](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
