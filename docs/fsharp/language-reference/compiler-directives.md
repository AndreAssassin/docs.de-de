---
title: Compileranweisungen
description: Erfahren Sie mehr über F# Sprache präprozessoranweisungen, Anweisungen für bedingte Kompilierung, Line-Anweisungen und Compiler-Direktiven.
ms.date: 12/10/2018
ms.openlocfilehash: 3fade7407f84b00163bd5b3d7774104bce8a25af
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766102"
---
# <a name="compiler-directives"></a>Compileranweisungen

In diesem Thema werden Prozessor- und Compileranweisungen beschrieben.

## <a name="preprocessor-directives"></a>Präprozessordirektiven

Einer Präprozessordirektive wird das #-Symbol vorangestellt und wird für sich genommen in einer Zeile angezeigt. Sie wird durch den Präprozessor interpretiert, der vom Compiler ausgeführt wird.

In der folgenden Tabelle werden die Präprozessordirektiven aufgelistet, die in F# verfügbar sind.

|Direktive|Beschreibung|
|---------|-----------|
|`#if` *symbol*|Unterstützt die bedingte Kompilierung. Code im Abschnitt nach der `#if` enthalten ist, wenn die *Symbol* definiert ist. Das Symbol kann auch mit negiert `!`.|
|`#else`|Unterstützt die bedingte Kompilierung. Markiert einen einzubeziehenden Codeabschnitt, wenn das mit dem vorherigen verwendeten `#if` nicht definiert ist.|
|`#endif`|Unterstützt die bedingte Kompilierung. Markiert das Ende eines bedingten Codeabschnitts.|
|`#`[line] *int*,<br/>`#`[line] *int* *string*,<br/>`#`[line] *int* *verbatim-string*|Gibt die ursprüngliche Quellcodezeile und den Dateinamen für das Debuggen an. Diese Funktion wird für Tools bereitgestellt, die F#-Quellcode generieren.|
|`#nowarn` *warningcode*|Deaktiviert eine Compilerwarnung oder Warnungen. Suchen Sie zum Deaktivieren einer Warnung nach ihrer Nummer in der Compilerausgabe, und setzen Sie sie in Anführungszeichen. Lassen Sie das Präfix „FS“ weg. Zum Deaktivieren von mehreren Warnnummern in derselben Zeile müssen Sie jede Nummer in Anführungszeichen setzen und jede Zeichenfolge durch ein Leerzeichen abtrennen. Zum Beispiel:

`#nowarn "9" "40"`

Die Auswirkungen der Deaktivierung einer Warnung, die auf die gesamte Datei, einschließlich der Teile der Datei, die von der Anweisung vorausgehen angewendet wird. |

## <a name="conditional-compilation-directives"></a>Anweisungen für die bedingte Kompilierung

Code, der durch eine dieser Anweisungen deaktiviert wird, die im Visual Studio Code-Editor abgeblendet angezeigt.

> [!NOTE]
> Das Verhalten der Anweisungen für die bedingte Kompilierung entspricht nicht dem in anderen Sprachen. Beispielsweise können Sie keine booleschen Ausdrücke mit Symbolen verwenden, zudem verfügen `true` und `false` über keine besondere Bedeutung. In der `if`-Direktive von Ihnen verwendete Symbole müssen über die Befehlszeile oder in den Projekteinstellungen definiert werden. Es steht keine `define`-Präprozessordirektive zur Verfügung.

