---
title: 'Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile'
ms.date: 09/29/2017
f1_keywords:
- cs.build.commandline
helpviewer_keywords:
- csc.exe, command-line builds
- Visual C#, command-line builds
- command-line compilers, Visual C#
- Vsvars32.bat
- builds [C#], command-line
- compilers, invoking from command line
- Vcvars32.bat file
- command line [C#], building from
- Visual C# compiler, enabling
- compiling source code, from command line
ms.assetid: 7ec09480-5612-4f6a-8d00-ad90ea9bca5d
ms.openlocfilehash: 9eea7f76d386816aad060e9b99cea6b906a09ab9
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612120"
---
# <a name="how-to-set-environment-variables-for-the-visual-studio-command-line"></a><span data-ttu-id="1a80c-102">Vorgehensweise: Festlegen von Umgebungsvariablen für die Visual Studio-Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="1a80c-102">How to: Set Environment Variables for the Visual Studio Command Line</span></span>

<span data-ttu-id="1a80c-103">Die Umgebungsvariablen, die für Befehlszeilenbuilds erforderlich sind, werden durch die Datei VSDevCmd.bat festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1a80c-103">The VsDevCmd.bat file sets the appropriate environment variables to enable command-line builds.</span></span>

> [!NOTE]
> <span data-ttu-id="1a80c-104">Bei der Datei VsDevCmd.bat handelt es sich um eine neue Datei, die im Lieferumfang von Visual Studio 2017 enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1a80c-104">The VsDevCmd.bat file is a new file delivered with Visual Studio 2017.</span></span> <span data-ttu-id="1a80c-105">In Visual Studio 2015 und früheren Versionen wurde für den gleichen Zweck VSVARS32.bat verwendet.</span><span class="sxs-lookup"><span data-stu-id="1a80c-105">Visual Studio 2015 and earlier versions used VSVARS32.bat for the same purpose.</span></span> <span data-ttu-id="1a80c-106">Diese Datei wurde unter „\Programme\Microsoft Visual Studio\\*Version*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1a80c-106">This file was stored in \Program Files\Microsoft Visual Studio\\*Version*\Common7\Tools or Program Files (x86)\Microsoft Visual Studio\\*Version*\Common7\Tools.</span></span>

<span data-ttu-id="1a80c-107">Falls die aktuelle Version von Visual Studio auf einem Computer installiert ist, der zusätzlich über eine frühere Version von Visual Studio verfügt, sollten Sie die Dateien VsDevCmd.bat und VSVARS32.BAT aus unterschiedlichen Versionen nicht im selben Eingabeaufforderungsfenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a80c-107">If the current version of Visual Studio is installed on a computer that also has an earlier version of Visual Studio, you should not run VsDevCmd.bat and VSVARS32.BAT from different versions in the same Command Prompt window.</span></span> <span data-ttu-id="1a80c-108">Stattdessen sollten Sie den Befehl für jede Version in ihrem eigenen Fenster ausführen.</span><span class="sxs-lookup"><span data-stu-id="1a80c-108">Instead, you should run the command for each version in its own window.</span></span>

### <a name="to-run-vsdevcmdbat"></a><span data-ttu-id="1a80c-109">Ausführen von VsDevCmd.BAT</span><span class="sxs-lookup"><span data-stu-id="1a80c-109">To run VsDevCmd.BAT</span></span>

1. <span data-ttu-id="1a80c-110">Öffnen Sie über das Menü **Start** die **Developer-Eingabeaufforderung für VS 2017**.</span><span class="sxs-lookup"><span data-stu-id="1a80c-110">From the **Start** menu, open the **Developer Command Prompt for VS 2017**.</span></span>  <span data-ttu-id="1a80c-111">Sie befindet sich im Ordner **Visual Studio 2017**.</span><span class="sxs-lookup"><span data-stu-id="1a80c-111">It's in the **Visual Studio 2017** folder.</span></span>

2. <span data-ttu-id="1a80c-112">Wechseln Sie zum Unterverzeichnis „Programme\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ oder „Programme (x86)\Microsoft Visual Studio\\*Version*\\*Angebot*\Common7\Tools“ Ihrer Installation.</span><span class="sxs-lookup"><span data-stu-id="1a80c-112">Change to the \Program Files\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools or \Program Files (x86)\Microsoft Visual Studio\\*Version*\\*Offering*\Common7\Tools subdirectory of your installation.</span></span>  <span data-ttu-id="1a80c-113">(Die *Version* lautet für die aktuelle Version *2017*.</span><span class="sxs-lookup"><span data-stu-id="1a80c-113">(*Version* is *2017* for the current version.</span></span> <span data-ttu-id="1a80c-114">*Angebot* ist einer der Werte *Enterprise*, *Professional* oder *Community*.)</span><span class="sxs-lookup"><span data-stu-id="1a80c-114">*Offering* is one of *Enterprise*, *Professional* or *Community*.)</span></span>

3. <span data-ttu-id="1a80c-115">Führen Sie VsDevCmd.bat aus, indem Sie **VsDevCmd** eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a80c-115">Run VsDevCmd.bat by typing **VsDevCmd**.</span></span>

    > [!CAUTION]
    > <span data-ttu-id="1a80c-116">VsDevCmd.bat kann auf verschiedenen Computern unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="1a80c-116">VsDevCmd.bat can vary from computer to computer.</span></span> <span data-ttu-id="1a80c-117">Falls die Datei VsDevCmd.bat nicht vorhanden oder beschädigt ist, sollten Sie sie nicht durch die VsDevCmd.bat-Datei eines anderen Computers ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1a80c-117">Do not replace a missing or damaged VsDevCmd.bat file with a VsDevCmd.bat from another computer.</span></span> <span data-ttu-id="1a80c-118">Führen Sie stattdessen Setup erneut aus, um die fehlende Datei zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="1a80c-118">Instead, rerun setup to replace the missing file.</span></span>

### <a name="available-options-for-vsdevcmdbat"></a><span data-ttu-id="1a80c-119">Verfügbare Optionen für „VsDevCmd.BAT“</span><span class="sxs-lookup"><span data-stu-id="1a80c-119">Available options for VsDevCmd.BAT</span></span>

<span data-ttu-id="1a80c-120">Um die verfügbaren Optionen für „VsDevCmd.BAT“ anzuzeigen, führen Sie den Befehl mit der `-help`-Option aus:</span><span class="sxs-lookup"><span data-stu-id="1a80c-120">To see the available options for VsDevCmd.BAT, run the command with the `-help` option:</span></span>

```console
VsDevCmd.bat -help
```

## <a name="see-also"></a><span data-ttu-id="1a80c-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a80c-121">See also</span></span>

- [<span data-ttu-id="1a80c-122">Erstellen über die Befehlszeile mit csc.exe</span><span class="sxs-lookup"><span data-stu-id="1a80c-122">Command-line Building With csc.exe</span></span>](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)
