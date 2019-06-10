---
title: Vergleichsoperatoren – C#-Referenz
description: Erfahren Sie mehr über C#-Vergleichsoperatoren, mit denen Sie die Reihenfolge numerischer Werte überprüfen können.
ms.date: 04/25/2019
author: pkulikov
f1_keywords:
- <_CSharpKeyword
- '>_CSharpKeyword'
- <=_CSharpKeyword
- '>=_CSharpKeyword'
helpviewer_keywords:
- comparison operators [C#]
- relational operators [C#]
- less than operator [C#]
- < operator [C#]
- greater than operator [C#]
- '> operator [C#]'
- less than or equal to operator [C#]
- <= operator [C#]
- greater than or equal to operator [C#]
- '>= operator [C#]'
ms.openlocfilehash: 3b123ea1ae57735cdcb763087f12c30b8008dc11
ms.sourcegitcommit: 904b98d8d706f0e2d5ceaa00ce17ffbd92adfb88
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2019
ms.locfileid: "66758197"
---
# <a name="comparison-operators-c-reference"></a>Vergleichsoperatoren (C#-Referenz)

Die Vergleichsoperatoren [`<` (kleiner als)](#less-than-operator-), [`>` (größer als)](#greater-than-operator-), [`<=` (kleiner als oder gleich)](#less-than-or-equal-operator-) und [`>=` (größer als oder gleich)](#greater-than-or-equal-operator-) – auch bekannt als relationale Operatoren – vergleichen ihre Operanden. Diese Operatoren unterstützen alle numerischen [Ganzzahl](../keywords/integral-types-table.md)- und [Gleitkomma](../keywords/floating-point-types-table.md)-Typen.

> [!NOTE]
> Bei den Operatoren `==`, `<`, `>`, `<=` und `>=` ist das Ergebnis eines Vorgangs gleich `false`, wenn einer der Operanden keine Zahl ist (<xref:System.Double.NaN?displayProperty=nameWithType> oder <xref:System.Single.NaN?displayProperty=nameWithType>). Das bedeutet, dass der `NaN`-Wert weder größer als noch kleiner als noch gleich einem anderen `double`-Wert (oder `float`-Wert) ist, einschließlich `NaN`. Weitere Informationen und Beispiele finden Sie im <xref:System.Double.NaN?displayProperty=nameWithType>- oder <xref:System.Single.NaN?displayProperty=nameWithType>-Referenzartikel.

Enumerationstypen unterstützen auch Vergleichsoperatoren. Für Operanden desselben [enum](../keywords/enum.md)-Typs werden die entsprechenden Werte des zugrunde liegenden integralen Typs verglichen.

Die Operatoren [`==` und `!=`](equality-operators.md) überprüfen, ob die Operanden gleich sind oder nicht.

## <a name="less-than-operator-"></a>„Kleiner als“-Operator \<

Der `<`-Operator gibt `true` zurück, wenn sein erster Operand kleiner ist als sein zweiter Operand, andernfalls `false`:

[!code-csharp-interactive[less than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Less)]

## <a name="greater-than-operator-"></a>„Größer als“-Operator >

Der `>`-Operator gibt `true` zurück, wenn sein erster Operand größer ist als sein zweiter Operand, andernfalls `false`:

[!code-csharp-interactive[greater than example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#Greater)]

## <a name="less-than-or-equal-operator-"></a>„Kleiner oder gleich“-Operator \<=

Der `<=`-Operator gibt `true` zurück, wenn sein erster Operand kleiner als sein zweiter Operand oder gleich ist, andernfalls `false`:

[!code-csharp-interactive[less than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#LessOrEqual)]

## <a name="greater-than-or-equal-operator-"></a>„Größer oder gleich“-Operator >=

Der `>=`-Operator gibt `true` zurück, wenn sein erster Operand größer als sein zweiter Operand oder gleich ist, andernfalls `false`:

[!code-csharp-interactive[greater than or equal example](~/samples/csharp/language-reference/operators/ComparisonOperators.cs#GreaterOrEqual)]

## <a name="operator-overloadability"></a>Operatorüberladbarkeit

Ein benutzerdefinierter Typ kann die Operatoren `<`, `>`, `<=` und `>=` [überladen](../keywords/operator.md).

Wenn ein Typ einen der `<`- oder `>`-Operatoren überlädt, muss er sowohl `<` als auch `>` überladen. Wenn ein Typ einen der `<=`- oder `>=`-Operatoren überlädt, muss er sowohl `<=` als auch `>=` überladen.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Relationale und Typtestoperatoren](~/_csharplang/spec/expressions.md#relational-and-type-testing-operators) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [C#-Operatoren](index.md)
- <xref:System.IComparable%601?displayProperty=nameWithType>
- [Gleichheitsoperatoren](equality-operators.md)
