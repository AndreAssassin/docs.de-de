---
title: Neues in C# 8.0 – C#-Leitfaden
description: Überblick über die neuen Funktionen von C# 8.0. Dieser Artikel ist auf dem neuesten Stand mit Vorschauversion 2.
ms.date: 02/12/2019
ms.openlocfilehash: eecc37433e4b026b7337418eac1a5e80ef48ea6e
ms.sourcegitcommit: d21bee9dbd32b9540ad30f9d0e2e874227040be3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59427278"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="3f1f8-104">Neues in C# 8.0</span><span class="sxs-lookup"><span data-stu-id="3f1f8-104">What's new in C# 8.0</span></span>

<span data-ttu-id="3f1f8-105">Wir haben viele Verbesserungen an der C#-Sprache vorgenommen, die Sie bereits mit Vorschau 2 ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-105">There are many enhancements to the C# language that you can try out already with preview 2.</span></span> <span data-ttu-id="3f1f8-106">Diese neuen Funktionen wurde in Vorschauversion 2 hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-106">The new features added in preview 2 are:</span></span>

- <span data-ttu-id="3f1f8-107">[Verbesserungen am Musterabgleich](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="3f1f8-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  * [<span data-ttu-id="3f1f8-108">Switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3f1f8-108">Switch expressions</span></span>](#switch-expressions)
  * [<span data-ttu-id="3f1f8-109">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-109">Property patterns</span></span>](#property-patterns)
  * [<span data-ttu-id="3f1f8-110">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-110">Tuple patterns</span></span>](#tuple-patterns)
  * [<span data-ttu-id="3f1f8-111">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="3f1f8-112">Using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="3f1f8-113">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="3f1f8-114">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-114">Disposable ref structs</span></span>](#disposable-ref-structs)

<span data-ttu-id="3f1f8-115">Die folgenden Sprachfunktionen sind erstmals in der Vorschauversion 1 von C# 8.0 erschienen:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-115">The following language features first appeared in C# 8.0 preview 1:</span></span>

- [<span data-ttu-id="3f1f8-116">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-116">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="3f1f8-117">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="3f1f8-117">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="3f1f8-118">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="3f1f8-118">Indices and ranges</span></span>](#indices-and-ranges)

> [!NOTE]
> <span data-ttu-id="3f1f8-119">Dieser Artikel wurde zuletzt für Vorschauversion 2 von C# 8.0 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-119">This article was last updated for C# 8.0 preview 2.</span></span>

<span data-ttu-id="3f1f8-120">Der Rest dieses Artikels beschreibt diese Funktionen kurz.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-120">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="3f1f8-121">Wenn ausführliche Artikel verfügbar sind, werden Links zu diesen Tutorials und Übersichten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-121">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="3f1f8-122">Weitere Muster an mehr Orten</span><span class="sxs-lookup"><span data-stu-id="3f1f8-122">More patterns in more places</span></span>

<span data-ttu-id="3f1f8-123">**Musterabgleich** bietet Tools zur Bereitstellung formabhängiger Funktionalität für verwandte, aber unterschiedliche Datentypen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-123">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="3f1f8-124">C# 7.0 führte eine Syntax für Typmuster und konstante Muster ein, indem der Ausdruck [`is`](../language-reference/keywords/is.md) und die Anweisung [`switch`](../language-reference/keywords/switch.md) verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-124">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="3f1f8-125">Diese Funktionen stellten die ersten vorläufigen Schritte zur Unterstützung von Programmierparadigmen dar, bei denen Daten und Funktionalität getrennt voneinander sind.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-125">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="3f1f8-126">Da sich die Branche immer mehr auf Mikroservices und andere Cloud-basierte Architekturen konzentriert, werden andere Sprachtools benötigt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-126">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="3f1f8-127">C# 8.0 erweitert dieses Vokabular, sodass Sie mehr Musterausdrücke an mehreren Stellen in Ihrem Code verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-127">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="3f1f8-128">Berücksichtigen Sie diese Funktionen, wenn Ihre Daten und Funktionen getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-128">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="3f1f8-129">Berücksichtigen Sie den Musterabgleich, wenn Ihre Algorithmen von einer anderen Tatsache als dem Runtimetyp eines Objekts abhängen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-129">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="3f1f8-130">Diese Verfahren bieten eine weitere Möglichkeit, Entwürfe auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-130">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="3f1f8-131">Zusätzlich zu neuen Mustern an neuen Orten fügt C# 8.0 **rekursive Muster** hinzu.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-131">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="3f1f8-132">Das Ergebnis eines beliebigen Musterausdrucks ist ein Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-132">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="3f1f8-133">Ein rekursives Muster ist einfach ein Musterausdruck, der auf die Ausgabe eines anderen Musterausdrucks angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-133">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="3f1f8-134">switch-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="3f1f8-134">switch expressions</span></span>

<span data-ttu-id="3f1f8-135">Häufig liefert eine [`switch`](../language-reference/keywords/switch.md)-Anweisung in jedem ihrer `case`-Blöcke einen Wert.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-135">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="3f1f8-136">Mit **switch-Ausdrücken** können Sie eine präzisere Ausdruckssyntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-136">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="3f1f8-137">Es gibt weniger repetitive `case`- und `break`-Schlüsselwörter und weniger geschweifte Klammern.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-137">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="3f1f8-138">Betrachten Sie als Beispiel die folgende Enumeration, die die Farben des Regenbogens enumeriert:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-138">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="3f1f8-139">Wenn Ihre Anwendung einen `RGBColor`-Typ definiert hat, der aus den Komponenten `R`, `G` und `B` aufgebaut ist, können Sie einen `Rainbow`-Wert in seine RGB-Werte konvertieren, indem Sie die folgende Methode verwenden, die einen Switch-Ausdruck enthält:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-139">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="3f1f8-140">Es gibt hier verschiedene Syntaxverbesserungen:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-140">There are several syntax improvements here:</span></span>

- <span data-ttu-id="3f1f8-141">Die Variable steht vor dem `switch`-Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-141">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="3f1f8-142">Die unterschiedliche Reihenfolge macht es optisch einfach, den switch-Ausdruck von der switch-Anweisung zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-142">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="3f1f8-143">Die `case`- und `:`-Elemente werden durch `=>` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-143">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="3f1f8-144">Es ist präziser und intuitiver.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-144">It's more concise and intuitive.</span></span>
- <span data-ttu-id="3f1f8-145">Der `default`-Fall wird durch eine `_`-Ausschlussvariable ersetzt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-145">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="3f1f8-146">Die Textkörper sind Ausdrücke, keine Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-146">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="3f1f8-147">Stellen Sie dies mit dem entsprechenden Code unter Verwendung der klassischen `switch`-Anweisung gegenüber:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-147">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="3f1f8-148">Eigenschaftsmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-148">Property patterns</span></span>

<span data-ttu-id="3f1f8-149">Mit dem **Eigenschaftsmuster** können Sie die Eigenschaften des untersuchten Objekts anpassen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-149">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="3f1f8-150">Denken Sie an eine eCommerce-Website, die die Umsatzsteuer auf der Grundlage der Adresse des Käufers berechnen muss.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-150">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="3f1f8-151">Diese Berechnung ist keine Kernaufgabe einer `Address`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-151">That computation is not a core responsibility of an `Address` class.</span></span> <span data-ttu-id="3f1f8-152">Sie wird sich im Laufe der Zeit ändern, wahrscheinlich häufiger als Adressformatänderungen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-152">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="3f1f8-153">Die Höhe der Umsatzsteuer hängt von der `State`-Eigenschaft der Adresse ab.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-153">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="3f1f8-154">Die folgende Methode verwendet das Eigenschaftsmuster, um die Umsatzsteuer aus der Adresse und dem Preis zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-154">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.75M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="3f1f8-155">Ein Musterabgleich erstellt eine präzise Syntax,. um diesen Algorithmus auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-155">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="3f1f8-156">Tupelmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-156">Tuple patterns</span></span>

<span data-ttu-id="3f1f8-157">Einige Algorithmen sind von mehreren Eingaben abhängig.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-157">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="3f1f8-158">**Tupelmuster** erlauben Ihnen, auf Grundlage mehrerer Werte, ausgedrückt als ein [Tupel](../tuples.md), zu wechseln („switch“).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-158">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="3f1f8-159">Der folgende Code zeigt einen switch-Ausdruck für das Spiel *Stein, Schere, Papier* (Schnick, Schnack, Schnuck):</span><span class="sxs-lookup"><span data-stu-id="3f1f8-159">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="3f1f8-160">Die Meldungen zeigen den Gewinner an.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-160">The messages indicate the winner.</span></span> <span data-ttu-id="3f1f8-161">Der Fall „Verwerfen“ („case discard“) stellt die drei Kombinationen für Unentschieden oder andere Texteingaben dar.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-161">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="3f1f8-162">Positionsmuster</span><span class="sxs-lookup"><span data-stu-id="3f1f8-162">Positional patterns</span></span>

<span data-ttu-id="3f1f8-163">Einige Typen umfassen eine `Deconstruct`-Methode, die ihre Eigenschaften in diskrete Variablen dekonstruiert.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-163">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="3f1f8-164">Wenn auf eine `Deconstruct`-Methode zugegriffen werden kann, können Sie **Positionsmuster** verwenden, um Eigenschaften des Objekts zu untersuchen, und diese Eigenschaften für ein Muster verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-164">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="3f1f8-165">Beachten Sie die folgende `Point`-Klasse, die eine `Deconstruct`-Methode umfasst, um diskrete Variablen für `X` und `Y` zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-165">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="3f1f8-166">Beachten Sie zudem die folgende Enumeration, die verschiedene Positionen eines Quadranten darstellt:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-166">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="3f1f8-167">Die folgende Methode verwendet das **Positionsmuster**, um die Werte von `x` und `y` zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-167">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="3f1f8-168">Dann wird mit einer `when`-Klausel der `Quadrant` des Punktes bestimmt:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-168">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="3f1f8-169">Das Ausschussmuster im vorherigen Switch stimmt überein, wenn entweder `x` oder `y` 0 ist, jedoch nicht beide.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-169">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="3f1f8-170">Ein switch-Ausdruck muss entweder einen Wert erzeugen oder eine Ausnahme auslösen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-170">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="3f1f8-171">Wenn keiner der Fälle übereinstimmt, löst der switch-Ausdruck eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-171">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="3f1f8-172">Der Compiler erzeugt für Sie eine Warnung, wenn Sie nicht alle möglichen Fälle in Ihrem switch-Ausdruck abdecken.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-172">The compiler generates a warning for you if you do not cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="3f1f8-173">In diesem [erweiterten Tutorial zum Musterabgleich](../tutorials/pattern-matching.md) erhalten Sie weitere Informationen zu Musterabgleichverfahren.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-173">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="3f1f8-174">using-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-174">using declarations</span></span>

<span data-ttu-id="3f1f8-175">Eine **using-Deklaration** ist eine Variablendeklaration, der das Schlüsselwort `using` vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-175">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="3f1f8-176">Es teilt dem Compiler mit, dass die zu deklarierende Variable am Ende des umschließenden Bereichs angeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-176">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="3f1f8-177">Sehen Sie sich beispielsweise den folgenden Code an, der eine Textdatei schreibt:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-177">For example, consider the following code that writes a text file:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    foreach (string line in lines)
    {
        // If the line doesn't contain the word 'Second', write the line to the file.
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
    }
// file is disposed here
}
```

<span data-ttu-id="3f1f8-178">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die schließende Klammer für die Methode erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-178">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="3f1f8-179">Dies ist das Ende des Bereichs, in dem `file` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-179">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="3f1f8-180">Der vorhergehende Code entspricht dem folgenden Code unter Verwendung der klassischen [using statements](../language-reference/keywords/using-statement.md)-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-180">The preceding code is equivalent to the following code using the classic [using statements](../language-reference/keywords/using-statement.md) statement:</span></span>

```csharp
static void WriteLinesToFile(IEnumerable<string> lines)
{
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            // If the line doesn't contain the word 'Second', write the line to the file.
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
        }
    } // file is disposed here
}
```

<span data-ttu-id="3f1f8-181">Im vorhergehenden Beispiel wird die Datei angeordnet, wenn die der `using`-Anweisung zugeordnete schließende Klammer erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-181">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="3f1f8-182">In beiden Fällen generiert der Compiler den Aufruf von `Dispose()`.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-182">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="3f1f8-183">Der Compiler erzeugt einen Fehler, wenn der Ausdruck in der using-Anweisung nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-183">The compiler generates an error if the expression in the using statement is not disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="3f1f8-184">Statische lokale Funktionen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-184">Static local functions</span></span>

<span data-ttu-id="3f1f8-185">Sie können nun den `static`-Modifikator zu lokalen Funktionen hinzufügen, um sicherzustellen, dass die lokale Funktion keine Variablen aus dem umschließenden Bereich erfasst (referenziert).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-185">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="3f1f8-186">Dadurch wird `CS8421` erzeugt: „Eine statische lokale Funktion kann keine Referenz auf \<variable> enthalten.“</span><span class="sxs-lookup"><span data-stu-id="3f1f8-186">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span> 

<span data-ttu-id="3f1f8-187">Betrachten Sie folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-187">Consider the following code.</span></span> <span data-ttu-id="3f1f8-188">Die lokale Funktion `LocalFunction` greift auf die Variable `y` zu, die im umschließenden Bereich (die Methode `M`) deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-188">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="3f1f8-189">Daher kann `LocalFunction` nicht mit dem `static`-Modifikator deklariert werden:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-189">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="3f1f8-190">Der folgende Code enthält eine statische lokale Funktion.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-190">The following code contains a static local function.</span></span> <span data-ttu-id="3f1f8-191">Er kann statisch sein, da er nicht auf Variablen im umschließenden Bereich zugreift:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-191">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="3f1f8-192">Verwerfbare Referenzstrukturen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-192">Disposable ref structs</span></span>

<span data-ttu-id="3f1f8-193">Ein mit dem `ref`-Modifikator deklarierter `struct` darf keine Schnittstellen und damit auch keine <xref:System.IDisposable> implementieren.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-193">A `struct` declared with the `ref` modifier may not implement any interfaces and so cannot implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="3f1f8-194">Aus diesem Grund Aktivieren einer `ref struct` um verworfen werden, muss eine zugängliche `void Dispose()` Methode.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-194">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="3f1f8-195">Dies gilt auch für `readonly ref struct`-Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-195">This also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="3f1f8-196">Nullwerte zulassende Verweistypen</span><span class="sxs-lookup"><span data-stu-id="3f1f8-196">Nullable reference types</span></span>

<span data-ttu-id="3f1f8-197">In einem Nullwerte zulassenden Anmerkungskontext, wird jede Variable eines Referenztyps als **keine Nullwerte zulassender Referenztyp** betrachtet.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-197">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="3f1f8-198">Wenn Sie angeben möchten, dass eine Variable Null sein kann, müssen Sie den Typnamen mit `?` ergänzen, um die Variable als **keine Nullwerte zulassenden Verweistyp** zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-198">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="3f1f8-199">Wenn der Verweistyp keine Nullwerte zulässt, verwendet der Compiler die Flussanalyse, um sicherzustellen, dass lokale Variablen bei der Deklaration auf einen Nicht-Null-Wert initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-199">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="3f1f8-200">Felder müssen während der Erstellung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-200">Fields must be initialized during construction.</span></span> <span data-ttu-id="3f1f8-201">Der Compiler erzeugt eine Warnung, wenn die Variable nicht durch einen Aufruf eines der verfügbaren Konstruktoren oder durch einen Initialisierer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-201">The compiler generates a warning if the variable is not set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="3f1f8-202">Darüber hinaus kann Verweistypen, die keine Nullwerte zulassen, kein Wert zugewiesen werden, der Null sein könnte.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-202">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="3f1f8-203">Verweistypen, die keine Nullwerte zulassen werden nicht überprüft, um sicherzustellen, dass sie nicht mit Null belegt oder initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-203">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="3f1f8-204">Der Compiler verwendet jedoch die Flussanalyse, um sicherzustellen, dass jede Variable eines Verweistypen, der Nullwerte zulässt, gegen null geprüft wird, bevor auf sie zugegriffen oder einem nicht Verweistypen zugewiesen wird, der Nullwerte zulässt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-204">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="3f1f8-205">Mehr über die Funktion erfahren Sie in der Übersicht der [Verweistypen, die Nullwerte zulassen](../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-205">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="3f1f8-206">Probieren Sie es selbst in einer neuen Anwendung in diesem [Tutorial für Verweistypen, die Nullwerte zulassen](../tutorials/nullable-reference-types.md) aus.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-206">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="3f1f8-207">Weitere Informationen über die Schritte zur Migration einer bestehenden Codebasis, um Verweistypen zu nutzen, die Nullwerte zulassen, finden Sie im Tutorial [Migration einer Anwendung zur Verwendung Nullwerte zulassenden Verweistypen](../tutorials/upgrade-to-nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="3f1f8-207">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="3f1f8-208">Asynchrone Streams</span><span class="sxs-lookup"><span data-stu-id="3f1f8-208">Asynchronous streams</span></span>

<span data-ttu-id="3f1f8-209">Ab C# 8.0 können Sie Streams asynchron erstellen und nutzen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-209">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="3f1f8-210">Eine Methode, die einen asynchronen Stream zurückgibt, hat drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-210">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="3f1f8-211">Die Deklaration erfolgte mit dem `async`-Modifikator.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-211">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="3f1f8-212">Es wird <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-212">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="3f1f8-213">Das Verfahren enthält `yield return`-Anweisungen, um aufeinanderfolgende Elemente im asynchronen Stream zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-213">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="3f1f8-214">Die Verwendung eines asynchronen Streams erfordert, dass Sie das Schlüsselwort `await` vor dem Schlüsselwort `foreach` hinzufügen, wenn Sie die Elemente des Streams auflisten.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-214">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="3f1f8-215">Das Hinzufügen des Schlüsselwortes `await` erfordert, dass die Methode, die den asynchronen Strom enumiert, mit dem Modifikator `async` deklariert wird und einen für eine `async`-Methode zulässigen Typ zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-215">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="3f1f8-216">In der Regel ist dies die Rückgabe von <xref:System.Threading.Tasks.Task> oder <xref:System.Threading.Tasks.Task%601>.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-216">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="3f1f8-217">Es kann auch <xref:System.Threading.Tasks.ValueTask> oder <xref:System.Threading.Tasks.ValueTask%601> sein.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-217">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="3f1f8-218">Eine Methode kann einen asynchronen Stream sowohl verwenden als auch erzeugen, was bedeutet, dass sie <xref:System.Collections.Generic.IAsyncEnumerable%601> zurückgeben würde.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-218">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="3f1f8-219">Der folgende Code erzeugt eine Sequenz von 0 bis 19 und wartet 100 ms zwischen der Generierung jeder Zahl:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-219">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="3f1f8-220">Die Enumeration der Sequenz erfolgt mit der `await foreach`-Anweisung:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-220">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="3f1f8-221">Sie können asynchrone Streams selbst in unserem Tutorial zum [Erstellen und Verwenden von asynchronen Streams](../tutorials/generate-consume-asynchronous-stream.md) ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-221">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="3f1f8-222">Indizes und Bereiche</span><span class="sxs-lookup"><span data-stu-id="3f1f8-222">Indices and ranges</span></span>

<span data-ttu-id="3f1f8-223">Bereiche und Indizes bieten eine prägnante Syntax zur Angabe von Teilbereichen in einem Array, <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-223">Ranges and indices provide a succinct syntax for specifying subranges in an array, <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span>

<span data-ttu-id="3f1f8-224">Sie können einen Index  **from the end** aus angeben.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-224">You can specify an index **from the end**.</span></span> <span data-ttu-id="3f1f8-225">Sie geben **from the end** mithilfe des `^`-Operators an.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-225">You specify **from the end** using the `^` operator.</span></span> <span data-ttu-id="3f1f8-226">Sie kennen `array[2]`. Damit wird das Element „2 from the start“ bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-226">You are familiar with `array[2]` meaning the element "2 from the start".</span></span> <span data-ttu-id="3f1f8-227">Jetzt bezeichnet `array[^2]` das Element „2 from the end“.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-227">Now, `array[^2]` means the element "2 from the end".</span></span> <span data-ttu-id="3f1f8-228">Der Index `^0` bedeutet „das Ende“ oder der Index, der dem letzten Element folgt.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-228">The index `^0` means "the end", or the index that follows the last element.</span></span>

<span data-ttu-id="3f1f8-229">Sie können einen **Bereich** mit dem **Bereichsoperator** angeben: `..`.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-229">You can specify a **range** with the **range operator**: `..`.</span></span> <span data-ttu-id="3f1f8-230">So gibt beispielsweise `0..^0` den gesamten Bereich des Arrays an: 0 vom Anfang bis zum Ende, aber nicht einschließlich 0 vom Ende.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-230">For example, `0..^0` specifies the entire range of the array: 0 from the start up to, but not including 0 from the end.</span></span> <span data-ttu-id="3f1f8-231">Jeder der beiden Operanden kann „from the start“ oder „from the end“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-231">Either operand may use "from the start" or "from the end".</span></span> <span data-ttu-id="3f1f8-232">Darüber hinaus kann jeder der beiden Operanden weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-232">Furthermore, either operand may be omitted.</span></span> <span data-ttu-id="3f1f8-233">Die Standardeinstellungen sind `0` für den Startindex und `^0` für den Endindex.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-233">The defaults are `0` for the start index, and `^0` for the end index.</span></span>

<span data-ttu-id="3f1f8-234">Schauen wir uns einige Beispiele an.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-234">Let's look at a few examples.</span></span> <span data-ttu-id="3f1f8-235">Betrachten Sie das folgende Array, kommentiert mit seinem Index „from the start“ und „from the end“:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-235">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};
```

<span data-ttu-id="3f1f8-236">Der Index jedes Elements verstärkt das Konzept von „from the start“ und „from the end“, und dass Bereiche das Ende des Bereichs ausschließen.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-236">The index of each element reinforces the concept of "from the start", and "from the end", and that ranges are exclusive of the end of the range.</span></span> <span data-ttu-id="3f1f8-237">Der „start“ des gesamten Arrays ist das erste Element.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-237">The "start" of the entire array is the first element.</span></span> <span data-ttu-id="3f1f8-238">Das „end“ des gesamten Arrays liegt *hinter* dem letzten Element.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-238">The "end" of the entire array is *past* the last element.</span></span>

<span data-ttu-id="3f1f8-239">Sie können das letzte Wort mit dem `^1`-Index abrufen:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-239">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="3f1f8-240">Der folgende Code erzeugt einen Teilbereich mit den Worten „quick“, „brown“ und „fox“.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-240">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="3f1f8-241">Er enthält `words[1]` bis `words[3]`.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-241">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="3f1f8-242">Das Element `words[4]` gehört nicht zum Bereich.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-242">The element `words[4]` is not in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="3f1f8-243">Der folgende Code erzeugt einen Teilbereich mit „lazy“ und „dog“.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-243">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="3f1f8-244">Dazu gehören `words[^2]` und `words[^1]`.</span><span class="sxs-lookup"><span data-stu-id="3f1f8-244">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="3f1f8-245">Der Endindex `words[^0]` ist nicht enthalten:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-245">The end index `words[^0]` is not included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="3f1f8-246">Die folgenden Beispiele erstellen Bereiche, die am Anfang, am Ende und auf beiden Seiten offen sind:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-246">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the, "lazy" and "dog"
```

<span data-ttu-id="3f1f8-247">Sie können Bereiche auch als Variablen deklarieren:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-247">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="3f1f8-248">Der Bereich kann dann innerhalb der Zeichen `[` und `]` verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3f1f8-248">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```
