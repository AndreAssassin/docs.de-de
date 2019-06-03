---
title: Tabelle zur Formatierung numerischer Ergebnisse – C#-Referenz
ms.custom: seodec18
description: Erfahren Sie mehr über numerische Standardformatzeichenfolgen in C#
ms.date: 09/20/2018
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
ms.openlocfilehash: 0f2b5bc54a0e9055d64a95dc229eaadf66687b43
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421971"
---
# <a name="formatting-numeric-results-table-c-reference"></a>Tabelle zur Formatierung numerischer Ergebnisse (C#-Referenz)

Die folgende Tabelle weist die unterstützten Formatbezeichner zum Formatieren von numerischen Ergebnissen aus. Das formatierte Ergebnis in der letzten Spalte entspricht dem „en-US“ <xref:System.Globalization.CultureInfo>.

|Formatbezeichner|Beschreibung|Beispiele|Ergebnis|  
|----------------------|-----------------|--------------|------------|  
|C oder c|Währung|`string s = $"{2.5:C}";`<br /><br /> `string s = $"{-2.5:C}";`|$2.50<br /><br /> ($2.50)|  
|D oder d|Decimal|`string s = $"{25:D5}";`|00025|  
|E oder e|Exponentiell|`string s = $"{250000:E2}";`|2.50E + 005|  
|F oder f|Festkomma|`string s = $"{2.5:F2}";`<br /><br /> `string s = $"{2.5:F0}";`|2.50<br /><br /> 3|  
|G oder g|Allgemein|`string s = $"{2.5:G}";`|2.5|  
|N oder n|Numeric|`string s = $"{2500000:N}";`|2,500,000.00|  
|P oder p|Prozent|`string s = $"{0.25:P}";`|25.00%|  
|R oder r|Schleife|`string s = $"{2.5:R}";`|2.5|  
|X oder x|Hexadezimal|`string s = $"{250:X}";`<br /><br /> `string s = $"{0xffff:X}";`|FA<br /><br /> FFFF|  

## <a name="remarks"></a>Anmerkungen

Ein Formatbezeichner wird zum Erstellen einer Formatzeichenfolge verwendet. Die Formatzeichenfolge weist die folgende Form auf: `Axx`, wobei

- `A` der Formatbezeichner ist, der die Art der Formatierung steuert, die auf den numerischen Wert angewendet wird.
- `xx` der Genauigkeitsbezeichner ist, der sich auf die Anzahl der Stellen in der formatierten Ausgabe auswirkt. Der Wert der Genauigkeitsangabe liegt im Bereich 0–99.

Die Dezimal- („D“ oder „d“) und Hexadezimal- („X“ oder „x“) Formatbezeichner werden nur für integrale Typen unterstützt. Der Round-Trip-Formatbezeichner („R“ oder „r“) wird nur für die Typen <xref:System.Single>, <xref:System.Double> und <xref:System.Numerics.BigInteger> unterstützt.

Standardmäßige Zahlenformatzeichenfolgen werden von Folgendem unterstützt:

- Einigen Überladungen der `ToString`-Methode aller numerischen Typen. Sie können z.B. eine numerische Formatzeichenfolge an die <xref:System.Int32.ToString%28System.String%29?displayProperty=nameWithType>-Methode und <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29?displayProperty=nameWithType>-Methode übergeben.

- Beispielsweise das [zusammengesetzte Formatierungsfeature](../../../standard/base-types/composite-formatting.md) von .NET, das von der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode unterstützt wird.

- [Interpolierte Zeichenfolgen](../tokens/interpolated.md).

Weitere Informationen finden Sie unter [Numerische Standard-Formatzeichenfolgen](../../../standard/base-types/standard-numeric-format-strings.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Programmierhandbuch](../../programming-guide/index.md)
- [Formatierung von Typen](../../../standard/base-types/formatting-types.md)
- [Kombinierte Formatierung](../../../standard/base-types/composite-formatting.md)
- [Zeichenfolgeninterpolation](../tokens/interpolated.md)
- [string](string.md)
