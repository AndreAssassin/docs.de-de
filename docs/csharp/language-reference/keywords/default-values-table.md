---
title: 'Tabelle für Standardwerte: C#-Referenz'
ms.custom: seodec18
description: Erfahren Sie, wie die Standardwerte der C#-Typen lauten.
ms.date: 07/29/2019
helpviewer_keywords:
- default [C#]
- parameterless constructor [C#]
ms.openlocfilehash: d9889ce389eed73a9af0a3f72dcca6ec476cae15
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796502"
---
# <a name="default-values-table-c-reference"></a>Tabelle für Standardwerte (C#-Referenz)

In der folgenden Tabelle werden die Standardwerte von C#-Typen gezeigt:

|Typ|Standardwert|
|---------|------------------|
|Verweistyp|`null`|
|Beliebiger [integrierter integraler numerischer Typ](../builtin-types/integral-numeric-types.md)|0 (null)|
|Beliebiger [integrierter numerischer Gleitkommatyp](../builtin-types/floating-point-numeric-types.md)|0 (null)|
|[bool](bool.md)|`false`|
|[char](char.md)|`'\0'` (U+0000)|
|[enum](enum.md)|Der Wert, der vom Ausdruck `(E)0` erzeugt wird, bei dem `E` der Enumerationsbezeichner ist.|
|[struct](struct.md)|Der Wert, der erzeugt wird, indem alle Werttypfelder auf ihre Standardwerte festgelegt werden und alle Verweistypfelder auf `null`.|
|Ein [Werttyp, der NULL-Werte zulässt](../../programming-guide/nullable-types/index.md).|Eine Instanz, für die die <xref:System.Nullable%601.HasValue%2A>-Eigenschaft `false` und die <xref:System.Nullable%601.Value%2A>-Eigenschaft nicht definiert ist. Dieser Standardwert wird auch als *NULL*-Wert des Werttyps bezeichnet, der NULL-Werte zulässt.|

Verwenden Sie den [default-Operator](../operators/default.md), um wie im folgenden Beispiel den Standardwert eines Typs zu erzeugen:

```csharp
int a = default(int);
```

Ab C# 7.1 können Sie das [`default`-Literal](../operators/default.md#default-literal) verwenden, um eine Variable mit dem Standardwert des Typs zu initialisieren:

```csharp
int a = default;
```

Für eine Wertart generiert der implizite parameterlose Konstruktor auch den Standardwert des Typs, wie das folgende Beispiel zeigt:

```csharp-interactive
var n = new System.Numerics.Complex();
Console.WriteLine(n);  // output: (0, 0)
```

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md):

- [Standardwerte](~/_csharplang/spec/variables.md#default-values)
- [Standardkonstruktoren](~/_csharplang/spec/types.md#default-constructors)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Schlüsselwörter](index.md)
- [Tabelle integrierter Typen](built-in-types-table.md)
- [Konstruktoren](../../programming-guide/classes-and-structs/constructors.md)
