---
title: Komponententests für F# in .NET Core mit „dotnet test“ und xUnit
description: Erfahren Sie mehr über die Konzepte von Komponententests für F# in .NET Core, indem Sie im Rahmen eines interaktiven Tutorials Schritt für Schritt eine Beispielprojektmappe mithilfe von „dotnet test“ und xUnit erstellen.
author: billwagner
ms.author: wiwagn
ms.date: 08/30/2017
ms.custom: seodec18
ms.openlocfilehash: 3a9744bfebd93c5004011819b8c6e739e84b97d0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626487"
---
# <a name="unit-testing-f-libraries-in-net-core-using-dotnet-test-and-xunit"></a><span data-ttu-id="56c16-103">Komponententests für F#-Bibliotheken in .NET Core mit „dotnet test“ und xUnit</span><span class="sxs-lookup"><span data-stu-id="56c16-103">Unit testing F# libraries in .NET Core using dotnet test and xUnit</span></span>

<span data-ttu-id="56c16-104">Dieses Tutorial führt Sie interaktiv Schritt für Schritt durch das Erstellen einer Beispielprojektmappe, um die Konzepte von Unittests zu erlernen.</span><span class="sxs-lookup"><span data-stu-id="56c16-104">This tutorial takes you through an interactive experience building a sample solution step-by-step to learn unit testing concepts.</span></span> <span data-ttu-id="56c16-105">Wenn Sie dem Tutorial lieber mit einer vorgefertigten Projektmappe folgen, [zeigen Sie den Beispielcode an, oder laden Sie ihn herunter](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/), bevor Sie beginnen.</span><span class="sxs-lookup"><span data-stu-id="56c16-105">If you prefer to follow the tutorial using a pre-built solution, [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/getting-started/unit-testing-with-fsharp/) before you begin.</span></span> <span data-ttu-id="56c16-106">Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span><span class="sxs-lookup"><span data-stu-id="56c16-106">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

## <a name="creating-the-source-project"></a><span data-ttu-id="56c16-107">Erstellen des Quellprojekts</span><span class="sxs-lookup"><span data-stu-id="56c16-107">Creating the source project</span></span>

<span data-ttu-id="56c16-108">Öffnen eines Shell-Fensters.</span><span class="sxs-lookup"><span data-stu-id="56c16-108">Open a shell window.</span></span> <span data-ttu-id="56c16-109">Erstellen Sie ein Verzeichnis namens *unit-testing-with-fsharp*, um die Projektmappe zu speichern.</span><span class="sxs-lookup"><span data-stu-id="56c16-109">Create a directory called *unit-testing-with-fsharp* to hold the solution.</span></span>
<span data-ttu-id="56c16-110">Führen Sie in diesem neuen Verzeichnis [`dotnet new sln`](../tools/dotnet-new.md) aus, um eine neue Projektmappe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56c16-110">Inside this new directory, run [`dotnet new sln`](../tools/dotnet-new.md) to create a new solution.</span></span> <span data-ttu-id="56c16-111">Dies vereinfacht die Verwaltung des Klassenbibliotheks- und Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="56c16-111">This makes it easier to manage both the class library and the unit test project.</span></span>
<span data-ttu-id="56c16-112">Erstellen Sie im Projektmappenverzeichnis ein *MathService*-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="56c16-112">Inside the solution directory, create a *MathService* directory.</span></span> <span data-ttu-id="56c16-113">Nachfolgend wird die bisherige Verzeichnis- und Dateistruktur dargestellt:</span><span class="sxs-lookup"><span data-stu-id="56c16-113">The directory and file structure thus far is shown below:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
```

<span data-ttu-id="56c16-114">Machen Sie *MathService* zum aktuellen Verzeichnis, und führen Sie [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) aus, um das Quellprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56c16-114">Make *MathService* the current directory and run [`dotnet new classlib -lang F#`](../tools/dotnet-new.md) to create the source project.</span></span>  <span data-ttu-id="56c16-115">Sie erstellen eine fehlerhafte Implementierung des Math-Diensts:</span><span class="sxs-lookup"><span data-stu-id="56c16-115">You'll create a failing implementation of the math service:</span></span>

