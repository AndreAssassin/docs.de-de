---
title: 'Ausnahmen: Die failwith-Funktion'
description: Erfahren Sie, wie die Funktion "Failwith" F#-Ausnahme generiert.
ms.date: 05/16/2016
ms.openlocfilehash: 05d385ddfc98a910779a6f59949a7187c38f0812
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772683"
---
# <a name="exceptions-the-failwith-function"></a>Ausnahmen: Die failwith-Funktion

Die `failwith` -Funktion generiert eine F# Ausnahme.

## <a name="syntax"></a>Syntax

```fsharp
failwith error-message-string
```

## <a name="remarks"></a>Hinweise

Die *Fehlermeldungszeichenfolge* in der vorherigen Syntax ist ein Zeichenfolgenliteral oder ein Wert vom Typ `string`. Es wird die `Message` -Eigenschaft der Ausnahme.

Die Ausnahme, die vom generierten `failwith` ist eine `System.Exception` Ausnahme aus, die ein Verweis ist mit dem Namen `Failure` in F# Code. Der folgende Code veranschaulicht die Verwendung von `failwith` eine Ausnahme ausgelöst.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-2/snippet6001.fs)]

## <a name="see-also"></a>Siehe auch

- [Ausnahmebehandlung](index.md)
- [Ausnahmetypen](exception-types.md)
- [Ausnahmen: Die `try...with` Ausdruck](the-try-with-expression.md)
- [Ausnahmen: Die `try...finally` Ausdruck](the-try-finally-expression.md)
- [Ausnahmen: Die `raise`-Funktion](the-raise-function.md)