---
title: Generische Typparameter – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- generics [C#], type parameters
- type parameters [C#]
ms.assetid: a03b0ab2-0606-4b41-b7bf-e64d5bb4d18f
ms.openlocfilehash: 096fce3affb9461c57ae9c0ffd57367d1b4349df
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/31/2019
ms.locfileid: "66423419"
---
# <a name="generic-type-parameters-c-programming-guide"></a><span data-ttu-id="ffe4a-102">Generische Typparameter (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ffe4a-102">Generic type parameters (C# Programming Guide)</span></span>

<span data-ttu-id="ffe4a-103">Bei der Definition eines generischen Typs oder einer Methode ist ein Typparameter ein Platzhalter für einen bestimmten Typ, den ein Client angibt, wenn eine Instanz des generischen Typs erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-103">In a generic type or method definition, a type parameter is a placeholder for a specific type that a client specifies when they create an instance of the generic type.</span></span> <span data-ttu-id="ffe4a-104">Eine generische Klasse, z.B. die unter [Einführung in Generics](../../../csharp/programming-guide/generics/index.md) aufgelistete Klasse `GenericList<T>`, kann nicht ohne Anpassung verwendet werden, denn sie ist nicht wirklich ein Typ, sondern mehr wie die Kopie eines Typs.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-104">A generic class, such as `GenericList<T>` listed in [Introduction to Generics](../../../csharp/programming-guide/generics/index.md), cannot be used as-is because it is not really a type; it is more like a blueprint for a type.</span></span> <span data-ttu-id="ffe4a-105">Um `GenericList<T>` verwenden zu können, muss der Clientcode einen konstruierten Typ deklarieren und instanziieren, indem er ein Typargument in spitzen Klammern angibt.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-105">To use `GenericList<T>`, client code must declare and instantiate a constructed type by specifying a type argument inside the angle brackets.</span></span> <span data-ttu-id="ffe4a-106">Das Typargument für diese spezielle Klasse kann jeder Typ sein, der vom Compiler erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-106">The type argument for this particular class can be any type recognized by the compiler.</span></span> <span data-ttu-id="ffe4a-107">Instanzen von konstruierten Typen können in beliebiger Zahl erstellt werden, wobei jede Instanz ein anderes Typargument verwendet, z.B.:</span><span class="sxs-lookup"><span data-stu-id="ffe4a-107">Any number of constructed type instances can be created, each one using a different type argument, as follows:</span></span>  
  
[!code-csharp[csProgGuideGenerics#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#7)]  
  
<span data-ttu-id="ffe4a-108">Bei jeder dieser Instanzen von `GenericList<T>` wird jedes Vorkommen von `T` in der Klasse zur Laufzeit durch das Typargument ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-108">In each of these instances of `GenericList<T>`, every occurrence of `T` in the class is substituted at run time with the type argument.</span></span> <span data-ttu-id="ffe4a-109">Aufgrund dieser Ersetzung werden drei separate typsichere und effiziente Objekte mithilfe einer einzigen Klassendefinition erstellt.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-109">By means of this substitution, we have created three separate type-safe and efficient objects using a single class definition.</span></span> <span data-ttu-id="ffe4a-110">Weitere Informationen dazu, wie diese Ersetzung von der CLR ausgeführt wird, finden Sie unter [Generics zur Laufzeit](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span><span class="sxs-lookup"><span data-stu-id="ffe4a-110">For more information on how this substitution is performed by the CLR, see [Generics in the Run Time](../../../csharp/programming-guide/generics/generics-in-the-run-time.md).</span></span>  
  
## <a name="type-parameter-naming-guidelines"></a><span data-ttu-id="ffe4a-111">Richtlinien für die Benennung von Typparametern</span><span class="sxs-lookup"><span data-stu-id="ffe4a-111">Type parameter naming guidelines</span></span>  
  
- <span data-ttu-id="ffe4a-112">**Verwenden** Sie zur Benennung von generischen Typparametern beschreibende Namen, es sei denn, ein Name aus einem einzelnen Buchstaben reicht als Erklärung völlig aus, und ein beschreibender Name würde das Verständnis für den Namen nicht wirklich erhöhen.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-112">**Do** name generic type parameters with descriptive names, unless a single letter name is completely self explanatory and a descriptive name would not add value.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#8)]  
  
- <span data-ttu-id="ffe4a-113">**Verwenden** Sie T als Typparametername für Typen, die einen einzelnen Buchstaben als Typparameter haben.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-113">**Consider** using T as the type parameter name for types with one single letter type parameter.</span></span>  
  
   [!code-csharp[csProgGuideGenerics#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#9)]  
  
- <span data-ttu-id="ffe4a-114">**Verwenden** Sie das Präfix „T“ für beschreibende Typparameternamen.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-114">**Do** prefix descriptive type parameter names with "T".</span></span>  
  
   [!code-csharp[csProgGuideGenerics#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideGenerics/CS/Generics.cs#10)]  
  
- <span data-ttu-id="ffe4a-115">**Überlegen** Sie, ob Sie Einschränkungen, die für einen Typparameter gelten, im Namen des Parameters angeben möchten.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-115">**Consider** indicating constraints placed on a type parameter in the name of parameter.</span></span> <span data-ttu-id="ffe4a-116">Ein auf `ISession` eingeschränkter Parameter könnte z.B. `TSession` genannt werden.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-116">For example, a parameter constrained to `ISession` may be called `TSession`.</span></span>

<span data-ttu-id="ffe4a-117">Die Codeanalyseregel [CA1715](/visualstudio/code-quality/ca1715-identifiers-should-have-correct-prefix) kann verwendet werden, um sicherzustellen, dass Typparameter entsprechend benannt werden.</span><span class="sxs-lookup"><span data-stu-id="ffe4a-117">The code analysis rule [CA1715](/visualstudio/code-quality/ca1715-identifiers-should-have-correct-prefix) can be used to ensure that type parameters are named appropriately.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ffe4a-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ffe4a-118">See also</span></span>

- <xref:System.Collections.Generic>
- [<span data-ttu-id="ffe4a-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ffe4a-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="ffe4a-120">Generics</span><span class="sxs-lookup"><span data-stu-id="ffe4a-120">Generics</span></span>](../../../csharp/programming-guide/generics/index.md)
- [<span data-ttu-id="ffe4a-121">Unterschiede zwischen C++-Vorlagen und C#-Generics</span><span class="sxs-lookup"><span data-stu-id="ffe4a-121">Differences Between C++ Templates and C# Generics</span></span>](../../../csharp/programming-guide/generics/differences-between-cpp-templates-and-csharp-generics.md)