```fsharp
module MyMath =
    let squaresOfOdds xs = raise (System.NotImplementedException("You haven't written a test yet!"))
```

<span data-ttu-id="56c16-116">Ändern Sie das Verzeichnis wieder in das Verzeichnis *unit-testing-with-fsharp*.</span><span class="sxs-lookup"><span data-stu-id="56c16-116">Change the directory back to the *unit-testing-with-fsharp* directory.</span></span> <span data-ttu-id="56c16-117">Führen Sie [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) aus, um das Klassenbibliotheksprojekt zur Projektmappe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="56c16-117">Run [`dotnet sln add .\MathService\MathService.fsproj`](../tools/dotnet-sln.md) to add the class library project to the solution.</span></span>

## <a name="creating-the-test-project"></a><span data-ttu-id="56c16-118">Erstellen des Testprojekts</span><span class="sxs-lookup"><span data-stu-id="56c16-118">Creating the test project</span></span>

<span data-ttu-id="56c16-119">Erstellen Sie als Nächstes das Verzeichnis *MathService.Tests*.</span><span class="sxs-lookup"><span data-stu-id="56c16-119">Next, create the *MathService.Tests* directory.</span></span> <span data-ttu-id="56c16-120">Die folgende Gliederung zeigt die Verzeichnisstruktur:</span><span class="sxs-lookup"><span data-stu-id="56c16-120">The following outline shows the directory structure:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
```

<span data-ttu-id="56c16-121">Machen Sie das *MathService.Tests*-Verzeichnis zum aktuellen Verzeichnis, und erstellen Sie ein neues Projekt mit [`dotnet new xunit -lang F#`](../tools/dotnet-new.md).</span><span class="sxs-lookup"><span data-stu-id="56c16-121">Make the *MathService.Tests* directory the current directory and create a new project using [`dotnet new xunit -lang F#`](../tools/dotnet-new.md).</span></span> <span data-ttu-id="56c16-122">Dies erstellt ein Testprojekt, das xUnit als Testbibliothek verwendet.</span><span class="sxs-lookup"><span data-stu-id="56c16-122">This creates a test project that uses xUnit as the test library.</span></span> <span data-ttu-id="56c16-123">Die generierte Vorlage konfiguriert Test Runner in *MathServiceTests.fsproj*:</span><span class="sxs-lookup"><span data-stu-id="56c16-123">The generated template configures the test runner in the *MathServiceTests.fsproj*:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.3.0-preview-20170628-02" />
  <PackageReference Include="xunit" Version="2.2.0" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0" />
</ItemGroup>
```

<span data-ttu-id="56c16-124">Für das Testprojekt sind weitere Pakete zum Erstellen und Ausführen von Unittests erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56c16-124">The test project requires other packages to create and run unit tests.</span></span> <span data-ttu-id="56c16-125">`dotnet new` hat im vorherigen Schritt xUnit und xUnit Runner hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="56c16-125">`dotnet new` in the previous step added xUnit and the xUnit runner.</span></span> <span data-ttu-id="56c16-126">Fügen Sie jetzt die `MathService`-Klassenbibliothek als eine andere Abhängigkeit zum Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="56c16-126">Now, add the `MathService` class library as another dependency to the project.</span></span> <span data-ttu-id="56c16-127">Verwenden Sie den Befehl [`dotnet add reference`](../tools/dotnet-add-reference.md):</span><span class="sxs-lookup"><span data-stu-id="56c16-127">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```
dotnet add reference ../MathService/MathService.fsproj
```

<span data-ttu-id="56c16-128">Die ganze Datei finden Sie im [Beispielerepository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="56c16-128">You can see the entire file in the [samples repository](https://github.com/dotnet/samples/blob/master/core/getting-started/unit-testing-with-fsharp/MathService.Tests/MathService.Tests.fsproj) on GitHub.</span></span>

<span data-ttu-id="56c16-129">Sie verfügen über das folgende endgültige Projektmappenlayout:</span><span class="sxs-lookup"><span data-stu-id="56c16-129">You have the following final solution layout:</span></span>

```
/unit-testing-with-fsharp
    unit-testing-with-fsharp.sln
    /MathService
        Source Files
        MathService.fsproj
    /MathService.Tests
        Test Source Files
        MathServiceTests.fsproj
