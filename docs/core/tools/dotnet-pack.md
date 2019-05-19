---
title: Befehl „dotnet pack“
description: Der dotnet pack-Befehl erstellt NuGet-Pakete für ein .NET Core-Projekt.
ms.date: 12/04/2018
ms.openlocfilehash: 5d48e5957e8095cc9ef4eaca2e1e1746c25a2a88
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876043"
---
# <a name="dotnet-pack"></a><span data-ttu-id="8f0d2-103">dotnet pack</span><span class="sxs-lookup"><span data-stu-id="8f0d2-103">dotnet pack</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8f0d2-104">name</span><span class="sxs-lookup"><span data-stu-id="8f0d2-104">Name</span></span>

<span data-ttu-id="8f0d2-105">`dotnet pack`: Packt den Code in ein NuGet-Paket</span><span class="sxs-lookup"><span data-stu-id="8f0d2-105">`dotnet pack` - Packs the code into a NuGet package.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8f0d2-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="8f0d2-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f0d2-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f0d2-107">.NET Core 2.x</span></span>](#tab/netcore2x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--force] [--include-source] [--include-symbols] [--no-build] [--no-dependencies]
    [--no-restore] [-o|--output] [--runtime] [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f0d2-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f0d2-108">.NET Core 1.x</span></span>](#tab/netcore1x)

```
dotnet pack [<PROJECT>] [-c|--configuration] [--include-source] [--include-symbols] [--no-build] [-o|--output]
    [-s|--serviceable] [-v|--verbosity] [--version-suffix]
dotnet pack [-h|--help]
```

---

## <a name="description"></a><span data-ttu-id="8f0d2-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="8f0d2-109">Description</span></span>

<span data-ttu-id="8f0d2-110">Der Befehl `dotnet pack` erstellt das Projekt und NuGet-Pakete.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-110">The `dotnet pack` command builds the project and creates NuGet packages.</span></span> <span data-ttu-id="8f0d2-111">Das Ergebnis dieses Befehls ist ein NuGet-Paket.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-111">The result of this command is a NuGet package.</span></span> <span data-ttu-id="8f0d2-112">Wenn die `--include-symbols`-Option vorhanden ist, wird ein anderes Paket mit den Debugsymbolen erstellt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-112">If the `--include-symbols` option is present, another package containing the debug symbols is created.</span></span>

<span data-ttu-id="8f0d2-113">NuGet-Abhängigkeiten des gepackten Projekts werden der Datei *nuspec* hinzugefügt. Sie werden ordnungsgemäß aufgelöst, wenn das Paket installiert wird.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-113">NuGet dependencies of the packed project are added to the *.nuspec* file, so they're properly resolved when the package is installed.</span></span> <span data-ttu-id="8f0d2-114">Verweise zwischen Projekten werden innerhalb des Projekts nicht gepackt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-114">Project-to-project references aren't packaged inside the project.</span></span> <span data-ttu-id="8f0d2-115">Derzeit benötigen Sie ein Paket pro Projekt, wenn Sie Abhängigkeiten zwischen Projekten haben.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-115">Currently, you must have a package per project if you have project-to-project dependencies.</span></span>

<span data-ttu-id="8f0d2-116">`dotnet pack` erstellt standardmäßig zuerst das Projekt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-116">By default, `dotnet pack` builds the project first.</span></span> <span data-ttu-id="8f0d2-117">Wenn Sie dieses Verhalten vermeiden möchten, übergeben Sie die Option `--no-build`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-117">If you wish to avoid this behavior, pass the `--no-build` option.</span></span> <span data-ttu-id="8f0d2-118">Diese Option ist bei Buildszenarios der Continuous Integration (CI) oft hilfreich, bei denen Sie wissen, dass der Code kürzlich erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-118">This option is often useful in Continuous Integration (CI) build scenarios where you know the code was previously built.</span></span>

<span data-ttu-id="8f0d2-119">Sie können dem `dotnet pack`-Befehl MSBuild-Eigenschaften für den Packvorgang bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-119">You can provide MSBuild properties to the `dotnet pack` command for the packing process.</span></span> <span data-ttu-id="8f0d2-120">Weitere Informationen finden Sie in den [NuGet-Metadateneigenschaften](csproj.md#nuget-metadata-properties) und in der [MSBuild-Befehlszeilenreferenz](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="8f0d2-120">For more information, see [NuGet metadata properties](csproj.md#nuget-metadata-properties) and the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span> <span data-ttu-id="8f0d2-121">Der Abschnitt [Beispiele](#examples) enthält Informationen darüber, wie der MSBuild-Schalter „-p“ für verschiedene Szenarien verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-121">The [Examples](#examples) section shows how to use the MSBuild -p switch for a couple of different scenarios.</span></span>

<span data-ttu-id="8f0d2-122">Webprojekte können standardmäßig nicht verpackt werden.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-122">Web projects aren't packable by default.</span></span> <span data-ttu-id="8f0d2-123">Um das Standardverhalten zu überschreiben, fügen Sie Ihrer *.csproj*-Datei die folgende Eigenschaft hinzu:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-123">To override the default behavior, add the following property to your *.csproj* file:</span></span>

```xml
<PropertyGroup>
   <IsPackable>true</IsPackable>
</PropertyGroup>
```

[!INCLUDE[dotnet restore note + options](~/includes/dotnet-restore-note-options.md)]

## <a name="arguments"></a><span data-ttu-id="8f0d2-124">Argumente</span><span class="sxs-lookup"><span data-stu-id="8f0d2-124">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="8f0d2-125">Das zu packende Projekt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-125">The project to pack.</span></span> <span data-ttu-id="8f0d2-126">Es ist entweder ein Pfad zu einer [csproj-Datei](csproj.md) oder zu einem Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-126">It's either a path to a [csproj file](csproj.md) or to a directory.</span></span> <span data-ttu-id="8f0d2-127">Wenn nicht angegeben, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-127">If not specified, it defaults to the current directory.</span></span>

## <a name="options"></a><span data-ttu-id="8f0d2-128">Optionen</span><span class="sxs-lookup"><span data-stu-id="8f0d2-128">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="8f0d2-129">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="8f0d2-129">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="8f0d2-130">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-130">Defines the build configuration.</span></span> <span data-ttu-id="8f0d2-131">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-131">The default value is `Debug`.</span></span>

* **`--force`**

  <span data-ttu-id="8f0d2-132">Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-132">Forces all dependencies to be resolved even if the last restore was successful.</span></span> <span data-ttu-id="8f0d2-133">Dieses Flag anzugeben, entspricht dem Löschen der Datei *project.assets.json*.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-133">Specifying this flag is the same as deleting the *project.assets.json* file.</span></span>

* **`-h|--help`**

  <span data-ttu-id="8f0d2-134">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-134">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="8f0d2-135">Nimmt die Quelldateien in das NuGet-Paket auf.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-135">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="8f0d2-136">Die Quelldateien befinden sich im Ordner `src` im `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-136">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="8f0d2-137">Generiert die Symbole `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-137">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="8f0d2-138">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-138">Doesn't build the project before packing.</span></span> <span data-ttu-id="8f0d2-139">Zudem wird das Flag `--no-restore` implizit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-139">It also implicitly sets the `--no-restore` flag.</span></span>

* **`--no-dependencies`**

  <span data-ttu-id="8f0d2-140">Ignoriert Verweise zwischen Projekten und stellt nur das zum Erstellen angegebene Stammprojekt wieder her.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-140">Ignores project-to-project references and only restores the root project.</span></span>

* **`--no-restore`**

  <span data-ttu-id="8f0d2-141">Führt keine implizite Wiederherstellung aus, wenn der Befehl ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-141">Doesn't execute an implicit restore when running the command.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8f0d2-142">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-142">Places the built packages in the directory specified.</span></span>

* **`--runtime <RUNTIME_IDENTIFIER>`**

  <span data-ttu-id="8f0d2-143">Gibt die Ziellaufzeit an, für die Pakete wiederhergestellt werden sollen</span><span class="sxs-lookup"><span data-stu-id="8f0d2-143">Specifies the target runtime to restore packages for.</span></span> <span data-ttu-id="8f0d2-144">Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md).</span><span class="sxs-lookup"><span data-stu-id="8f0d2-144">For a list of Runtime Identifiers (RIDs), see the [RID catalog](../rid-catalog.md).</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="8f0d2-145">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-145">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="8f0d2-146">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="8f0d2-146">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="8f0d2-147">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-147">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8f0d2-148">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-148">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8f0d2-149">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-149">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="8f0d2-150">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="8f0d2-150">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`-c|--configuration {Debug|Release}`**

  <span data-ttu-id="8f0d2-151">Legt die Buildkonfiguration fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-151">Defines the build configuration.</span></span> <span data-ttu-id="8f0d2-152">Der Standardwert ist `Debug`sein.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-152">The default value is `Debug`.</span></span>

* **`-h|--help`**

  <span data-ttu-id="8f0d2-153">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-153">Prints out a short help for the command.</span></span>

* **`--include-source`**

  <span data-ttu-id="8f0d2-154">Nimmt die Quelldateien in das NuGet-Paket auf.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-154">Includes the source files in the NuGet package.</span></span> <span data-ttu-id="8f0d2-155">Die Quelldateien befinden sich im Ordner `src` im `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-155">The sources files are included in the `src` folder within the `nupkg`.</span></span>

* **`--include-symbols`**

  <span data-ttu-id="8f0d2-156">Generiert die Symbole `nupkg`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-156">Generates the symbols `nupkg`.</span></span>

* **`--no-build`**

  <span data-ttu-id="8f0d2-157">Erstellt das Projekt nicht vor dem Packen.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-157">Doesn't build the project before packing.</span></span>

* **`-o|--output <OUTPUT_DIRECTORY>`**

  <span data-ttu-id="8f0d2-158">Platziert die erstellten Pakete in das angegebene Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-158">Places the built packages in the directory specified.</span></span>

* **`-s|--serviceable`**

  <span data-ttu-id="8f0d2-159">Legt das zu verarbeitende Flag im Paket fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-159">Sets the serviceable flag in the package.</span></span> <span data-ttu-id="8f0d2-160">Weitere Informationen finden Sie unter [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries (.NET Blog: .NET 4.5.1 unterstützt Microsoft Sicherheitsupdates für .NET NuGet-Bibliotheken)](https://aka.ms/nupkgservicing).</span><span class="sxs-lookup"><span data-stu-id="8f0d2-160">For more information, see [.NET Blog: .NET 4.5.1 Supports Microsoft Security Updates for .NET NuGet Libraries](https://aka.ms/nupkgservicing).</span></span>

* **`--version-suffix <VERSION_SUFFIX>`**

  <span data-ttu-id="8f0d2-161">Definiert den Wert für die `$(VersionSuffix)`-MSBuild-Eigenschaft im Projekt.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-161">Defines the value for the `$(VersionSuffix)` MSBuild property in the project.</span></span>

* **`-v|--verbosity <LEVEL>`**

  <span data-ttu-id="8f0d2-162">Legt den Ausführlichkeitsgrad für den Befehl fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-162">Sets the verbosity level of the command.</span></span> <span data-ttu-id="8f0d2-163">Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-163">Allowed values are `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]`, and `diag[nostic]`.</span></span>

---

## <a name="examples"></a><span data-ttu-id="8f0d2-164">Beispiele</span><span class="sxs-lookup"><span data-stu-id="8f0d2-164">Examples</span></span>

* <span data-ttu-id="8f0d2-165">Packt das Projekt im aktuellen Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-165">Pack the project in the current directory:</span></span>

  ```console
  dotnet pack
  ```

* <span data-ttu-id="8f0d2-166">Packt das `app1`-Projekt:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-166">Pack the `app1` project:</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj
  ```

* <span data-ttu-id="8f0d2-167">Packt das Projekt im aktuellen Verzeichnis, und platziert die erstellten Pakete in den `nupkgs`-Ordner:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-167">Pack the project in the current directory and place the resulting packages into the `nupkgs` folder:</span></span>

  ```console
  dotnet pack --output nupkgs
  ```

* <span data-ttu-id="8f0d2-168">Packt das Projekt im aktuellen Verzeichnis in den `nupkgs`-Ordner und überspringt den Buildschritt:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-168">Pack the project in the current directory into the `nupkgs` folder and skip the build step:</span></span>

  ```console
  dotnet pack --no-build --output nupkgs
  ```

* <span data-ttu-id="8f0d2-169">Mit dem Versionssuffix des Projekts, das als `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in der *.csproj*-Datei konfiguriert ist, packen Sie das aktuelle Projekt, und aktualisieren Sie die resultierende Paketversion mit dem angegebenen Suffix:</span><span class="sxs-lookup"><span data-stu-id="8f0d2-169">With the project's version suffix configured as `<VersionSuffix>$(VersionSuffix)</VersionSuffix>` in the *.csproj* file, pack the current project and update the resulting package version with the given suffix:</span></span>

  ```console
  dotnet pack --version-suffix "ci-1234"
  ```

* <span data-ttu-id="8f0d2-170">Legen Sie die Paketversion auf `2.1.0` mithilfe der MSBuild-Eigenschaft `PackageVersion` fest.</span><span class="sxs-lookup"><span data-stu-id="8f0d2-170">Set the package version to `2.1.0` with the `PackageVersion` MSBuild property:</span></span>

  ```console
  dotnet pack -p:PackageVersion=2.1.0
  ```

* <span data-ttu-id="8f0d2-171">Packen Sie das Projekt für ein bestimmtes [Zielframework](../../standard/frameworks.md):</span><span class="sxs-lookup"><span data-stu-id="8f0d2-171">Pack the project for a specific [target framework](../../standard/frameworks.md):</span></span>

  ```console
  dotnet pack -p:TargetFrameworks=net45
  ```

* <span data-ttu-id="8f0d2-172">Packen Sie das Projekt, und verwenden Sie eine bestimmte Runtime (Windows 10) für den Wiederherstellungsvorgang (.NET Core SDK 2.0 und spätere Versionen):</span><span class="sxs-lookup"><span data-stu-id="8f0d2-172">Pack the project and use a specific runtime (Windows 10) for the restore operation (.NET Core SDK 2.0 and later versions):</span></span>

  ```console
  dotnet pack --runtime win10-x64
  ```

* <span data-ttu-id="8f0d2-173">Packen Sie das Projekt mithilfe einer [NUSPEC-Datei](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span><span class="sxs-lookup"><span data-stu-id="8f0d2-173">Pack the project using a [.nuspec file](https://docs.microsoft.com/nuget/reference/msbuild-targets#packing-using-a-nuspec):</span></span>

  ```console
  dotnet pack ~/projects/app1/project.csproj /p:NuspecFile=~/projects/app1/project.nuspec /p:NuspecBasePath=~/projects/app1/nuget
  ```
