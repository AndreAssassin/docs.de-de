---
title: Puffer fester Größe – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 04/20/2018
helpviewer_keywords:
- fixed size buffers [C#]
- unsafe buffers [C#]
- unsafe code [C#], fixed size buffers
ms.openlocfilehash: 5bfd9f3f559e4780b910a2e5a3430b08a2183ee3
ms.sourcegitcommit: 34593b4d0be779699d38a9949d6aec11561657ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2019
ms.locfileid: "66833502"
---
# <a name="fixed-size-buffers-c-programming-guide"></a><span data-ttu-id="86b99-102">Puffer fester Größe (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="86b99-102">Fixed Size Buffers (C# Programming Guide)</span></span>

<span data-ttu-id="86b99-103">In C# können Sie die [fixed](../../language-reference/keywords/fixed-statement.md)-Anweisung verwenden, um einen Puffer mit einem Array fester Größe in einer Datenstruktur zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="86b99-103">In C#, you can use the [fixed](../../language-reference/keywords/fixed-statement.md) statement to create a buffer with a fixed size array in a data structure.</span></span> <span data-ttu-id="86b99-104">Puffer mit fester Größe sind nützlich, wenn Sie Methoden schreiben, die mit Datenquellen aus anderen Sprachen oder Plattformen zusammenarbeiten.</span><span class="sxs-lookup"><span data-stu-id="86b99-104">Fixed size buffers are useful when you write methods that interop with data sources from other languages or platforms.</span></span> <span data-ttu-id="86b99-105">Das Array fester Größe kann sämtliche Attribute und Modifizierer, die für reguläre Strukturmember zulässig sind, in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="86b99-105">The fixed array can take any attributes or modifiers that are allowed for regular struct members.</span></span> <span data-ttu-id="86b99-106">Die einzige Einschränkung besteht darin, dass der Arraytyp `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float` oder `double` sein muss.</span><span class="sxs-lookup"><span data-stu-id="86b99-106">The only restriction is that the array type must be `bool`, `byte`, `char`, `short`, `int`, `long`, `sbyte`, `ushort`, `uint`, `ulong`, `float`, or `double`.</span></span>

```csharp
private fixed char name[30];
```

## <a name="remarks"></a><span data-ttu-id="86b99-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="86b99-107">Remarks</span></span>

<span data-ttu-id="86b99-108">Eine C#-Struktur in sicherem Code, die ein Array enthält, enthält nicht die Elemente des Arrays.</span><span class="sxs-lookup"><span data-stu-id="86b99-108">In safe code, a C# struct that contains an array does not contain the array elements.</span></span> <span data-ttu-id="86b99-109">Stattdessen enthält die Struktur einen Verweis auf die Elemente.</span><span class="sxs-lookup"><span data-stu-id="86b99-109">Instead, the struct contains a reference to the elements.</span></span> <span data-ttu-id="86b99-110">Sie können ein Array mit einer festen Größe in eine [Struktur](../../language-reference/keywords/struct.md) einbetten, wenn es in einem [unsicheren](../../language-reference/keywords/unsafe.md) Codeblock verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="86b99-110">You can embed an array of fixed size in a [struct](../../language-reference/keywords/struct.md) when it is used in an [unsafe](../../language-reference/keywords/unsafe.md) code block.</span></span>

<span data-ttu-id="86b99-111">Das folgende `struct` ist 8 Byte groß.</span><span class="sxs-lookup"><span data-stu-id="86b99-111">The following `struct` is 8 bytes in size.</span></span> <span data-ttu-id="86b99-112">Das `pathName`-Array ist ein Verweis:</span><span class="sxs-lookup"><span data-stu-id="86b99-112">The `pathName` array is a reference:</span></span>

[!code-csharp[Struct with embedded array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#6)]

<span data-ttu-id="86b99-113">Ein `struct` kann ein eingebettetes Array in unsicheren Code enthalten.</span><span class="sxs-lookup"><span data-stu-id="86b99-113">A `struct` can contain an embedded array in unsafe code.</span></span> <span data-ttu-id="86b99-114">Im folgenden Beispiel verfügt das `fixedBuffer`-Array über eine feste Größe.</span><span class="sxs-lookup"><span data-stu-id="86b99-114">In the following example, the `fixedBuffer` array has a fixed size.</span></span> <span data-ttu-id="86b99-115">Sie können eine `fixed`-Anweisung verwenden, um einen Zeiger auf das erste Element festzulegen.</span><span class="sxs-lookup"><span data-stu-id="86b99-115">You use a `fixed` statement to establish a pointer to the first element.</span></span> <span data-ttu-id="86b99-116">Über diesen Zeiger können Sie auf die Elemente des Arrays zugreifen.</span><span class="sxs-lookup"><span data-stu-id="86b99-116">You access the elements of the array through this pointer.</span></span> <span data-ttu-id="86b99-117">Die `fixed`-Anweisung fixiert das Instanzenfeld `fixedBuffer` an einem bestimmten Speicherort im Arbeitsspeicher.</span><span class="sxs-lookup"><span data-stu-id="86b99-117">The `fixed` statement pins the `fixedBuffer` instance field to a specific location in memory.</span></span>

[!code-csharp[Struct with embedded inline array](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#7)]

<span data-ttu-id="86b99-118">Die Größe des 128-Element-`char`-Arrays beträgt 256 Bytes.</span><span class="sxs-lookup"><span data-stu-id="86b99-118">The size of the 128 element `char` array is 256 bytes.</span></span> <span data-ttu-id="86b99-119">[Char](../../language-reference/keywords/char.md)-Puffer mit fester Größe verwenden immer zwei Bytes pro Zeichen, unabhängig von der Codierung.</span><span class="sxs-lookup"><span data-stu-id="86b99-119">Fixed size [char](../../language-reference/keywords/char.md) buffers always take two bytes per character, regardless of the encoding.</span></span> <span data-ttu-id="86b99-120">Dies gilt auch, wenn Char-Puffer zu API-Methoden oder Strukturen mit `CharSet = CharSet.Auto` oder `CharSet = CharSet.Ansi` gemarshallt werden.</span><span class="sxs-lookup"><span data-stu-id="86b99-120">This is true even when char buffers are marshaled to API methods or structs with `CharSet = CharSet.Auto` or `CharSet = CharSet.Ansi`.</span></span> <span data-ttu-id="86b99-121">Weitere Informationen finden Sie unter <xref:System.Runtime.InteropServices.CharSet>.</span><span class="sxs-lookup"><span data-stu-id="86b99-121">For more information, see <xref:System.Runtime.InteropServices.CharSet>.</span></span>

<span data-ttu-id="86b99-122">Im obigen Beispiel wird der Zugriff auf `fixed`-Felder ohne Anheften dargestellt – diese Funktionalität ist ab C# 7.3 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="86b99-122">The  preceding example demonstrates accessing `fixed` fields without pinning, which is available starting with C# 7.3.</span></span>

<span data-ttu-id="86b99-123">Ein anderes häufiges Array mit fester Größe ist das [bool](../../language-reference/keywords/bool.md)-Array.</span><span class="sxs-lookup"><span data-stu-id="86b99-123">Another common fixed-size array is the [bool](../../language-reference/keywords/bool.md) array.</span></span> <span data-ttu-id="86b99-124">Die Elemente in einem `bool`-Array sind immer ein Byte groß.</span><span class="sxs-lookup"><span data-stu-id="86b99-124">The elements in a `bool` array are always one byte in size.</span></span> <span data-ttu-id="86b99-125">`bool`-Arrays eignen sich nicht zum Erstellen von Bitarrays oder Puffern.</span><span class="sxs-lookup"><span data-stu-id="86b99-125">`bool` arrays are not appropriate for creating bit arrays or buffers.</span></span>

> [!NOTE]
> <span data-ttu-id="86b99-126">Mit Ausnahme von Arbeitsspeicher, der mithilfe von [stackalloc](../../language-reference/operators/stackalloc.md) erstellt wurde, führen der C#-Compiler und die Common Language Runtime (CLR) keine Sicherheitsüberprüfungen für Pufferüberlauf aus.</span><span class="sxs-lookup"><span data-stu-id="86b99-126">Except for memory created by using [stackalloc](../../language-reference/operators/stackalloc.md), the C# compiler and the common language runtime (CLR) do not perform any security buffer overrun checks.</span></span> <span data-ttu-id="86b99-127">Lassen Sie, wie bei jedem unsicheren Code, Vorsicht walten.</span><span class="sxs-lookup"><span data-stu-id="86b99-127">As with all unsafe code, use caution.</span></span>

<span data-ttu-id="86b99-128">Unsichere Puffer unterscheiden sich folgendermaßen von normalen Arrays:</span><span class="sxs-lookup"><span data-stu-id="86b99-128">Unsafe buffers differ from regular arrays in the following ways:</span></span>

- <span data-ttu-id="86b99-129">Sie können nur in einem unsicheren Kontext unsichere Puffer verwenden.</span><span class="sxs-lookup"><span data-stu-id="86b99-129">You can only use unsafe buffers in an unsafe context.</span></span>
- <span data-ttu-id="86b99-130">Unsichere Puffer sind immer Vektoren oder eindimensionale Arrays.</span><span class="sxs-lookup"><span data-stu-id="86b99-130">Unsafe buffers are always vectors, or one-dimensional arrays.</span></span>
- <span data-ttu-id="86b99-131">Die Deklaration des Arrays muss eine Anzahl enthalten, z.B. `char id[8]`.</span><span class="sxs-lookup"><span data-stu-id="86b99-131">The declaration of the array should include a count, such as `char id[8]`.</span></span> <span data-ttu-id="86b99-132">Sie können `char id[]` nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="86b99-132">You cannot use `char id[]`.</span></span>
- <span data-ttu-id="86b99-133">Unsichere Puffer können nur Instanzfelder von Strukturen in einem unsicheren Kontext sein.</span><span class="sxs-lookup"><span data-stu-id="86b99-133">Unsafe buffers can only be instance fields of structs in an unsafe context.</span></span>

## <a name="see-also"></a><span data-ttu-id="86b99-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="86b99-134">See also</span></span>

- [<span data-ttu-id="86b99-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="86b99-135">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="86b99-136">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="86b99-136">Unsafe Code and Pointers</span></span>](index.md)
- [<span data-ttu-id="86b99-137">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="86b99-137">fixed Statement</span></span>](../../language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="86b99-138">Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="86b99-138">Interoperability</span></span>](../interop/index.md)
