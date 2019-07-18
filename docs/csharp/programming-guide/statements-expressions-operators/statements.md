---
title: Anweisungen – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- statements [C#], about statements
- C# language, statements
ms.assetid: 901bcde7-87de-4e15-833c-f9cfd40c8ce3
ms.openlocfilehash: 78d40aa2069e56357f55f39c3b7479ee46d0342c
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422827"
---
# <a name="statements-c-programming-guide"></a>Anweisungen (C#-Programmierhandbuch)
Von einer Anwendung ausgeführte Aktionen werden in Anweisungen ausgedrückt. Häufig verwendete Aktionen umfassen das Deklarieren von Variablen, Zuweisen von Werten, Aufrufen von Methoden, Durchlaufen von Auflistungen und das Verzweigen auf einen oder einen anderen Codeblock, je nach gegebener Bedingung. Die Reihenfolge, in der Anweisungen in einem Programm ausgeführt werden, wird „Ablaufsteuerung“ oder „Ausführungsablauf“ genannt. Die Ablaufsteuerung kann jedes Mal, wenn ein Programm ausgeführt wird, variieren, je nachdem, wie die Anwendung auf eine Eingabe reagiert, die sie während der Laufzeit empfängt.  
  
 Eine Anweisung kann aus einer einzelnen Codezeile, die mit einem Semikolon endet, oder aus einer Reihe von einzeiligen Anweisungen in einem Block bestehen. Ein Anweisungsblock ist in geschweiften Klammern ({}) eingeschlossen und kann geschachtelte Blöcke enthalten. Der folgende Code zeigt zwei Beispiele für einzeilige Anweisungen und einen mehrzeiligen Anweisungsblock:  
  
 [!code-csharp[csProgGuideStatements#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#1)]  
  
## <a name="types-of-statements"></a>Typen von Anweisungen  
 Die folgende Tabelle enthält die verschiedenen Typen von Anweisungen in C# und die zugehörigen Schlüsselwörter, mit Links zu Themen, die weitere Informationen enthalten:  
  
|Kategorie|C#-Schlüsselwörter / Hinweise|  
|--------------|---------------------------|  
|[Declaration statements (Deklarationsanweisungen)](#declaration-statements)|Eine Deklarationsanweisung führt eine neue Variable oder Konstante ein. Eine Deklaration einer Variable kann der Variable optional einen Wert zuweisen. Bei einer Deklaration einer Konstante ist die Zuweisung erforderlich.|  
|[Expression statements (Ausdrucksanweisungen)](expressions.md)|Ausdrucksanweisungen, die einen Wert berechnen, müssen den Wert in einer Variablen speichern. Weitere Informationen finden Sie unter [Ausdrucksanweisungen](#expression-statements).|  
|Auswahlanweisungen|Auswahlanweisungen helfen Ihnen in unterschiedliche Codeabschnitte zu verzweigen, abhängig von einer oder mehreren angegebenen Bedingungen. Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> [if](../../../csharp/language-reference/keywords/if-else.md), [else](../../../csharp/language-reference/keywords/if-else.md), [switch](../../../csharp/language-reference/keywords/switch.md), [case](../../../csharp/language-reference/keywords/switch.md)|  
|Iterationsanweisungen|Iterationsanweisungen helfen Ihnen, Auflistungen, wie z.B. Arrays, zu durchlaufen oder den selben Satz von Anweisungen solange zu wiederholen, bis eine angegebene Bedingung erfüllt ist. Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> [do](../../../csharp/language-reference/keywords/do.md), [for](../../../csharp/language-reference/keywords/for.md), [foreach](../../../csharp/language-reference/keywords/foreach-in.md), [in](../../../csharp/language-reference/keywords/foreach-in.md), [while](../../../csharp/language-reference/keywords/while.md)|  
|Sprunganweisungen|Sprunganweisungen übertragen Steuerelemente zu einem anderen Codeabschnitt. Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> [break](../../../csharp/language-reference/keywords/break.md), [continue](../../../csharp/language-reference/keywords/continue.md), [default](../../../csharp/language-reference/keywords/switch.md), [goto](../../../csharp/language-reference/keywords/goto.md), [return](../../../csharp/language-reference/keywords/return.md), [yield](../../../csharp/language-reference/keywords/yield.md)|  
|Ausnahmebehandlungsanweisungen|Mit Ausnahmebehandlungsanweisungen können Sie ordnungsgemäß von Ausnahmebedingungen wiederherstellen, die zur Laufzeit auftreten. Weitere Informationen finden Sie unter den folgenden Themen:<br /><br /> [throw](../../../csharp/language-reference/keywords/throw.md), [try-catch](../../../csharp/language-reference/keywords/try-catch.md), [try-finally](../../../csharp/language-reference/keywords/try-finally.md), [try-catch-finally](../../../csharp/language-reference/keywords/try-catch-finally.md)|  
|[Checked und unchecked](../../../csharp/language-reference/keywords/checked-and-unchecked.md)|Die Anweisungen „checked“ und „unchecked“ helfen Ihnen anzugeben, ob numerische Vorgänge einen Überlauf verursachen dürfen, wenn das Ergebnis in einer Variable gespeichert ist, die zu klein ist, um den resultierenden Wert zu speichern. Weitere Informationen finden Sie unter [checked](../../../csharp/language-reference/keywords/checked.md) und [unchecked](../../../csharp/language-reference/keywords/unchecked.md).|  
|Die Anweisung `await`|Wenn Sie eine Methode mit dem [async](../../../csharp/language-reference/keywords/async.md) -Modifizierer kennzeichnen, können Sie den [await](../../../csharp/language-reference/keywords/await.md) Operator in der Methode verwenden. Wenn ein Ausdruck `await` in der asynchronen Methode erreicht wird, wird die Steuerung an den Aufrufer zurückgegeben, und die Ausführung der Methode wird angehalten, bis die erwartete Aufgabe abgeschlossen ist. Wenn die Aufgabe abgeschlossen ist, kann die Ausführung in der Methode fortgesetzt werden.<br /><br /> Ein einfaches Beispiel finden Sie im Abschnitt „Async-Methoden“ unter [Methoden](../../../csharp/programming-guide/classes-and-structs/methods.md). Weitere Informationen finden Sie unter [Asynchrone Programmierung mit Async und Await](../../../csharp/programming-guide/concepts/async/index.md).|  
|Die Anweisung `yield return`|Ein Iterator führt eine benutzerdefinierte Iteration durch eine Auflistung durch, z. B. eine Liste oder ein Array. Ein Iterator verwendet die Anweisung [yield return](../../../csharp/language-reference/keywords/yield.md), um jedes Element einzeln nacheinander zurückzugeben. Wenn eine `yield return`-Anweisung erreicht wird, wird die aktuelle Position im Code gespeichert. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.<br /><br /> Weitere Informationen finden Sie unter [Iteratoren](../../../csharp/programming-guide/concepts/iterators.md).|  
|Die Anweisung `fixed`|Die fixed-Anweisung verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt. Weitere Informationen finden Sie unter [fixed](../../../csharp/language-reference/keywords/fixed-statement.md).|  
|Die Anweisung `lock`|Die lock-Anweisung hilft Ihnen, den Zugriff auf Codeblöcke auf jeweils einen Thread zu beschränken. Weitere Informationen finden Sie unter [lock](../../../csharp/language-reference/keywords/lock-statement.md).|  
|Anweisungen mit Bezeichnung|Sie können einer Anweisung eine Bezeichnung geben, und anschließend mit dem Schlüsselwort [goto](../../../csharp/language-reference/keywords/goto.md) zu der Anweisung mit Bezeichnung springen. (Ein Beispiel finden Sie in der folgenden Zeile.)|  
|Die [leere Anweisung](#the-empty-statement)|Die leere Anweisung besteht aus einem einzelnen Semikolon. Sie führt keine Aktion aus und kann an Orten verwendet werden, an denen eine Anweisung erforderlich ist, aber keine Aktion ausgeführt werden muss.|  
  
## <a name="declaration-statements"></a>Deklarationsanweisungen

Der folgende Code zeigt Beispiele für Variablendeklarationen mit und ohne anfängliche Zuweisung sowie eine Konstantendeklaration mit der erforderlichen Initialisierung.

 [!code-csharp[csProgGuideStatements#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#23)]

## <a name="expression-statements"></a>Ausdrucksanweisungen

Der folgende Code zeigt Beispiele für Ausdrucksanweisungen, einschließlich Zuweisung, Objekterstellung mit Zuweisung und Methodenaufruf.

 [!code-csharp[csProgGuideStatements#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#24)]

## <a name="the-empty-statement"></a>Die leere Anweisung

Die folgenden Beispiele zeigen zwei Verwendungen für eine leere Anweisung:

 [!code-csharp[csProgGuideStatements#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#25)]

## <a name="embedded-statements"></a>Eingebettete Anweisungen

 Einige Anweisungen, z.B. [do](../../../csharp/language-reference/keywords/do.md), [while](../../../csharp/language-reference/keywords/while.md), [for](../../../csharp/language-reference/keywords/for.md) und [foreach](../../../csharp/language-reference/keywords/foreach-in.md), haben immer eine eingebettete Anweisung, die diesen folgt. Diese eingebettete Anweisung kann entweder eine einzelne Anweisung oder mehrere Anweisungen sein, die durch geschweifte Klammern ({}) in einem Anweisungsblock umschlossen werden. In geschweiften Klammern ({}) können sogar einzeilige eingebettete Anweisungen wie im folgenden Beispiel gezeigt eingeschlossen werden:  
  
 [!code-csharp[csProgGuideStatements#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#26)]  
  
 Eine eingebettete Anweisung, die nicht in geschweifte Klammern ({}) eingeschlossen ist, darf keine Deklarationsanweisung oder eine Anweisung mit Bezeichnung sein. Dies wird im folgenden Beispiel gezeigt:  
  
 [!code-csharp[csProgGuideStatements#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#27)]  
  
 Fügen Sie die eingebettete Anweisung in einen Block ein, um den Fehler zu beheben:  
  
 [!code-csharp[csProgGuideStatements#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#28)]  
  
## <a name="nested-statement-blocks"></a>Geschachtelte Anweisungsblöcke  
 Anweisungsblöcke können geschachtelt werden, wie im folgenden Code gezeigt wird:  
  
 [!code-csharp[csProgGuideStatements#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#29)]  
  
## <a name="unreachable-statements"></a>Nicht erreichbare Anweisungen  
 Wenn der Compiler festlegt, dass der Steuerungsablauf nie auf eine bestimmte Anweisung unter jeglichen Umständen zugreifen kann, wird die Warnung CS0162 erzeugt, wie im folgenden Beispiel gezeigt wird:  
  
 [!code-csharp[csProgGuideStatements#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideStatements/CS/Statements.cs#22)]  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
  
- [Anweisungsschlüsselwörter](../../../csharp/language-reference/keywords/statement-keywords.md)  
  
- [Ausdrücke](../../../csharp/programming-guide/statements-expressions-operators/expressions.md)  
  
- [Operatoren](../../../csharp/programming-guide/statements-expressions-operators/operators.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
