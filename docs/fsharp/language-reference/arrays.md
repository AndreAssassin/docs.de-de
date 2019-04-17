---
title: Arrays
description: Informationen Sie zum Erstellen und Verwenden von Arrays in der Programmiersprache F#.
ms.date: 05/16/2016
ms.openlocfilehash: 4a81a0994479ecd92b8556c4901fea23c3c0507b
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59610937"
---
# <a name="arrays"></a>Arrays

> [!NOTE]
> Mit dem API-Referenz-Link gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.

## <a name="creating-arrays"></a>Erstellen von Arrays

Sie können Arrays auf verschiedene Arten erstellen. Sie können ein kleines Array erstellen, indem Sie aufeinanderfolgende Werte zwischen auflisten `[|` und `|]` und durch Semikolons getrennt werden, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet1.fs)]

Sie können auch jedes Element in einer eigenen Zeile anordnen. In diesem Fall ist das Semikolontrennzeichen optional.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet2.fs)]

Der Typ der Arrayelemente wird von den verwendeten Literalen abgeleitet, und er muss konsistent sein. Somit verursacht der folgende Code einen Fehler, da 1.0 ein Gleitkommawert ist und 2 und 3 ganze Zahlen sind.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

Sie können Arrays mithilfe von Sequenzausdrücken erstellen. Im folgenden Beispiel wird ein Array aus den Quadraten von ganzen Zahlen zwischen 1 und 10 erstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet3.fs)]

Verwenden Sie `Array.zeroCreate`, um ein Array zu erstellen, dessen sämtliche Elemente mit 0 (null) initialisiert sind.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="accessing-elements"></a>Zugreifen auf Elemente

Sie können Elemente des Arrays zugreifen, mit dem Punktoperator (`.`) und eckige Klammern (`[` und `]`).

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet5.fs)]

Arrayindizes beginnen bei 0.

Der Zugriff auf Arrayelemente kann auch mit Slicenotation erfolgen, die es Ihnen ermöglicht, einen Teilbereich des Arrays anzugeben. Im Folgenden erhalten Sie Beispiele für Slicenotation.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet51.fs)]

Bei Verwendung von Slicenotation wird eine neue Kopie des Arrays erstellt.

## <a name="array-types-and-modules"></a>Arraytypen und Module

Alle F#-Arrays sind vom .NET Framework-Typ <xref:System.Array?displayProperty=nameWithType>. Daher unterstützen F#-Arrays alle in <xref:System.Array?displayProperty=nameWithType> verfügbaren Funktionen.

