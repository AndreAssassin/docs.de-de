---
ms.openlocfilehash: 98893470b64de4abf7f04817871e3053bf25b86d
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71119101"
---
### <a name="jsonelement-api-changes"></a>Änderungen der JsonElement-API

Ab . NET Core 3.0 Vorschau 7 wurden einige <xref:System.Text.Json.JsonElement>-APIs geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.

#### <a name="change-description"></a>Änderungsbeschreibung

In . NET Core 3.0 Vorschau 7 wurden <xref:System.Text.Json.JsonElement>-APIs wie folgt geändert, um einfachere Ermittlung und bessere Benutzerfreundlichkeit zu ermöglichen.

1. Alle `WriteProperty`-Methodenüberladungen wurden aus <xref:System.Text.Json.JsonElement>entfernt. Dies wirkt sich auf Code wie den folgenden aus:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
      JsonElement root = doc.RootElement;
      root.WriteProperty(propertyNameString, writer);
      // ..
      root.WriteProperty(propertyNameSpan, writer);
      // ..
      root.WriteProperty(propertyNameJsonEncoded, writer);
      // ..
      root.WriteProperty(utf8PropertyName, writer);
      //..
   }
   ```

1. `WriteValue` wurde in <xref:System.Text.Json.JsonElement.WriteTo%2A> umbenannt. Dies wirkt sich auf Code wie den folgenden aus:

```csharp
using (JsonDocument doc = JsonDocument.Parse(jsonString))
{
    JsonElement root = doc.RootElement;
    root.WriteValue(writer);
}

```

1. <xref:System.Text.Json.JsonElement.WriteTo%2A> löst nun eine <xref:System.ArgumentNullException> aus, wenn der Methodenparameter `null` ist.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 7

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Ihr Code von diesen Änderungen betroffen ist, können Sie wie folgt vorgehen:

- Es gibt keine Ersatz-API für die `WriteProperty`-Überladungen in <xref:System.Text.Json.JsonElement>. Stattdessen können Sie eine der <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName%2A?displayProperty=nameWithType>-Überladungen zusammen mit der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode aufzurufen, um das gleiche Ergebnis zu erhalten. Beispiel:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       writer.WritePropertyName(propertyNameString);
       root.WriteTo(writer);
   }
   ```

- Benennen Sie die `WriteValue`-Methode in <xref:System.Text.Json.JsonElement.WriteTo(System.Text.Json.Utf8JsonWriter)> um. Der Methodenparameter bleibt unverändert. Der vorherige Code sollte z.B. wie folgt geändert werden:

   ```csharp
   using (JsonDocument doc = JsonDocument.Parse(jsonString))
   {
       JsonElement root = doc.RootElement;
       root.WriteTo(writer);
   }
   ```

- Verarbeiten Sie die <xref:System.ArgumentNullException> in Aufrufen der <xref:System.Text.Json.JsonElement.WriteTo%2A>-Methode.

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Text.Json.JsonElement>
- <xref:System.Text.Json.JsonElement.WriteTo%2A?displayProperty=nameWithType>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonElement.WriteProperty`
- `M:System.Text.Json.JsonElement.WriteValue(System.Text.Json.Utf8JsonWriter)`

-->
