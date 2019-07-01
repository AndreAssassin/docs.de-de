---
title: Tabelle für implizite numerische Konvertierungen – C#-Referenz
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 9c3efe1dbea355e8bc00ef44e08efcc9d0e0bdca
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424177"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="3df02-102">Tabelle für implizite numerische Konvertierungen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="3df02-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="3df02-103">Folgende Tabelle veranschaulicht vordefinierte implizite Konvertierungen zwischen numerischen .NET-Typen.</span><span class="sxs-lookup"><span data-stu-id="3df02-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="3df02-104">Von</span><span class="sxs-lookup"><span data-stu-id="3df02-104">From</span></span>|<span data-ttu-id="3df02-105">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3df02-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="3df02-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="3df02-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-107">`short`, `int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-108">byte</span><span class="sxs-lookup"><span data-stu-id="3df02-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-110">char</span><span class="sxs-lookup"><span data-stu-id="3df02-110">char</span></span>](char.md)|<span data-ttu-id="3df02-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-112">short</span><span class="sxs-lookup"><span data-stu-id="3df02-112">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-113">`int`, `long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-114">ushort</span><span class="sxs-lookup"><span data-stu-id="3df02-114">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-115">`int`, `uint`, `long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-116">int</span><span class="sxs-lookup"><span data-stu-id="3df02-116">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-117">`long`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-118">uint</span><span class="sxs-lookup"><span data-stu-id="3df02-118">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-119">`long`, `ulong`, `float`, `double` oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-120">long</span><span class="sxs-lookup"><span data-stu-id="3df02-120">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-121">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-122">ulong</span><span class="sxs-lookup"><span data-stu-id="3df02-122">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="3df02-123">`float`, `double`oder `decimal`</span><span class="sxs-lookup"><span data-stu-id="3df02-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="3df02-124">float</span><span class="sxs-lookup"><span data-stu-id="3df02-124">float</span></span>](float.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="3df02-125">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="3df02-125">Remarks</span></span>  

- <span data-ttu-id="3df02-126">Jeder [integrale Typ](../builtin-types/integral-numeric-types.md) kann implizit in einen beliebigen [Gleitkommatyp](floating-point-types-table.md) konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="3df02-126">Any [integral type](../builtin-types/integral-numeric-types.md) is implicitly convertible to any [floating-point type](floating-point-types-table.md).</span></span>

- <span data-ttu-id="3df02-127">Bei der Konvertierung von `int`, `uint`, `long` oder `ulong` in `float` und von `long` oder `ulong` in `double` kann Präzision verloren gehen, aber keine Größe.</span><span class="sxs-lookup"><span data-stu-id="3df02-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="3df02-128">Es gibt keine impliziten Konvertierungen in die Typen `char`, `byte` und `sbyte`.</span><span class="sxs-lookup"><span data-stu-id="3df02-128">There are no implicit conversions to the `char`, `byte`, and `sbyte` types.</span></span>  

- <span data-ttu-id="3df02-129">Es gibt keine impliziten Konvertierungen aus den Typen `double` und `decimal`.</span><span class="sxs-lookup"><span data-stu-id="3df02-129">There are no implicit conversions from the `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="3df02-130">Es gibt keine impliziten Konvertierungen zwischen dem Typ `decimal` und dem Typ `float` oder `double`.</span><span class="sxs-lookup"><span data-stu-id="3df02-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="3df02-131">Ein Wert eines konstanten Ausdrucks vom Typ `int` (z.B. ein Wert, der von einem integralen Literal dargestellt wird) kann in `sbyte`, `byte`, `short`, `ushort`, `uint` oder `ulong` konvertiert werden, solange er sich innerhalb des Bereichs des Zieltyps befindet:</span><span class="sxs-lookup"><span data-stu-id="3df02-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="3df02-132">Weitere Informationen über implizite Konvertierungen finden Sie im Abschnitt [Implicit conversions (Implizite Konvertierungen)](~/_csharplang/spec/conversions.md#implicit-conversions) der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="3df02-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3df02-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3df02-133">See also</span></span>

- [<span data-ttu-id="3df02-134">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="3df02-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3df02-135">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3df02-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3df02-136">Integrale Typen</span><span class="sxs-lookup"><span data-stu-id="3df02-136">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="3df02-137">Tabelle für Gleitkommatypen</span><span class="sxs-lookup"><span data-stu-id="3df02-137">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="3df02-138">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="3df02-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="3df02-139">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="3df02-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="3df02-140">Umwandlung und Typkonvertierungen</span><span class="sxs-lookup"><span data-stu-id="3df02-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
