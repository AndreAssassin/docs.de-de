---
title: Mehrfachdateiassemblys
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], multifile
- entry point for assembly
- compiling assemblies
- command-line compilers
- assembly manifest, multifile assemblies
- code modules
- multifile assemblies
ms.assetid: 13509e73-db77-4645-8165-aad8dfaedff6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e00ec239fbe5d5963edd3a7656961556792c6324
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593545"
---
# <a name="multifile-assemblies"></a><span data-ttu-id="3b49e-102">Mehrfachdateiassemblys</span><span class="sxs-lookup"><span data-stu-id="3b49e-102">Multifile Assemblies</span></span>

<span data-ttu-id="3b49e-103">Sie können Mehrfachdateiassemblys mit dem Befehlszeilencompiler oder in Visual Studio mit Visual C++ erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b49e-103">You can create multifile assemblies using command-line compilers or Visual Studio with Visual C++.</span></span> <span data-ttu-id="3b49e-104">Eine Datei in der Assembly muss das Assemblymanifest enthalten.</span><span class="sxs-lookup"><span data-stu-id="3b49e-104">One file in the assembly must contain the assembly manifest.</span></span> <span data-ttu-id="3b49e-105">Eine Assembly, die eine Anwendung startet, muss außerdem einen Einstiegspunkt enthalten, wie z.B. die Methoden „Main“ oder „WinMain“.</span><span class="sxs-lookup"><span data-stu-id="3b49e-105">An assembly that starts an application must also contain an entry point, such as a Main or WinMain method.</span></span>

<span data-ttu-id="3b49e-106">Nehmen Sie z.B. an, dass Sie eine Anwendung haben, die zwei Codemodule enthält, „client.cs“ und „stringer.cs“.</span><span class="sxs-lookup"><span data-stu-id="3b49e-106">For example, suppose you have an application that contains two code modules, Client.cs and Stringer.cs.</span></span> <span data-ttu-id="3b49e-107">„Stringer.cs“ erstellt den Namespace `myStringer`, auf den vom Code in „client.cs“ verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3b49e-107">Stringer.cs creates the `myStringer` namespace that is referenced by the code in Client.cs.</span></span> <span data-ttu-id="3b49e-108">„Client.cs“ enthält die Methode `Main`, die der Einstiegspunkt der Anwendung ist.</span><span class="sxs-lookup"><span data-stu-id="3b49e-108">Client.cs contains the `Main` method, which is the application's entry point.</span></span> <span data-ttu-id="3b49e-109">In diesem Beispiel kompilieren Sie die zwei Codemodule und erstellen dann eine dritte Datei, die das Assemblymanifest enthält, das die Anwendung startet.</span><span class="sxs-lookup"><span data-stu-id="3b49e-109">In this example, you compile the two code modules, and then create a third file that contains the assembly manifest, which launches the application.</span></span> <span data-ttu-id="3b49e-110">Das Assemblymanifest verweist sowohl auf das Modul `Client` als auch auf das Modul `Stringer`.</span><span class="sxs-lookup"><span data-stu-id="3b49e-110">The assembly manifest references both the `Client` and `Stringer` modules.</span></span>

> [!NOTE]
> <span data-ttu-id="3b49e-111">Mehrfachdateiassemblys können nur einen Einstiegspunkt haben, auch wenn die Assembly über mehrere Codemodule verfügt.</span><span class="sxs-lookup"><span data-stu-id="3b49e-111">Multifile assemblies can have only one entry point, even if the assembly has multiple code modules.</span></span>

<span data-ttu-id="3b49e-112">Es gibt mehrere Gründe, sich für eine Mehrfachdateiassembly zu entscheiden:</span><span class="sxs-lookup"><span data-stu-id="3b49e-112">There are several reasons you might want to create a multifile assembly:</span></span>

- <span data-ttu-id="3b49e-113">Das Kombinieren von Modulen, die in unterschiedlichen Sprachen geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="3b49e-113">To combine modules written in different languages.</span></span> <span data-ttu-id="3b49e-114">Dies ist der häufigste Grund für das Erstellen einer Mehrfachdateiassembly.</span><span class="sxs-lookup"><span data-stu-id="3b49e-114">This is the most common reason for creating a multifile assembly.</span></span>

