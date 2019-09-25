---
ms.openlocfilehash: 6643f64010332cf14d466cbba28a1c3cca671ac3
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117220"
---
### <a name="net-core-30-follows-unicode-best-practices-when-replacing-ill-formed-utf-8-byte-sequences"></a>.NET Core 3.0 befolgt bewährte Unicode-Methoden beim Ersetzen von falsch formatierten UTF-8-Bytesequenzen

Wenn die <xref:System.Text.UTF8Encoding>-Klasse während eines Byte-in-Zeichen-Transcodierungsvorgangs auf eine falsch formatierte UTF-8-Bytesequenz trifft, wird diese Sequenz durch das Zeichen „�“ (U+FFFD-ERSETZUNGSZEICHEN) in der Ausgabezeichenfolge ersetzt. .NET Core 3.0 unterscheidet sich von früheren Versionen von .NET Core und .NET Framework durch die Einhaltung der bewährten Unicode-Methoden für die Durchführung dieser Ersetzung während des Transcodierungsvorgangs.

Dies ist Teil einer größeren Maßnahme zur Verbesserung der UTF-8-Verarbeitung in .NET, auch bei den neuen Typen <xref:System.Text.Unicode.Utf8?displayProperty=nameWithType> und <xref:System.Text.Rune?displayProperty=nameWithType>. Der Typ <xref:System.Text.UTF8Encoding> wurde mit einem verbesserten Verfahren für die Fehlerbehandlung versehen, sodass die Ausgabe konsistent mit den neu eingeführten Typen generiert wird.

#### <a name="details"></a>Details

Ab .NET Core 3.0 führt die <xref:System.Text.UTF8Encoding>-Klasse bei der Transcodierung von Bytes in Zeichen Zeichenersetzung basierend auf bewährten Unicode-Methoden aus. Der verwendete Ersetzungsmechanismus wird durch [The Unicode Standard, Version 12.0, Abschnitt 3.9 (PDF)](https://www.unicode.org/versions/Unicode12.0.0/ch03.pdf) unter der Überschrift _U+FFFD Substitution of Maximum Subparts_ beschrieben.

Dieses Verhalten gilt _nur_, wenn die Eingabebytesequenz falsch formatierte UTF-8-Daten enthält. Außerdem gilt: Wenn die <xref:System.Text.UTF8Encoding>-Instanz mit `throwOnInvalidBytes: true` erstellt wurde (siehe [UTF8Encoding-Konstruktordokumentation] (<xref:System.Text.UTF8Encoding.%23ctor(System.Boolean,System.Boolean)>)), wird die `UTF8Encoding`-Instanz weiterhin bei ungültiger Eingabe ausgelöst, anstatt U+FFFD -Ersetzung auszuführen.

Das folgende Beispiel veranschaulicht die Auswirkung dieser Änderung mit einer ungültigen 3-Byte-Eingabe:

|Falsch formatierte 3-Byte-Eingabe|Ausgabe vor .NET Core 3.0|Ausgabe ab .NET Core 3.0|
|---|---|---|
| `[ ED A0 90 ]` | `[ FFFD FFFD ]` (2-Zeichen-Ausgabe)| `[ FFFD FFFD FFFD ]` (3-Zeichen-Ausgabe)|

Diese 3-Zeichen-Ausgabe ist die bevorzugte Ausgabe gemäß _Tabelle 3-9_ der oben genannten PDF-Datei zum Unicode-Standard.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Auf der Seite des Entwicklers ist keine Aktion erforderlich.

#### <a name="category"></a>Category (Kategorie)

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.UTF8Encoding.GetCharCount%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetChars%2A?displayProperty=nameWithType>
- <xref:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Text.UTF8Encoding.GetCharCount`
- `Overload:System.Text.UTF8Encoding.GetChars`
- `M:System.Text.UTF8Encoding.GetString(System.Byte[],System.Int32,System.Int32)`

-->

