---
title: CType-Funktion (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.CType
helpviewer_keywords:
- expression conversion results
- explicit data type conversions [Visual Basic]
- CType function
- conversions [Visual Basic], expression
ms.assetid: dd4b29e7-6fa1-428c-877e-69955420bb72
ms.openlocfilehash: 4a0391b0a5d76f36803b433369d4832c02b05e09
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592096"
---
# <a name="ctype-function-visual-basic"></a><span data-ttu-id="fc393-102">CType-Funktion (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fc393-102">CType Function (Visual Basic)</span></span>

<span data-ttu-id="fc393-103">Gibt das Ergebnis einer expliziten Konvertierung eines Ausdrucks in einen angegebenen Datentyp, ein Objekt, eine Struktur, Klasse oder Schnittstelle zurück.</span><span class="sxs-lookup"><span data-stu-id="fc393-103">Returns the result of explicitly converting an expression to a specified data type, object, structure, class, or interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="fc393-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc393-104">Syntax</span></span>

```vb
CType(expression, typename)
```

## <a name="parts"></a><span data-ttu-id="fc393-105">Teile</span><span class="sxs-lookup"><span data-stu-id="fc393-105">Parts</span></span>

<span data-ttu-id="fc393-106">`expression` jeder gültige Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="fc393-106">`expression` Any valid expression.</span></span> <span data-ttu-id="fc393-107">Wenn der Wert von `expression` außerhalb des von `typename` definierten Bereichs liegt, wird von Visual Basic eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fc393-107">If the value of `expression` is outside the range allowed by `typename`, Visual Basic throws an exception.</span></span>

<span data-ttu-id="fc393-108">`typename` beliebiger Ausdruck, der in einer `As`-Klausel in einer `Dim`-Anweisung zulässig ist, d. h. der Name eines beliebigen Datentyps, Objekts, Struktur, Klasse oder Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="fc393-108">`typename` Any expression that is legal within an `As` clause in a `Dim` statement, that is, the name of any data type, object, structure, class, or interface.</span></span>

## <a name="remarks"></a><span data-ttu-id="fc393-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc393-109">Remarks</span></span>

> [!TIP]
> <span data-ttu-id="fc393-110">Sie können die folgenden Funktionen auch zum Ausführen einer Typkonvertierung verwenden:</span><span class="sxs-lookup"><span data-stu-id="fc393-110">You can also use the following functions to perform a type conversion:</span></span>
>
> - <span data-ttu-id="fc393-111">Typkonvertierungsfunktionen, wie `CByte`, `CDbl` und `CInt`, mit denen eine Konvertierung in einen bestimmten Datentyp ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fc393-111">Type conversion functions such as `CByte`, `CDbl`, and `CInt` that perform a conversion to a specific data type.</span></span> <span data-ttu-id="fc393-112">Weitere Informationen finden Sie unter [Typkonvertierungs Funktionen](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span><span class="sxs-lookup"><span data-stu-id="fc393-112">For more information, see [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md).</span></span>
> - <span data-ttu-id="fc393-113">[DirectCast-Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) oder [TryCast-Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span><span class="sxs-lookup"><span data-stu-id="fc393-113">[DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) or [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span> <span data-ttu-id="fc393-114">Diese Operatoren erfordern, dass ein Typ von dem Anderen erbt oder diesen implementiert.</span><span class="sxs-lookup"><span data-stu-id="fc393-114">These operators require that one type inherit from or implement the other type.</span></span> <span data-ttu-id="fc393-115">Sie können etwas bessere Leistung beim Konvertieren in und aus dem `CType`-Datentyp bieten, als `Object`.</span><span class="sxs-lookup"><span data-stu-id="fc393-115">They can provide somewhat better performance than `CType` when converting to and from the `Object` data type.</span></span>

<span data-ttu-id="fc393-116">`CType` wird inline kompiliert. Das bedeutet, dass der Konvertierungscode Bestandteil des Codes für die Auswertung des Ausdrucks ist.</span><span class="sxs-lookup"><span data-stu-id="fc393-116">`CType` is compiled inline, which means that the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="fc393-117">In einigen Fällen wird der Code schneller ausgeführt, da keine Prozeduren zum Ausführen der Konvertierung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fc393-117">In some cases, the code runs faster because no procedures are called to perform the conversion.</span></span>

<span data-ttu-id="fc393-118">Wenn keine Konvertierung von `expression` in `typename` (zum Beispiel von `Integer` in `Date`) definiert ist, wird von Visual Basic zur Kompilierungszeit eine Fehlermeldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc393-118">If no conversion is defined from `expression` to `typename` (for example, from `Integer` to `Date`), Visual Basic displays a compile-time error message.</span></span>

<span data-ttu-id="fc393-119">Falls eine Konvertierung zur Laufzeit fehlschlägt, wird die entsprechende Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fc393-119">If a conversion fails at run time, the appropriate exception is thrown.</span></span> <span data-ttu-id="fc393-120">Ist eine einschränkende Konvertierung fehlerhaft, wird meist ein <xref:System.OverflowException>-Fehler verursacht.</span><span class="sxs-lookup"><span data-stu-id="fc393-120">If a narrowing conversion fails, an <xref:System.OverflowException> is the most common result.</span></span> <span data-ttu-id="fc393-121">Wenn die Konvertierung nicht definiert ist, wird eine <xref:System.InvalidCastException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="fc393-121">If the conversion is undefined, an <xref:System.InvalidCastException> in thrown.</span></span> <span data-ttu-id="fc393-122">Dies kann z. B. der Fall sein, wenn `expression` vom Typ `Object` ist und für seinen Laufzeittyp keine Konvertierung in `typename` definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fc393-122">For example, this can happen  if `expression` is of type `Object` and its run-time type has no conversion to `typename`.</span></span>

<span data-ttu-id="fc393-123">Handelt es sich beim Datentyp von `expression` oder `typename` um eine von Ihnen definierte Klasse oder Struktur, können Sie `CType` für diese Klasse oder Struktur als Konvertierungsoperator definieren.</span><span class="sxs-lookup"><span data-stu-id="fc393-123">If the data type of `expression` or `typename` is a class or structure you've defined, you can define `CType` on that class or structure as a conversion operator.</span></span> <span data-ttu-id="fc393-124">Dadurch wird `CType` als *überladener Operator*fungieren.</span><span class="sxs-lookup"><span data-stu-id="fc393-124">This makes `CType` act as an *overloaded operator*.</span></span> <span data-ttu-id="fc393-125">Wenn Sie einen Konvertierungsoperator definieren, können Sie nicht nur das Verhalten von Konvertierungen in und aus der Klasse oder Struktur steuern, sondern auch die ausgelösten Ausnahmen bestimmen.</span><span class="sxs-lookup"><span data-stu-id="fc393-125">If you do this, you can control the behavior of conversions to and from your class or structure, including the exceptions that can be thrown.</span></span>

## <a name="overloading"></a><span data-ttu-id="fc393-126">Überladen</span><span class="sxs-lookup"><span data-stu-id="fc393-126">Overloading</span></span>

<span data-ttu-id="fc393-127">Der Operator `CType` kann auch für eine Klasse oder Struktur überladen werden, die außerhalb des Codes definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fc393-127">The `CType` operator can also be overloaded on a class or structure defined outside your code.</span></span> <span data-ttu-id="fc393-128">Wenn in dem Code Konvertierungen in eine solche Klasse oder Struktur oder in umgekehrter Richtung durchführt werden, müssen Sie sicherstellen, dass Sie das Verhalten des betreffenden `CType`-Operators verstehen.</span><span class="sxs-lookup"><span data-stu-id="fc393-128">If your code converts to or from such a class or structure, be sure you understand the behavior of its `CType` operator.</span></span> <span data-ttu-id="fc393-129">Weitere Informationen finden Sie unter [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span><span class="sxs-lookup"><span data-stu-id="fc393-129">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>

## <a name="converting-dynamic-objects"></a><span data-ttu-id="fc393-130">Konvertieren von dynamischen Objekten</span><span class="sxs-lookup"><span data-stu-id="fc393-130">Converting Dynamic Objects</span></span>

<span data-ttu-id="fc393-131">Typkonvertierungen für dynamische Objekte werden durch benutzerdefinierte dynamische Konvertierungen ausgeführt, bei denen die <xref:System.Dynamic.DynamicObject.TryConvert%2A>-Methode oder die <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A>-Methode verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fc393-131">Type conversions of dynamic objects are performed by user-defined dynamic conversions that use the <xref:System.Dynamic.DynamicObject.TryConvert%2A> or <xref:System.Dynamic.DynamicMetaObject.BindConvert%2A> methods.</span></span> <span data-ttu-id="fc393-132">Wenn Sie mit dynamischen Objekten arbeiten, verwenden Sie zum Konvertieren des dynamischen Objekts die <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A>-Methode.</span><span class="sxs-lookup"><span data-stu-id="fc393-132">If you're working with dynamic objects, use the <xref:Microsoft.VisualBasic.Conversion.CTypeDynamic%2A> method to convert the dynamic object.</span></span>

## <a name="example"></a><span data-ttu-id="fc393-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc393-133">Example</span></span>

<span data-ttu-id="fc393-134">In diesem Beispiel wird die `CType`-Funktion zum Konvertieren eines Ausdrucks in den `Single`-Datentyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="fc393-134">The following example uses the `CType` function to convert an expression to the `Single` data type.</span></span>

[!code-vb[VbVbalrFunctions#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#24)]

<span data-ttu-id="fc393-135">Weitere Beispiele finden Sie unter [implizite und explizite Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span><span class="sxs-lookup"><span data-stu-id="fc393-135">For additional examples, see [Implicit and Explicit Conversions](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="fc393-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc393-136">See also</span></span>

- <xref:System.OverflowException>
- <xref:System.InvalidCastException>
- [<span data-ttu-id="fc393-137">Typkonvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="fc393-137">Type Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="fc393-138">Konvertierungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="fc393-138">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="fc393-139">Operator-Anweisung</span><span class="sxs-lookup"><span data-stu-id="fc393-139">Operator Statement</span></span>](../../../visual-basic/language-reference/statements/operator-statement.md)
- [<span data-ttu-id="fc393-140">Vorgehensweise: Definieren eines Konvertierungsoperators</span><span class="sxs-lookup"><span data-stu-id="fc393-140">How to: Define a Conversion Operator</span></span>](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
- [<span data-ttu-id="fc393-141">Typkonvertierung in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fc393-141">Type Conversion in the .NET Framework</span></span>](../../../standard/base-types/type-conversion.md)
