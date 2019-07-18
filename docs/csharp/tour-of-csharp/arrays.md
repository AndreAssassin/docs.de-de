---
title: C#-Arrays – Überblick über C#
description: Arrays sind der grundlegendste Auflistungstyp in der Sprache C#.
ms.date: 08/10/2016
ms.assetid: a440704c-9e88-4c75-97dd-bfe30ca0fb97
ms.openlocfilehash: 56a053ac8525d4c6c34592d6092f3f162cb04247
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65634607"
---
# <a name="arrays"></a>Arrays

Ein ***Array*** ist eine Datenstruktur, die eine Anzahl von Variablen enthält, auf die über berechnete Indizes zugegriffen wird. Die im Array enthaltenen Variablen, auch ***Elemente*** des Arrays genannt, weisen alle denselben Typ auf. Dieser Typ wird als ***Elementtyp*** des Arrays bezeichnet.

Arraytypen sind Verweistypen, und die Deklaration einer Arrayvariablen reserviert Speicher für einen Verweis auf eine Arrayinstanz. Die tatsächlichen Arrayinstanzen werden unter Verwendung des new-Operators zur Laufzeit dynamisch erstellt. Der new-Vorgang legt die ***Länge*** der neuen Arrayinstanz fest, die dann für die Lebensdauer der Instanz beibehalten wird. Die Indizes der Arrayelemente reichen von `0` bis `Length - 1`. Der `new`-Operator initialisiert die Elemente eines Arrays automatisch mit ihren Standardwerten. Dieser lautet z.B. für alle numerischen Typen 0 und für alle Verweistypen `null`.

Im folgenden Beispiel wird ein Array aus `int`-Elementen erstellt. Anschließend wird das Array initialisiert und die Inhalte des Arrays werden gedruckt.

[!code-csharp[ArraySample](../../../samples/snippets/csharp/tour/arrays/Program.cs#L3-L18)]

Mit diesem Beispiel wird ein ***eindimensionales Array*** erstellt und verwendet. C# unterstützt auch ***mehrdimensionale Arrays***. Die Anzahl von Dimensionen eines Arraytyps, auch als ***Rang*** des Arraytyps bezeichnet, ist 1 plus die Anzahl von Kommas, die innerhalb der eckigen Klammern des Arraytyps angegeben ist. Mit dem folgenden Beispiel wird respektive ein eindimensionales, ein zweidimensionales und ein dreidimensionales Array erstellt.

[!code-csharp[ArrayRank](../../../samples/snippets/csharp/tour/arrays/Program.cs#L24-L26)]

Das `a1`-Array enthält 10 Elemente, das `a2`-Array umfasst 50 (10 × 5) Elemente, und das `a3`-Array enthält 100 (10 × 5 × 2) Elemente.
Ein Array kann einen beliebigen Elementtyp verwenden, einschließlich eines Arraytyps.  Ein Array mit Elementen eines Arraytyps wird auch als ***verzweigtes Array*** bezeichnet, weil die Länge der Elementarrays nicht identisch sein muss. Im folgenden Beispiel wird ein Array aus `int`-Arrays zugewiesen:

[!code-csharp[ArrayAllocation](../../../samples/snippets/csharp/tour/arrays/Program.cs#L31-L34)]

In der ersten Zeile wird ein Array mit drei Elementen erstellt, das jeweils den Typ `int[]` und einen Anfangswert von `null` aufweist. In den folgenden Zeilen werden die drei Elemente mit Verweisen auf einzelne Arrayinstanzen unterschiedlicher Länge initialisiert.

Der new-Operator erlaubt es, die Anfangswerte der Arrayelemente unter Verwendung eines ***Arrayinitialisierers*** anzugeben, bei dem es sich um eine Liste von Ausdrücken zwischen den Trennzeichen `{` und `}` handelt. Mit dem folgenden Beispiel wird ein `int[]` mit drei Elementen zugewiesen und initialisiert.

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L39-L39)]

Beachten Sie, dass die Länge des Arrays aus der Anzahl von Ausdrücken zwischen { und } abgeleitet wird. Deklarationen lokaler Variablen und Felder können weiter verkürzt werden, sodass der Arraytyp nicht erneut aufgeführt werden muss.

[!code-csharp[ArrayInitialization](../../../samples/snippets/csharp/tour/arrays/Program.cs#L44-L44)]

Die zwei vorherigen Beispiele entsprechen dem folgenden:

[!code-csharp[ArrayAssignment](../../../samples/snippets/csharp/tour/arrays/Program.cs#L49-L53)]

>[!div class="step-by-step"]
>[Zurück](structs.md)
>[Weiter](interfaces.md)
