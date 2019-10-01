---
title: Decimal-Datentyp (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Decimal
helpviewer_keywords:
- literal type characters [Visual Basic], D
- trailing zeros
- real numbers
- trailing 0 characters [Visual Basic]
- Decimal data type
- D literal type character [Visual Basic]
- decimals, Decimal data type
- 0 characters [Visual Basic], trailing
- data types [Visual Basic], assigning
- decimal keyword [Visual Basic]
- numbers [Visual Basic], real
- variable-precision numbers
- zeros, trailing
- '@ identifier type character'
- identifier type characters [Visual Basic], @
ms.assetid: 1d855b45-afe2-45b0-a623-96b6f63a43d5
ms.openlocfilehash: 892824b61cfb6a0172361d220c638cab0a78565d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700876"
---
# <a name="decimal-data-type-visual-basic"></a>Decimal-Datentyp (Visual Basic)

Enthält signierte 128-Bit-Werte (16 Byte), die 96-Bit (12-Byte)-ganzzahlige Zahlen darstellen, die durch eine Variablen Potenz von 10 skaliert werden. Der Skalierungsfaktor gibt die Anzahl der Ziffern rechts vom Dezimaltrennzeichen an. der Bereich reicht von 0 bis 28. Bei einer Skala von 0 (keine Dezimalstellen) ist der größte mögliche Wert +/-337 (+/-7.9228162514264337593543950335E + 28). Bei 28 Dezimalstellen ist der größte Wert +/-7.9228162514264337593543950335, und der kleinste Wert ungleich 0 (null) ist +/-0,0000000000000000000000000001 (+/-1E-28).

## <a name="remarks"></a>Hinweise

Der `Decimal`-Datentyp gibt die größte Anzahl von signifikanten Ziffern für eine Zahl an. Sie unterstützt bis zu 29 signifikante Ziffern und kann Werte über 7,9228 x 10 ^ 28 darstellen. Sie eignet sich besonders für Berechnungen, z. b. Finanz Weise, die eine große Anzahl von Ziffern erfordern, aber keine Rundungsfehler tolerieren können.

Der Standardwert von `Decimal` lautet 0.

## <a name="programming-tips"></a>Programmiertipps

- **Präziser.** `Decimal` ist kein Gleit Komma Datentyp. Die `Decimal`-Struktur enthält einen binären ganzzahligen Wert sowie ein Vorzeichen-und einen ganzzahligen Skalierungsfaktor, der angibt, welcher Teil des Werts ein Dezimal Bruch ist. Aus diesem Grund weisen `Decimal`-Zahlen eine präzisere Darstellung im Arbeitsspeicher auf als Gleit Komma Typen (`Single` und `Double`).

- **Leistung:** Der `Decimal`-Datentyp ist der langsamste Wert aller numerischen Typen. Vor dem Auswählen eines Datentyps sollten Sie die Wichtigkeit der Genauigkeit vor der Leistung abwägen.

- **Tet.** Der `Decimal`-Datentyp wird auf `Single` oder `Double` erweitert. Dies bedeutet, dass Sie `Decimal` in einen dieser Typen konvertieren können, ohne dass ein <xref:System.OverflowException?displayProperty=nameWithType>-Fehler auftritt.

- **Nachfolgende Nullen.** Visual Basic speichert nachfolgende Nullen nicht in einem `Decimal`-Literal. Allerdings behält eine `Decimal`-Variable alle nachfolgenden Nullen, die rechnerisch abgerufen wurden. Dies wird anhand des folgenden Beispiels veranschaulicht.

  ```vb
  Dim d1, d2, d3, d4 As Decimal
  d1 = 2.375D
  d2 = 1.625D
  d3 = d1 + d2
  d4 = 4.000D
  MsgBox("d1 = " & CStr(d1) & ", d2 = " & CStr(d2) &
        ", d3 = " & CStr(d3) & ", d4 = " & CStr(d4))
  ```

  Die Ausgabe von `MsgBox` im vorangehenden Beispiel lautet wie folgt:

  ```console
  d1 = 2.375, d2 = 1.625, d3 = 4.000, d4 = 4
  ```

- **Geben Sie Zeichen ein.** Durch Anhängen des Literaltypzeichens `D` an ein Literal wird der `Decimal`-Datentyp erzwungen. Durch Anhängen des Typkennzeichens `@` an einen beliebigen Bezeichner wird für diesen ebenfalls der `Decimal`-Datentyp erzwungen.

- **Frameworktyp.** Der entsprechende Typ in .NET Framework ist die <xref:System.Decimal?displayProperty=nameWithType>-Struktur.

## <a name="range"></a>Bereich
 Möglicherweise müssen Sie das Typzeichen "`D`" verwenden, um einer `Decimal`-Variablen oder-Konstante einen großen Wert zuzuweisen. Diese Anforderung liegt daran, dass der Compiler ein Literale als `Long` interpretiert, es sei denn, ein Literaltypzeichen folgt dem Literalzeichen, wie im folgenden Beispiel gezeigt.

```vb
Dim bigDec1 As Decimal = 9223372036854775807   ' No overflow.
Dim bigDec2 As Decimal = 9223372036854775808   ' Overflow.
Dim bigDec3 As Decimal = 9223372036854775808D  ' No overflow.
```

Die Deklaration für `bigDec1` erzeugt keinen Überlauf, da der zugewiesene Wert innerhalb des Bereichs für `Long` liegt. Der `Long`-Wert kann der Variablen `Decimal` zugewiesen werden.

Die Deklaration für "`bigDec2`" generiert einen Überlauf Fehler, da der zugewiesene Wert für `Long` zu groß ist. Da das numerische Literale nicht als `Long` interpretiert werden kann, kann es nicht der `Decimal`-Variablen zugewiesen werden.

Bei `bigDec3` löst das Literaltypzeichen `D` das Problem, indem der Compiler gezwungen wird, das Literale als `Decimal` statt als `Long` zu interpretieren.

## <a name="see-also"></a>Siehe auch

- <xref:System.Decimal?displayProperty=nameWithType>
- <xref:System.Decimal.%23ctor%2A?displayProperty=nameWithType>
- <xref:System.Math.Round%2A?displayProperty=nameWithType>
- [Datentypen](../../../visual-basic/language-reference/data-types/index.md)
- [Single-Datentyp](../../../visual-basic/language-reference/data-types/single-data-type.md)
- [Double-Datentyp](../../../visual-basic/language-reference/data-types/double-data-type.md)
- [Typkonvertierungsfunktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Konvertierung: Zusammenfassung](../../../visual-basic/language-reference/keywords/conversion-summary.md)
- [Effiziente Verwendung von Datentypen](../../../visual-basic/programming-guide/language-features/data-types/efficient-use-of-data-types.md)
