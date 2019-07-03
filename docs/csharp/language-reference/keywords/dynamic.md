---
title: dynamic – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- dynamic_CSharpKeyword
helpviewer_keywords:
- dynamic [C#]
- dynamic keyword [C#]
ms.assetid: 9e797102-cc83-4964-bf58-afe4f54d16bc
ms.openlocfilehash: c8748f1869e8e2d5246910fac0100a6c70790579
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/21/2019
ms.locfileid: "67306638"
---
# <a name="dynamic-c-reference"></a><span data-ttu-id="a004f-102">dynamic (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a004f-102">dynamic (C# Reference)</span></span>

<span data-ttu-id="a004f-103">Der `dynamic`-Typ ermöglicht die Vorgänge, in denen er auftritt, um die Typüberprüfung zur Kompilierzeit zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="a004f-103">The `dynamic` type enables the operations in which it occurs to bypass compile-time type checking.</span></span> <span data-ttu-id="a004f-104">Stattdessen werden diese Vorgänge zur Laufzeit aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="a004f-104">Instead, these operations are resolved at run time.</span></span> <span data-ttu-id="a004f-105">Der `dynamic`-Typ vereinfacht den Zugriff auf COM-APIs, z.B. die Office Automation-APIs, und auch auf dynamische APIs, beispielsweise IronPython-Bibliotheken und auf das HTML-Dokumentobjektmodell (Document Object Model, DOM).</span><span class="sxs-lookup"><span data-stu-id="a004f-105">The `dynamic` type simplifies access to COM APIs such as the Office Automation APIs, and also to dynamic APIs such as IronPython libraries, and to the HTML Document Object Model (DOM).</span></span>

<span data-ttu-id="a004f-106">Der Typ `dynamic` verhält sich in den meisten Fällen wie Typ `object`.</span><span class="sxs-lookup"><span data-stu-id="a004f-106">Type `dynamic` behaves like type `object` in most circumstances.</span></span> <span data-ttu-id="a004f-107">Jedoch werden Vorgänge, die Ausdrücke des Typs `dynamic` enthalten, nicht aufgelöst oder durch den Compiler typgeprüft.</span><span class="sxs-lookup"><span data-stu-id="a004f-107">However, operations that contain expressions of type `dynamic` are not resolved or type checked by the compiler.</span></span> <span data-ttu-id="a004f-108">Der Compiler packt Informationen über den Vorgang. Diese Informationen werden später zur Evaluierung des Vorgangs zur Laufzeit verwendet.</span><span class="sxs-lookup"><span data-stu-id="a004f-108">The compiler packages together information about the operation, and that information is later used to evaluate the operation at run time.</span></span> <span data-ttu-id="a004f-109">Als Teil dieses Prozesses werden Variablen des Typs `dynamic` in Variablen des Typs `object` kompiliert.</span><span class="sxs-lookup"><span data-stu-id="a004f-109">As part of the process, variables of type `dynamic` are compiled into variables of type `object`.</span></span> <span data-ttu-id="a004f-110">Deshalb existiert der Typ `dynamic` nur zur Kompilierzeit und nicht zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="a004f-110">Therefore, type `dynamic` exists only at compile time, not at run time.</span></span>

<span data-ttu-id="a004f-111">Das folgende Beispiel vergleicht den Unterschied einer Variable des Typs `dynamic` mit einer Variable des Typs `object`.</span><span class="sxs-lookup"><span data-stu-id="a004f-111">The following example contrasts a variable of type `dynamic` to a variable of type `object`.</span></span> <span data-ttu-id="a004f-112">Um den Typ jeder Variable zur Kompilierzeit zu überprüfen, zeigen Sie mit dem Mauszeiger auf `dyn` oder `obj` in den `WriteLine`-Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="a004f-112">To verify the type of each variable at compile time, place the mouse pointer over `dyn` or `obj` in the `WriteLine` statements.</span></span> <span data-ttu-id="a004f-113">IntelliSense zeigt **dynamic** für `dyn` und **object** für `obj`.</span><span class="sxs-lookup"><span data-stu-id="a004f-113">IntelliSense shows **dynamic** for `dyn` and **object** for `obj`.</span></span>

[!code-csharp[csrefKeywordsTypes#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#21)]

<span data-ttu-id="a004f-114">Die `WriteLine`-Anweisungen zeigen die Laufzeittypen von `dyn` und `obj`.</span><span class="sxs-lookup"><span data-stu-id="a004f-114">The `WriteLine` statements display the run-time types of `dyn` and `obj`.</span></span> <span data-ttu-id="a004f-115">Zu diesem Zeitpunkt verfügen beide denselben Typ, Integer.</span><span class="sxs-lookup"><span data-stu-id="a004f-115">At that point, both have the same type, integer.</span></span> <span data-ttu-id="a004f-116">Es wird die folgende Ausgabe generiert:</span><span class="sxs-lookup"><span data-stu-id="a004f-116">The following output is produced:</span></span>

`System.Int32`

`System.Int32`

<span data-ttu-id="a004f-117">Um den Unterschied zwischen `dyn` und `obj` zur Kompilierzeit anzuzeigen, fügen Sie die folgenden zwei Zeilen zwischen die Deklarationen und die `WriteLine`-Anweisungen im vorherigen Beispiel ein.</span><span class="sxs-lookup"><span data-stu-id="a004f-117">To see the difference between `dyn` and `obj` at compile time, add the following two lines between the declarations and the `WriteLine` statements in the previous example.</span></span>

```csharp
dyn = dyn + 3;
obj = obj + 3;
```

 <span data-ttu-id="a004f-118">Es wird ein Kompilierfehler für den Versuch, einen Integer und ein Objekt im Ausdruck `obj + 3` einzufügen, ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="a004f-118">A compiler error is reported for the attempted addition of an integer and an object in expression `obj + 3`.</span></span> <span data-ttu-id="a004f-119">Es wird jedoch kein Fehler für `dyn + 3` gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a004f-119">However, no error is reported for `dyn + 3`.</span></span> <span data-ttu-id="a004f-120">Der Ausdruck, der `dyn` enthält, wird nicht zur Kompilierzeit überprüft, da der Typ von `dyn` `dynamic` ist.</span><span class="sxs-lookup"><span data-stu-id="a004f-120">The expression that contains `dyn` is not checked at compile time because the type of `dyn` is `dynamic`.</span></span>

## <a name="context"></a><span data-ttu-id="a004f-121">Kontext</span><span class="sxs-lookup"><span data-stu-id="a004f-121">Context</span></span>

<span data-ttu-id="a004f-122">Das Schlüsselwort `dynamic` kann direkt oder als Komponente eines konstruierten Typs in den folgenden Situationen erscheinen:</span><span class="sxs-lookup"><span data-stu-id="a004f-122">The `dynamic` keyword can appear directly or as a component of a constructed type in the following situations:</span></span>

- <span data-ttu-id="a004f-123">In Deklarationen, als Typ einer Eigenschaft, als Feld, Indexer, Parameter, Rückgabewert, lokale Variable oder Typeinschränkung.</span><span class="sxs-lookup"><span data-stu-id="a004f-123">In declarations, as the type of a property, field, indexer, parameter, return value, local variable, or type constraint.</span></span> <span data-ttu-id="a004f-124">Die folgende Klassendefinition verwendet `dynamic` in einigen unterschiedlichen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="a004f-124">The following class definition uses `dynamic` in several different declarations.</span></span>

    [!code-csharp[csrefKeywordsTypes#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#22)]

- <span data-ttu-id="a004f-125">In expliziten Typkonvertierungen als Zieltyp einer Konversion.</span><span class="sxs-lookup"><span data-stu-id="a004f-125">In explicit type conversions, as the target type of a conversion.</span></span>

    [!code-csharp[csrefKeywordsTypes#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#23)]

- <span data-ttu-id="a004f-126">In jedem Kontext, in dem Typen als Werte, z.B. auf der rechten Seite eines `is`-Operators oder eines `as`-Operators oder als Argument für `typeof` als Teil eines konstruierten Typs dienen.</span><span class="sxs-lookup"><span data-stu-id="a004f-126">In any context where types serve as values, such as on the right side of an `is` operator or an `as` operator, or as the argument to `typeof` as part of a constructed type.</span></span> <span data-ttu-id="a004f-127">Zum Beispiel kann `dynamic` in den folgenden Ausdrücken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a004f-127">For example, `dynamic` can be used in the following expressions.</span></span>

    [!code-csharp[csrefKeywordsTypes#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic1.cs#24)]

## <a name="example"></a><span data-ttu-id="a004f-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a004f-128">Example</span></span>

<span data-ttu-id="a004f-129">Das folgende Beispiel verwendet `dynamic` in einigen Deklarationen.</span><span class="sxs-lookup"><span data-stu-id="a004f-129">The following example uses `dynamic` in several declarations.</span></span> <span data-ttu-id="a004f-130">Die `Main`-Methode unterscheidet auch die Typüberprüfung zur Kompilierzeit und die Laufzeittypüberprüfung.</span><span class="sxs-lookup"><span data-stu-id="a004f-130">The `Main` method also contrasts compile-time type checking with run-time type checking.</span></span>

[!code-csharp[csrefKeywordsTypes#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/dynamic2.cs#25)]

<span data-ttu-id="a004f-131">Weitere Informationen und Beispiele finden Sie unter [Verwenden von dynamischen Typen](../../../csharp/programming-guide/types/using-type-dynamic.md).</span><span class="sxs-lookup"><span data-stu-id="a004f-131">For more information and examples, see [Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a004f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a004f-132">See also</span></span>

- <xref:System.Dynamic.ExpandoObject?displayProperty=nameWithType>
- <xref:System.Dynamic.DynamicObject?displayProperty=nameWithType>
- [<span data-ttu-id="a004f-133">Verwenden von dynamischen Typen</span><span class="sxs-lookup"><span data-stu-id="a004f-133">Using Type dynamic</span></span>](../../programming-guide/types/using-type-dynamic.md)
- [<span data-ttu-id="a004f-134">object</span><span class="sxs-lookup"><span data-stu-id="a004f-134">object</span></span>](object.md)
- [<span data-ttu-id="a004f-135">is</span><span class="sxs-lookup"><span data-stu-id="a004f-135">is</span></span>](../operators/type-testing-and-conversion-operators.md#is-operator)
- [<span data-ttu-id="a004f-136">as</span><span class="sxs-lookup"><span data-stu-id="a004f-136">as</span></span>](../operators/type-testing-and-conversion-operators.md#as-operator)
- [<span data-ttu-id="a004f-137">typeof</span><span class="sxs-lookup"><span data-stu-id="a004f-137">typeof</span></span>](../operators/type-testing-and-conversion-operators.md#typeof-operator)
- [<span data-ttu-id="a004f-138">Vorgehensweise: Sicheres Umwandeln mit Musterabgleich mit den Operatoren „as“ und „is“</span><span class="sxs-lookup"><span data-stu-id="a004f-138">How to: safely cast using pattern matching and the as and is operators</span></span>](../../how-to/safely-cast-using-pattern-matching-is-and-as-operators.md)
- [<span data-ttu-id="a004f-139">Exemplarische Vorgehensweise: Erstellen und Verwenden von dynamischen Objekten</span><span class="sxs-lookup"><span data-stu-id="a004f-139">Walkthrough: creating and using dynamic objects</span></span>](../../programming-guide/types/walkthrough-creating-and-using-dynamic-objects.md)
