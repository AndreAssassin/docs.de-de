---
title: override-Modifizierer – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: cedce26373c49d33ee17602b621f71ef6732d145
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/26/2019
ms.locfileid: "67401543"
---
# <a name="override-c-reference"></a><span data-ttu-id="56e39-102">override (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="56e39-102">override (C# Reference)</span></span>

<span data-ttu-id="56e39-103">Der `override`-Modifizierer wird benötigt, um die abstrakte oder virtuelle Implementierung einer geerbten Methode, Eigenschaft, eines Indexers oder Ereignisses zu erweitern oder ändern.</span><span class="sxs-lookup"><span data-stu-id="56e39-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="56e39-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56e39-104">Example</span></span>

<span data-ttu-id="56e39-105">In diesem Beispiel muss die `Square`-Klasse eine überschriebene Implementierung von `Area` bereitstellen, da `Area` von der abstrakten `ShapesClass` geerbt wurde:</span><span class="sxs-lookup"><span data-stu-id="56e39-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="56e39-106">Eine `override`-Methode stellt eine neue Implementierung eines Members bereit, der von einer Basisklasse geerbt wurde.</span><span class="sxs-lookup"><span data-stu-id="56e39-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="56e39-107">Die Methode, die durch eine `override`-Deklaration überschrieben wird, wird als die überschriebene Basismethode bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="56e39-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="56e39-108">Die überschriebene Basismethode muss die gleiche Signatur wie die `override`-Methode haben.</span><span class="sxs-lookup"><span data-stu-id="56e39-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="56e39-109">Weitere Informationen zur Vererbung in C# finden Sie unter [Vererbung](../../programming-guide/classes-and-structs/inheritance.md).</span><span class="sxs-lookup"><span data-stu-id="56e39-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="56e39-110">Sie können keine nicht virtuelle oder statische Methode überschreiben.</span><span class="sxs-lookup"><span data-stu-id="56e39-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="56e39-111">Die überschriebene Basismethode muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="56e39-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="56e39-112">Ein `override`-Deklaration kann nicht die Erreichbarkeit auf die `virtual` Methode ändern.</span><span class="sxs-lookup"><span data-stu-id="56e39-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="56e39-113">Sowohl die Methode `override` als auch `virtual` müssen den gleichen [Zugriffsebenenmodifizierer](access-modifiers.md) besitzen.</span><span class="sxs-lookup"><span data-stu-id="56e39-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="56e39-114">Sie können die Modifizierer `new`, `static` oder `virtual` nicht verwenden, um eine `override`-Methode zu ändern.</span><span class="sxs-lookup"><span data-stu-id="56e39-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="56e39-115">Eine überschreibende Eigenschaftsdeklaration muss genau den selben Zugriffsmodifizierertyp und -namen wie die geerbte Eigenschaft angeben, und die überschriebene Eigenschaft muss `virtual`, `abstract` oder `override` sein.</span><span class="sxs-lookup"><span data-stu-id="56e39-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="56e39-116">Weitere Informationen zur Verwendung des `override`-Schlüsselworts finden Sie unter [Versionsverwaltung mit den Schlüsselwörtern „override“ und „new“](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) und [Wann müssen die Schlüsselwörter „override“ und „new“ verwendet werden?](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span><span class="sxs-lookup"><span data-stu-id="56e39-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="56e39-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56e39-117">Example</span></span>

<span data-ttu-id="56e39-118">In diesem Beispiel wird eine Basisklasse namens `Employee` und eine abgeleitete Klasse namens `SalesEmployee` definiert.</span><span class="sxs-lookup"><span data-stu-id="56e39-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="56e39-119">Die `SalesEmployee`-Klasse enthält ein zusätzliches Feld `salesbonus`, und überschreibt die `CalculatePay`-Methode, um dies zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="56e39-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="56e39-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="56e39-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="56e39-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56e39-121">See also</span></span>

- [<span data-ttu-id="56e39-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="56e39-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="56e39-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="56e39-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="56e39-124">Vererbung</span><span class="sxs-lookup"><span data-stu-id="56e39-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="56e39-125">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="56e39-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="56e39-126">Modifizierer</span><span class="sxs-lookup"><span data-stu-id="56e39-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="56e39-127">abstract</span><span class="sxs-lookup"><span data-stu-id="56e39-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="56e39-128">virtual</span><span class="sxs-lookup"><span data-stu-id="56e39-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="56e39-129">new (Modifizierer)</span><span class="sxs-lookup"><span data-stu-id="56e39-129">new (modifier)</span></span>](new-modifier.md)
- [<span data-ttu-id="56e39-130">Polymorphismus</span><span class="sxs-lookup"><span data-stu-id="56e39-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
