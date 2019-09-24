---
ms.openlocfilehash: 101740e828589d7d210527e3db82a1c949a6e0fd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117096"
---
### <a name="jsonencodedtextencode-methods-have-an-additional-javascriptencoder-argument"></a><span data-ttu-id="a24bd-101">JsonEncodedText.Encode-Methoden weisen ein zusätzliches JavaScriptEncoder-Argument auf</span><span class="sxs-lookup"><span data-stu-id="a24bd-101">JsonEncodedText.Encode methods have an additional JavaScriptEncoder argument</span></span>

<span data-ttu-id="a24bd-102">Ab .NET Core 3.0 Vorschau 8 enthalten die <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>-Methoden ein optionales <xref:System.Text.Encodings.Web.JavaScriptEncoder>-Argument.</span><span class="sxs-lookup"><span data-stu-id="a24bd-102">Starting with .NET Core 3.0 Preview 8, the <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> methods contain an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> argument.</span></span> 

#### <a name="details"></a><span data-ttu-id="a24bd-103">Details</span><span class="sxs-lookup"><span data-stu-id="a24bd-103">Details</span></span>

<span data-ttu-id="a24bd-104">.Net Core 3.0 enthält den neuen Typ: xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="a24bd-104">.NET Core 3.0 includes a new type, xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="a24bd-105">Ab .NET Core 3.0 Vorschau 8 wurde die Signatur aller <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType>-Methodenüberladungen geändert, um einen optionalen <xref:System.Text.Encodings.Web.JavaScriptEncoder>-Parameter einzubinden.</span><span class="sxs-lookup"><span data-stu-id="a24bd-105">Starting with .NET Core 3.0 Preview 8, the signature of all <xref:System.Text.Json.JsonEncodedText.Encode%2A?displayProperty=nameWithType> method overloads has changed to include an optional <xref:System.Text.Encodings.Web.JavaScriptEncoder> parameter.</span></span> <span data-ttu-id="a24bd-106">Diese Änderung wurde vorgenommen, um einen anderen oder benutzerdefinierten Encoder zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a24bd-106">This change was made to allow for a different or custom encoder.</span></span>

<span data-ttu-id="a24bd-107">Dies ist die Signatur der `Encode`-Methoden in .NET Core 3.0 Vorschau 7:</span><span class="sxs-lookup"><span data-stu-id="a24bd-107">The signature of the `Encode` methods in .NET Core 3.0 Preview 7 is:</span></span>

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

<span data-ttu-id="a24bd-108">Dies ist die Signatur der gleichen `Encode`-Methoden in .NET Core 3.0 Vorschau 8 oder höher:</span><span class="sxs-lookup"><span data-stu-id="a24bd-108">The signature of the same `Encode` methods in .NET Core 3.0 Preview 8 and later versions is:</span></span>

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

#### <a name="version-introduced"></a><span data-ttu-id="a24bd-109">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="a24bd-109">Version introduced</span></span>

<span data-ttu-id="a24bd-110">.NET Core 3.0 Preview 8</span><span class="sxs-lookup"><span data-stu-id="a24bd-110">.NET Core 3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a24bd-111">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="a24bd-111">Recommended action</span></span>

<span data-ttu-id="a24bd-112">Dies ist nur ein binärer Breaking Change. Bei einer erneuten Kompilierung für .NET Core 3.0 Vorschau 8 oder eine höhere Version werden alle Laufzeitprobleme behoben.</span><span class="sxs-lookup"><span data-stu-id="a24bd-112">This is a binary breaking change only; a recompile against .NET Core 3.0 Preview 8 or a later version will fix any runtime issues.</span></span>

#### <a name="category"></a><span data-ttu-id="a24bd-113">Category (Kategorie)</span><span class="sxs-lookup"><span data-stu-id="a24bd-113">Category</span></span>

<span data-ttu-id="a24bd-114">CoreFx</span><span class="sxs-lookup"><span data-stu-id="a24bd-114">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a24bd-115">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a24bd-115">Affected APIs</span></span>

<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Byte%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan%7BSystem.Char%7D,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>
<xref:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)?displayProperty=nameWithType>

<!--

### Affected APIs 

- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Byte},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.ReadOnlySpan{System.Char},System.Text.Encodings.Web.JavaScriptEncoder)`
- `M:System.Text.Json.JsonEncodedText.Encode(System.String,System.Text.Encodings.Web.JavaScriptEncoder)`

-->