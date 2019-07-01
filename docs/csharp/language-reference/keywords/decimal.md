---
title: decimal-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
ms.openlocfilehash: 7ad01f9e4f5a8b1a153b1ef306e9d6168335eb3d
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424307"
---
# <a name="decimal-c-reference"></a>decimal (C#-Referenz)

Das `decimal`-Schlüsselwort kennzeichnet einen 128-Bit-Datentyp. Im Vergleich zu anderen Gleitkommatypen verfügt der `decimal`-Typ über höhere Genauigkeit und einen kleineren Wertebereich. Dadurch eignet er sich für Finanz- und Währungskalkulationen. Der folgenden Tabelle können Sie den ungefähren Bereich und die Genauigkeit des `decimal`-Typs entnehmen.

|Typ|Ungefährer Bereich|Genauigkeit|.NET-Typ|
|----------|-----------------------|---------------|-------------------------|
|`decimal`|±1.0 × 10<sup>-28</sup> to ±7.9228 × 10<sup>28</sup>|28-29 signifikante Stellen|<xref:System.Decimal?displayProperty=nameWithType>|

Der Standardwert eines `decimal`-Objekts ist 0m.

## <a name="literals"></a>Literale

Wenn ein echtes numerisches Literal als `decimal` behandelt werden soll, verwenden Sie das Suffix m oder M. Beispiel:

```csharp
decimal myMoney = 300.5m;
```

Ohne das Suffix „m“ wird die Zahl als [double](../../../csharp/language-reference/keywords/double.md) behandelt, was zu einem Compilerfehler führt.

## <a name="conversions"></a>Konvertierungen

Die ganzzahligen Typen werden implizit in `decimal` konvertiert, und das Ergebnis wird als `decimal` ausgewertet. Aus diesem Grund können Sie eine decimal-Variable mit einem Ganzzahlliteral ohne das Suffix initialisieren. Beispiel:

```csharp
decimal myMoney = 300;
```

Es findet keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ statt. Folglich muss die Konvertierung zwischen diesen beiden Typen mittels einer Typumwandlung durchgeführt werden. Beispiel:

```csharp
decimal myMoney = 99.9m;
double x = (double)myMoney;
myMoney = (decimal)x;
```

`decimal`-Typen und numerische ganzzahlige Typen können auch gemeinsam im selben Ausdruck verwendet werden. Wenn Sie jedoch andere Gleitkomma- und `decimal`-Typen ohne Typumwandlung in einem Ausdruck verwenden, tritt ein Kompilierungsfehler auf.

Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).

Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).

## <a name="formatting-decimal-output"></a>Formatieren von Dezimalausgaben

Sie können die Ergebnisse mithilfe der `String.Format`-Methode oder der <xref:System.Console.Write%2A?displayProperty=nameWithType>-Methode formatieren, durch die `String.Format()` aufgerufen wird. Das Währungsformat wird mit der Standardwährungsformat-Zeichenfolge "C" oder "c" angegeben, wie in Beispiel 2 weiter unten in diesem Artikel dargestellt. Weitere Informationen zur `String.Format`-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=nameWithType>.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Compilerfehler aufgrund des Versuchs verursacht, [Double](../../../csharp/language-reference/keywords/double.md)- und `decimal`-Variablen hinzuzufügen.

```csharp
decimal dec = 0m;
double dub = 9;
// The following line causes an error that reads "Operator '+' cannot be applied to
// operands of type 'double' and 'decimal'"
Console.WriteLine(dec + dub);

// You can fix the error by using explicit casting of either operand.
Console.WriteLine(dec + (decimal)dub);
Console.WriteLine((double)dec + dub);
```

Das Ergebnis ist der folgende Fehler:

`Operator '+' cannot be applied to operands of type 'double' and 'decimal'`

In diesem Beispiel werden `decimal` und [int](../../../csharp/language-reference/builtin-types/integral-numeric-types.md) in demselben Ausdruck verwendet. Das Ergebnis wird als `decimal`-Typ ausgewertet.

[!code-csharp[csrefKeywordsTypes#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#6)]

## <a name="example"></a>Beispiel

In diesem Beispiel wird die Ausgabe mit der Währungsformatzeichenfolge formatiert. Beachten Sie, dass `x` gerundet wird, da mehr Dezimalstellen als im Format $0.99 vorhanden sind. Die Variable `y`, die die maximale Anzahl exakter Stellen darstellt, wird genau im richtigen Format angezeigt.

[!code-csharp[csrefKeywordsTypes#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#7)]

## <a name="c-language-specification"></a>C#-Sprachspezifikation

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Decimal>
- [C#-Referenz](../../../csharp/language-reference/index.md)
- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md)
- [Integrale Typen](../../../csharp/language-reference/builtin-types/integral-numeric-types.md)
- [Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md)
- [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)
- [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)
- [Standard Numeric Format Strings](../../../standard/base-types/standard-numeric-format-strings.md)