Im folgenden Code wird die Verwendung der Direktiven `#if`, `#else` und `#endif` veranschaulicht. In diesem Beispiel enthält der Code zwei Versionen der Definition von `function1`. Wenn `VERSION1` wird definiert, mit der [-define-Compileroption](https://msdn.microsoft.com/library/434394ae-0d4a-459c-a684-bffede519a04), den Code zwischen die `#if` Richtlinie und die `#else` aktiviert. Andernfalls wird der Code zwischen `#else` und `#endif` aktiviert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7301.fs)]

Es gibt keine `#define`-Präprozessoranweisung in F#. Sie müssen die Compileroption oder Projekteinstellungen verwenden, um die durch die `#if`-Direktive verwendeten Symbole zu definieren.

Direktiven für die bedingte Kompilierung können geschachtelt werden. Der Einzug ist für Präprozessordirektiven nicht entscheidend.

Sie können ein Symbol mit Vorgangskategorien `!`. In diesem Beispiel ist der Wert einer Zeichenfolge etwas nur, wenn _nicht_ Debuggen:

```fsharp
#if !DEBUG
let str = "Not debugging!"
#else
let str = "Debugging!"
#endif
```

## <a name="line-directives"></a>Line-Direktiven

Beim Erstellen meldet der Compiler Fehler im F#-Code durch das Referenzieren von Zeilennummern, in denen die jeweiligen Fehler auftreten. Diese Zeilennummern beginnen bei 1 für die erste Zeile in einer Datei. Wenn Sie jedoch F#-Quellcode aus einem anderen Tool generieren, sind die Zeilennummern im generierten Code im Allgemeinen nicht relevant, da die Fehler im generierten F#-Code höchstwahrscheinlich auf eine andere Quelle zurückgehen. Mit der `#line`-Direktive können Autoren von Tools, die F#-Quellcode generieren, Informationen über die ursprünglichen Zeilennummern und Quelldateien an den generierten F#-Code weitergeben.

Beim Verwenden der `#line`-Direktive müssen Dateinamen in Anführungszeichen gesetzt werden. Sofern das verbatim-Token (`@`) nicht am Anfang der Zeichenfolge angezeigt wird, müssen Sie umgekehrte Schrägstriche durch die Verwendung von zwei (und nicht nur einem) umgekehrten Schrägstrichen escapen, um sie im Pfad zu verwenden. Im Folgenden finden Sie gültige Zeilentoken. In diesen Beispielen wird davon ausgegangen, dass die ursprüngliche `Script1`-Datei in einer automatisch generierten F#-Codedatei resultiert, wenn er über ein Tool ausgeführt wird, und dass der Code am Speicherort dieser Anweisungen aus einigen Token in Zeile 25 in der Datei `Script1` generiert wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7303.fs)]

Diese Token geben an, dass der an diesem Speicherort generierte F#-Code aus einigen Konstrukten in oder in der Nähe der Zeile `25` in `Script1` abgeleitet ist.

## <a name="compiler-directives"></a>Compileranweisungen

Compilerdirektiven ähneln Präprozessordirektiven, da ihnen ein #-Zeichen vorangestellt ist. Anstelle jedoch durch den Präprozessor interpretiert zu werden, werden sie durch den Compiler interpretiert und verarbeitet.

Die folgende Tabelle enthält die Compilerdirektive, die in F# verfügbar ist.

|Direktive|Beschreibung|
|---------|-----------|
|`#light` ["on"&#124;"off"]|Aktiviert oder deaktiviert die einfache Syntax für die Kompatibilität mit anderen MK-Versionen. Standardmäßig ist die einfache Syntax aktiviert. Die ausführliche Syntax ist immer aktiviert. Daher können Sie die einfache und ausführliche Syntax verwenden. Die Direktive `#light` an sich entspricht `#light "on"`. Beim Angeben von `#light "off"` müssen Sie die ausführliche Syntax für alle Sprachkonstrukte verwenden. Bei der in der Dokumentation für F# gezeigten Syntax wird davon ausgegangen, dass Sie die einfache Syntax verwenden. Weitere Informationen finden Sie unter [ausführliche Syntax](verbose-syntax.md).|

Interpreter (fsi.exe)-Anweisungen finden Sie unter [Interaktive Programmierung mit F#](../tutorials/fsharp-interactive/index.md).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Compileroptionen](compiler-options.md)