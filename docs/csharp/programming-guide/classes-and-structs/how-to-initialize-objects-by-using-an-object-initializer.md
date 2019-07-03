---
title: 'Vorgehensweise: Initialisieren von Objekten mit einem Objektinitialisierer – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 7b31e28c23a70e9f0794c82feb2a984c40ee9d0f
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67267583"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a><span data-ttu-id="a426f-102">Vorgehensweise: Initialisieren von Objekten mit einem Objektinitialisierer (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a426f-102">How to: Initialize Objects by Using an Object Initializer (C# Programming Guide)</span></span>

<span data-ttu-id="a426f-103">Mit Objektinitialisierern können Sie deklarativ Typenobjekte initialisieren, ohne explizit einen Konstruktor für den Typ aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="a426f-103">You can use object initializers to initialize type objects in a declarative manner without explicitly invoking a constructor for the type.</span></span>  
  
<span data-ttu-id="a426f-104">Die folgenden Beispiele zeigen, wie Objektinitialisierer mit benannten Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a426f-104">The following examples show how to use object initializers with named objects.</span></span> <span data-ttu-id="a426f-105">Der Compiler verarbeitet Objektinitialisierer, indem zuerst auf den Standardinstanzinstruktor zugegriffen wird und anschließend die Memeberinitialisierungen verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="a426f-105">The compiler processes object initializers by first accessing the default instance constructor and then processing the member initializations.</span></span> <span data-ttu-id="a426f-106">Daher tritt bei Objektinitialisierern, die öffentlichen Zugriff benötigen, ein Fehler auf, wenn der parameterlose Konstruktor in der Klasse als `private` deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="a426f-106">Therefore, if the parameterless constructor is declared as `private` in the class, object initializers that require public access will fail.</span></span>
  
<span data-ttu-id="a426f-107">Sie müssen einen Objektinitialisierer verwenden, wenn Sie einen anonymen Typ definieren.</span><span class="sxs-lookup"><span data-stu-id="a426f-107">You must use an object initializer if you're defining an anonymous type.</span></span> <span data-ttu-id="a426f-108">Weitere Informationen finden Sie unter [Vorgehensweise: Zurückgeben von Teilmengen von Elementeigenschaften in einer Abfrage](how-to-return-subsets-of-element-properties-in-a-query.md).</span><span class="sxs-lookup"><span data-stu-id="a426f-108">For more information, see [How to: Return Subsets of Element Properties in a Query](how-to-return-subsets-of-element-properties-in-a-query.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a426f-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a426f-109">Example</span></span>  

<span data-ttu-id="a426f-110">Im folgenden Beispiel wird das Initialisieren eines neuen `StudentName`-Typs mithilfe eines Objektinitialisierers gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a426f-110">The following example shows how to initialize a new `StudentName` type by using object initializers.</span></span> <span data-ttu-id="a426f-111">Dieses Beispiel legt Eigenschaften für den Typ `StudentName` fest:</span><span class="sxs-lookup"><span data-stu-id="a426f-111">This example sets properties in the `StudentName` type:</span></span>
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

<span data-ttu-id="a426f-112">Objektinitialisierer können dafür verwendet werden, Indexer in einem Objekt festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a426f-112">Object initializers can be used to set indexers in an object.</span></span> <span data-ttu-id="a426f-113">Das folgende Beispiel definiert eine `BaseballTeam`-Klasse, die einen Indexer verwendet, um Player an verschiedenen Positionen abzurufen und festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a426f-113">The following example defines a `BaseballTeam` class that uses an indexer to get and set players at different positions.</span></span> <span data-ttu-id="a426f-114">Der Initialisierer kann Player auf Grundlage der Abkürzung für die Position oder der Zahl, die für jede einzelne Position auf einem Baseball-Scoresheet verwendet wird, zuweisen:</span><span class="sxs-lookup"><span data-stu-id="a426f-114">The initializer can assign players, based on the abbreviation for the position, or the number used for each position baseball scorecards:</span></span>

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a><span data-ttu-id="a426f-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a426f-115">See also</span></span>

- [<span data-ttu-id="a426f-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a426f-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="a426f-117">Objekt- und Auflistungsinitialisierer</span><span class="sxs-lookup"><span data-stu-id="a426f-117">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
