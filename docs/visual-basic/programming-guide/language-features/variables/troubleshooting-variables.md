---
title: Problembehandlung bei Variablen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting [Visual Basic], variables
- variables [Visual Basic], troubleshooting
ms.assetid: 928a2dc8-e565-4ae4-8ba3-80cc0cb50090
ms.openlocfilehash: 31aca95bb292ecd0bb04fda6ded83d4af8be0e2f
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64598617"
---
# <a name="troubleshooting-variables-in-visual-basic"></a>Problembehandlung bei Variablen in Visual Basic
Diese Seite listet einige der häufigsten Probleme, die auftreten können, bei der Arbeit mit Variablen in Visual Basic.  
  
## <a name="unable-to-access-members-of-an-object"></a>Zugriff auf Member eines Objekts ist nicht möglich  
 Wenn Ihr Code versucht, auf eine Eigenschaft oder Methode eines Objekts zuzugreifen, können zwei Arten von Fehlern auftreten:  
  
- Der Compiler kann eine Fehlermeldung generieren, wenn Sie die Objektvariable als bestimmten Typ deklarieren und dann auf einen Member verweisen, der nicht durch diesen Typ definiert ist.  
  
- Eine Laufzeit- <xref:System.MemberAccessException> tritt auf, wenn das einer Objektvariablen zugewiesene Objekt nicht den Member verfügbar macht, auf den Ihr Code zugreifen möchten. Bei einer Variablen von [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md)können Sie diese Ausnahmemeldung auch erhalten, wenn der Member nicht `Public`auftreten können. Der Grund ist, dass die späte Bindung nur den Zugriff auf `Public` -Member erlaubt.  
  
 Wenn [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) für die Typüberprüfung `On`festlegt, kann eine Objektvariable nur auf die Methoden und Eigenschaften der Klasse zugreifen, mit der Sie sie deklarieren. Dies wird anhand des folgenden Beispiels veranschaulicht.  

 [!code-vb[VbVbalrVariables#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrVariables/VB/Class1.vb#2)]  
  
 In diesem Beispiel kann `p` nur die Mitglieder der <xref:System.Object> -Klasse selbst verwenden, die nicht die `Left` -Eigenschaft enthalten. Auf der anderen Seite wurde `q` als Typ <xref:System.Windows.Forms.Label>deklariert, sodass es alle Methoden und Eigenschaften der <xref:System.Windows.Forms.Label> -Klasse im <xref:System.Windows.Forms> -Namespace verwenden kann.  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Um auf alle Member eines Objekts einer bestimmten Klasse zugreifen zu können, deklarieren Sie die Objektvariable nach Möglichkeit als Typ der Klasse. Wenn Sie dies nicht möglich, z. B. Wenn Sie den Objekttyp zur Kompilierzeit nicht bekannt ist, müssen Sie festlegen `Option Strict` zu `Off` und deklarieren Sie die Variable der [Object Data Type](../../../../visual-basic/language-reference/data-types/object-data-type.md). So können der Variablen Objekte beliebigen Typs zugewiesen werden, und Sie sollten Maßnahmen ergreifen, um sicherzustellen, dass das aktuell zugewiesene Objekt einen zulässigen Typ hat. Sie können die [TypeOf-Operator](../../../../visual-basic/language-reference/operators/typeof-operator.md) , diese Entscheidung zu treffen.  
  
## <a name="other-components-cannot-access-your-variable"></a>Andere Komponenten können nicht auf die Variable zugreifen  
 Visual Basic-Namen sind *Groß-/Kleinschreibung*. Wenn zwei Namen sich nur in der Groß- und Kleinschreibung unterscheiden, interpretiert der Compiler sie als identisch. Er geht z. B. davon aus, dass `ABC` und `abc` auf das gleiche deklarierte Element verweisen.  
  
 Allerdings verwendet die Common Language Runtime (CLR) die *Groß-/Kleinschreibung unterscheidende* Bindung. Wenn Sie also eine Assembly oder DLL erstellen und für andere Assemblys verfügbar machen, wird bei Ihren Namen Groß-und Kleinschreibung unterschieden. Wenn Sie z. B. eine Klasse mit einem Element namens `ABC`definieren, müssen andere Assemblys, die die Klasse über die Common Language Runtime verwenden, auf das Element als `ABC`verweisen. Wenn Sie danach die Klasse erneut kompilieren und den Namen des Elements in `abc`ändern, können andere Assemblys, die Ihre Klasse verwenden, nicht mehr auf dieses Element zugreifen. Wenn Sie also eine aktualisierte Version einer Assembly herausgeben, sollten Sie die Groß-/Kleinschreibung öffentlicher Elemente nicht ändern.  
  
 Weitere Informationen finden Sie unter [Common Language Runtime](../../../../standard/clr.md).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Um anderen Komponenten den Zugriff auf Ihre Variablen zu ermöglichen, behandeln Sie deren Namen so, als würde die Groß-/Kleinschreibung unterschieden. Stellen Sie beim Testen der Klasse oder des Moduls sicher, dass andere Assemblys sich gemäß Ihrer Erwartung an die Variablen binden. Nachdem Sie eine Komponente veröffentlicht haben, nehmen Sie keine Änderungen an vorhandenen Namen von Variablen vor, Ändern von Groß-/Kleinschreibung inbegriffen.  
  
## <a name="wrong-variable-being-used"></a>Falsche Variable wird verwendet  
 Wenn Sie mehr als eine Variable mit dem gleichen Namen haben, versucht Visual Basic-Compiler, jeden Verweis auf diesen Namen aufzulösen. Wenn die Variablen über unterschiedliche Gültigkeitsbereiche verfügen, löst der Compiler einen Verweis auf die Deklaration mit dem engsten Gültigkeitsbereich auf. Wenn sie den gleichen Gültigkeitsbereich aufweisen, gelingt die Auflösung nicht, und der Compiler signalisiert einen Fehler. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
### <a name="correct-approach"></a>Richtige Vorgehensweise  
 Vermeiden Sie, Variablen mit gleichem Namen, aber unterschiedlichen Gültigkeitsbereichen zu verwenden. Wenn Sie andere Assemblys oder Projekte verwenden, vermeiden Sie so weit wie möglich die Verwendung von Namen, die in diesen externen Komponenten definiert werden. Wenn Sie über mehrere Variablen gleichen Namens verfügen, achten Sie darauf, jeden Verweis auf sie zu qualifizieren. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="see-also"></a>Siehe auch

- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)
- [Vorgehensweise: Zugreifen auf Member eines Objekts](../../../../visual-basic/programming-guide/language-features/variables/how-to-access-members-of-an-object.md)
- [Werte von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)
- [Vorgehensweise: Bestimmen des Typs, um eine Objektvariable verweist](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-what-type-an-object-variable-refers-to.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
