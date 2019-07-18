---
title: Verweise und die Imports-Anweisung (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- assemblies [Visual Basic], namespaces
- references [Visual Basic], assembly
- namespaces [Visual Basic], assemblies
- referencing assemblies
- Imports statement [Visual Basic], referencing assemblies
- assemblies [Visual Basic], references
ms.assetid: 38149bd4-0a6f-4b31-b5f8-94a8c33f1600
ms.openlocfilehash: f3396eb3e758dc456d86de80246de24349680f2e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967751"
---
# <a name="references-and-the-imports-statement-visual-basic"></a>Verweise und die Imports-Anweisung (Visual Basic)
Können Sie externe Objekte verfügbar machen zu Ihrem Projekt durch Auswählen der **Verweis hinzufügen** Befehl die **Projekt** Menü. Verweise in Visual Basic können auf Assemblys verweisen, die ähneln Typbibliotheken jedoch mehr Informationen enthalten.  
  
## <a name="the-imports-statement"></a>Die Imports-Anweisung  
 Assemblys enthalten einen oder mehrere Namespaces. Wenn Sie einen Verweis auf eine Assembly hinzufügen, können Sie auch Hinzufügen einer `Imports` Anweisung, um ein Modul, das die Sichtbarkeit dieses Namespaces innerhalb des Moduls gesteuert. Die `Imports` Anweisung stellt einen Kontextbereich mit der Sie nur den Teil des Namespace erforderlich, geben Sie einen eindeutigen Verweis verwenden kann.  
  
 Die `Imports` Anweisung weist die folgende Syntax:  
  
 `Imports [Aliasname =] Namespace`  
  
 `Aliasname` bezieht sich auf einen kurzen Namen, die, den Sie im Code verwenden können, um zu einem importierten Namespace zu verweisen. `Namespace` ist ein Namespace, die zur Verfügung, entweder durch einen Projektverweis, über eine Definition innerhalb des Projekts oder durch eine vorherige `Imports` Anweisung.  
  
 Ein Modul kann eine beliebige Anzahl von enthalten `Imports` Anweisungen. Müssen sie nach jedem stehen `Option` -Anweisungen, falls vorhanden, jedoch vor jedem anderen Code.  
  
> [!NOTE]
>  Verwechseln Sie nicht die Projektverweise mit den `Imports` Anweisung oder der `Declare` Anweisung. Projekt-verweisen, an dem externe Objekte, z. B. Objekte, die in Assemblys, Visual Basic-Projekte zur Verfügung stellen. Die `Imports` Anweisung wird verwendet, um den Zugriff auf die Projektverweise vereinfachen, aber ermöglicht keinen Zugriff auf diese Objekte. Die `Declare` -Anweisung verwendet, um einen Verweis auf eine externe Prozedur in einer Dynamic Link Library (DLL) zu deklarieren.  
  
## <a name="using-aliases-with-the-imports-statement"></a>Using-Aliase mit der Importanweisung  
 Die `Imports` Anweisung erleichtert es, Methoden der Klassen für den Datenzugriff durch den Wegfall um explizit die vollqualifizierten Namen von verweisen. Aliase können Sie nur einen Teil eines Namespace einen aussagekräftigeren Namen zuweisen. Beispielsweise ist der Wagenrücklauf/Zeilenvorschub Sequenz, die bewirkt, dass ein einzelnes Stück Text auf mehrere Zeilen angezeigt werden Teil der <xref:Microsoft.VisualBasic.ControlChars> -Modul in die <xref:Microsoft.VisualBasic?displayProperty=nameWithType> Namespace. Um diese Konstante in einem Programm ohne Alias verwenden, müssen Sie den folgenden Code eingeben:  
  
 [!code-vb[VbVbalrApplication#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#3)]  
  
 `Imports` Anweisungen muss immer die ersten Zeilen, die unmittelbar nach einem `Option` Anweisungen in einem Modul. Das folgende Codefragment zeigt, wie zum Importieren und weisen Sie einen Alias für die <xref:Microsoft.VisualBasic.ControlChars?displayProperty=nameWithType> Modul:  
  
 [!code-vb[VbVbalrApplication#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#4)]  
  
 Zukünftige Verweise für diesen Namespace können wesentlich kürzer sein:  
  
 [!code-vb[VbVbalrApplication#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrApplication/VB/Class1.vb#5)]  
  
 Wenn ein `Imports` -Anweisung keinen Aliasnamen, die in den importierten Namespace definierten Elemente in das Modul ohne Qualifikation verwendet werden können. Wenn der Aliasname angegeben wird, muss sie für Namen, die in diesem Namespace enthaltenen als Qualifizierer verwendet werden.  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ControlChars>
- <xref:Microsoft.VisualBasic>
- [Namespaces in Visual Basic](../../../visual-basic/programming-guide/program-structure/namespaces.md)
- [Assemblys in .NET](../../../standard/assembly/index.md)
- [Vorgehensweise: Erstellen und Verwenden von Assemblys über die Befehlszeile](../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)
- [Imports-Anweisung (.NET-Namespace und -Typ)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
