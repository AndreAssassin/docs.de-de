---
title: Serialisieren und Deserialisieren von JSON mit C# -.NET
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 8025f84f2425f5b91e08b28ddb24d105d8c4d1a3
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159584"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>Serialisieren und Deserialisieren (Mars Hallen und Unmarshalling) von JSON in .NET

In diesem Artikel wird gezeigt, wie Sie den <xref:System.Text.Json>-Namespace zum Serialisieren und Deserialisieren in und aus JavaScript Object Notation (JSON) verwenden.

Die Anleitungen und der Beispielcode verwenden die Bibliothek direkt und nicht über ein Framework, wie z. b. [ASP.net Core](/aspnet/core/).

Der größte Teil des serialisierungsbeispielcodes legt <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> fest, um die JSON-Datei zu `true` (mit einzügkeit und Leerraum für die Lesbarkeit des Menschen). Für die Verwendung in der Produktion akzeptieren Sie in der Regel den Standardwert `false` für diese Einstellung.

## <a name="namespaces"></a>Namespaces

Der <xref:System.Text.Json>-Namespace enthält alle Einstiegspunkte und die Haupttypen. Der <xref:System.Text.Json.Serialization>-Namespace enthält Attribute und APIs für erweiterte Szenarien und Anpassungen, die für die Serialisierung und Deserialisierung spezifisch sind. Die in diesem Artikel gezeigten Codebeispiele erfordern `using`-Direktiven für einen oder beide Namespaces:

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

Attribute aus dem <xref:System.Runtime.Serialization>-Namespace werden derzeit in `System.Text.Json`nicht unterstützt.

## <a name="how-to-write-net-objects-to-json-serialize"></a>Schreiben von .NET-Objekten in JSON (Serialisieren)

Um JSON in eine Zeichenfolge oder eine Datei zu schreiben, müssen Sie die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode aufzurufen.

Im folgenden Beispiel wird JSON als Zeichenfolge erstellt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird synchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

Im folgenden Beispiel wird asynchroner Code verwendet, um eine JSON-Datei zu erstellen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

In den vorangehenden Beispielen wird der Typrückschluss für den serialisierten Typ verwendet. Eine Überladung von `Serialize()` nimmt einen generischen Typparameter an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Beispiel für die Serialisierung

Im Folgenden finden Sie eine Beispiel-Klasse, die Auflistungen und eine geschachtelte Klasse enthält:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

Die JSON-Ausgabe der Serialisierung einer Instanz des vorangehenden Typs sieht wie im folgenden Beispiel aus. Die JSON-Ausgabe wird standardmäßig minimiert:

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

Im folgenden Beispiel wird derselbe JSON-Code dargestellt, der formatiert ist (d. h. mit Leerraum und Einzug):

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>In UTF-8 serialisieren

Um zu UTF-8 zu serialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType>-Methode aufzurufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

Eine <xref:System.Text.Json.JsonSerializer.Serialize%2A> Überladung, die einen <xref:System.Text.Json.Utf8JsonWriter> annimmt, ist ebenfalls verfügbar.

Die Serialisierung in UTF-8 ist ungefähr 5-10 % schneller als die Verwendung der auf Zeichenfolgen basierten Methoden. Der Unterschied liegt darin, dass die Bytes (als UTF-8) nicht in Zeichenfolgen (UTF-16) konvertiert werden müssen.

## <a name="serialization-behavior"></a>Serialisierungsverhalten

* Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Sie können [Eigenschaften angeben, die ausgeschlossen werden sollen](#exclude-properties-from-serialization).
* Der [Standard Encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) schützt nicht-ASCII-Zeichen, HTML-abhängige Zeichen innerhalb des ASCII-Bereichs und Zeichen, die gemäß [der RFC 8259 JSON-Spezifikation](https://tools.ietf.org/html/rfc8259#section-7)mit Escapezeichen versehen werden müssen.
* Standardmäßig wird JSON minimiert. Sie können [den JSON-Code ziemlich ausdrucken](#serialize-to-formatted-json).
* Standardmäßig entspricht die Groß-/Kleinschreibung von JSON-Namen den .NET-Namen. Sie können die [JSON-namens](#customize-json-names-and-values)Schreibweise anpassen.
* Zirkuläre Verweise werden erkannt, und Ausnahmen werden ausgelöst.
* Felder werden derzeit ausgeschlossen.

Folgende Typen werden unterstützt:

* .Net-primitive, die JavaScript-primitiven zugeordnet sind, z. b. numerische Typen, Zeichen folgen und boolesche Werte.
* Benutzerdefinierte [Plain Old CLR Objects (POCOS)](https://stackoverflow.com/questions/250001/poco-definition).
* Eindimensionales und verzweigte Arrays (`ArrayName[][]`).
* `Dictionary<string,TValue>`, wo `TValue` `object`, `JsonElement`oder poco ist.
* Sammlungen aus den folgenden Namespaces.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um zusätzliche Typen zu verarbeiten oder Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>Lesen von JSON in .NET-Objekte (Deserialisieren)

Um eine Zeichenfolge oder eine Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode aufzurufen.

Im folgenden Beispiel wird JSON aus einer Zeichenfolge gelesen und eine Instanz der `WeatherForecast`-Klasse erstellt, die zuvor für das [serialisierungsbeispiel](#serialization-example)gezeigt wurde:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

Wenn Sie aus einer Datei mithilfe von synchronem Code deserialisieren möchten, lesen Sie die Datei in eine Zeichenfolge, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

Um mithilfe von asynchronem Code aus einer Datei zu deserialisieren, müssen Sie die <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A>-Methode abrufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>Aus UTF-8 deserialisieren

Um von UTF-8 zu deserialisieren, müssen Sie eine <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> Überladung aufrufen, die eine `Utf8JsonReader` oder eine `ReadOnlySpan<byte>`annimmt, wie in den folgenden Beispielen gezeigt. In den Beispielen wird davon ausgegangen, dass sich JSON in einem Bytearray namens jsonUtf8Bytes befindet.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Deserialisierungsverhalten

* Standardmäßig wird die Groß-/Kleinschreibung bei der Übereinstimmung von Eigenschaften Namen Sie können die [Groß-/Kleinschreibung](#case-insensitive-property-matching)nicht beachten.
* Wenn der JSON-Wert einen Wert für eine schreibgeschützte Eigenschaft enthält, wird der Wert ignoriert, und es wird keine Ausnahme ausgelöst.
* Die Deserialisierung für Verweis Typen ohne Parameter losen Konstruktor wird nicht unterstützt.
* Die Deserialisierung zu unveränderlichen Objekten oder schreibgeschützten Eigenschaften wird nicht unterstützt.
* Standardmäßig werden Enumerationen als Zahlen unterstützt. Enumerationsnamen können als Zeichen folgen [serialisiert](#enums-as-strings)werden.
* Felder werden nicht unterstützt.
* Standardmäßig lösen Kommentare oder nachfolgende Kommas in der JSON-Datei Ausnahmen aus. Sie können [Kommentare und nachfolgende Kommas zulassen](#allow-comments-and-trailing-commas).
* Der Standardwert für die [Maximale Tiefe](xref:System.Text.Json.JsonReaderOptions.MaxDepth) ist 64.

Sie können [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md) , um Funktionen bereitzustellen, die von den integrierten Konvertern nicht unterstützt werden.

## <a name="serialize-to-formatted-json"></a>Serialisieren in formatierten JSON-Code

Um die JSON-Ausgabe zu Recht drucken, legen Sie <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> auf `true`fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

Im Folgenden finden Sie eine Beispielklasse, die serialisiert werden soll, und die formatierte JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>Anpassen von JSON-Namen und -Werten

Standardmäßig sind Eigenschaftsnamen und Wörterbuchschlüssel in der JSON-Ausgabe unverändert, einschließlich der Groß-/Kleinschreibung. Enumerationswerte werden als Zahlen dargestellt. In diesem Abschnitt wird Folgendes beschrieben:

* [Anpassen einzelner Eigenschaftsnamen](#customize-individual-property-names)
* [Alle Eigenschaftsnamen in Camel-Case konvertieren](#use-camel-case-for-all-json-property-names)
* [Implementieren einer benutzerdefinierten Benennungs Richtlinie für Eigenschaften](#use-a-custom-json-property-naming-policy)
* [Wörterbuch Schlüssel in Kamel-Schreibweise konvertieren](#camel-case-dictionary-keys)
* [Enumerationszeichen in Zeichen folgen und Camel-Case konvertieren](#enums-as-strings)

Für andere Szenarien, die eine besondere Behandlung von JSON-Eigenschaftsnamen und-Werten erfordern, können Sie [benutzerdefinierte Konverter implementieren](system-text-json-converters-how-to.md).

### <a name="customize-individual-property-names"></a>Anpassen einzelner Eigenschaftsnamen

Um den Namen einzelner Eigenschaften festzulegen, verwenden Sie das [[jsonpropertyname]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) -Attribut.

Hier ist ein Beispiel für die Serialisierung und die daraus resultierende JSON-Datei:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

Der durch dieses Attribut festgelegte Eigenschaftsname:

* Gilt in beide Richtungen, für die Serialisierung und Deserialisierung
* Hat Vorrang vor Benennungsrichtlinien für Eigenschaften

### <a name="use-camel-case-for-all-json-property-names"></a>Camel-Case für alle JSON-Eigenschaftsnamen verwenden

Wenn Sie die Kamel-Schreibweise für alle JSON-Eigenschaftsnamen verwenden möchten, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

Die Camel-Case-Benennungsrichtlinie für Eigenschaften:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]` Attributen überschrieben. Aus diesem Grund ist der Name der JSON-Eigenschaft `Wind` im Beispiel nicht Camel Case.

### <a name="use-a-custom-json-property-naming-policy"></a>Verwenden einer benutzerdefinierten Benennungsrichtlinie für JSON-Eigenschaften

Um eine benutzerdefinierte JSON-Benennungs Richtlinie zu verwenden, erstellen Sie eine Klasse, die von <xref:System.Text.Json.JsonNamingPolicy> abgeleitet ist, und überschreiben Sie die <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A>-Methode, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

Legen Sie dann die <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>-Eigenschaft auf eine Instanz Ihrer Benennungs Richtlinien Klasse fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

Im Folgenden finden Sie eine Beispielklasse zum Serialisieren und die JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

Die Benennungsrichtlinie für JSON-Eigenschaften:

* Gilt für die Serialisierung und Deserialisierung.
* Wird von `[JsonPropertyName]` Attributen überschrieben. Aus diesem Grund ist der JSON-Eigenschaftsname `Wind` im Beispiel nicht Großbuchstaben.

### <a name="camel-case-dictionary-keys"></a>Camel-Case Wörterbuchschlüssel

Wenn eine Eigenschaft eines zu serialisierenden Objekts vom Typ `Dictionary<string,TValue>`ist, können die `string` Schlüssel in die Kamel-Schreibweise konvertiert werden. Legen Sie zu diesem Zweck <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> auf `JsonNamingPolicy.CamelCase`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

Das Serialisieren eines Objekts mit einem Wörterbuch mit dem Namen `TemperatureRanges`, das Schlüssel-Wert-Paare `"ColdMinTemp", 20` und `"HotMinTemp", 40` hat, führt zu einer JSON-Ausgabe wie im folgenden Beispiel:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

Die Camel-Case-Benennungsrichtlinie für Wörterbuchschlüssel gilt nur für die Serialisierung. Wenn Sie ein Wörterbuch deserialisieren, entsprechen die Schlüssel der JSON-Datei, auch wenn Sie `JsonNamingPolicy.CamelCase` für die `DictionaryKeyPolicy`angeben.

### <a name="enums-as-strings"></a>Enumerationen als Zeichenfolgen

Standardmäßig werden Enumerationen als Zahlen serialisiert. Verwenden Sie die <xref:System.Text.Json.Serialization.JsonStringEnumConverter>, um Enumerationsnamen als Zeichen folgen zu serialisieren.

Nehmen Sie beispielsweise an, Sie müssen die folgende Klasse serialisieren, die über eine Enumeration verfügt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

Wenn die Zusammenfassung `Hot`ist, hat die serialisierte JSON standardmäßig den numerischen Wert 3:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

Der folgende Beispielcode serialisiert die Enumerationsnamen anstelle der numerischen Werte und konvertiert die Namen in die Camel-Case-Schreibweise:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

Der resultierende JSON-Code sieht wie im folgenden Beispiel aus:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

Enumerationsnamen-Zeichenfolgen können ebenfalls deserialisiert werden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Eigenschaften von der Serialisierung ausschließen

Standardmäßig werden alle öffentlichen Eigenschaften serialisiert. Wenn Sie möchten, dass einige von ihnen nicht in der JSON-Ausgabe angezeigt werden, haben Sie mehrere Möglichkeiten. In diesem Abschnitt wird erläutert, wie verschiedene Dinge ausgeschlossen werden können:

* [Einzelne Eigenschaften](#exclude-individual-properties)
* [Alle schreibgeschützten Eigenschaften](#exclude-all-read-only-properties)
* [Alle NULL-Wert-Eigenschaften](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>Einzelne Eigenschaften ausschließen

Verwenden Sie das Attribut [[jsonignore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) , um einzelne Eigenschaften zu ignorieren.

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>Alle schreibgeschützten Eigenschaften ausschließen

Eine Eigenschaft ist schreibgeschützt, wenn Sie einen öffentlichen Getter, aber keinen öffentlichen Setter enthält. Um alle schreibgeschützten Eigenschaften auszuschließen, legen Sie den <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

Hier ist ein Beispiel für die Serialisierung und JSON-Ausgabe:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

Diese Option gilt nur für die Serialisierung. Während der Deserialisierung werden schreibgeschützte Eigenschaften standardmäßig ignoriert.

### <a name="exclude-all-null-value-properties"></a>Alle Eigenschaften mit NULL-Wert ausschließen

Um alle NULL-Wert Eigenschaften auszuschließen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues>-Eigenschaft auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

Im folgenden finden Sie ein Beispiel Objekt für die Serialisierung und JSON-Ausgabe:

|Eigenschaft |Wert  |
|---------|---------|
| Datum    | 01.08.2019 00:00:00 -07:00|
| TemperatureCelsius| 25 |
| Zusammenfassung| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

Diese Einstellung gilt für die Serialisierung und Deserialisierung. Informationen zu den Auswirkungen auf die Deserialisierung finden Sie unter [Ignorieren von NULL beim Deserialisieren](#ignore-null-when-deserializing).

## <a name="customize-character-encoding"></a>Zeichencodierung anpassen

Standardmäßig schützt der Serialisierer alle Nicht-ASCII-Zeichen.  Das heißt, Sie ersetzt Sie durch `\uxxxx`, wobei `xxxx` der Unicode-Code des Zeichens ist.  Wenn die `Summary`-Eigenschaft z. b. auf Cyrillic-"-Eigenschaft" festgelegt ist, wird das `WeatherForecast` Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>Serialisieren von Sprachzeichensätzen

Wenn Sie die Zeichensätze mindestens einer Sprache ohne Escapezeichen serialisieren möchten, müssen Sie beim Erstellen einer Instanz von <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>[Unicode-Bereiche](xref:System.Text.Unicode.UnicodeRanges) angeben, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

Mit diesem Code werden kyrillische und griechische Zeichen nicht geschützt. Wenn die `Summary`-Eigenschaft auf Cyrillic--,-festgelegt ist, wird das `WeatherForecast`-Objekt wie in diesem Beispiel gezeigt serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

Verwenden Sie <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>, um alle sprach Sätze ohne Escapezeichen zu serialisieren.

### <a name="serialize-specific-characters"></a>Serialisieren bestimmter Zeichen

Alternativ können Sie einzelne Zeichen angeben, die Sie zulassen möchten, ohne dass sie geschützt werden. Im folgenden Beispiel werden nur die ersten zwei Zeichen von "жарко" serialisiert:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

Im Folgenden finden Sie ein Beispiel für die JSON-Ausgabe, die durch den vorangehenden Code generiert wird:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>Alle Zeichen serialisieren

Um das Escapezeichen zu minimieren, können Sie <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>verwenden, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> Im Vergleich zum Standard-Encoder ist der `UnsafeRelaxedJsonEscaping` Encoder eher für das Zulassen von Zeichen ohne Escapezeichen zulässig:
>
> * Es werden keine HTML-sensiblen Zeichen wie `<`, `>`, `&`und `'`mit Escapezeichen versehen.
> * Er bietet keine zusätzlichen Schutzmaßnahmen vor XSS-oder Informations Offenlegungs Angriffen, wie z. b. solche, die sich aus dem Client und dem Server ergeben könnten, die auf dem *CharSet*nicht einverstanden sind.
>
> Verwenden Sie den unsicheren Encoder nur dann, wenn bekannt ist, dass der Client die resultierende Nutzlast als UTF-8-codiertes JSON-Format interpretiert. Sie können Sie beispielsweise verwenden, wenn der Server den Antwortheader `Content-Type: application/json; charset=utf-8`sendet. Gestatten Sie niemals, dass die Roh`UnsafeRelaxedJsonEscaping` Ausgabe in eine HTML-Seite oder ein `<script>` Element ausgegeben wird.

## <a name="serialize-properties-of-derived-classes"></a>Serialisieren von Eigenschaften abgeleiteter Klassen

Die Serialisierung einer polymorphen Typhierarchie wird nicht unterstützt. Wenn eine Eigenschaft beispielsweise als eine Schnittstelle oder eine abstrakte Klasse definiert ist, werden nur die Eigenschaften, die für die Schnittstelle oder die abstrakte Klasse definiert sind, serialisiert, auch wenn der Lauf Zeittyp über zusätzliche Eigenschaften verfügt. Die Ausnahmen für dieses Verhalten werden in diesem Abschnitt erläutert.

Nehmen Sie beispielsweise an, Sie verfügen über eine `WeatherForecast`-Klasse und eine abgeleitete Klasse `WeatherForecastDerived`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

Angenommen, das Typargument der `Serialize` Methode zum Zeitpunkt der Kompilierung ist `WeatherForecast`:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

In diesem Szenario wird die `WindSpeed`-Eigenschaft nicht serialisiert, auch wenn das `weatherForecast`-Objekt tatsächlich ein `WeatherForecastDerived`-Objekt ist. Es werden nur die Eigenschaften der Basisklasse serialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

Dieses Verhalten soll dabei helfen, das versehentliche Verfügbarmachen von Daten in einem abgeleiteten, von der Laufzeit erstellten Typ zu verhindern.

Verwenden Sie einen der folgenden Ansätze, um die Eigenschaften des abgeleiteten Typs im vorherigen Beispiel zu serialisieren:

* Aufrufen einer Überladung von <xref:System.Text.Json.JsonSerializer.Serialize%2A>, mit der Sie den Typ zur Laufzeit angeben können:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* Deklarieren Sie das Objekt, das als `object`serialisiert werden soll.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

Im vorherigen Beispielszenario bewirken beide Ansätze, dass die `WindSpeed`-Eigenschaft in der JSON-Ausgabe enthalten ist:

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> Diese Ansätze bieten polymorphe Serialisierung nur für das Stamm Objekt, das serialisiert werden soll, und nicht für die Eigenschaften dieses Stamm Objekts.

Sie können die polymorphe Serialisierung für Objekte auf niedrigerer Ebene erhalten, wenn Sie Sie als Typ `object`definieren. Angenommen, die `WeatherForecast`-Klasse verfügt über eine Eigenschaft mit dem Namen `PreviousForecast`, die als Typ `WeatherForecast` oder `object`definiert werden kann:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

Wenn die `PreviousForecast`-Eigenschaft eine Instanz von `WeatherForecastDerived`enthält:

* Die JSON-Ausgabe der Serialisierung `WeatherForecastWithPrevious` **enthält keine** `WindSpeed`.
* Die JSON-Ausgabe der Serialisierung `WeatherForecastWithPreviousAsObject` **enthält** `WindSpeed`.

Um `WeatherForecastWithPreviousAsObject`zu serialisieren, ist es nicht erforderlich, `Serialize<object>` oder `GetType` aufzurufen, da das Stamm Objekt nicht das Objekt ist, das möglicherweise ein abgeleiteter Typ ist. Im folgenden Codebeispiel wird weder `Serialize<object>` noch `GetType`aufgerufen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

Der vorangehende Code serialisiert `WeatherForecastWithPreviousAsObject`ordnungsgemäß:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

Der gleiche Ansatz zum Definieren von Eigenschaften als `object` funktioniert mit Schnittstellen. Angenommen, Sie haben die folgende Schnittstelle und Implementierung, und Sie möchten eine Klasse mit Eigenschaften serialisieren, die Implementierungs Instanzen enthalten:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

Wenn Sie eine Instanz von `Forecasts`serialisieren, zeigt nur `Tuesday` die `WindSpeed`-Eigenschaft an, da `Tuesday` als `object`definiert ist:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

Das folgende Beispiel zeigt die JSON-Datei, die sich aus dem vorangehenden Code ergibt:

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

Weitere Informationen zur polymorphen **Serialisierung**und Informationen zur **Deserialisierung**finden [Sie unter Migrieren von "newtonsoft. JSON" zu "System. Text. JSON](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)".

## <a name="allow-comments-and-trailing-commas"></a>Kommentare und nachfolgende Kommas zulassen

Standardmäßig sind Kommentare und nachfolgende Kommas in JSON nicht zulässig. Um Kommentare im JSON-Code zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType>-Eigenschaft auf `JsonCommentHandling.Skip`fest.
Um nachfolgende Kommas zuzulassen, legen Sie die <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType>-Eigenschaft auf `true`fest. Im folgenden Beispiel wird gezeigt, wie Sie beides zulassen:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie ein Beispiel für JSON mit Kommentaren und einem nachfolgenden Komma:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>Groß-/Kleinschreibung bei Eigenschaftsnamen ignorieren

Standardmäßig wird bei der Deserialisierung darauf geachtet, dass die Groß-/Kleinschreibung der Eigenschaftsnamen zwischen JSON und dem Zielobjekt übereinstimmt. Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> auf `true`fest:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

Im Folgenden finden Sie eine Beispiel-JSON-Datei mit Camel-Case Namen. Sie kann in den folgenden Typ deserialisiert werden, der über Pascal-Case-Eigenschaftsnamen verfügt.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>Behandeln von JSON-Überlauf

Während der Deserialisierung erhalten Sie möglicherweise Daten im JSON-Code, der nicht durch Eigenschaften des Zieltyps dargestellt wird. Angenommen, Ihr Zieltyp lautet:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Der JSON-Code, der deserialisiert werden soll, lautet wie folgt:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Wenn Sie den JSON-Code deserialisieren, der in den angezeigten Typ angezeigt wird, sind die Eigenschaften `DatesAvailable` und `SummaryWords` nicht mehr vorhanden und gehen verloren. Um zusätzliche Daten wie diese Eigenschaften zu erfassen, wenden Sie das [jsonextensiondata](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) -Attribut auf eine Eigenschaft vom Typ `Dictionary<string,object>` oder `Dictionary<string,JsonElement>`an:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

Wenn Sie den zuvor gezeigten JSON-Code in diesen Beispieltyp deserialisieren, werden die zusätzlichen Daten zu Schlüssel-Wert-Paaren der `ExtensionData`-Eigenschaft:

|Eigenschaft |Wert  |Hinweise  |
|---------|---------|---------|
| Datum    | 01.08.2019 00:00:00 -07:00||
| TemperatureCelsius| 0 | Unterscheidung nach Groß-/Kleinschreibung (`temperatureCelsius` im JSON-Code), sodass die-Eigenschaft nicht festgelegt ist. |
| Zusammenfassung | Hohe Auslastung ||
| ExtensionData | TemperatureCelsius: 25 |Da die Groß-/Kleinschreibung nicht entsprach, ist diese JSON-Eigenschaft ein zusätzliches und wird zu einem Schlüssel-Wert-Paar im Wörterbuch.|
|| Datesavailable:<br>  01.08.2019 00:00:00 -07:00<br>8/2/2019 12:00:00 Uhr-07:00 |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|
| |Summarywords:<br>Toll<br>Windy<br>Feu |Die zusätzliche Eigenschaft aus dem JSON-Code wird zu einem Schlüssel-Wert-Paar, wobei ein Array als Wertobjekt fungiert.|

Wenn das Zielobjekt serialisiert wird, werden die Schlüssel-Wert-Paare der Erweiterungsdaten zu JSON-Eigenschaften, genauso wie sie im eingelesenen JSON-Code waren:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

Beachten Sie, dass der `ExtensionData`-Eigenschaftsname nicht im JSON-Code angezeigt wird. Durch dieses Verhalten kann der JSON-Code einen Roundtrip durchführen, ohne dass zusätzliche Daten verloren gehen, die andernfalls nicht deserialisiert werden.

## <a name="ignore-null-when-deserializing"></a>NULL beim Deserialisieren ignorieren

Wenn eine Eigenschaft in JSON NULL ist, wird die entsprechende Eigenschaft im Zielobjekt standardmäßig auf NULL festgelegt. In einigen Szenarios hat die Zieleigenschaft möglicherweise einen Standardwert, und Sie möchten nicht, dass ein NULL-Wert den Standardwert überschreibt.

Nehmen Sie beispielsweise an, der folgende Code stellt das Zielobjekt dar:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

Angenommen, der folgende JSON-Code wird deserialisiert:

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Nach der Deserialisierung ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault`-Objekts NULL.

Um dieses Verhalten zu ändern, legen Sie <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> auf `true`fest, wie im folgenden Beispiel gezeigt:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

Bei dieser Option ist die `Summary`-Eigenschaft des `WeatherForecastWithDefault` Objekts der Standardwert "keine Zusammenfassung" nach der Deserialisierung.

NULL-Werte in JSON werden nur ignoriert, wenn sie gültig sind. NULL-Werte für Werttypen, die keine NULL-Werte zulassen, verursachen Ausnahmen.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter und JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> ist eine leistungsstarke, niedrige und vorwärts gerichtete Funktion für UTF-8-codierten JSON-Text, der aus einem `ReadOnlySpan<byte>` oder `ReadOnlySequence<byte>`gelesen wird. Der `Utf8JsonReader` ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Parser und deserialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonReader` unter dem Cover.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> ist eine hochleistungsfähige Methode zum Schreiben von UTF-8-codiertem JSON-Text aus gängigen .NET-Typen wie `String`, `Int32`und `DateTime`. Der Writer ist ein Typ auf niedriger Ebene, der zum Erstellen von benutzerdefinierten Serialisierern verwendet werden kann. Die <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>-Methode verwendet `Utf8JsonWriter` unter dem Cover.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName> bietet die Möglichkeit, mit `Utf8JsonReader`ein Schreib geschütztes Dokumentobjektmodell (DOM) zu erstellen. Das DOM bietet wahlfreien Zugriff auf Daten in einer JSON-Nutzlast. Auf die JSON-Elemente, aus denen sich die Nutzlast zusammensetzt, kann über den <xref:System.Text.Json.JsonElement> Typ zugegriffen werden. Der `JsonElement`-Typ stellt Array-und Objekt Enumeratoren zusammen mit APIs bereit, um JSON-Text in allgemeine .NET-Typen zu konvertieren. `JsonDocument` macht eine <xref:System.Text.Json.JsonDocument.RootElement>-Eigenschaft verfügbar.

In den folgenden Abschnitten wird gezeigt, wie diese Tools zum Lesen und Schreiben von JSON verwendet werden.

## <a name="use-jsondocument-for-access-to-data"></a>Verwenden von JsonDocument für den Zugriff auf Daten

Im folgenden Beispiel wird gezeigt, wie Sie die <xref:System.Text.Json.JsonDocument>-Klasse für den zufälligen Zugriff auf Daten in einer JSON-Zeichenfolge verwenden:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

Der vorangehende Code:

* Geht davon aus, dass der zu analysierende JSON-Code eine Zeichenfolge namens `jsonString`
* Berechnet eine durchschnittliche Qualität für Objekte in einem `Students` Array mit einer `Grade`-Eigenschaft.
* Weist eine Standardnote von 70 für Studenten zu, die keine Note haben
* Zählt Schüler und Studenten durch Inkrementieren einer `count` Variablen bei jeder Iterationen. Eine Alternative besteht darin, <xref:System.Text.Json.JsonElement.GetArrayLength%2A>aufzurufen, wie im folgenden Beispiel gezeigt:

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

Im Folgenden finden Sie ein Beispiel für die JSON-Zeichenfolge, die von diesem Code verarbeitet wird:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>Verwenden von jsondocument zum Schreiben von JSON

Im folgenden Beispiel wird gezeigt, wie JSON aus einem <xref:System.Text.Json.JsonDocument>geschrieben wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

Der vorangehende Code:

* Liest eine JSON-Datei, lädt die Daten in eine `JsonDocument`und schreibt formatierte (hübsch gedruckte) JSON-Daten in eine Datei.
* Verwendet <xref:System.Text.Json.JsonDocumentOptions>, um anzugeben, dass Kommentare in der JSON-Eingabe zulässig sind, aber ignoriert werden.
* Wenn Sie fertig sind, ruft <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> für den Writer auf. Eine Alternative besteht darin, den Writer automatisch flushen zu lassen, wenn er verworfen wird.

Im Folgenden finden Sie ein Beispiel für eine JSON-Eingabe, die durch den Beispielcode verarbeitet werden soll:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

Das Ergebnis ist die folgende formatierte JSON-Ausgabe:

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Utf8JsonWriter verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonWriter>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Utf8JsonReader verwenden

Im folgenden Beispiel wird gezeigt, wie die <xref:System.Text.Json.Utf8JsonReader>-Klasse verwendet wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

Der vorangehende Code geht davon aus, dass es sich bei der `jsonUtf8` Variable um ein Bytearray handelt, das gültige JSON-Codierung als UTF-8 enthält

### <a name="filter-data-using-utf8jsonreader"></a>Filtern von Daten mithilfe von Utf8JsonReader

Im folgenden Beispiel wird gezeigt, wie eine Datei synchron gelesen und nach einem Wert gesucht wird:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

Der vorangehende Code:

* Geht davon aus, dass der JSON-Code ein Array von Objekten enthält und jedes Objekt eine "name"-Eigenschaft vom Typ "String" enthalten kann.
* Zählt Objekte und "Name"-Eigenschaftswerte, die mit "University" enden.
* Geht davon aus, dass die Datei UTF-16-codiert ist, und transcodiert sie in UTF-8. Eine Datei, die als UTF-8 codiert ist, kann mithilfe des folgenden Codes direkt in eine `ReadOnlySpan<byte>`gelesen werden:

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  Wenn die Datei eine UTF-8-Byte Reihenfolge-Marke (BOM) enthält, entfernen Sie diese, bevor Sie die Bytes an den `Utf8JsonReader`übergeben, da der Reader Text erwartet. Andernfalls wird die BOM als ungültige JSON betrachtet, und der Reader löst eine Ausnahme aus.

Im Folgenden finden Sie ein JSON-Beispiel, das der vorherige Code lesen kann. Die resultierende Zusammenfassungsmeldung lautet: "2 out of 4 have names that end with 'University'":

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>Zusätzliche Ressourcen

* [Übersicht über System.Text.Json](system-text-json-overview.md)
* [Schreiben von benutzerdefinierten Konvertern](system-text-json-converters-how-to.md)
* [Migrieren von Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)
* [DateTime-und DateTimeOffset-Unterstützung in System.Text.Json](../datetime/system-text-json-support.md)
* [API-Referenz für System.Text.Json](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
