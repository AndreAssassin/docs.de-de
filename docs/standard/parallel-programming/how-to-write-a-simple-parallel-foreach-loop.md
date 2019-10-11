---
title: Schreiben eines einfachen parallelen Programms mit Parallel.ForEach
ms.date: 02/14/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- foreach, parallel version
- parallel programming, foreach
ms.assetid: cb5fab92-1c19-499e-ae91-8b7525dd875f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9d54f06c1fc774a2e73b3b99a7d5bb24dd8baf3f
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835261"
---
# <a name="how-to-write-a-simple-parallelforeach-loop"></a><span data-ttu-id="479cb-102">Vorgehensweise: Schreiben einer einfachen Parallel.ForEach-Schleife</span><span class="sxs-lookup"><span data-stu-id="479cb-102">How to: Write a simple Parallel.ForEach loop</span></span>

<span data-ttu-id="479cb-103">Dieses Beispiel zeigt die Verwendung einer <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife, um alle <xref:System.Collections.IEnumerable?displayProperty=nameWithType>- oder <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>-Datenquellen übergreifende Datenparallelität zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="479cb-103">This example shows how to use a <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop to enable data parallelism over any <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> data source.</span></span>

> [!NOTE]
> <span data-ttu-id="479cb-104">In dieser Dokumentation werden Delegaten in PLINQ mithilfe von Lambdaausdrücken definiert.</span><span class="sxs-lookup"><span data-stu-id="479cb-104">This documentation uses lambda expressions to define delegates in PLINQ.</span></span> <span data-ttu-id="479cb-105">Falls Sie mit Lambdaausdrücken in C# oder Visual Basic nicht vertraut sind, finden Sie entsprechende Informationen unter [Lambdaausdrücke in PLINQ und TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span><span class="sxs-lookup"><span data-stu-id="479cb-105">If you are not familiar with lambda expressions in C# or Visual Basic, see [Lambda expressions in PLINQ and TPL](../../../docs/standard/parallel-programming/lambda-expressions-in-plinq-and-tpl.md).</span></span>

## <a name="example"></a><span data-ttu-id="479cb-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="479cb-106">Example</span></span>

<span data-ttu-id="479cb-107">In diesem Beispiel wird davon ausgegangen, dass mehrere JPG-Dateien im Ordner *C:\Users\Public\Pictures\Sample Pictures* (C:\Benutzer\Öffentlich\Bilder\Beispielbilder) vorhanden sind, und es wird ein neuer Unterordner namens *Modified* (Geändert) erstellt.</span><span class="sxs-lookup"><span data-stu-id="479cb-107">This example assumes you have several .jpg files in a *C:\Users\Public\Pictures\Sample Pictures* folder and creates a new sub-folder named *Modified*.</span></span> <span data-ttu-id="479cb-108">Wenn Sie das Beispiel ausführen, wird jedes JPG-Bild in *Sample Pictures* (Beispielbilder) gedreht und unter *Modified* (Geändert) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="479cb-108">When you run the example, it rotates each .jpg image in *Sample Pictures* and saves it to *Modified*.</span></span> <span data-ttu-id="479cb-109">Sie können die beiden Pfade nach Bedarf anpassen.</span><span class="sxs-lookup"><span data-stu-id="479cb-109">You can modify the two paths as necessary.</span></span>

