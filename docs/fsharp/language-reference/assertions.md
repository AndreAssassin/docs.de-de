---
title: Assertionen
description: Erfahren Sie, wie Sie mit der Ausdruck "assert" als eine Debugfunktion zum Testen von Ausdrücken in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: c2d97386e87e9b915da490a78fff9aedb9def616
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61703217"
---
# <a name="assertions"></a>Assertionen

Die `assert` Ausdruck ist eine Debugfunktion, die Sie verwenden können, um einen Ausdruck zu testen. Bei einem Fehler im Debugmodus generiert eine Assertion ein Dialogfeld „Systemfehler“.

## <a name="syntax"></a>Syntax

```fsharp
assert condition
```

## <a name="remarks"></a>Hinweise

Die `assert` Ausdruck weist Typ `bool -> unit`.

In der vorherigen Syntax *Bedingung* stellt einen booleschen Ausdruck, der getestet werden soll. Wenn der Ausdruck ergibt `true`, Ausführung wird fortgeführt, nicht betroffen. Ergibt die Auswertung `false`, wird ein Dialogfeld System Fehler generiert. Das Dialogfeld "Fehler" hat einer Beschriftung, die die Zeichenfolge enthält **Assertionsfehler**. Das Dialogfeld enthält eine stapelüberwachung, die angibt, in der Assertionsfehler aufgetreten ist.

Assertionsüberprüfung ist aktiviert, nur beim Kompilieren im Debugmodus befindet. d.h., wenn die Konstante `DEBUG` definiert ist. Im Projektsystem, standardmäßig die `DEBUG` Konstante wird definiert, in der Debug-Konfiguration jedoch nicht in der Releasekonfiguration.

Der Assertionsfehler kann nicht abgefangen werden, mithilfe von F# Ausnahmebehandlung.

> [!NOTE]
> Die `assert` Funktion löst in <xref:System.Diagnostics.Debug.Assert*?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Verwendung von der `assert` Ausdruck.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5401.fs)]

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)