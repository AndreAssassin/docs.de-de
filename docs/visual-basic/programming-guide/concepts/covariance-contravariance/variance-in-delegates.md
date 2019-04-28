---
title: Varianz in Delegaten (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 38e9353f-74f8-4211-a8f0-7a495414df4a
ms.openlocfilehash: 6d341c7c2b5adeebcafc5b0787b132ab6bd57e41
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61787230"
---
# <a name="variance-in-delegates-visual-basic"></a><span data-ttu-id="0fba7-102">Varianz in Delegaten (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fba7-102">Variance in Delegates (Visual Basic)</span></span>

<span data-ttu-id="0fba7-103">Seit .NET Framework 3.5-Unterstützung von Varianz für Methodensignaturen und Delegattypen in allen Delegaten in C# und Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="0fba7-103">.NET Framework 3.5 introduced variance support for matching method signatures with delegate types in all delegates in C# and Visual Basic.</span></span> <span data-ttu-id="0fba7-104">Das bedeutet, dass Sie Delegaten nicht nur Methoden mit übereinstimmenden Signaturen zuweisen können, sondern auch Methoden, die mehrere abgeleitete Typen zurückgeben (Kovarianz) oder die Parameter akzeptieren, die über weniger abgeleitete Typen verfügen, als durch den Delegattyp angegeben wurde (Kontravarianz).</span><span class="sxs-lookup"><span data-stu-id="0fba7-104">This means that you can assign to delegates not only methods that have matching signatures, but also methods that return more derived types (covariance) or that accept parameters that have less derived types (contravariance) than that specified by the delegate type.</span></span> <span data-ttu-id="0fba7-105">Dies umfasst generische und nicht generische Delegaten.</span><span class="sxs-lookup"><span data-stu-id="0fba7-105">This includes both generic and non-generic delegates.</span></span>

<span data-ttu-id="0fba7-106">Betrachten Sie beispielsweise folgenden Code, der zwei Klassen und zwei Delegaten aufweist: generisch und nicht generisch.</span><span class="sxs-lookup"><span data-stu-id="0fba7-106">For example, consider the following code, which has two classes and two delegates: generic and non-generic.</span></span>

```vb
Public Class First
End Class

Public Class Second
    Inherits First
End Class

Public Delegate Function SampleDelegate(ByVal a As Second) As First
Public Delegate Function SampleGenericDelegate(Of A, R)(ByVal a As A) As R
```

<span data-ttu-id="0fba7-107">Beim Erstellen von Delegaten vom Typ `SampleDelegate` oder `SampleDelegate(Of A, R)` können Sie diesen Delegaten eine der folgenden Methoden zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0fba7-107">When you create delegates of the `SampleDelegate` or `SampleDelegate(Of A, R)` types, you can assign any one of the following methods to those delegates.</span></span>

```vb
' Matching signature.
Public Shared Function ASecondRFirst(
    ByVal second As Second) As First
    Return New First()
End Function

' The return type is more derived.
Public Shared Function ASecondRSecond(
    ByVal second As Second) As Second
    Return New Second()
End Function

' The argument type is less derived.
Public Shared Function AFirstRFirst(
    ByVal first As First) As First
    Return New First()
End Function

' The return type is more derived
' and the argument type is less derived.
Public Shared Function AFirstRSecond(
    ByVal first As First) As Second
    Return New Second()
End Function
```

<span data-ttu-id="0fba7-108">Das folgende Codebeispiel veranschaulicht die implizite Konvertierung zwischen der Methodensignatur und dem Delegattyp.</span><span class="sxs-lookup"><span data-stu-id="0fba7-108">The following code example illustrates the implicit conversion between the method signature and the delegate type.</span></span>

```vb
' Assigning a method with a matching signature
' to a non-generic delegate. No conversion is necessary.
Dim dNonGeneric As SampleDelegate = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a non-generic delegate.
' The implicit conversion is used.
Dim dNonGenericConversion As SampleDelegate = AddressOf AFirstRSecond

' Assigning a method with a matching signature to a generic delegate.
' No conversion is necessary.
Dim dGeneric As SampleGenericDelegate(Of Second, First) = AddressOf ASecondRFirst
' Assigning a method with a more derived return type
' and less derived argument type to a generic delegate.
' The implicit conversion is used.
Dim dGenericConversion As SampleGenericDelegate(Of Second, First) = AddressOf AFirstRSecond
```

<span data-ttu-id="0fba7-109">Weitere Beispiele finden Sie unter [Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) und [Verwenden von Varianz für Delegaten Func und Action Generic (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0fba7-109">For more examples, see [Using Variance in Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

## <a name="variance-in-generic-type-parameters"></a><span data-ttu-id="0fba7-110">Varianz in generischen Typparametern</span><span class="sxs-lookup"><span data-stu-id="0fba7-110">Variance in Generic Type Parameters</span></span>

<span data-ttu-id="0fba7-111">In .NET Framework 4 und höher, können Sie implizite Konvertierung zwischen Delegaten aktivieren, damit, dass generische Delegaten, die verschiedene Typen von generischen Typparametern angegeben haben, zugewiesen werden können, wenn die Typen voneinander, wie erforderlich geerbt werden Varianz.</span><span class="sxs-lookup"><span data-stu-id="0fba7-111">In .NET Framework 4 and later you can enable implicit conversion between delegates, so that generic delegates that have different types specified by generic type parameters can be assigned to each other, if the types are inherited from each other as required by variance.</span></span>

<span data-ttu-id="0fba7-112">Sie müssen einen generischen Parameter in einem Delegaten mithilfe der Schlüsselwörter `in` oder `out` explizit als kovariant oder kontravariant deklarieren, um die implizite Konvertierung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-112">To enable implicit conversion, you must explicitly declare generic parameters in a delegate as covariant or contravariant by using the `in` or `out` keyword.</span></span>

<span data-ttu-id="0fba7-113">Im folgenden Codebeispiel wird veranschaulicht, wie Sie einen Delegaten erstellen können, der über einen kovarianten generischen Typparameter verfügt.</span><span class="sxs-lookup"><span data-stu-id="0fba7-113">The following code example shows how you can create a delegate that has a covariant generic type parameter.</span></span>

```vb
' Type T is declared covariant by using the out keyword.
Public Delegate Function SampleGenericDelegate(Of Out T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "
    ' You can assign delegates to each other,
    ' because the type T is declared covariant.
    Dim dObject As SampleGenericDelegate(Of Object) = dString
End Sub
```

<span data-ttu-id="0fba7-114">Wenn Sie die Unterstützung von Varianz nur verwenden, um Methodensignaturen mit Delegaten zu vergleichen und nicht die Schlüsselwörter `in` und `out` verwenden, kann es möglicherweise passieren, dass Sie zwar Delegate mit identischen Lambdaausdrücken oder -Methoden instanziieren, aber keinen Delegaten einem anderen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="0fba7-114">If you use only variance support to match method signatures with delegate types and do not use the `in` and `out` keywords, you may find that sometimes you can instantiate delegates with identical lambda expressions or methods, but you cannot assign one delegate to another.</span></span>

<span data-ttu-id="0fba7-115">Das folgende Codebeispiel zeigt `SampleGenericDelegate(Of String)` nicht explizit in konvertiert werden `SampleGenericDelegate(Of Object)`, obwohl `String` erbt `Object`.</span><span class="sxs-lookup"><span data-stu-id="0fba7-115">In the following code example, `SampleGenericDelegate(Of String)` can't be explicitly converted to `SampleGenericDelegate(Of Object)`, although `String` inherits `Object`.</span></span> <span data-ttu-id="0fba7-116">Sie können dieses Problem beheben, indem Sie den generischen Parameter `T` mit dem Schlüsselwort `out` markieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-116">You can fix this problem by marking the generic parameter `T` with the `out` keyword.</span></span>

```vb
Public Delegate Function SampleGenericDelegate(Of T)() As T
Sub Test()
    Dim dString As SampleGenericDelegate(Of String) = Function() " "

    ' You can assign the dObject delegate
    ' to the same lambda expression as dString delegate
    ' because of the variance support for
    ' matching method signatures with delegate types.
    Dim dObject As SampleGenericDelegate(Of Object) = Function() " "

    ' The following statement generates a compiler error
    ' because the generic type T is not marked as covariant.
    ' Dim dObject As SampleGenericDelegate(Of Object) = dString

End Sub
```

### <a name="generic-delegates-that-have-variant-type-parameters-in-the-net-framework"></a><span data-ttu-id="0fba7-117">Generische Delegaten mit varianten Typparametern in .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0fba7-117">Generic Delegates That Have Variant Type Parameters in the .NET Framework</span></span>

<span data-ttu-id="0fba7-118">Mit .NET Framework 4 wurde die Unterstützung von Varianz für generische Typparameter in verschiedenen vorhandenen generischen Delegaten eingeführt:</span><span class="sxs-lookup"><span data-stu-id="0fba7-118">.NET Framework 4 introduced variance support for generic type parameters in several existing generic delegates:</span></span>

- <span data-ttu-id="0fba7-119">`Action`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Action%601> und <xref:System.Action%602></span><span class="sxs-lookup"><span data-stu-id="0fba7-119">`Action` delegates from the <xref:System> namespace, for example, <xref:System.Action%601> and <xref:System.Action%602></span></span>

- <span data-ttu-id="0fba7-120">`Func`-Delegaten aus dem <xref:System>-Namespace, z.B. <xref:System.Func%601> und <xref:System.Func%602></span><span class="sxs-lookup"><span data-stu-id="0fba7-120">`Func` delegates from the <xref:System> namespace, for example, <xref:System.Func%601> and <xref:System.Func%602></span></span>

- <span data-ttu-id="0fba7-121">Der <xref:System.Predicate%601>-Delegat.</span><span class="sxs-lookup"><span data-stu-id="0fba7-121">The <xref:System.Predicate%601> delegate</span></span>

- <span data-ttu-id="0fba7-122">Der <xref:System.Comparison%601>-Delegat.</span><span class="sxs-lookup"><span data-stu-id="0fba7-122">The <xref:System.Comparison%601> delegate</span></span>

- <span data-ttu-id="0fba7-123">Der <xref:System.Converter%602>-Delegat.</span><span class="sxs-lookup"><span data-stu-id="0fba7-123">The <xref:System.Converter%602> delegate</span></span>

<span data-ttu-id="0fba7-124">Weitere Informationen und Beispiele finden Sie unter [Verwenden von Varianz für Delegaten Func und Action Generic (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="0fba7-124">For more information and examples, see [Using Variance for Func and Action Generic Delegates (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

### <a name="declaring-variant-type-parameters-in-generic-delegates"></a><span data-ttu-id="0fba7-125">Angeben varianter Typparameter in generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="0fba7-125">Declaring Variant Type Parameters in Generic Delegates</span></span>

<span data-ttu-id="0fba7-126">Wenn ein generischer Delegat über kovariante oder kontravariante generische Typparameter verfügt, kann er als *varianter generischer Delegat* bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="0fba7-126">If a generic delegate has covariant or contravariant generic type parameters, it can be referred to as a *variant generic delegate*.</span></span>

<span data-ttu-id="0fba7-127">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `out` in einem generischen Delegaten als kovariant deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-127">You can declare a generic type parameter covariant in a generic delegate by using the `out` keyword.</span></span> <span data-ttu-id="0fba7-128">Der kovariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fba7-128">The covariant type can be used only as a method return type and not as a type of method arguments.</span></span> <span data-ttu-id="0fba7-129">Das folgende Codebeispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-129">The following code example shows how to declare a covariant generic delegate.</span></span>

```vb
Public Delegate Function DCovariant(Of Out R)() As R
```

<span data-ttu-id="0fba7-130">Sie können einen generischen Typparameter mithilfe des Schlüsselworts `in` in einem generischen Delegaten als kontravariant deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-130">You can declare a generic type parameter contravariant in a generic delegate by using the `in` keyword.</span></span> <span data-ttu-id="0fba7-131">Der kontravariante Typ kann nur als Typ von Methodenrückgaben und nicht von Methodenargumenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0fba7-131">The contravariant type can be used only as a type of method arguments and not as a method return type.</span></span> <span data-ttu-id="0fba7-132">Das folgende Codebeispiel zeigt, wie Sie einen kontravarianten generischen Delegaten deklarieren.</span><span class="sxs-lookup"><span data-stu-id="0fba7-132">The following code example shows how to declare a contravariant generic delegate.</span></span>

```vb
Public Delegate Sub DContravariant(Of In A)(ByVal a As A)
```

> [!IMPORTANT]
> <span data-ttu-id="0fba7-133">`ByRef` -Parametern in Visual Basic können nicht als Variant markiert werden.</span><span class="sxs-lookup"><span data-stu-id="0fba7-133">`ByRef` parameters in Visual Basic can't be marked as variant.</span></span>

<span data-ttu-id="0fba7-134">Es ist auch möglich, Varianz und Kovarianz im gleichen Delegaten, aber für verschiedene Typparameter, zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0fba7-134">It is also possible to support both variance and covariance in the same delegate, but for different type parameters.</span></span> <span data-ttu-id="0fba7-135">Dies wird im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0fba7-135">This is shown in the following example.</span></span>

```vb
Public Delegate Function DVariant(Of In A, Out R)(ByVal a As A) As R
```

### <a name="instantiating-and-invoking-variant-generic-delegates"></a><span data-ttu-id="0fba7-136">Instanziieren und Aufrufen von varianten generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="0fba7-136">Instantiating and Invoking Variant Generic Delegates</span></span>

<span data-ttu-id="0fba7-137">Sie können variante Delegaten genau wie invariante Delegaten instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="0fba7-137">You can instantiate and invoke variant delegates just as you instantiate and invoke invariant delegates.</span></span> <span data-ttu-id="0fba7-138">Im folgenden Beispiel wird der Delegat durch einen Lambdaausdruck instanziiert.</span><span class="sxs-lookup"><span data-stu-id="0fba7-138">In the following example, the delegate is instantiated by a lambda expression.</span></span>

```vb
Dim dvariant As DVariant(Of String, String) = Function(str) str + " "
dvariant("test")
```

### <a name="combining-variant-generic-delegates"></a><span data-ttu-id="0fba7-139">Kombinieren von varianten generischen Delegaten</span><span class="sxs-lookup"><span data-stu-id="0fba7-139">Combining Variant Generic Delegates</span></span>

<span data-ttu-id="0fba7-140">Variante Delegaten sollten nicht kombiniert werden.</span><span class="sxs-lookup"><span data-stu-id="0fba7-140">You should not combine variant delegates.</span></span> <span data-ttu-id="0fba7-141">Die Methode <xref:System.Delegate.Combine%2A> unterstützt keine Konvertierung von varianten Delegaten und erwartet, dass Delegaten vom exakt gleichen Typ sind.</span><span class="sxs-lookup"><span data-stu-id="0fba7-141">The <xref:System.Delegate.Combine%2A> method does not support variant delegate conversion and expects delegates to be of exactly the same type.</span></span> <span data-ttu-id="0fba7-142">Dies kann zu einer Laufzeitausnahme führen, beim Kombinieren von Delegaten entweder mit der <xref:System.Delegate.Combine%2A> Methode (in C# und Visual Basic) oder mithilfe der `+` Operator (in C#), wie im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="0fba7-142">This can lead to a run-time exception when you combine delegates either by using the <xref:System.Delegate.Combine%2A> method (in C# and Visual Basic) or by using the `+` operator (in C#), as shown in the following code example.</span></span>

```vb
Dim actObj As Action(Of Object) = Sub(x) Console.WriteLine("object: {0}", x)
Dim actStr As Action(Of String) = Sub(x) Console.WriteLine("string: {0}", x)

' The following statement throws an exception at run time.
' Dim actCombine = [Delegate].Combine(actStr, actObj)
```

## <a name="variance-in-generic-type-parameters-for-value-and-reference-types"></a><span data-ttu-id="0fba7-143">Varianz in generischen Typparametern für Wert- und Referenztypen</span><span class="sxs-lookup"><span data-stu-id="0fba7-143">Variance in Generic Type Parameters for Value and Reference Types</span></span>

<span data-ttu-id="0fba7-144">Varianz für generische Typparameter wird nur für Referenztypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="0fba7-144">Variance for generic type parameters is supported for reference types only.</span></span> <span data-ttu-id="0fba7-145">Z. B. `DVariant(Of Int)`kann nicht implizit konvertiert `DVariant(Of Object)` oder `DVariant(Of Long)`, da ganze Zahl einen Werttyp handelt.</span><span class="sxs-lookup"><span data-stu-id="0fba7-145">For example, `DVariant(Of Int)`can't be implicitly converted to `DVariant(Of Object)` or `DVariant(Of Long)`, because integer is a value type.</span></span>

<span data-ttu-id="0fba7-146">Das folgende Beispiel veranschaulicht, dass Varianz in generischen Typparametern für Werttypen nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0fba7-146">The following example demonstrates that variance in generic type parameters is not supported for value types.</span></span>

```vb
' The type T is covariant.
Public Delegate Function DVariant(Of Out T)() As T
' The type T is invariant.
Public Delegate Function DInvariant(Of T)() As T
Sub Test()
    Dim i As Integer = 0
    Dim dInt As DInvariant(Of Integer) = Function() i
    Dim dVariantInt As DVariant(Of Integer) = Function() i

    ' All of the following statements generate a compiler error
    ' because type variance in generic parameters is not supported
    ' for value types, even if generic type parameters are declared variant.
    ' Dim dObject As DInvariant(Of Object) = dInt
    ' Dim dLong As DInvariant(Of Long) = dInt
    ' Dim dVariantObject As DInvariant(Of Object) = dInt
    ' Dim dVariantLong As DInvariant(Of Long) = dInt
End Sub
```

## <a name="relaxed-delegate-conversion-in-visual-basic"></a><span data-ttu-id="0fba7-147">Gelockerte Delegatenkonvertierung in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fba7-147">Relaxed Delegate Conversion in Visual Basic</span></span>

<span data-ttu-id="0fba7-148">Gelockerte delegatenkonvertierung ermöglicht eine höhere Flexibilität in Methodensignaturen und Delegattypen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="0fba7-148">Relaxed delegate conversion enables more flexibility in matching method signatures with delegate types.</span></span> <span data-ttu-id="0fba7-149">Angenommen, können dass Sie die Parameterspezifikationen und Rückgabewerte zu verzichten, wenn Sie eine Methode einem Delegaten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="0fba7-149">For example, it lets you omit parameter specifications and omit function return values when you assign a method to a delegate.</span></span> <span data-ttu-id="0fba7-150">Weitere Informationen finden Sie unter [gelockerte Delegatenkonvertierung](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span><span class="sxs-lookup"><span data-stu-id="0fba7-150">For more information, see [Relaxed Delegate Conversion](../../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="0fba7-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fba7-151">See also</span></span>

- [<span data-ttu-id="0fba7-152">Generika</span><span class="sxs-lookup"><span data-stu-id="0fba7-152">Generics</span></span>](~/docs/standard/generics/index.md)
- [<span data-ttu-id="0fba7-153">Using Variance for Func and Action Generic Delegates (Visual Basic) (Verwenden von Varianz für die generischen Delegaten Func und Action (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="0fba7-153">Using Variance for Func and Action Generic Delegates (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