[!code-csharp[TPL_Parallel#03](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/simpleforeach.cs#03)]
[!code-vb[TPL_Parallel#03](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/simpleforeach.vb#03)]

<span data-ttu-id="479cb-110">Eine <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType>-Schleife funktioniert wie eine <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType>-Schleife.</span><span class="sxs-lookup"><span data-stu-id="479cb-110">A <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> loop works like a <xref:System.Threading.Tasks.Parallel.For%2A?displayProperty=nameWithType> loop.</span></span> <span data-ttu-id="479cb-111">Die Schleife partitioniert die Quellsammlung und plant die Arbeit basierend auf der Systemumgebung in mehrere Threads ein.</span><span class="sxs-lookup"><span data-stu-id="479cb-111">The loop partitions the source collection and schedules the work on multiple threads based on the system environment.</span></span> <span data-ttu-id="479cb-112">Je mehr Prozessoren das System aufweist, desto schneller wird die parallele Methode ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="479cb-112">The more processors on the system, the faster the parallel method runs.</span></span> <span data-ttu-id="479cb-113">Bei manchen Quellsammlungen ist eine sequenzielle Schleife je nach Größe der Quelle und Art der Arbeit, die die Schleife ausführt, möglicherweise schneller.</span><span class="sxs-lookup"><span data-stu-id="479cb-113">For some source collections, a sequential loop may be faster, depending on the size of the source and the kind of work the loop performs.</span></span> <span data-ttu-id="479cb-114">Weitere Informationen zur Leistung finden Sie unter [Potenzielle Fehler bei Daten- und Aufgabenparallelität](potential-pitfalls-in-data-and-task-parallelism.md).</span><span class="sxs-lookup"><span data-stu-id="479cb-114">For more information about performance, see [Potential pitfalls in data and task parallelism](potential-pitfalls-in-data-and-task-parallelism.md).</span></span>

<span data-ttu-id="479cb-115">Weitere Informationen zu parallelen Schleifen finden Sie unter [Vorgehensweise: Schreiben einer einfachen Parallel.For-Schleife](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span><span class="sxs-lookup"><span data-stu-id="479cb-115">For more information about parallel loops, see [How to: Write a simple Parallel.For loop](../../../docs/standard/parallel-programming/how-to-write-a-simple-parallel-for-loop.md).</span></span>

<span data-ttu-id="479cb-116">Um <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> mit einer nicht generischen Sammlung zu verwenden, können Sie die Sammlung mithilfe der <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType>-Erweiterungsmethode in eine generische Sammlung umwandeln, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="479cb-116">To use <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> with a non-generic collection, you can use the <xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType> extension method to convert the collection to a generic collection, as shown in the following example:</span></span>

[!code-csharp[TPL_Parallel#07](../../../samples/snippets/csharp/VS_Snippets_Misc/tpl_parallel/cs/nongeneric.cs#07)]
[!code-vb[TPL_Parallel#07](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpl_parallel/vb/nongeneric.vb#07)]

<span data-ttu-id="479cb-117">Sie können auch Parallel LINQ (PLINQ) verwenden, um die Verarbeitung von <xref:System.Collections.Generic.IEnumerable%601>-Datenquellen zu parallelisieren.</span><span class="sxs-lookup"><span data-stu-id="479cb-117">You can also use Parallel LINQ (PLINQ) to parallelize processing of <xref:System.Collections.Generic.IEnumerable%601> data sources.</span></span> <span data-ttu-id="479cb-118">Mit PLINQ können Sie deklarative Abfragesyntax verwenden, um das Schleifenverhalten auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="479cb-118">PLINQ enables you to use declarative query syntax to express the loop behavior.</span></span> <span data-ttu-id="479cb-119">Weitere Informationen finden Sie unter [Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span><span class="sxs-lookup"><span data-stu-id="479cb-119">For more information, see [Parallel LINQ (PLINQ)](../../../docs/standard/parallel-programming/parallel-linq-plinq.md).</span></span>

## <a name="compile-and-run-the-code"></a><span data-ttu-id="479cb-120">Kompilieren und Ausführen des Codes</span><span class="sxs-lookup"><span data-stu-id="479cb-120">Compile and run the code</span></span>

<span data-ttu-id="479cb-121">Sie können den Code als Konsolenanwendung für das .NET Framework oder als Konsolenanwendung für .NET Core kompilieren.</span><span class="sxs-lookup"><span data-stu-id="479cb-121">You can compile the code as a console application for .NET Framework or as a console application for .NET Core.</span></span>

<span data-ttu-id="479cb-122">In Visual Studio gibt es Visual Basic- und C#-Konsolenanwendungsvorlagen für Windows Desktop und .NET Core.</span><span class="sxs-lookup"><span data-stu-id="479cb-122">In Visual Studio, there are Visual Basic and C# console application templates for Windows Desktop and .NET Core.</span></span>

<span data-ttu-id="479cb-123">Sie können über die Befehlszeile entweder .NET Core und die zugehörigen CLI-Tools (z.B. `dotnet new console` oder `dotnet new console -lang vb`) nutzen oder die Datei erstellen und den Befehlszeilencompiler für eine .NET Framework-Anwendung nutzen.</span><span class="sxs-lookup"><span data-stu-id="479cb-123">From the command line, you can use either .NET Core and its CLI tools (for example, `dotnet new console` or `dotnet new console -lang vb`), or you can create the file and use the command-line compiler for a .NET Framework application.</span></span>

<span data-ttu-id="479cb-124">Bei einem .NET Core-Projekt müssen Sie auf das NuGet-Paket **System.Drawing.Common** verweisen.</span><span class="sxs-lookup"><span data-stu-id="479cb-124">For a .NET Core project, you must reference the **System.Drawing.Common** NuGet package.</span></span> <span data-ttu-id="479cb-125">Verwenden Sie in Visual Studio den NuGet-Paket-Manager zum Installieren des Pakets.</span><span class="sxs-lookup"><span data-stu-id="479cb-125">In Visual Studio, use the NuGet Package Manager to install the package.</span></span> <span data-ttu-id="479cb-126">Alternativ können Sie in Ihrer \*.CSPROJ oder \*.VBPROJ-Datei auf das Paket verweisen:</span><span class="sxs-lookup"><span data-stu-id="479cb-126">Alternatively, you can add a reference to the package in your \*.csproj or \*.vbproj file:</span></span>
 
```xml
<ItemGroup>
     <PackageReference Include="System.Drawing.Common" Version="4.5.1" />
</ItemGroup>
```

<span data-ttu-id="479cb-127">Verwenden Sie zum Ausführen einer .NET Core-Konsolenanwendung über die Befehlszeile `dotnet run` aus dem Ordner, der Ihre Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="479cb-127">To run a .NET Core console application from the command line, use `dotnet run` from the folder that contains your application.</span></span>

<span data-ttu-id="479cb-128">Drücken Sie zum Ausführen Ihrer Konsolenanwendung aus Visual Studio **F5**.</span><span class="sxs-lookup"><span data-stu-id="479cb-128">To run your console application from Visual Studio, press **F5**.</span></span>

## <a name="see-also"></a><span data-ttu-id="479cb-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="479cb-129">See also</span></span>

- [<span data-ttu-id="479cb-130">Datenparallelität</span><span class="sxs-lookup"><span data-stu-id="479cb-130">Data parallelism</span></span>](../../../docs/standard/parallel-programming/data-parallelism-task-parallel-library.md)
- [<span data-ttu-id="479cb-131">Parallele Programmierung</span><span class="sxs-lookup"><span data-stu-id="479cb-131">Parallel programming</span></span>](../../../docs/standard/parallel-programming/index.md)
- [<span data-ttu-id="479cb-132">Parallel LINQ (PLINQ) (Paralleles LINQ (PLINQ))</span><span class="sxs-lookup"><span data-stu-id="479cb-132">Parallel LINQ (PLINQ)</span></span>](../../../docs/standard/parallel-programming/parallel-linq-plinq.md)