Das Bibliotheksmodul [ `Microsoft.FSharp.Collections.Array` ](https://msdn.microsoft.com/library/0cda8040-9396-40dd-8dcd-cf48542165a1) Operationen auf eindimensionalen Arrays unterstützt. Die Module `Array2D`, `Array3D` und `Array4D` enthalten Funktionen, die Operationen für Arrays mit zwei, drei bzw. vier Dimensionen unterstützen. Mit <xref:System.Array?displayProperty=nameWithType> können Sie Arrays mit einem Rang größer vier erstellen.

### <a name="simple-functions"></a>Einfache Funktionen

[`Array.get`](https://msdn.microsoft.com/library/dd93e85d-7e80-4d76-8de0-b6d45bcf07bc) Ruft ein Element ab. [`Array.length`](https://msdn.microsoft.com/library/0d775b6a-4a8f-4bd1-83e5-843b3251725f) Gibt die Länge eines Arrays. [`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Legt ein Element mit einem angegebenen Wert fest. Im folgenden Codebeispiel wird die Verwendung dieser Funktionen veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet9.fs)]

Die Ausgabe lautet wie folgt.

```
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Funktionen, die Arrays generieren

Mehrere Funktionen erstellen Arrays, ohne ein vorhandenes Array zu erfordern. [`Array.empty`](https://msdn.microsoft.com/library/c3694b92-1c16-4c54-9bf2-fe398fadce32) erstellt ein neues Array, das keine Elemente enthält. [`Array.create`](https://msdn.microsoft.com/library/e848c8d6-1142-4080-9727-8dacc26066be) erstellt ein Array mit einer angegebenen Größe aus, und legt alle Elemente mit angegebenen Werten. [`Array.init`](https://msdn.microsoft.com/library/ee898089-63b0-40aa-910c-5ae7e32f6665) erstellt ein Array unter Verwendung einer Dimensionen und eine Funktion, die die Elemente zu generieren. [`Array.zeroCreate`](https://msdn.microsoft.com/library/fa5b8e7a-1b5b-411c-8622-b58d7a14d3b2) erstellt ein Array, in dem alle Elemente auf den Wert für den Typ des Arrays initialisiert werden. Dieser Code demonstriert die Funktionen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet91.fs)]

Die Ausgabe lautet wie folgt.

```
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://msdn.microsoft.com/library/9d0202f1-1ea0-475e-9d66-4f8ccc3c5b5f) erstellt ein neues Array, das Elemente enthält, die aus einem vorhandenen Array kopiert werden. Beachten Sie, dass die Kopie eine flache Kopie ist, d. h., wenn der Elementtyp ein Verweistyp ist, wird nur der Verweis, nicht das zugrunde liegende Objekt kopiert. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet11.fs)]

Der obige Code gibt Folgendes aus:

```
[|Test1; Test2; |]
[|; Test2; |]
```

Die Zeichenfolge `Test1` wird nur im ersten Array angezeigt, da der Vorgang der Erstellung eines neuen Elements, den Verweis in `firstArray` überschreibt, aber sich nicht auf den ursprünglichen Verweis auf eine leere Zeichenfolge auswirkt, die immer noch im `secondArray` vorhanden ist. Die Zeichenfolge `Test2` wird in beiden Arrays angezeigt, da sich die `Insert`-Operation für den <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Typ auf das zugrundeliegende <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Objekt auswirkt, auf das in beiden Arrays verwiesen wird.

[`Array.sub`](https://msdn.microsoft.com/library/40fb12ba-41d7-4ef0-b33a-56727deeef9d) generiert ein neues Array aus einem Teilbereich eines Arrays an. Sie geben den Teilbereich an, indem Sie den Startindex und die Länge bereitstellen. Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.sub`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet12.fs)]

Die Ausgabe zeigt an, dass das Unterfeld bei Element "5" beginnt und 10 Elemente enthält.

```
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://msdn.microsoft.com/library/08836310-5036-4474-b9a2-2c73e2293911) ein neues Array erstellt, indem zwei vorhandene Arrays kombiniert.

Der folgende Code veranschaulicht **Array.append**.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet13.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://msdn.microsoft.com/library/f5c8a5e2-637f-44d4-b35c-be96a6618b09) Wählt Elemente eines Arrays in ein neues Array eingeschlossen werden sollen. Der folgende Code stellt `Array.choose` dar. Beachten Sie, dass der Elementtyp des Arrays nicht zum Typ des Werts passen muss, der im Optionstyp zurückgegeben wurde. In diesem Beispiel ist der Elementtyp `int`, und die Option ist das Ergebnis einer Polynomfunktion (`elem*elem - 1`) als Gleitkommazahl.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet14.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://msdn.microsoft.com/library/c3b60c3b-9455-48c9-bc2b-e88f0434342a) führt eine angegebene Funktion für jedes Arrayelement eines vorhandenen Arrays und erfasst die von der Funktion generierten Elemente und kombiniert diese Elemente in ein neues Array. Der folgende Code stellt `Array.collect` dar.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet15.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://msdn.microsoft.com/library/f7219b79-1ec8-4a25-96b1-edbedb358302) nimmt eine Sequenz von Arrays und kombiniert diese Elemente in ein einzelnes Array. Der folgende Code stellt `Array.concat` dar.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet16.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://msdn.microsoft.com/library/b885b214-47fc-4639-9664-b8c183a39ede) nimmt eine boolesche Bedingungsfunktion und generiert ein neues Array, das nur die Elemente des Eingabearrays enthält, für die die Bedingung erfüllt ist. Der folgende Code stellt `Array.filter` dar.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet17.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://msdn.microsoft.com/library/1bbf822c-763b-4794-af21-97d2e48ef709) generiert ein neues Array durch Umkehren der Reihenfolge eines vorhandenen Arrays an. Der folgende Code stellt `Array.rev` dar.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet18.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
"Hello world!"
```

Sie können problemlos Funktionen im Arraymodul, die Arrays zu transformieren, indem Sie mit dem Pipeline-Operator kombinieren (`|>`), wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet19.fs)]

Ausgabe:

```
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Mehrdimensionale Arrays

Ein mehrdimensionales Array kann erstellt werden, jedoch gibt es keine Syntax zum Schreiben eines mehrdimensionalen Arrayliterals. Verwenden Sie den Operator [ `array2D` ](https://msdn.microsoft.com/library/1d52503d-2990-49fc-8fd3-6b0e508aa236) um ein Array aus einer Sequenz von Sequenzen von Arrayelementen zu erstellen. Die Sequenzen können Array- oder Listenliterale sein. Im folgenden Code wird z. B. ein zweidimensionales Array erstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet20.fs)]

Sie können auch die Funktion [ `Array2D.init` ](https://msdn.microsoft.com/library/9de07e95-bc21-4927-b5b4-08fdec882c7b) zum Initialisieren von Arrays mit zwei Dimensionen und ähnliche Funktionen für Arrays mit drei und vier Dimensionen verfügbar sind. Diese Funktionen nehmen eine Funktion, die zum Erstellen der Elemente verwendet wird. Verwenden Sie zum Erstellen eines zweidimensionalen Arrays, die Elemente, die festlegen, die auf einen Anfangswert anstelle einer Funktion enthält die [ `Array2D.create` ](https://msdn.microsoft.com/library/36c9d980-b241-4a20-bc64-bcfa0205d804) arrays mit bis zu vier Dimensionen-Funktion, die auch für verfügbar ist. Im folgenden Codebeispiel wird die Erstellung eines Arrays von Arrays mit den gewünschten Elementen veranschaulicht, und dann wird mit `Array2D.init` das gewünschte zweidimensionale Array generiert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet21.fs)]

Arrayindizierung und das Aufteilen von Syntax in Slices werden für Arrays bis zu Rang 4 unterstützt. Wenn Sie einen Index in mehreren Dimensionen angeben, verwenden Sie Kommas zum Trennen die Indizes, wie im folgenden Codebeispiel dargestellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet22.fs)]

Der Typ eines zweidimensionalen Arrays wird als `<type>[,]` (z. B.,`int[,]`, `double[,]`) geschrieben, und der Typ eines dreidimensionalen Arrays wird als `<type>[,,]` usw. für Arrays mit mehr Dimensionen geschrieben.

Nur eine Teilmenge der Funktionen für eindimensionale Arrays ist auch für mehrdimensionale Arrays verfügbar. Weitere Informationen finden Sie unter [ `Collections.Array Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array-module-%5bfsharp%5d), [ `Collections.Array2D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array2d-module-%5bfsharp%5d), [ `Collections.Array3D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array3d-module-%5bfsharp%5d), und [ `Collections.Array4D Module` ](https://msdn.microsoft.com/visualfsharpdocs/conceptual/collections.array4d-module-%5bfsharp%5d).

### <a name="array-slicing-and-multidimensional-arrays"></a>Arraysegmentierung und mehrdimensionale Arrays

In einem zweidimensionalen Array (eine Matrix), können Sie eine Sub-Matrix extrahieren, indem Sie Bereiche angeben und Verwenden eines Platzhalters (`*`) Zeichen, ganze Zeilen oder Spalten anzugeben.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

Ab F# 3.1 können Sie ein mehrdimensionales Array in Unterarrays derselben oder einer niedrigeren Dimension zerlegen. Beispielsweise können Sie einen Vektor aus einer Matrix abrufen, indem Sie eine einzelne Zeile oder eine Spalte angeben.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

Sie können diese segmentierende Syntax für Typen verwenden, die die Elementzugriffsoperatoren und die überladenen `GetSlice`-Methoden implementieren. Beispielsweise erstellt der folgende Code einen Matrixtyp, der das F# 2D-Array umschließt, eine Elementeigenschaft implementiert, um Unterstützung für die Arrayindizierung bereitzustellen, und drei Versionen von `GetSlice` implementiert. Wenn Sie diesen Code als Vorlage für Ihre Matrixtypen verwenden können, können Sie alle in diesem Abschnitt beschriebenen Segmentierungsvorgänge verwenden.

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a>Boolesche Funktionen für Arrays

Die Funktionen [ `Array.exists` ](https://msdn.microsoft.com/library/8e47ad6c-c065-4876-8cb4-ec960ec3e5c9) und [ `Array.exists2` ](https://msdn.microsoft.com/library/2e384a6a-f99d-4e23-b677-250ffbc1dd8e) bzw. Testen von Elemente in einer oder zwei Arrays. Diese Funktionen akzeptieren eine Testfunktion und geben `true` zurück, wenn die Bedingung von einem Element (oder Elementpaaren für `Array.exists2`) erfüllt wird.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.exists` und `Array.exists2`. In diesen Beispielen werden neue Funktionen durch das Übernehmen von nur einem der Argumente, in diesen Fällen das Funktionsargument, erstellt.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet23.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```
true
false
false
true
```

Auf ähnliche Weise die Funktion [ `Array.forall` ](https://msdn.microsoft.com/library/d88f2cd0-fa7f-45cf-ac15-31eae9086cc4) testet ein Array, um zu bestimmen, ob jedes Element eine boolesche Bedingung erfüllt. Die Variation [ `Array.forall2` ](https://msdn.microsoft.com/library/c68f61a1-030c-4024-b705-c4768b6c96b9) führt die gleiche Aufgabe mithilfe einer booleschen Funktion, die Elemente zweier Arrays gleicher Länge umfasst. Im folgenden Code wird die Verwendung dieser Funktionen veranschaulicht.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet24.fs)]

Die Ausgabe dieser Beispiele lautet folgendermaßen.

```
false
true
true
false
```

### <a name="searching-arrays"></a>Durchsuchen von Arrays

[`Array.find`](https://msdn.microsoft.com/library/db6d920a-de19-4520-85a4-d83de77c1b33) nimmt eine boolesche Funktion und gibt das erste Element, das für die die Funktion zurückgibt `true`, oder löst eine <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> , wenn kein Element die Bedingung gefunden wird. [`Array.findIndex`](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) entspricht dem `Array.find`, außer dass der Index des Elements statt dem Element selbst zurückgegeben.

Der folgende Code sucht mithilfe von `Array.find` und `Array.findIndex` eine Zahl, die sowohl ein perfektes Quadrat als auch perfekter Cube ist.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet25.fs)]

Die Ausgabe lautet wie folgt.

```
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://msdn.microsoft.com/library/7bd65f6c-df77-454c-ac3a-6f7baecec9d9) entspricht dem `Array.find`, außer dass das Ergebnis ein Optionstyp ist und es gibt `None` , wenn kein Element gefunden wird. `Array.tryFind` sollte statt `Array.find` verwendet werden, wenn nicht bekannt ist, ob ein entsprechendes Element im Array vorhanden ist. Auf ähnliche Weise [ `Array.tryFindIndex` ](https://msdn.microsoft.com/library/da82f7fe-95e9-4fd5-a924-cd3c9d10618a) ähnelt [ `Array.findIndex` ](https://msdn.microsoft.com/library/5ae3a8f9-7b8f-44ea-a740-d5700f4d899f) mit dem Unterschied, dass der Optionstyp der Rückgabewert ist. Wenn kein Element gefunden wird, lautet die Option `None`.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.tryFind`. Dieser Code hängt vom vorherigen Code ab.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet26.fs)]

Die Ausgabe lautet wie folgt.

```
Found an element: 1
Found an element: 729
```

Verwendung [ `Array.tryPick` ](https://msdn.microsoft.com/library/72d45f85-037b-43a9-97fd-17239f72713e) Wenn Sie ein Element zusätzlich zu suchen, sie transformieren müssen. Das Ergebnis ist das erste Element, für das die Funktion das transformierte Element als Optionswert zurückgibt, oder `None`, wenn kein solches Element gefunden wird.

Im folgenden Code wird die Verwendung von `Array.tryPick` veranschaulicht: In diesem Fall werden statt eines Lambdaausdrucks mehrere lokale Hilfsfunktionen definiert, um den Code zu vereinfachen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet27.fs)]

Die Ausgabe lautet wie folgt.

```
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
```

### <a name="performing-computations-on-arrays"></a>Ausführen von Berechnungen für Arrays

Die [ `Array.average` ](https://msdn.microsoft.com/library/7029f2b9-91ea-41cb-be1b-466a5a0db20e) Funktion gibt den Durchschnitt jedes Elements in einem Array zurück. Sie ist auf Elementtypen beschränkt, die die exakte Division durch eine ganze Zahl unterstützen, wozu Gleitkommatypen aber keine ganzzahligen Typen gehören. Die [ `Array.averageBy` ](https://msdn.microsoft.com/library/e9d64609-06a3-48f0-bc07-226ab0f85c54) Funktion gibt den Durchschnitt der Ergebnisse des Aufrufs einer Funktion auf jedes Element zurück. Für ein Array eines ganzzahligen Typs können Sie `Array.averageBy` verwenden und für die Berechnung die Funktion jedes Element in einen Gleitkommatyp konvertieren lassen.

Verwendung [ `Array.max` ](https://msdn.microsoft.com/library/f03fbda0-fce6-40e2-a85d-79c9d81f710b) oder [ `Array.min` ](https://msdn.microsoft.com/library/d6b3da5f-bac0-4355-9846-4b72d95bc3fd) um die maximale oder minimale Element abzurufen, wenn der Elementtyp dies unterstützt. Auf ähnliche Weise [ `Array.maxBy` ](https://msdn.microsoft.com/library/18dbe7c5-482e-4766-8e01-12a76f847045) und [ `Array.minBy` ](https://msdn.microsoft.com/library/24091583-be78-4cc9-9fab-de6d7506af4f) ermöglichen einer Funktion, die zuerst ausgeführt werden, ggf. zur Transformation eines Typs, der Vergleich unterstützt.

[`Array.sum`](https://msdn.microsoft.com/library/4ffdb8c8-cd94-4b0b-9e5c-a7c9c17963c2) Fügt die Elemente eines Arrays hinzu und [ `Array.sumBy` ](https://msdn.microsoft.com/library/41698ba6-1adc-4169-8cc5-7a0e3f8de56b) Ruft eine Funktion für jedes Element und fügt die Ergebnisse zusammen.

Verwenden Sie zum Ausführen einer Funktion auf jedes Element in einem Array ohne zu speichern die Rückgabewerte [ `Array.iter` ](https://msdn.microsoft.com/library/94eba0f1-ecd7-459f-b89f-ed2a2923e516). Verwenden Sie für eine Funktion mit zwei Arrays gleicher Länge [ `Array.iter2` ](https://msdn.microsoft.com/library/018aa9b9-f186-4142-be8a-a62462794fdc). Wenn Sie auch ein Array mit den Ergebnissen der Funktion behalten müssen, verwenden Sie [ `Array.map` ](https://msdn.microsoft.com/library/38cbe824-0480-47be-85fd-df3afdd97a45) oder [ `Array.map2` ](https://msdn.microsoft.com/library/bb7aafe8-4a1f-45b9-92fc-1af9eafbea5c), die zwei Arrays zu einem Zeitpunkt verarbeitet.

Die Varianten [ `Array.iteri` ](https://msdn.microsoft.com/library/8bbe2ed4-ada7-4906-ac3e-cb09f9db6486) und [ `Array.iteri2` ](https://msdn.microsoft.com/library/c041b91f-6080-45b7-867b-2ed983a90405) ermöglichen dem Index des Elements, der Berechnung beteiligt sein; das gleiche gilt für [ `Array.mapi` ](https://msdn.microsoft.com/library/f7e45994-b0a1-49e6-8fb5-5641cea8fde4) und [ `Array.mapi2` ](https://msdn.microsoft.com/library/5edb33d2-47da-44e1-9290-40c00c47d5b0).

Die Funktionen [ `Array.fold` ](https://msdn.microsoft.com/library/5ed9dd3b-3694-4567-94d0-fd9a24474e09), [ `Array.foldBack` ](https://msdn.microsoft.com/library/1121a453-dead-4711-a0ca-cc147752989c), [ `Array.reduce` ](https://msdn.microsoft.com/library/fd62a985-89fe-4f49-a9d4-0c808ac6749d), [ `Array.reduceBack` ](https://msdn.microsoft.com/library/4fdd4cbe-2238-4c5c-b286-597a7e9036f9), [ `Array.scan` ](https://msdn.microsoft.com/library/f6893608-9146-450d-9ebb-a0016803fbb0), und [ `Array.scanBack` ](https://msdn.microsoft.com/library/7610f406-7a5c-41db-a0ca-8e2a2a4826ad) führen Algorithmen aus, die alle Elemente eines Arrays einschließen. Auf ähnliche Weise die Variationen [ `Array.fold2` ](https://msdn.microsoft.com/library/5c845087-d041-476e-8cc4-53ae6849ef79) und [ `Array.foldBack2` ](https://msdn.microsoft.com/library/aa51b405-df20-4c51-9998-a6530f7db862) führen Berechnungen für zwei Arrays.

Diese Funktionen zum Ausführen von Berechnungen entsprechen den Funktionen, mit dem gleichen Namen in der [listenmodul](https://msdn.microsoft.com/library/a2264ba3-2d45-40dd-9040-4f7aa2ad9788). Verwendungsbeispiele finden Sie unter [listet](lists.md).

### <a name="modifying-arrays"></a>Ändern von Arrays

[`Array.set`](https://msdn.microsoft.com/library/847edc0d-4dc5-4a39-98c7-d4320c60e790) Legt ein Element mit einem angegebenen Wert fest. [`Array.fill`](https://msdn.microsoft.com/library/c83c9886-81d9-44f9-a195-61c7b87f7df2) Legt einen Bereich von Elementen in einem Array mit einem angegebenen Wert fest. Das folgende Codebeispiel enthält ein Beispiel für `Array.fill`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/arrays/snippet28.fs)]

Die Ausgabe lautet wie folgt.

```
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Sie können [ `Array.blit` ](https://msdn.microsoft.com/library/675e13e4-7fb9-4e0d-a5be-a112830de667) einen Unterabschnitt eines Arrays in ein anderes Array kopieren.

### <a name="converting-to-and-from-other-types"></a>Konvertieren von Typen

[`Array.ofList`](https://msdn.microsoft.com/library/e7225239-f561-45a4-b0b5-69a1cdcae78b) erstellt ein Array aus einer Liste an. [`Array.ofSeq`](https://msdn.microsoft.com/library/6bedf5e0-4b22-46da-b09c-6aa09eff220c) erstellt ein Array aus einer Sequenz an. [`Array.toList`](https://msdn.microsoft.com/library/4deff724-0be4-4688-92e7-9d67a1097786) und [ `Array.toSeq` ](https://msdn.microsoft.com/library/ac28dbab-406c-4fe0-ab08-c1ce5e247af4) konvertieren vom Arraytyp in diese anderen Auflistungstypen.

### <a name="sorting-arrays"></a>Sortieren von Arrays

Verwendung [ `Array.sort` ](https://msdn.microsoft.com/library/c6679075-e7eb-463c-9be5-c89be140c312) , mithilfe der generischen Vergleichsfunktion ein Array zu sortieren. Verwenden [ `Array.sortBy` ](https://msdn.microsoft.com/library/144498dc-091d-4575-a229-c0bcbd61426b) an, die einen Wert generiert eine Funktion als bezeichnet ein *Schlüssel*, sortieren, indem Sie die generische Vergleichsfunktion auf den Schlüssel verwenden. Verwendung [ `Array.sortWith` ](https://msdn.microsoft.com/library/699d3638-4244-4f42-8496-45f53d43ce95) , wenn Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen möchten. `Array.sort`, `Array.sortBy` und `Array.sortWith` geben das sortierte Array als neues Array zurück. Die Varianten [ `Array.sortInPlace` ](https://msdn.microsoft.com/library/36f39947-8a88-4823-9e9b-e9d838d292e0), [ `Array.sortInPlaceBy` ](https://msdn.microsoft.com/library/7fb9d2dd-d461-4c67-8b43-b5c59fc12c3f), und [ `Array.sortInPlaceWith` ](https://msdn.microsoft.com/library/454f9e11-972d-47a6-a854-8031cb0c7b0b) anstatt eine neue Ressourcengruppe des vorhandenen Arrays zu ändern.

### <a name="arrays-and-tuples"></a>Arrays und Tupel

Die Funktionen [ `Array.zip` ](https://msdn.microsoft.com/library/23e086b8-b266-4db2-8b68-e88e6a8e2187) und [ `Array.unzip` ](https://msdn.microsoft.com/library/a529b47c-2e2b-4f79-ad44-c578432d2f48) Arrays von Tupelpaaren in Tupel von Arrays und umgekehrt zu konvertieren. [`Array.zip3`](https://msdn.microsoft.com/library/1745744a-d2ca-4c3e-b825-3f15d9f4000d) und [ `Array.unzip3` ](https://msdn.microsoft.com/library/bc3e6db0-f334-444f-8c30-813942880677) sind ähnlich, außer dass sie mit Tupeln von drei Elementen oder Tupeln von drei Arrays arbeiten.

## <a name="parallel-computations-on-arrays"></a>Parallele Berechnungen auf Arrays

Das Modul [ `Array.Parallel` ](https://msdn.microsoft.com/library/60f30b77-5af4-4050-9a5c-bcdb3f5cbb09) enthält Funktionen zum Ausführen paralleler Berechnungen für Arrays. Dieses Modul ist in Anwendungen nicht verfügbar, die auf Versionen vor Version 4 von .NET Framework abzielen.

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
