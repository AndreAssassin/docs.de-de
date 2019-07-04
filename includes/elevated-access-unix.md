---
ms.openlocfilehash: dece035f443ff827a250ca1c1233b7651df7d108
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424712"
---
### <a name="install-the-global-tool"></a><span data-ttu-id="611d9-101">Installieren des globalen Tools</span><span class="sxs-lookup"><span data-stu-id="611d9-101">Install the global tool</span></span>

<span data-ttu-id="611d9-102">Paketobjekte sollten an einem geschützten Speicherort mit der Option `--tool-path` installiert werden.</span><span class="sxs-lookup"><span data-stu-id="611d9-102">Package assets should be installed in a protected location using the `--tool-path` option.</span></span> <span data-ttu-id="611d9-103">Diese Trennung vermeidet die gemeinsame Nutzung einer eingeschränkten Benutzerumgebung mit einer erhöhten Umgebung.</span><span class="sxs-lookup"><span data-stu-id="611d9-103">This separation avoids sharing a restricted user environment with an elevated environment.</span></span>

```bash
sudo dotnet tool install PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="611d9-104">`/usr/local/share/dotnet-tools` wird mit der Berechtigung `drwxr-xr-x` erstellt.</span><span class="sxs-lookup"><span data-stu-id="611d9-104">`/usr/local/share/dotnet-tools` will be created with permission `drwxr-xr-x`.</span></span> <span data-ttu-id="611d9-105">Wenn das Verzeichnis bereits vorhanden ist, verwenden Sie den Befehl `ls -l`, um sicherzustellen, dass der eingeschränkte Benutzer keine Berechtigung zum Bearbeiten des Verzeichnisses hat.</span><span class="sxs-lookup"><span data-stu-id="611d9-105">If the directory already exists, use the `ls -l` command to verify the restricted user doesn't have permission to edit the directory.</span></span> <span data-ttu-id="611d9-106">Wenn dies der Fall ist, verwenden Sie den Befehl `sudo chmod o-w -R /usr/share/dotnet-tools`, um den Zugriff zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="611d9-106">If so, use the `sudo chmod o-w -R /usr/share/dotnet-tools` command to remove the access.</span></span>

### <a name="run-the-global-tool"></a><span data-ttu-id="611d9-107">Ausführen des globalen Tools</span><span class="sxs-lookup"><span data-stu-id="611d9-107">Run the global tool</span></span>

<span data-ttu-id="611d9-108">**Option 1** Verwenden des vollständigen Pfads mit sudo:</span><span class="sxs-lookup"><span data-stu-id="611d9-108">**Option 1** Use the full path with sudo:</span></span>

```bash
sudo /usr/local/share/dotnet-tools/TOOLCOMMAND
```

<span data-ttu-id="611d9-109">**Option 2** Hinzufügen des Symbollinks des Tools, einmal pro Tool:</span><span class="sxs-lookup"><span data-stu-id="611d9-109">**Option 2** Add the symbol link of the tool, once per tool:</span></span>

```bash
sudo ln -s /usr/local/share/dotnet-tools/TOOLCOMMAND /usr/local/bin/TOOLCOMMAND
```

<span data-ttu-id="611d9-110">Und ausführen mit:</span><span class="sxs-lookup"><span data-stu-id="611d9-110">And run with:</span></span>

```bash
sudo TOOLCOMMAND
```

### <a name="uninstall-the-global-tool"></a><span data-ttu-id="611d9-111">Deinstallieren des globalen Tools</span><span class="sxs-lookup"><span data-stu-id="611d9-111">Uninstall the global tool</span></span>

```bash
sudo dotnet tool uninstall PACKAGEID --tool-path /usr/local/share/dotnet-tools
```

<span data-ttu-id="611d9-112">Wenn Sie einen Symbollink erstellt haben, müssen Sie diesen ebenfalls entfernen:</span><span class="sxs-lookup"><span data-stu-id="611d9-112">If you made a symbol link, you also need to remove it:</span></span>

```bash
sudo rm /usr/local/bin/TOOLCOMMAND
```