---
ms.openlocfilehash: 375a6f57a867c2a11fe95753c1085d6d708db2bd
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2019
ms.locfileid: "72237365"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a>JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf

Ab .NET Core 3.0 Vorschau 8 enthalten die <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>-Methoden ein optionales <xref:System.Text.Encodings.Web.JavaScriptEncoder>-Argument.

#### <a name="change-description"></a>Änderungsbeschreibung

.Net Core 3.0 enthält den neuen Typ: xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>. Ab .NET Core 3.0 Vorschau 8 wurde die Signatur aller <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>-Methodenüberladungen geändert, um einen optionalen <xref:System.Text.Encodings.Web.JavaScriptEncoder>-Parameter einzubinden. Diese Änderung wurde vorgenommen, um einen anderen oder benutzerdefinierten Encoder zu ermöglichen.

Dies ist die Signatur der `Encode`-Methoden in .NET Core 3.0 Vorschau 7:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value);
        public static JsonEncodedText Encode(string value);
    }
}
```

Dies ist die Signatur der gleichen `Encode`-Methoden in .NET Core 3.0 Vorschau 8 oder höher:

```csharp
namespace System.Text.Json
{
    public readonly struct JsonEncodedText
    {
        public static JsonEncodedText Encode(ReadOnlySpan<byte> utf8Value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(ReadOnlySpan<char> value, JavaScriptEncoder encoder = null);
        public static JsonEncodedText Encode(string value, JavaScriptEncoder encoder = null);
    }
}
```

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0 Preview 8

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Dies ist nur ein binärer Breaking Change. Bei einer erneuten Kompilierung für .NET Core 3.0 Vorschau 8 oder eine höhere Version werden alle Laufzeitprobleme behoben.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->
