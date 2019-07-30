---
title: 'sizeof-Operator: C#-Verweis'
ms.custom: seodec18
ms.date: 07/25/2019
f1_keywords:
- sizeof_CSharpKeyword
- sizeof
helpviewer_keywords:
- sizeof keyword [C#]
ms.assetid: c548592c-677c-4f40-a4ce-e613f7529141
ms.openlocfilehash: 4852e1166a975b1a45c5bd905123a35fc846aa28
ms.sourcegitcommit: 463f3f050cecc0b6403e67f19a61f870fb8e7b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/26/2019
ms.locfileid: "68513124"
---
# <a name="sizeof-operator-c-reference"></a>sizeof-Operator (C#-Verweis)

Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von einer Variablen eines bestimmten Typs belegt werden. Ein Argument des `sizeof`-Operators muss der Namen eines [nicht verwalteten Typs](../builtin-types/unmanaged-types.md) oder eines Typparameters sein, der darauf [beschränkt](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) ist, ein nicht verwalteter Typ zu sein.

Der `sizeof`-Operator erfordert einen [unsicheren](../keywords/unsafe.md) Kontext. Die in der folgenden Tabelle dargestellten Ausdrücke werden jedoch in der Kompilierzeit auf die entsprechenden konstanten Werte ausgewertet und erfordern keinen unsicheren Kontext:

|Ausdruck|Konstanter Wert|
|---------|---------------|
|`sizeof(sbyte)`|1|
|`sizeof(byte)`|1|
|`sizeof(short)`|2|
|`sizeof(ushort)`|2|
|`sizeof(int)`|4|
|`sizeof(uint)`|4|
|`sizeof(long)`|8|
|`sizeof(ulong)`|8|
|`sizeof(char)`|2|
|`sizeof(float)`|4|
|`sizeof(double)`|8|
|`sizeof(decimal)`|16|
|`sizeof(bool)`|1|

Sie müssen auch keinen unsicheren Kontext verwenden, wenn der Operand des `sizeof`-Operators der Name eines [Enumerationstyps](../keywords/enum.md) ist.

Im folgenden Beispiel wird die Verwendung des `sizeof`-Operators veranschaulicht:

[!code-csharp[sizeof examples](~/samples/csharp/language-reference/operators/SizeOfOperator.cs)]

Der `sizeof`-Operator gibt die Anzahl der Bytes zurück, die von der Common Language Runtime im verwalteten Speicher belegt werden. Wie im vorherigen Beispiel veranschaulicht, enthält dieser Wert für [Strukturtypen](../keywords/struct.md) alle Auffüllzeichen. Das Ergebnis des `sizeof`-Operators unterscheidet sich möglicherweise von dem Ergebnis der <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType>-Methode, die die Größe eines Typs in *nicht verwaltetem* Speicher zurückgibt.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Der sizeof-Operator](~/_csharplang/spec/unsafe-code.md#the-sizeof-operator) in der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren](index.md)
- [Operatoren im Zusammenhang mit Zeigern](pointer-related-operators.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Memory- und Span-bezogene Typen](../../../standard/memory-and-spans/index.md)
