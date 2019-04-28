---
title: Kopieren und Aktualisieren von Datensatzausdrücken
description: Informationen Sie zum Schreiben von 'kopieren und aktualisieren Datensatz Ausdruck', die einen vorhandenen Datensatz, Updates kopiert Felder angegeben und gibt den aktualisierten Datensatz zurück.
author: ChrSteinert
ms.date: 06/04/2016
ms.openlocfilehash: 5f9b13ebf6c456aff73872b7522d7670c068dd88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766050"
---
# <a name="copy-and-update-record-expressions"></a>Kopieren und Aktualisieren von Datensatzausdrücken

Ein *kopieren und Aktualisieren des Datensatzes Ausdruck* ist ein Ausdruck, der einen vorhandenen Datensatz kopiert werden, aktualisiert die angegebenen Felder und gibt den aktualisierten Datensatz zurück.

## <a name="syntax"></a>Syntax

```fsharp
{ record-name with
    updated-member-definitions }
```

## <a name="remarks"></a>Hinweise

Datensätze sind standardmäßig unveränderlich, sodass es kein Update einen vorhandenen Datensatz möglich ist. Um eine aktualisierte Datensatz alle Felder eines Datensatzes erstellen müsste erneut angegeben werden. Zur Vereinfachung dieser Aufgabe eine *kopieren und Aktualisieren des Datensatzes Ausdruck* kann verwendet werden. Dieser Ausdruck verwendet einen vorhandenen Datensatz, erstellt eine neue des gleichen Typs mit angegebenen Felder aus dem Ausdruck und das fehlende Feld, das dem angegebenen Ausdruck.
Dies kann nützlich sein, beim Kopieren eines vorhandenen Datensatzes, und möglicherweise einige Werte der Felder ändern.

Nehmen Sie z. B. einen neu erstellten Datensatz.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1905.fs)]

Würden Sie nur auf das Feld für diesen Datensatz aktualisieren Sie können die *kopieren und Aktualisieren des Datensatzes Ausdruck* wie folgt:

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet1906.fs)]

## <a name="see-also"></a>Siehe auch

- [Datensätze](records.md)
- [F#-Sprachreferenz](index.md)