---
title: interface – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 058d6b96e96a3237ebac2ca079807fd154715d68
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69608647"
---
# <a name="interface-c-reference"></a><span data-ttu-id="bc32d-102">interface (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="bc32d-102">interface (C# Reference)</span></span>

<span data-ttu-id="bc32d-103">Eine Schnittstelle enthält nur die Signaturen von [Methoden](../../programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../programming-guide/classes-and-structs/properties.md), [Ereignissen](../../programming-guide/events/index.md) oder [Indexern](../../programming-guide/indexers/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc32d-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="bc32d-104">Eine Klasse oder eine Struktur, die die Schnittstelle implementiert, muss die Member der Schnittstelle implementieren, die in der Schnittstellendefinition angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bc32d-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="bc32d-105">Im folgenden Beispiel muss die Klasse `ImplementationClass` eine Methode mit dem Namen `SampleMethod` implementieren, die keine Parameter hat und `void` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bc32d-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="bc32d-106">Weitere Informationen und Beispiele finden Sie unter [Schnittstellen](../../programming-guide/interfaces/index.md).</span><span class="sxs-lookup"><span data-stu-id="bc32d-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="bc32d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc32d-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="bc32d-108">Eine Schnittstelle kann ein Member eines Namespaces oder einer Klasse sein und Signaturen der folgenden Member enthalten:</span><span class="sxs-lookup"><span data-stu-id="bc32d-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="bc32d-109">Methoden</span><span class="sxs-lookup"><span data-stu-id="bc32d-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="bc32d-110">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bc32d-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="bc32d-111">Indexer</span><span class="sxs-lookup"><span data-stu-id="bc32d-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="bc32d-112">Ereignisse</span><span class="sxs-lookup"><span data-stu-id="bc32d-112">Events</span></span>](event.md)

<span data-ttu-id="bc32d-113">Eine Schnittstelle kann von einer oder mehreren Basisschnittstellen erben.</span><span class="sxs-lookup"><span data-stu-id="bc32d-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="bc32d-114">Wenn eine Basistypliste sowohl eine Basisklasse als auch Schnittstellen umfasst, muss die Basisklasse zuerst in der Liste stehen.</span><span class="sxs-lookup"><span data-stu-id="bc32d-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="bc32d-115">Eine Klasse, die eine Schnittstelle implementiert, kann Member dieser Schnittstelle explizit implementieren.</span><span class="sxs-lookup"><span data-stu-id="bc32d-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="bc32d-116">Auf einen explizit implementierten Member kann nicht durch eine Klasseninstanz zugegriffen werden, sondern nur durch eine Schnittstelleninstanz.</span><span class="sxs-lookup"><span data-stu-id="bc32d-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="bc32d-117">Weitere Details und Codebeispiele zur expliziten Schnittstellenimplementierung finden Sie unter [Explizite Schnittstellenimplementierung](../../programming-guide/interfaces/explicit-interface-implementation.md).</span><span class="sxs-lookup"><span data-stu-id="bc32d-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="bc32d-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc32d-118">Example</span></span>

<span data-ttu-id="bc32d-119">Das folgende Beispiel veranschaulicht die Schnittstellenimplementierung.</span><span class="sxs-lookup"><span data-stu-id="bc32d-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="bc32d-120">In diesem Beispiel enthält die Schnittstelle die Eigenschaftendeklaration, und die Klasse enthält die Implementierung.</span><span class="sxs-lookup"><span data-stu-id="bc32d-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="bc32d-121">Eine beliebige Instanz einer Klasse, die `IPoint` implementiert, hat die ganzzahligen Eigenschaften `x` und `y`.</span><span class="sxs-lookup"><span data-stu-id="bc32d-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="bc32d-122">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="bc32d-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="bc32d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bc32d-123">See also</span></span>

- [<span data-ttu-id="bc32d-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="bc32d-124">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="bc32d-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="bc32d-125">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="bc32d-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="bc32d-126">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="bc32d-127">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="bc32d-127">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="bc32d-128">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc32d-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
- [<span data-ttu-id="bc32d-129">Verwenden von Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="bc32d-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)
- [<span data-ttu-id="bc32d-130">Verwenden von Indexern</span><span class="sxs-lookup"><span data-stu-id="bc32d-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)
- [<span data-ttu-id="bc32d-131">class</span><span class="sxs-lookup"><span data-stu-id="bc32d-131">class</span></span>](class.md)
- [<span data-ttu-id="bc32d-132">struct</span><span class="sxs-lookup"><span data-stu-id="bc32d-132">struct</span></span>](struct.md)
- [<span data-ttu-id="bc32d-133">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="bc32d-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
