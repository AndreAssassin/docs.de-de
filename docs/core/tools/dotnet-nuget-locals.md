---
title: Befehl „dotnet nuget locals“
description: Der dotnet nuget locals-Befehl löscht lokale NuGet-Ressourcen, z.B. den http-Anforderungscache, den temporären Cache oder Ordner mit globalen Paketen auf dem Computer, bzw. listet diese Ressourcen auf.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 0a9fd7876aa4d1907eb37e6bac54295d938d36d3
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632423"
---
# <a name="dotnet-nuget-locals"></a><span data-ttu-id="08d52-103">dotnet nuget locals</span><span class="sxs-lookup"><span data-stu-id="08d52-103">dotnet nuget locals</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="08d52-104">name</span><span class="sxs-lookup"><span data-stu-id="08d52-104">Name</span></span>

<span data-ttu-id="08d52-105">`dotnet nuget locals`: Löscht lokale NuGet-Ressourcen oder listet diese auf.</span><span class="sxs-lookup"><span data-stu-id="08d52-105">`dotnet nuget locals` - Clears or lists local NuGet resources.</span></span>

## <a name="synopsis"></a><span data-ttu-id="08d52-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="08d52-106">Synopsis</span></span>

```
dotnet nuget locals <CACHE_LOCATION> [(-c|--clear)|(-l|--list)] [--force-english-output]
dotnet nuget locals [-h|--help]
```

## <a name="description"></a><span data-ttu-id="08d52-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="08d52-107">Description</span></span>

<span data-ttu-id="08d52-108">Der `dotnet nuget locals`-Befehl löscht lokale NuGet-Ressourcen im http-Anforderungscache, temporären Cache oder Ordner mit globalen Paketen auf dem Computer bzw. listet diese Ressourcen auf.</span><span class="sxs-lookup"><span data-stu-id="08d52-108">The `dotnet nuget locals` command clears or lists local NuGet resources in the http-request cache, temporary cache, or machine-wide global packages folder.</span></span>

## <a name="arguments"></a><span data-ttu-id="08d52-109">Argumente</span><span class="sxs-lookup"><span data-stu-id="08d52-109">Arguments</span></span>

* **`CACHE_LOCATION`**

  <span data-ttu-id="08d52-110">Der aufzulistende oder zu löschende Cachespeicherort.</span><span class="sxs-lookup"><span data-stu-id="08d52-110">The cache location to list or clear.</span></span> <span data-ttu-id="08d52-111">Einer der folgenden Werte wird akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="08d52-111">It accepts one of the following values:</span></span>

  * <span data-ttu-id="08d52-112">`all`: gibt an, dass der angegebene Vorgang auf alle Cachetypen angewendet wird: Auf den http-Anforderungscache, den Cache für globale Pakete und den temporären Cache.</span><span class="sxs-lookup"><span data-stu-id="08d52-112">`all` - Indicates that the specified operation is applied to all cache types: http-request cache, global packages cache, and the temporary cache.</span></span>
  * <span data-ttu-id="08d52-113">`http-cache`: gibt an, dass der angegebene Vorgang nur auf den http-Anforderungscache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="08d52-113">`http-cache` - Indicates that the specified operation is applied only to the http-request cache.</span></span> <span data-ttu-id="08d52-114">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="08d52-114">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="08d52-115">`global-packages`: gibt an, dass der angegebene Vorgang nur auf den Cache für globale Pakete angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="08d52-115">`global-packages` - Indicates that the specified operation is applied only to the global packages cache.</span></span> <span data-ttu-id="08d52-116">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="08d52-116">The other cache locations aren't affected.</span></span>
  * <span data-ttu-id="08d52-117">`temp`: gibt an, dass der angegebene Vorgang nur auf den temporären Cache angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="08d52-117">`temp` - Indicates that the specified operation is applied only to the temporary cache.</span></span> <span data-ttu-id="08d52-118">Die anderen Cachespeicherorte sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="08d52-118">The other cache locations aren't affected.</span></span>