```

<span data-ttu-id="56c16-130">Führen Sie [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) im Verzeichnis *unit-testing-with-fsharp* aus.</span><span class="sxs-lookup"><span data-stu-id="56c16-130">Execute [`dotnet sln add .\MathService.Tests\MathService.Tests.fsproj`](../tools/dotnet-sln.md) in the *unit-testing-with-fsharp* directory.</span></span> 

## <a name="creating-the-first-test"></a><span data-ttu-id="56c16-131">Erstellen des ersten Tests</span><span class="sxs-lookup"><span data-stu-id="56c16-131">Creating the first test</span></span>

<span data-ttu-id="56c16-132">Sie schreiben einen fehlerhaften Test, lassen ihn bestehen und wiederholen dann den Prozess.</span><span class="sxs-lookup"><span data-stu-id="56c16-132">You write one failing test, make it pass, then repeat the process.</span></span> <span data-ttu-id="56c16-133">Öffnen Sie *Tests.fs*, und fügen Sie den folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="56c16-133">Open *Tests.fs* and add the following code:</span></span>

```fsharp
[<Fact>]
let ``My test`` () =
    Assert.True(true)

[<Fact>]
let ``Fail every time`` () = Assert.True(false)
```

<span data-ttu-id="56c16-134">Das `[<Fact>]`-Attribut kennzeichnet eine Testmethode, die von Test Runner ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56c16-134">The `[<Fact>]` attribute denotes a test method that is run by the test runner.</span></span> <span data-ttu-id="56c16-135">Führen Sie im Verzeichnis *unit-testing-with-fsharp* [`dotnet test`](../tools/dotnet-test.md) aus, um die Tests und die Klassenbibliothek zu erstellen und anschließend die Tests auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56c16-135">From the *unit-testing-with-fsharp*, execute [`dotnet test`](../tools/dotnet-test.md) to build the tests and the class library and then run the tests.</span></span> <span data-ttu-id="56c16-136">Der xUnit Test Runner enthält den Programmeinstiegspunkt zum Ausführen Ihrer Tests.</span><span class="sxs-lookup"><span data-stu-id="56c16-136">The xUnit test runner contains the program entry point to run your tests.</span></span> <span data-ttu-id="56c16-137">`dotnet test` startet Test Runner mithilfe des von Ihnen erstellten Komponententestprojekts.</span><span class="sxs-lookup"><span data-stu-id="56c16-137">`dotnet test` starts the test runner using the unit test project you've created.</span></span>

<span data-ttu-id="56c16-138">Diese zwei Tests geben jeweils den grundlegendsten bestandenen und fehlerhaften Test an.</span><span class="sxs-lookup"><span data-stu-id="56c16-138">These two tests show the most basic passing and failing tests.</span></span> <span data-ttu-id="56c16-139">`My test` wurde erfolgreich und `Fail every time` fehlerhaft abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="56c16-139">`My test` passes, and `Fail every time` fails.</span></span> <span data-ttu-id="56c16-140">Erstellen Sie jetzt einen Test für die `squaresOfOdds`-Methode.</span><span class="sxs-lookup"><span data-stu-id="56c16-140">Now, create a test for the `squaresOfOdds` method.</span></span> <span data-ttu-id="56c16-141">Die `squaresOfOdds`-Methode gibt eine Sequenz der Quadrate aller ungeraden ganzzahligen Werte zurück, die Teil der Eingabesequenz sind.</span><span class="sxs-lookup"><span data-stu-id="56c16-141">The `squaresOfOdds` method returns a sequence of the squares of all odd integer values that are part of the input sequence.</span></span> <span data-ttu-id="56c16-142">Anstatt zu versuchen, alle diese Funktionen gleichzeitig zu schreiben, können Sie iterativ Tests zum Überprüfen der Funktionalität erstellen.</span><span class="sxs-lookup"><span data-stu-id="56c16-142">Rather than trying to write all of those functions at once, you can iteratively create tests that validate the functionality.</span></span> <span data-ttu-id="56c16-143">Damit jeder Test erfolgreich abgeschlossen wird, muss die erforderliche Funktionalität für die Methode erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="56c16-143">Making each test pass means creating the necessary functionality for the method.</span></span>

<span data-ttu-id="56c16-144">Der einfachste Test, den wir schreiben können, ist das Aufrufen von `squaresOfOdds` mit allen geraden Zahlen, wobei das Ergebnis eine leere Sequenz von Ganzzahlen sein sollte.</span><span class="sxs-lookup"><span data-stu-id="56c16-144">The simplest test we can write is to call `squaresOfOdds` with all even numbers, where the result should be an empty sequence of integers.</span></span>  <span data-ttu-id="56c16-145">Im Folgenden wird dieser Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="56c16-145">Here's that test:</span></span>

```fsharp
[<Fact>]
let ``Sequence of Evens returns empty collection`` () =
    let expected = Seq.empty<int>
    let actual = MyMath.squaresOfOdds [2; 4; 6; 8; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="56c16-146">Ihr Test schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="56c16-146">Your test fails.</span></span> <span data-ttu-id="56c16-147">Sie haben die Implementierung noch nicht erstellt.</span><span class="sxs-lookup"><span data-stu-id="56c16-147">You haven't created the implementation yet.</span></span> <span data-ttu-id="56c16-148">Damit dieser Test erfolgreich verläuft, schreiben Sie einen ganz einfachen Code in die `MathService`-Klasse:</span><span class="sxs-lookup"><span data-stu-id="56c16-148">Make this test pass by writing the simplest code in the `MathService` class that works:</span></span>

```fsharp
let squaresOfOdds xs =
    Seq.empty<int>
```

<span data-ttu-id="56c16-149">Führen Sie im Verzeichnis *unit-testing-with-fsharp* erneut `dotnet test` aus.</span><span class="sxs-lookup"><span data-stu-id="56c16-149">In the *unit-testing-with-fsharp* directory, run `dotnet test` again.</span></span> <span data-ttu-id="56c16-150">Der `dotnet test`-Befehl führt einen Build für das `MathService`-Projekt und anschließend für das `MathService.Tests`-Projekt aus.</span><span class="sxs-lookup"><span data-stu-id="56c16-150">The `dotnet test` command runs a build for the `MathService` project and then for the `MathService.Tests` project.</span></span> <span data-ttu-id="56c16-151">Nachdem beide Projekte erstellt wurden, wird dieser einzelne Test ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56c16-151">After building both projects, it runs this single test.</span></span> <span data-ttu-id="56c16-152">Er ist erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="56c16-152">It passes.</span></span>

## <a name="completing-the-requirements"></a><span data-ttu-id="56c16-153">Erfüllen der Anforderungen</span><span class="sxs-lookup"><span data-stu-id="56c16-153">Completing the requirements</span></span>

<span data-ttu-id="56c16-154">Nachdem Sie dafür gesorgt haben, dass ein Test erfolgreich verläuft, schreiben Sie weiter.</span><span class="sxs-lookup"><span data-stu-id="56c16-154">Now that you've made one test pass, it's time to write more.</span></span> <span data-ttu-id="56c16-155">Der nächste einfache Fall funktioniert mit einer Sequenz, deren einzige ungerade Zahl `1` lautet.</span><span class="sxs-lookup"><span data-stu-id="56c16-155">The next simple case works with a sequence whose only odd number is `1`.</span></span> <span data-ttu-id="56c16-156">Die Zahl 1 ist einfacher, da 1 das Quadrat von 1 ist.</span><span class="sxs-lookup"><span data-stu-id="56c16-156">The number 1 is easier because the square of 1 is 1.</span></span> <span data-ttu-id="56c16-157">Im Folgenden wird der nächste Test vorgestellt:</span><span class="sxs-lookup"><span data-stu-id="56c16-157">Here's that next test:</span></span>

```fsharp
[<Fact>]
let ``Sequences of Ones and Evens returns Ones`` () =
    let expected = [1; 1; 1; 1]
    let actual = MyMath.squaresOfOdds [2; 1; 4; 1; 6; 1; 8; 1; 10]
    Assert.Equal<Collections.Generic.IEnumerable<int>>(expected, actual)
```

<span data-ttu-id="56c16-158">Bei der Ausführung von `dotnet test` werden Ihre Tests ausgeführt. Dabei zeigt sich, dass der neue Test fehlerhaft ist.</span><span class="sxs-lookup"><span data-stu-id="56c16-158">Executing `dotnet test` runs your tests and shows you that the new test fails.</span></span> <span data-ttu-id="56c16-159">Aktualisieren Sie nun die `squaresOfOdds`-Methode, um diesen neuen Test zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="56c16-159">Now, update the `squaresOfOdds` method to handle this new test.</span></span> <span data-ttu-id="56c16-160">Damit dieser Test erfolgreich durchgeführt wird, filtern Sie alle geraden Zahlen aus der Sequenz.</span><span class="sxs-lookup"><span data-stu-id="56c16-160">You filter all the even numbers out of the sequence to make this test pass.</span></span> <span data-ttu-id="56c16-161">Hierzu können Sie eine kleine Filterfunktion schreiben und `Seq.filter` verwenden:</span><span class="sxs-lookup"><span data-stu-id="56c16-161">You can do that by writing a small filter function and using `Seq.filter`:</span></span>

```fsharp
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs =
    xs
    |> Seq.filter isOdd
```

<span data-ttu-id="56c16-162">Ein weiterer Schritt ist noch notwendig: Bilden Sie das Quadrat von jeder ungeraden Zahl.</span><span class="sxs-lookup"><span data-stu-id="56c16-162">There's one more step to go: square each of the odd numbers.</span></span> <span data-ttu-id="56c16-163">Schreiben Sie zunächst einen neuen Test:</span><span class="sxs-lookup"><span data-stu-id="56c16-163">Start by writing a new test:</span></span>

```fsharp
[<Fact>]
let ``SquaresOfOdds works`` () =
    let expected = [1; 9; 25; 49; 81]
    let actual = MyMath.squaresOfOdds [1; 2; 3; 4; 5; 6; 7; 8; 9; 10]
    Assert.Equal(expected, actual)
```

<span data-ttu-id="56c16-164">Sie können den Test beheben, indem Sie für die gefilterte Sequenz einen Zuordnungsvorgang durchführen, um das Quadrat von jeder ungerade Zahl zu berechnen:</span><span class="sxs-lookup"><span data-stu-id="56c16-164">You can fix the test by piping the filtered sequence through a map operation to compute the square of each odd number:</span></span>

```fsharp
let private square x = x * x
let private isOdd x = x % 2 <> 0

let squaresOfOdds xs = 
    xs 
    |> Seq.filter isOdd 
    |> Seq.map square
```

<span data-ttu-id="56c16-165">Sie haben eine kleine Bibliothek und eine Reihe von Unittests für diese Bibliothek erstellt.</span><span class="sxs-lookup"><span data-stu-id="56c16-165">You've built a small library and a set of unit tests for that library.</span></span> <span data-ttu-id="56c16-166">Sie haben die Projektmappe so strukturiert, dass das Hinzufügen neuer Pakete und Tests Teil des normalen Workflows ist.</span><span class="sxs-lookup"><span data-stu-id="56c16-166">You've structured the solution so that adding new packages and tests is part of the normal workflow.</span></span> <span data-ttu-id="56c16-167">Sie haben den Großteil Ihrer Zeit und Ihres Aufwands mit der Erreichung der Anwendungsziele verbracht.</span><span class="sxs-lookup"><span data-stu-id="56c16-167">You've concentrated most of your time and effort on solving the goals of the application.</span></span>
