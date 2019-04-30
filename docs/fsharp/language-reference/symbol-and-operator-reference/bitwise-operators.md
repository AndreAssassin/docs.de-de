---
title: Bitweise Operatoren
description: Erfahren Sie, bis die bitweisen Operatoren, die in der Programmiersprache F# verfügbar sind.
ms.date: 07/20/2018
ms.openlocfilehash: 01c68be485525b49eb3121dfaea6dce0adfe3972
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61926294"
---
# <a name="bitwise-operators"></a>Bitweise Operatoren

In diesem Thema wird beschrieben, bitweise Operatoren, die in F# verfügbar sind.

## <a name="summary-of-bitwise-operators"></a>Zusammenfassung der Operatoren zur Bitmanipulation

Die folgende Tabelle beschreibt die bitweisen Operatoren, die für Unboxing integrale Typen in der Sprache F# unterstützt werden.

|Operator|Hinweise|
|--------|-----|
|`&&&`|Bitweise AND-Operator. Bits im Resultset haben den Wert 1, wenn die entsprechenden Bits in beide Quelloperanden den Wert 1 haben.|
|<code>&#124;&#124;&#124;</code>|Bitweiser OR-Operator. Bits im Resultset den Wert 1 haben, wenn beide entsprechenden Bits in der Quelle Operanden 1 sind.|
|`^^^`|Bitweiser exklusiver OR-Operator. Die Bits im Resultset haben den Wert 1, wenn Bits in der Quelloperanden ungleiche Werte aufweisen.|
|`~~~`|Operator für bitweise Negation. Dies ist ein unäroperator und erzeugt ein Ergebnis in dem alle 0 Bits in der Quelloperand in 1 Bit konvertiert werden, und alle 1-Bits in Bits 0 konvertiert.|
|`<<<`|Bitweiser Left Shift-Operator. Das Ergebnis ist, dass es sich bei der erste Operanden mit Bits durch die Anzahl der Bits in der zweite Operand nach links verschoben. Verschobene Position des höchstwertigen Bits werden nicht in der Position gedreht. Die am niedrigstwertigen Bits werden mit Nullen aufgefüllt. Der Typ des zweiten Arguments ist `int32`.|
|`>>>`|Bitweiser Rechtsschiebeoperator. Das Ergebnis ist der erste Operand mit Bits nach rechts verschoben, um die Anzahl der Bits im zweiten Operanden. Bits aus von der Position verschoben werden nicht in die Position des höchstwertigen gedreht. Für Typen ohne Vorzeichen werden die höchstwertigen Bits mit Nullen aufgefüllt. Für Typen mit Vorzeichen mit negativen Werten werden die höchstwertigen Bits mit denen aufgefüllt. Der Typ des zweiten Arguments ist `int32`.|

Die folgenden Typen können mit Operatoren zur Bitmanipulation verwendet werden: `byte`, `sbyte`, `int16`, `uint16`, `int32 (int)`, `uint32`, `int64`, `uint64`, `nativeint`, und `unativeint`.

## <a name="see-also"></a>Siehe auch

- [Symbol- und Operatorenreferenz](index.md)
- [Arithmetische Operatoren](arithmetic-operators.md)
- [Boolesche Operatoren](boolean-operators.md)