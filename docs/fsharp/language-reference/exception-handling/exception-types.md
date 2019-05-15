---
title: Ausnahmetypen
description: Erfahren Sie, wie Sie definieren und Verwenden von F# Ausnahmetypen.
ms.date: 05/16/2016
ms.openlocfilehash: b7203dc042c7207bca95cfd0372790bfe52e0226
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645568"
---
# <a name="exception-types"></a>Ausnahmetypen

Es gibt zwei Kategorien von Ausnahmen in F#: Ausnahmetypen in .NET und F#-Typen. In diesem Thema wird beschrieben, wie Sie definieren und verwenden F# Ausnahmetypen.

## <a name="syntax"></a>Syntax

```fsharp
exception exception-type of argument-type
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax *Ausnahmetyp* ist der Name eines neuen F# Ausnahmetyp und *Argumenttyp* stellt den Typ eines Arguments, die beim Auslösen einer Ausnahme dieses Typs bereitgestellt werden kann. Sie können mehrere Argumente angeben, indem Sie verwenden einen Tupeltyp für *Argumenttyp*.

Eine typische Definition für eine F# Ausnahme der folgenden Darstellung ähnelt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5501.fs)]

Sie können eine Ausnahme dieses Typs generieren, mit der `raise` -Funktion wie folgt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5502.fs)]

Können Sie eine F# Ausnahmetyp direkt in die Filter in einem `try...with` Ausdruck wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet5503.fs)]

Der Typ der Ausnahme, die Sie definieren, mit der `exception` Schlüsselwort in F# ist eine neue Art, die von erbt `System.Exception`.

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmenhierarchie](https://msdn.microsoft.com/library/z4c5tckx.aspx)
