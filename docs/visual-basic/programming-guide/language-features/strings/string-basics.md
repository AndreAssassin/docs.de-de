---
title: Grundlagen zu Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 9d2d3c82f5512bc1e37e3b05086fbd364ee12298
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61938332"
---
# <a name="string-basics-in-visual-basic"></a>Grundlagen zu Zeichenfolgen in Visual Basic
Der `String`-Datentyp stellt eine Reihe von Zeichen dar (wobei jedes Zeichen wiederum eine Instanz des `Char`-Datentyps darstellt). Dieses Thema führt die grundlegenden Konzepte von Zeichenfolgen in Visual Basic.  
  
## <a name="string-variables"></a>Zeichenfolgenvariablen  
 Einer Instanz einer Zeichenfolge kann ein Literalwert zugewiesen werden, der eine Reihe von Zeichen darstellt. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 Eine `String`-Variable kann auch einen beliebigen Ausdruck annehmen, der eine Zeichenfolge ergibt. Beispiele werden unten gezeigt:  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 Jedes Literal, das einer `String`-Variable zugewiesen ist, muss in Anführungszeichen eingeschlossen werden („“). Dies bedeutet, dass ein Anführungszeichen in einer Zeichenfolge nicht durch ein Anführungszeichen dargestellt werden kann. Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 Dieser Code verursacht einen Fehler, da der Compiler die Zeichenfolge nach dem zweiten Anführungszeichen beendet, und der Rest der Zeichenfolge wird als Code interpretiert. Um dieses Problem zu beheben, wird in Visual Basic zwei Anführungszeichen in einem Zeichenfolgenliteral als ein Anführungszeichen in der Zeichenfolge interpretiert. Das folgende Beispiel zeigt die korrekte Methode zum Einschließen eines Anführungszeichens in eine Zeichenfolge:  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 Im vorherigen Beispiel werden die beiden Anführungszeichen, die vor dem Wort `Look` vorhanden sind, zu einem Anführungszeichen in der Zeichenfolge. Die drei Anführungszeichen am Ende der Zeile stellen ein Anführungszeichen in der Zeichenfolge und das Abschlusszeichen der Zeichenfolge dar.  
  
 Zeichenfolgenliterale können mehrere Zeilen enthalten:  
  
```vb  
Dim x = "hello  
world"  
```  
  
 Die resultierende Zeichenfolge enthält Zeilenumbruchsequenzen, die Sie in Ihrem Zeichenfolgenliteral (vbcr, vbcrlf usw.) verwendet haben.  Sie müssen nicht mehr die bisherige Problemumgehung verwenden:  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a>Zeichen in Zeichenfolgen  
 Eine Zeichenfolge kann als eine Reihe von `Char`-Werten betrachtet werden, und der `String`-Typ verfügt über integrierte Funktionen, mit denen Sie zahlreiche Bearbeitungen an einer Zeichenfolge vornehmen können, die den durch Arrays zulässigen Bearbeitungen ähneln. Wie bei allen Arrays in [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], handelt es sich dabei um nullbasierte Arrays. Sie möchten möglicherweise auf ein bestimmtes Zeichen in einer Zeichenfolge durch die `Chars`-Eigenschaft verweisen, die eine Möglichkeit bietet, auf ein Zeichen durch die Position zuzugreifen, in der es in der Zeichenfolge auftritt. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 Im obigen Beispiel gibt die `Chars`-Eigenschaft der Zeichenfolge das vierte Zeichen in der Zeichenfolge zurück, wobei es sich um `D` handelt, und weist dieses `myChar` zu. Sie können auch die Länge einer bestimmten Zeichenfolge durch die `Length`-Eigenschaft abrufen. Wenn Sie mehrere Bearbeitungen hinsichtlich des Arraytyps an einer Zeichenfolge durchführen müssen, können Sie sie in ein Array von `Char`-Instanzen mit der `ToCharArray`-Funktion der Zeichenfolge konvertieren. Zum Beispiel:  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 Die Variable `myArray` enthält jetzt ein Array von `Char`-Werten, die jeweils ein Zeichen aus `myString` darstellen.  
  
## <a name="the-immutability-of-strings"></a>Die Unveränderlichkeit von Zeichenfolgen  
 Eine Zeichenfolge ist *unveränderliche*, d. h. der Wert nicht werden, wenn geändert kann er erstellt wurde. Sie können einer Zeichenfolgenvariablen trotzdem mehr als einen Wert zuweisen. Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 Hier wird eine Zeichenfolgenvariable erstellt, ein Wert zugewiesen, und dann wird der Wert geändert.  
  
 Genauer gesagt wird in der ersten Zeile eine Instanz des Typs `String` erstellt und der Wert `This string is immutable` zugewiesen. In der zweiten Zeile des Beispiels wird eine neue Instanz erstellt und der Wert `Or is it?` zugewiesen. Die Zeichenfolgenvariable verwirft den Verweis auf die erste Instanz und speichert einen Verweis auf die neue Instanz.  
  
 Im Gegensatz zu anderen systeminternen Datentypen ist `String` ein Verweistyp. Wenn eine Variable des Verweistyps als Argument an eine Funktion oder Unterroutine übergeben wird, wird ein Verweis auf die Speicheradresse, wo die Daten gespeichert werden, anstelle des tatsächlichen Werts der Zeichenfolge übergeben. Damit bleibt der Name der Variable im vorherigen Beispiel gleich, aber es wird auf eine neue und andere Instanz der `String`-Klasse verwiesen, die den neuen Wert enthält.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
- [String-Datentyp](../../../../visual-basic/language-reference/data-types/string-data-type.md)
- [Char-Datentyp](../../../../visual-basic/language-reference/data-types/char-data-type.md)
- [Grundlegende Zeichenfolgenoperationen](../../../../standard/base-types/basic-string-operations.md)