- <span data-ttu-id="3b49e-115">Die Optimierung des Herunterladens einer Anwendung durch das Einfügen selten verwendeter Typen in ein Modul, das nur wenn nötig heruntergeladen wird.</span><span class="sxs-lookup"><span data-stu-id="3b49e-115">To optimize downloading an application by putting seldom-used types in a module that is downloaded only when needed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b49e-116">Wenn Sie eine Anwendung erstellen, die mit dem `<object>`-Tag mit Microsoft Internet Explorer heruntergeladen wird, ist es wichtig, dass Sie Mehrfachdateiassemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="3b49e-116">If you are creating applications that will be downloaded using the `<object>` tag with Microsoft Internet Explorer, it is important that you create multifile assemblies.</span></span> <span data-ttu-id="3b49e-117">In diesem Szenario erstellen Sie eine von Ihren Codemodulen getrennte Datei, die nur das Assemblymanifest enthält.</span><span class="sxs-lookup"><span data-stu-id="3b49e-117">In this scenario, you create a file separate from your code modules that contains only the assembly manifest.</span></span> <span data-ttu-id="3b49e-118">Internet Explorer lädt zunächst das Assemblymanifest herunter und erstellt anschließend Arbeitsthreads, um alle weiteren erforderlichen Module bzw. Assemblys herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="3b49e-118">Internet Explorer downloads the assembly manifest first, and then creates worker threads to download any additional modules or assemblies required.</span></span> <span data-ttu-id="3b49e-119">Während des Downloads der Datei, die das Assemblymanifest enthält, reagiert Internet Explorer nicht auf Eingaben des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3b49e-119">While the file containing the assembly manifest is being downloaded, Internet Explorer will be unresponsive to user input.</span></span> <span data-ttu-id="3b49e-120">Je kleiner die Datei ist, die das Assemblymanifest enthält, desto kürzer ist die Zeitspanne, in der Internet Explorer nicht reagiert.</span><span class="sxs-lookup"><span data-stu-id="3b49e-120">The smaller the file containing the assembly manifest, the less time Internet Explorer will be unresponsive.</span></span>

- <span data-ttu-id="3b49e-121">Das Kombinieren von Codemodulen, die von mehreren Entwicklern geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="3b49e-121">To combine code modules written by several developers.</span></span> <span data-ttu-id="3b49e-122">Obwohl jeder Entwickler jedes Codemodul in eine Assembly kompilieren kann, kann dies dazu führen, dass einige Teile öffentlich gemacht werden, die aber nicht verfügbar gemacht werden, wenn alle Module in eine Mehrfachdateiassembly integriert werden.</span><span class="sxs-lookup"><span data-stu-id="3b49e-122">Although each developer can compile each code module into an assembly, this can force some types to be exposed publicly that are not exposed if all modules are put into a multifile assembly.</span></span>

<span data-ttu-id="3b49e-123">Sobald Sie die Assembly erstellt haben, können Sie die Datei signieren, die das Assemblymanifest enthält (und somit auch die Assembly). Alternativ können Sie der Datei auch einen starken Namen geben und sie in den globalen Assemblycache einfügen.</span><span class="sxs-lookup"><span data-stu-id="3b49e-123">Once you create the assembly, you can sign the file that contains the assembly manifest (and hence the assembly), or you can give the file (and the assembly) a strong name and put it in the global assembly cache.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b49e-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3b49e-124">See also</span></span>

- [<span data-ttu-id="3b49e-125">Vorgehensweise: Erstellen einer Mehrfachdateiassembly</span><span class="sxs-lookup"><span data-stu-id="3b49e-125">How to: Build a Multifile Assembly</span></span>](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)
- [<span data-ttu-id="3b49e-126">Programmieren mit Assemblys</span><span class="sxs-lookup"><span data-stu-id="3b49e-126">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)