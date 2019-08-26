---
title: Arrays als Objekte – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], as objects
ms.assetid: f76d4403-bd0a-42a0-9bc8-694c55b2c926
ms.openlocfilehash: fd4496e0f84953204ad8c3f40db699e911c3f477
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69597363"
---
# <a name="arrays-as-objects-c-programming-guide"></a><span data-ttu-id="d032a-102">Arrays als Objekte (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="d032a-102">Arrays as Objects (C# Programming Guide)</span></span>

<span data-ttu-id="d032a-103">In C# sind Arrays tatsächlich Objekte und nicht nur adressierbare Regionen zusammenhängender Speicher wie in C und C++.</span><span class="sxs-lookup"><span data-stu-id="d032a-103">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="d032a-104"><xref:System.Array> ist der abstrakte Basistyp aller Typen von Arrays.</span><span class="sxs-lookup"><span data-stu-id="d032a-104"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="d032a-105">Sie können die Eigenschaften und die anderen Klassenmember verwenden, über die <xref:System.Array> verfügt.</span><span class="sxs-lookup"><span data-stu-id="d032a-105">You can use the properties, and other class members, that <xref:System.Array> has.</span></span> <span data-ttu-id="d032a-106">Ein Beispiel dafür wäre die Verwendung der <xref:System.Array.Length%2A>-Eigenschaft, um die Länge eines Arrays zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="d032a-106">An example of this would be using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="d032a-107">Der folgende Code weist die Länge des `numbers`-Arrays, die `5` beträgt, einer Variablen mit dem Namen `lengthOfNumbers` zu:</span><span class="sxs-lookup"><span data-stu-id="d032a-107">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>  
  
 [!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]  
  
 <span data-ttu-id="d032a-108">Die <xref:System.Array>-Klasse bietet viele weitere nützliche Methoden und Eigenschaften zum Sortieren, Durchsuchen und Kopieren von Arrays.</span><span class="sxs-lookup"><span data-stu-id="d032a-108">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d032a-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d032a-109">Example</span></span>

 <span data-ttu-id="d032a-110">In diesem Beispiel wird die <xref:System.Array.Rank%2A>-Eigenschaft verwendet, um die Anzahl der Dimensionen eines Arrays anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d032a-110">This example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>  
  
 [!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d032a-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d032a-111">See also</span></span>

- [<span data-ttu-id="d032a-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d032a-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d032a-113">Arrays</span><span class="sxs-lookup"><span data-stu-id="d032a-113">Arrays</span></span>](./index.md)
- [<span data-ttu-id="d032a-114">Eindimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="d032a-114">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="d032a-115">Mehrdimensionale Arrays</span><span class="sxs-lookup"><span data-stu-id="d032a-115">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="d032a-116">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="d032a-116">Jagged Arrays</span></span>](./jagged-arrays.md)
