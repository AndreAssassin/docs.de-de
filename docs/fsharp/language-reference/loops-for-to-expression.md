---
title: 'Schleifen: for...to-Ausdruck'
description: Finden Sie unter wie die F# for..-Ausdruck wird verwendet, um einen Bereich der Werte einer Schleifenvariablen in einer Schleife zu durchlaufen.
ms.date: 05/16/2016
ms.openlocfilehash: 5b7bb9bac659ddf1d457be1ce17e90a2593666de
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645246"
---
# <a name="loops-forto-expression"></a>Schleifen: for...to-Ausdruck

Die `for...to` Ausdruck wird verwendet, um einen Bereich der Werte einer Schleifenvariablen in einer Schleife zu durchlaufen.

## <a name="syntax"></a>Syntax

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a>Hinweise

Der Typ des Bezeichners wird abgeleitet, vom Typ des der *starten* und *Fertig stellen* Ausdrücke. Typen, die für diese Ausdrücke müssen es sich um 32-Bit-Ganzzahlen sein.

Obwohl technisch gesehen ist ein Ausdruck, `for...to` eher wie eine herkömmliche Anweisung in einem imperativen Programmiersprache. Der Rückgabetyp für die *Body-Ausdruck* muss `unit`. Die folgenden Beispiele zeigen verschiedene Verwendungsmöglichkeiten der der `for...to` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

Der obige Code gibt Folgendes aus.

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Schleifen: `for...in` Ausdruck](loops-for-in-expression.md)
- [Schleifen: `while...do` Ausdruck](loops-while-do-expression.md)
