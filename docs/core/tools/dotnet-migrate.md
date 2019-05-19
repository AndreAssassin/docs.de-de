---
title: Befehl „dotnet migrate“
description: Der dotnet migrate-Befehl migriert ein Projekt und alle seine Abhängigkeiten.
ms.date: 05/25/2018
ms.openlocfilehash: 861cd2cb982c6f41baf00a2cbd7e04b26816af76
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631950"
---
# <a name="dotnet-migrate"></a><span data-ttu-id="50f21-103">dotnet migrate</span><span class="sxs-lookup"><span data-stu-id="50f21-103">dotnet migrate</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="50f21-104">name</span><span class="sxs-lookup"><span data-stu-id="50f21-104">Name</span></span>

<span data-ttu-id="50f21-105">`dotnet migrate`: Migriert ein .NET Core-Projekt von Preview 2 in ein .NET Core-Projekt von SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="50f21-105">`dotnet migrate` - Migrates a Preview 2 .NET Core project to a .NET Core SDK 1.0 project.</span></span>

## <a name="synopsis"></a><span data-ttu-id="50f21-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="50f21-106">Synopsis</span></span>

```
dotnet migrate [<SOLUTION_FILE|PROJECT_DIR>] [--format-report-file-json] [-r|--report-file] [-s|--skip-project-references] [--skip-backup] [-t|--template-file] [-v|--sdk-package-version] [-x|--xproj-file]
dotnet migrate [-h|--help]
```

## <a name="description"></a><span data-ttu-id="50f21-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="50f21-107">Description</span></span>

<span data-ttu-id="50f21-108">Der `dotnet migrate`-Befehl migriert ein gültiges *project.json*-basiertes Projekt von Preview 2 in ein gültiges *csproj*-Projekt von .NET Core SDK 1.0.</span><span class="sxs-lookup"><span data-stu-id="50f21-108">The `dotnet migrate` command migrates a valid Preview 2 *project.json*-based project to a valid .NET Core SDK 1.0 *csproj* project.</span></span>

<span data-ttu-id="50f21-109">Standardmäßig migriert der Befehl das Stammprojekt und alle Projektverweise, die das Stammprojekt enthält.</span><span class="sxs-lookup"><span data-stu-id="50f21-109">By default, the command migrates the root project and any project references that the root project contains.</span></span> <span data-ttu-id="50f21-110">Dieses Verhalten ist mithilfe der `--skip-project-references`-Option zur Laufzeit deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="50f21-110">This behavior is disabled using the `--skip-project-references` option at runtime.</span></span>

<span data-ttu-id="50f21-111">Die Migration kann auf den folgenden Objekten ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="50f21-111">Migration can be performed on the following assets:</span></span>

* <span data-ttu-id="50f21-112">Ein einzelnes Projekt durch Angabe der zu migrierenden *project.json*-Datei.</span><span class="sxs-lookup"><span data-stu-id="50f21-112">A single project by specifying the *project.json* file to migrate.</span></span>
* <span data-ttu-id="50f21-113">Alle Verzeichnisse, die in der *global.json*-Datei angegeben sind, indem ein Pfad zur *global.json*-Datei übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="50f21-113">All of the directories specified in the *global.json* file by passing in a path to the *global.json* file.</span></span>
* <span data-ttu-id="50f21-114">Ein *solution.sln*-Datei, in dem die Projekte, auf die in der Projektmappe verwiesen wird, migriert werden.</span><span class="sxs-lookup"><span data-stu-id="50f21-114">A *solution.sln* file, where it migrates the projects referenced in the solution.</span></span>
* <span data-ttu-id="50f21-115">Rekursiv für alle Unterverzeichnisse im angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="50f21-115">On all subdirectories of the given directory recursively.</span></span>

<span data-ttu-id="50f21-116">Der `dotnet migrate`-Befehl speichert die migrierte *project.json*-Datei in einem `backup`-Verzeichnis, das erstellt wird, falls das Verzeichnis noch nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="50f21-116">The `dotnet migrate` command keeps the migrated *project.json* file inside a `backup` directory, which it creates if the directory doesn't exist.</span></span> <span data-ttu-id="50f21-117">Das Verhalten wird mithilfe der `--skip-backup`-Option überschrieben.</span><span class="sxs-lookup"><span data-stu-id="50f21-117">This behavior is overridden using the `--skip-backup` option.</span></span>