## <a name="options"></a><span data-ttu-id="08d52-119">Optionen</span><span class="sxs-lookup"><span data-stu-id="08d52-119">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="08d52-120">Erzwingt die Ausführung der Anwendung mithilfe einer invarianten Kultur, die auf Englisch basiert.</span><span class="sxs-lookup"><span data-stu-id="08d52-120">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="08d52-121">Druckt eine kurze Hilfe für den Befehl.</span><span class="sxs-lookup"><span data-stu-id="08d52-121">Prints out a short help for the command.</span></span>

* **`-c|--clear`**

  <span data-ttu-id="08d52-122">Die Option „clear“ führt einen Löschvorgang für den angegebenen Cachetyp aus.</span><span class="sxs-lookup"><span data-stu-id="08d52-122">The clear option executes a clear operation on the specified cache type.</span></span> <span data-ttu-id="08d52-123">Die Inhalte der Cacheverzeichnisse werden rekursiv gelöscht.</span><span class="sxs-lookup"><span data-stu-id="08d52-123">The contents of the cache directories are deleted recursively.</span></span> <span data-ttu-id="08d52-124">Der ausführende Benutzer (bzw. die Gruppe) muss über Berechtigungen für die Dateien in den Cacheverzeichnissen verfügen.</span><span class="sxs-lookup"><span data-stu-id="08d52-124">The executing user/group must have permission to the files in the cache directories.</span></span> <span data-ttu-id="08d52-125">Andernfalls wird ein Fehler angezeigt, der die Dateien/Ordner angibt, die nicht gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="08d52-125">If not, an error is displayed indicating the files/folders that weren't cleared.</span></span>

* **`-l|--list`**

  <span data-ttu-id="08d52-126">Die list-Option wird verwendet, um den Speicherort des angegebenen Cachetyps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="08d52-126">The list option is used to display the location of the specified cache type.</span></span>

## <a name="examples"></a><span data-ttu-id="08d52-127">Beispiele</span><span class="sxs-lookup"><span data-stu-id="08d52-127">Examples</span></span>

* <span data-ttu-id="08d52-128">Zeigt die Pfade aller lokalen Cacheverzeichnisse an (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="08d52-128">Displays the paths of all the local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals –l all
  ```

* <span data-ttu-id="08d52-129">Zeigt den Pfad für das lokale http-Cacheverzeichnis an:</span><span class="sxs-lookup"><span data-stu-id="08d52-129">Displays the path for the local http-cache directory:</span></span>

  ```console
  dotnet nuget locals --list http-cache
  ```

* <span data-ttu-id="08d52-130">Löscht alle Dateien aus allen lokalen Cacheverzeichnissen (http-Cacheverzeichnis, Cacheverzeichnis für globale Pakete und temporäres Cacheverzeichnis):</span><span class="sxs-lookup"><span data-stu-id="08d52-130">Clears all files from all local cache directories (http-cache directory, global-packages cache directory, and temporary cache directory):</span></span>

  ```console
  dotnet nuget locals --clear all
  ```

* <span data-ttu-id="08d52-131">Löscht alle Dateien im lokalen Cacheverzeichnis für globale Pakete:</span><span class="sxs-lookup"><span data-stu-id="08d52-131">Clears all files in local global-packages cache directory:</span></span>

  ```console
  dotnet nuget locals -c global-packages
  ```

* <span data-ttu-id="08d52-132">Löscht alle Dateien im lokalen temporären Cacheverzeichnis:</span><span class="sxs-lookup"><span data-stu-id="08d52-132">Clears all files in local temporary cache directory:</span></span>

  ```console
  dotnet nuget locals -c temp
  ```

## <a name="troubleshooting"></a><span data-ttu-id="08d52-133">Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="08d52-133">Troubleshooting</span></span>

<span data-ttu-id="08d52-134">Weitere Informationen zu häufig auftretenden Problemen und Fehlern bei der Verwendung des `dotnet nuget locals`-Befehls finden Sie unter [Managing the NuGet cache (Verwalten des NuGet-Caches)](/nuget/consume-packages/managing-the-nuget-cache).</span><span class="sxs-lookup"><span data-stu-id="08d52-134">For information on common problems and errors while using the `dotnet nuget locals` command, see [Managing the NuGet cache](/nuget/consume-packages/managing-the-nuget-cache).</span></span>
