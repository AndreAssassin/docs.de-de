---
title: 'Ausnahmen: Die invalidArg-Funktion'
description: Erfahren Sie, wie die F# 'InvalidArg'-Funktion generiert einen Argument-Ausnahmefehler.
ms.date: 05/16/2016
ms.openlocfilehash: 7fd8d48b80970dbbafc0c23a478b4ccf3490f3ee
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61996880"
---
# <a name="exceptions-the-invalidarg-function"></a>Ausnahmen: Die invalidArg-Funktion

Die `invalidArg` Funktion generiert einen Argument-Ausnahmefehler.

## <a name="syntax"></a>Syntax

```fsharp
invalidArg parameter-name error-message-string
```

## <a name="remarks"></a>Hinweise

Der Parametername in der vorherigen Syntax ist eine Zeichenfolge mit dem Namen des Parameters, deren Argument ungültig war. Die *Fehlermeldungszeichenfolge* ist eine Literalzeichenfolge oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft des Ausnahmeobjekts.

Die Ausnahme abrufen, indem `invalidArg` ist eine `System.ArgumentException` Ausnahme. Der folgende Code veranschaulicht die Verwendung von `invalidArg` eine Ausnahme ausgelöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6101.fs)]

Die Ausgabe ist Folgendes ein, gefolgt von einer stapelverfolgung (nicht dargestellt).

```
December
January
System.ArgumentException: Month parameter out of range.
```

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Die `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Die `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)
- [Ausnahmen: Die `failwith` Funktion](the-failwith-function.md)