<span data-ttu-id="50f21-118">Standardmäßig gibt der Migrationsvorgang den Status der Migration in die Standardausgabe (STDOUT) aus.</span><span class="sxs-lookup"><span data-stu-id="50f21-118">By default, the migration operation outputs the state of the migration process to standard output (STDOUT).</span></span> <span data-ttu-id="50f21-119">Bei Verwendung der `--report-file <REPORT_FILE>`-Option wird die Ausgabe in die angegebene Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50f21-119">If you use the `--report-file <REPORT_FILE>` option, the output is saved to the file specify.</span></span>

<span data-ttu-id="50f21-120">Der `dotnet migrate`-Befehl unterstützt nur gültige *project.json*-basiere Projekte von Preview 2.</span><span class="sxs-lookup"><span data-stu-id="50f21-120">The `dotnet migrate` command only supports valid Preview 2 *project.json*-based projects.</span></span> <span data-ttu-id="50f21-121">Dies bedeutet, dass Sie ihn nicht zum Migrieren von *project.json*-basierten Projekte von DNX oder Preview 1 direkt an MSBuild/csproj-Projekte verwenden können.</span><span class="sxs-lookup"><span data-stu-id="50f21-121">This means that you cannot use it to migrate DNX or Preview 1 *project.json*-based projects directly to MSBuild/csproj projects.</span></span> <span data-ttu-id="50f21-122">Sie müssen zuerst das Projekt manuell auf ein *project.json*-basiertes Projekt von Preview 2 migrieren und anschließend den `dotnet migrate`-Befehl verwenden, um das Projekt zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="50f21-122">You first need to manually migrate the project to a Preview 2 *project.json*-based project and then use the `dotnet migrate` command to migrate the project.</span></span>

## <a name="arguments"></a><span data-ttu-id="50f21-123">Argumente</span><span class="sxs-lookup"><span data-stu-id="50f21-123">Arguments</span></span>

`PROJECT_JSON/GLOBAL_JSON/SOLUTION_FILE/PROJECT_DIR`

<span data-ttu-id="50f21-124">Der Pfad zu einem der Folgenden:</span><span class="sxs-lookup"><span data-stu-id="50f21-124">The path to one of the following:</span></span>

* <span data-ttu-id="50f21-125">eine *project.json*-Datei zum Migrieren.</span><span class="sxs-lookup"><span data-stu-id="50f21-125">a *project.json* file to migrate.</span></span>
* <span data-ttu-id="50f21-126">eine *global.json*-Datei. Die in *global.json* angegebenen Ordner werden migriert.</span><span class="sxs-lookup"><span data-stu-id="50f21-126">a *global.json* file: the folders specified in *global.json* are migrated.</span></span>
* <span data-ttu-id="50f21-127">eine *solution.sln*-Datei. Die in der Projektmappe referenzierten Projekte werden migriert.</span><span class="sxs-lookup"><span data-stu-id="50f21-127">a *solution.sln* file: the projects referenced in the solution are migrated.</span></span>
* <span data-ttu-id="50f21-128">ein zu migrierendes Verzeichnis. Sucht rekursiv nach *project.json*-Dateien, um diese im angegebenen Verzeichnis zu migrieren.</span><span class="sxs-lookup"><span data-stu-id="50f21-128">a directory to migrate: recursively searches for *project.json* files to migrate inside the specified directory.</span></span>

<span data-ttu-id="50f21-129">Wenn nichts angegeben ist, wird standardmäßig das aktuelle Verzeichnis gewählt.</span><span class="sxs-lookup"><span data-stu-id="50f21-129">Defaults to current directory if nothing is specified.</span></span>

## <a name="options"></a><span data-ttu-id="50f21-130">Optionen</span><span class="sxs-lookup"><span data-stu-id="50f21-130">Options</span></span>

`--format-report-file-json <REPORT_FILE>`

