---
title: 'Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], array access
ms.assetid: 6c46f2af-a730-4855-8638-f136d9abaa12
ms.openlocfilehash: b1538068f3ba37a7637e7dc3913e9511d4380daf
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635190"
---
# <a name="how-to-access-an-array-element-with-a-pointer-c-programming-guide"></a><span data-ttu-id="4617d-102">Gewusst wie: Zugreifen auf ein Arrayelement mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="4617d-102">How to: access an array element with a pointer (C# Programming Guide)</span></span>

<span data-ttu-id="4617d-103">In einem unsicheren Kontext können Sie mittels Zeigerelementzugriff auf ein Element im Speicher zugreifen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4617d-103">In an unsafe context, you can access an element in memory by using pointer element access, as shown in the following example:</span></span>

```csharp
char* charPointer = stackalloc char[123];
for (int i = 65; i < 123; i++)
{
    charPointer[i] = (char)i; //access array elements
}
```

<span data-ttu-id="4617d-104">Der Ausdruck in eckigen Klammern muss implizit in `int`, `uint`, `long` oder `ulong` konvertierbar sein.</span><span class="sxs-lookup"><span data-stu-id="4617d-104">The expression in square brackets must be implicitly convertible to `int`, `uint`, `long`, or `ulong`.</span></span> <span data-ttu-id="4617d-105">Der Vorgang `p[e]` entspricht `*(p+e)`.</span><span class="sxs-lookup"><span data-stu-id="4617d-105">The operation `p[e]` is equivalent to `*(p+e)`.</span></span> <span data-ttu-id="4617d-106">Wie in C und C++ überprüft der Zeigerelementzugriff keine Fehler außerhalb des gültigen Bereichs.</span><span class="sxs-lookup"><span data-stu-id="4617d-106">Like C and C++, the pointer element access does not check for out-of-bounds errors.</span></span>

## <a name="example"></a><span data-ttu-id="4617d-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4617d-107">Example</span></span>

<span data-ttu-id="4617d-108">In diesem Beispiel werden einem Zeichenarray, `charPointer`, 123 Speicheradressen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4617d-108">In this example, 123 memory locations are allocated to a character array, `charPointer`.</span></span> <span data-ttu-id="4617d-109">Das Array wird verwendet, um die Klein- und Großbuchstaben in zwei [for](../../../csharp/language-reference/keywords/for.md)-Schleifen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4617d-109">The array is used to display the lowercase letters and the uppercase letters in two [for](../../../csharp/language-reference/keywords/for.md) loops.</span></span>

<span data-ttu-id="4617d-110">Beachten Sie, dass der Ausdruck `charPointer[i]` und der Ausdruck `*(charPointer + i)` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="4617d-110">Notice that the expression `charPointer[i]` is equivalent to the expression `*(charPointer + i)`, and you can obtain the same result by using either of the two expressions.</span></span>

 [!code-csharp[csProgGuidePointers#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#11)]

 [!code-csharp[csProgGuidePointers#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#12)]

<span data-ttu-id="4617d-111">**Großbuchstaben:**</span><span class="sxs-lookup"><span data-stu-id="4617d-111">**Uppercase letters:**</span></span>  
<span data-ttu-id="4617d-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span><span class="sxs-lookup"><span data-stu-id="4617d-112">**ABCDEFGHIJKLMNOPQRSTUVWXYZ**</span></span>  
<span data-ttu-id="4617d-113">**Kleinbuchstaben:**</span><span class="sxs-lookup"><span data-stu-id="4617d-113">**Lowercase letters:**</span></span>  
<span data-ttu-id="4617d-114">**abcdefghijklmnopqrstuvwxyz**</span><span class="sxs-lookup"><span data-stu-id="4617d-114">**abcdefghijklmnopqrstuvwxyz**</span></span>  

## <a name="see-also"></a><span data-ttu-id="4617d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4617d-115">See also</span></span>

- [<span data-ttu-id="4617d-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4617d-116">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="4617d-117">Typen</span><span class="sxs-lookup"><span data-stu-id="4617d-117">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="4617d-118">unsafe</span><span class="sxs-lookup"><span data-stu-id="4617d-118">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="4617d-119">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4617d-119">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="4617d-120">stackalloc</span><span class="sxs-lookup"><span data-stu-id="4617d-120">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
