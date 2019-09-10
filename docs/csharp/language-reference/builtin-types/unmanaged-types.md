---
title: 'Nicht verwaltete Typen: C#-Verweis'
ms.date: 09/06/2019
helpviewer_keywords:
- unmanaged type [C#]
ms.openlocfilehash: 25aa42ba8c8f0023b4f818feb2edbb325f805fb6
ms.sourcegitcommit: c70542d02736e082e8dac67dad922c19249a8893
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2019
ms.locfileid: "70374112"
---
# <a name="unmanaged-types-c-reference"></a>Nicht verwaltete Typen (C#-Verweis)

Ein Typ ist ein **nicht verwalteter Typ**, wenn es sich um einen der folgenden Typen handelt:

- `sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, `double`, `decimal` oder `bool`
- Beliebiger [Enumerationstyp](../keywords/enum.md)
- Beliebiger [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- Jeder benutzerdefinierte [Strukturtyp](../keywords/struct.md), der nur Felder mit nicht verwalteten Typen enthält und – in C# 7.3 und früher – kein konstruierter Typ ist (ein konstruierter Typ ist ein Typ, der mindestens ein Typargument enthält)

Ab C# 7.3 können Sie die [`unmanaged`-Einschränkung](../../programming-guide/generics/constraints-on-type-parameters.md#unmanaged-constraint) verwenden, um anzugeben, dass ein Typparameter ein nicht verwalteter Nichtzeigertyp ist.

Ab C# 8.0 ist ein *konstruierter* Strukturtyp, der Felder mit nicht verwalteten Typen enthält, ebenfalls nicht verwaltet, wie das folgende Beispiel zeigt:

[!code-csharp[unmanaged constructed types](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#ProgramExample)]

Eine generische Struktur kann als Quelle sowohl für nicht verwaltete als auch für verwaltete konstruierte Typen dienen. Das oben stehende Beispiel definiert die generische Struktur `Coords<T>` und zeigt Beispiele nicht verwalteter konstruierter Typen. Ein Beispiel für einen verwalteten Typ ist `Coords<object>`. Der Typ ist verwaltet, weil er Felder des Typs `object` enthält, der verwaltet ist. Wenn *alle* konstruierten Typen nicht verwaltet sein sollen, verwenden Sie die `unmanaged`-Einschränkung in der Definition einer generischen Struktur:

[!code-csharp[unmanaged constraint in type definition](~/samples/csharp/language-reference/builtin-types/UnmanagedTypes.cs#AlwaysUnmanaged)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Zeigertypen](~/_csharplang/spec/unsafe-code.md#pointer-types) der [Spezifikation für die Sprache C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Memory- und Span-bezogene Typen](../../../standard/memory-and-spans/index.md)
- [sizeof (Operator)](../operators/sizeof.md)
- [stackalloc (Operator)](../operators/stackalloc.md)
