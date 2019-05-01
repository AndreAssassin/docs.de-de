---
title: Out (generischer Modifizierer) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.VarianceOut
helpviewer_keywords:
- Out keyword [Visual Basic]
- covariance, Out keyword [Visual Basic]
ms.assetid: c4418369-1518-4a46-9a1e-054c61038eca
ms.openlocfilehash: fa14e83af16cd30a72ca1c165596fa9320842fce
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053924"
---
# <a name="out-generic-modifier-visual-basic"></a><span data-ttu-id="fcfdf-102">Out (generischer Modifizierer) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fcfdf-102">Out (Generic Modifier) (Visual Basic)</span></span>

<span data-ttu-id="fcfdf-103">Für generische Typparameter der `Out` -Schlüsselwort Gibt an, dass der Typ kovariant ist.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-103">For generic type parameters, the `Out` keyword specifies that the type is covariant.</span></span>

## <a name="remarks"></a><span data-ttu-id="fcfdf-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fcfdf-104">Remarks</span></span>

<span data-ttu-id="fcfdf-105">Kovarianz ermöglicht Ihnen die Verwendung eines stärker abgeleiteten Typs als durch den generischen Parameter angegeben.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-105">Covariance enables you to use a more derived type than that specified by the generic parameter.</span></span> <span data-ttu-id="fcfdf-106">Dadurch wird eine implizite Konvertierung von Klassen berücksichtigt, die variante Schnittstellen und Konvertierung von Delegattypen implementiert.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-106">This allows for implicit conversion of classes that implement variant interfaces and implicit conversion of delegate types.</span></span>

<span data-ttu-id="fcfdf-107">Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md).</span><span class="sxs-lookup"><span data-stu-id="fcfdf-107">For more information, see [Covariance and Contravariance](../../programming-guide/concepts/covariance-contravariance/index.md).</span></span>

## <a name="rules"></a><span data-ttu-id="fcfdf-108">Regeln</span><span class="sxs-lookup"><span data-stu-id="fcfdf-108">Rules</span></span>

<span data-ttu-id="fcfdf-109">Sie können das `Out`-Schlüsselwort in generischen Schnittstellen und Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-109">You can use the `Out` keyword in generic interfaces and delegates.</span></span>

<span data-ttu-id="fcfdf-110">In einer generischen Schnittstelle kann ein Typparameter als kovariant deklariert werden, wenn er die folgenden Bedingungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="fcfdf-110">In a generic interface, a type parameter can be declared covariant if it satisfies the following conditions:</span></span>