<span data-ttu-id="50f21-131">Die Migrationsberichtsdatei wird als JSON statt als Benutzermeldungen ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="50f21-131">Output migration report file as JSON rather than user messages.</span></span>

`-h|--help`

<span data-ttu-id="50f21-132">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="50f21-132">Prints out a short help for the command.</span></span>

`-r|--report-file <REPORT_FILE>`

<span data-ttu-id="50f21-133">Der Migrationsbericht wird in eine Datei und in der Konsole ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="50f21-133">Output migration report to a file in addition to the console.</span></span>

`-s|--skip-project-references [Debug|Release]`

<span data-ttu-id="50f21-134">Die Migration von Projektverweisen wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="50f21-134">Skip migrating project references.</span></span> <span data-ttu-id="50f21-135">Standardmäßig werden Projektverweise rekursiv migriert.</span><span class="sxs-lookup"><span data-stu-id="50f21-135">By default, project references are migrated recursively.</span></span>

`--skip-backup`

<span data-ttu-id="50f21-136">Das Verschieben der Dateien *project.json*, *global.json* und *\*.xproj* in ein `backup`-Verzeichnis nach der erfolgreichen Migration wird übersprungen.</span><span class="sxs-lookup"><span data-stu-id="50f21-136">Skip moving *project.json*, *global.json*, and *\*.xproj* to a `backup` directory after successful migration.</span></span>

`-t|--template-file <TEMPLATE_FILE>`

<span data-ttu-id="50f21-137">Für die Migration zu verwendende CSPROJ-Vorlagendatei.</span><span class="sxs-lookup"><span data-stu-id="50f21-137">Template csproj file to use for migration.</span></span> <span data-ttu-id="50f21-138">Standardmäßig wird die gleiche Vorlage verwendet, die von `dotnet new console` abgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="50f21-138">By default, the same template as the one dropped by `dotnet new console` is used.</span></span>

`-v|--sdk-package-version <VERSION>`

<span data-ttu-id="50f21-139">Die Version des SDK-Pakets, auf das in der migrierten App verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="50f21-139">The version of the sdk package that's referenced in the migrated app.</span></span> <span data-ttu-id="50f21-140">Der Standardwert ist die Version des SDK in `dotnet new`.</span><span class="sxs-lookup"><span data-stu-id="50f21-140">The default is the version of the SDK in `dotnet new`.</span></span>

`-x|--xproj-file <FILE>`

<span data-ttu-id="50f21-141">Der Pfad zur XPROJ-Datei, die verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="50f21-141">The path to the xproj file to use.</span></span> <span data-ttu-id="50f21-142">Erforderlich, wenn mehrere XPROJ-Dateien in einem Projektverzeichnis vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="50f21-142">Required when there is more than one xproj in a project directory.</span></span>

## <a name="examples"></a><span data-ttu-id="50f21-143">Beispiele</span><span class="sxs-lookup"><span data-stu-id="50f21-143">Examples</span></span>

<span data-ttu-id="50f21-144">Migrieren Sie ein Projekt und alle Abhängigkeiten des Projekts mit anderen Projekten in das aktuelle Verzeichnis:</span><span class="sxs-lookup"><span data-stu-id="50f21-144">Migrate a project in the current directory and all of its project-to-project dependencies:</span></span>

`dotnet migrate`

<span data-ttu-id="50f21-145">Migrieren Sie alle Projekte, die die *global.json*-Datei umfasst:</span><span class="sxs-lookup"><span data-stu-id="50f21-145">Migrate all projects that *global.json* file includes:</span></span>

`dotnet migrate path/to/global.json`

<span data-ttu-id="50f21-146">Migrieren Sie nur das aktuelle Projekt und keine Abhängigkeiten des Projekts mit anderen Projekten (P2P).</span><span class="sxs-lookup"><span data-stu-id="50f21-146">Migrate only the current project and no project-to-project (P2P) dependencies.</span></span> <span data-ttu-id="50f21-147">Verwenden Sie außerdem eine bestimmte SDK-Version:</span><span class="sxs-lookup"><span data-stu-id="50f21-147">Also, use a specific SDK version:</span></span>

`dotnet migrate -s -v 1.0.0-preview4`
