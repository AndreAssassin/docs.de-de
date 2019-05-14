---
title: operator-Schlüsselwort – C#-Referenz
ms.custom: seodec18
description: Vorgehensweise beim Überladen eines integrierten C#-Operators
ms.date: 08/27/2018
f1_keywords:
- operator_CSharpKeyword
- operator
helpviewer_keywords:
- operator keyword [C#]
ms.assetid: 59218cce-e90e-42f6-a6bb-30300981b86a
ms.openlocfilehash: 47ce91c343092ac2f7555c1edf3418527776e131
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64754764"
---
# <a name="operator-c-reference"></a>operator (C#-Referenz)

Verwenden Sie das Schlüsselwort `operator`, um einen integrierten Operator zu überladen oder um eine benutzerdefinierte Konvertierung in einer Klassen- oder Strukturdeklaration bereitzustellen.

Zum Überladen eines Operators in einer benutzerdefinierten Klasse oder Struktur müssen Sie eine Operatordeklaration im entsprechenden Typ erstellen. Die Operatordeklaration, die einen integrierten C#-Operator überlädt, muss die folgenden Regeln erfüllen:

- Sie enthält sowohl einen `public`- als auch einen `static`-Modifizierer.
- Sie enthält `operator X`, wobei `X` für den Namen oder das Symbol des überladenen Operators steht.
- Unäre Operatoren verfügen über einen Parameter. Demgegenüber weisen binäre Operatoren zwei Parameter auf. In jedem Fall muss mindestens ein Parameter denselben Typ wie die Klasse oder Struktur aufweisen, die den Operator deklariert.

Weitere Informationen zum Definieren von Konvertierungsoperatoren finden Sie in den [expliziten](explicit.md) und [impliziten](implicit.md) Keyword-Artikeln.

Eine Übersicht über die C#-Operatoren, die überladen werden können, finden Sie im Artikel [Überladbare Operatoren](../../programming-guide/statements-expressions-operators/overloadable-operators.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein `Fraction`-Typ definiert, der Bruchzahlen darstellt. Sie überlädt die Operatoren `+` und `*`, um Addition und Multiplikation bei Brüchen auszuführen, und stellt einen Konvertierungsoperator bereit, der einen `Fraction`-Typ in einen `double`-Typ konvertiert.

[!code-csharp[csrefKeywordsConversion#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#6)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Schlüsselwörter](index.md)
- [implicit](implicit.md)
- [explicit](explicit.md)
- [Überladbare Operatoren](../../programming-guide/statements-expressions-operators/overloadable-operators.md)
- [Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)