- <span data-ttu-id="fcfdf-111">Der Typparameter wird nur als Rückgabetyp von Schnittstellenmethoden, und nicht als Typ von Methodenargumenten verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-111">The type parameter is used only as a return type of interface methods and not used as a type of method arguments.</span></span>

    > [!NOTE]
    > <span data-ttu-id="fcfdf-112">Es gibt allerdings eine Ausnahme zu dieser Regel.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-112">There is one exception to this rule.</span></span> <span data-ttu-id="fcfdf-113">Wenn Sie in einer kovarianten Schnittstelle einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für diesen Delegaten verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-113">If in a covariant interface you have a contravariant generic delegate as a method parameter, you can use the covariant type as a generic type parameter for this delegate.</span></span> <span data-ttu-id="fcfdf-114">Weitere Informationen über kovariante und kontravariante generische Delegate finden Sie unter [Varianz in Delegaten](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Verwenden von Varianz für die generischen Delegaten Func und Action](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span><span class="sxs-lookup"><span data-stu-id="fcfdf-114">For more information about covariant and contravariant generic delegates, see [Variance in Delegates](../../programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) and [Using Variance for Func and Action Generic Delegates](../../programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).</span></span>

- <span data-ttu-id="fcfdf-115">Der Typparameter wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-115">The type parameter is not used as a generic constraint for the interface methods.</span></span>

<span data-ttu-id="fcfdf-116">In einem generischen Delegaten kann ein Typparameter kovariant deklariert werden, wenn sie nur als Methodenrückgabetyp verwendet und nicht für Methodenargumente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-116">In a generic delegate, a type parameter can be declared covariant if it is used only as a method return type and not used for method arguments.</span></span>

<span data-ttu-id="fcfdf-117">Kovarianz und Kontravarianz werden für Verweistypen unterstützt, aber nicht für Werttypen.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-117">Covariance and contravariance are supported for reference types, but they are not supported for value types.</span></span>

<span data-ttu-id="fcfdf-118">In Visual Basic können Sie Ereignisse in Schnittstellen mit kovarianten deklarieren, ohne Typ des Delegaten angeben.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-118">In Visual Basic, you cannot declare events in covariant interfaces without specifying the delegate type.</span></span> <span data-ttu-id="fcfdf-119">Darüber hinaus werden kovariante Schnittstellen keine geschachtelten Klassen, Enumerationen und Strukturen, aber geschachtelte Schnittstellen.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-119">Also, covariant interfaces cannot have nested classes, enums, or structures, but they can have nested interfaces.</span></span>

## <a name="behavior"></a><span data-ttu-id="fcfdf-120">Verhalten</span><span class="sxs-lookup"><span data-stu-id="fcfdf-120">Behavior</span></span>

<span data-ttu-id="fcfdf-121">Die Methoden einer Schnittstelle, die einen kovarianten Typparameter hat, können mehr abgeleitete Typen als durch den Typparameter angegeben zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-121">An interface that has a covariant type parameter enables its methods to return more derived types than those specified by the type parameter.</span></span> <span data-ttu-id="fcfdf-122">Da z.B. in .NET Framework 4 Typ T in <xref:System.Collections.Generic.IEnumerable%601> kovariant ist, können Sie ein Objekt des `IEnumerable(Of String)`-Typs an ein Objekt des `IEnumerable(Of Object)`-Typs zuweisen, ohne besondere Konvertierungsmethoden zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-122">For example, because in .NET Framework 4, in <xref:System.Collections.Generic.IEnumerable%601>, type T is covariant, you can assign an object of the `IEnumerable(Of String)` type to an object of the `IEnumerable(Of Object)` type without using any special conversion methods.</span></span>

<span data-ttu-id="fcfdf-123">Ein kovarianter Delegat kann einem anderen Delegaten desselben Typs zugewiesen werden, jedoch mit einem stärker abgeleiteten generischen Typparameter.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-123">A covariant delegate can be assigned another delegate of the same type, but with a more derived generic type parameter.</span></span>

## <a name="example"></a><span data-ttu-id="fcfdf-124">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcfdf-124">Example</span></span>

<span data-ttu-id="fcfdf-125">Im folgenden Beispiel wird gezeigt, wie Sie eine kovariante generische Schnittstelle deklarieren, erweitern und implementieren.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-125">The following example shows how to declare, extend, and implement a covariant generic interface.</span></span> <span data-ttu-id="fcfdf-126">Es wird auch gezeigt, wie eine implizite Konvertierung für Klassen verwendet wird, die eine kovariante Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-126">It also shows how to use implicit conversion for classes that implement a covariant interface.</span></span>

[!code-vb[vbVarianceKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#3)]

## <a name="example"></a><span data-ttu-id="fcfdf-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fcfdf-127">Example</span></span>

<span data-ttu-id="fcfdf-128">Das folgende Beispiel zeigt, wie Sie einen kovarianten generischen Delegaten deklarieren, instanziieren und aufrufen.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-128">The following example shows how to declare, instantiate, and invoke a covariant generic delegate.</span></span> <span data-ttu-id="fcfdf-129">Es wird auch gezeigt, wie Sie die implizite Konvertierung für Delegattypen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fcfdf-129">It also shows how you can use implicit conversion for delegate types.</span></span>

[!code-vb[vbVarianceKeywords#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/vbvariancekeywords/vb/module1.vb#4)]

## <a name="see-also"></a><span data-ttu-id="fcfdf-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fcfdf-130">See also</span></span>

- [<span data-ttu-id="fcfdf-131">Varianz in generischen Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="fcfdf-131">Variance in Generic Interfaces</span></span>](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [<span data-ttu-id="fcfdf-132">In</span><span class="sxs-lookup"><span data-stu-id="fcfdf-132">In</span></span>](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
