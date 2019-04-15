---
title: -out (C#-Compileroptionen)
ms.date: 07/20/2015
f1_keywords:
- /out
helpviewer_keywords:
- /out compiler option [C#]
- out compiler option [C#]
- -out compiler option [C#]
ms.assetid: 70d91d01-7bd2-4aea-ba8b-4e9807e9caa5
ms.openlocfilehash: 459f83ee52d0ab6421fe7be4a597d8e5174b4fd9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59331298"
---
# <a name="-out-c-compiler-options"></a><span data-ttu-id="03474-102">-out (C#-Compileroptionen)</span><span class="sxs-lookup"><span data-stu-id="03474-102">-out (C# Compiler Options)</span></span>
<span data-ttu-id="03474-103">Die Option **-out** gibt den Namen der Ausgabedatei an.</span><span class="sxs-lookup"><span data-stu-id="03474-103">The **-out** option specifies the name of the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03474-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="03474-104">Syntax</span></span>  
  
```console  
-out:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="03474-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="03474-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="03474-106">Der Name der Ausgabedatei, die vom Compiler erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="03474-106">The name of the output file created by the compiler.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="03474-107">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="03474-107">Remarks</span></span>  
 <span data-ttu-id="03474-108">In der Befehlszeile ist es möglich, mehrere Ausgabedateien für die Kompilierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="03474-108">On the command line, it is possible to specify multiple output files for your compilation.</span></span> <span data-ttu-id="03474-109">Der Compiler geht davon aus, mindestens eine Quellcodedatei nach der Option **-out** zu finden.</span><span class="sxs-lookup"><span data-stu-id="03474-109">The compiler expects to find one or more source code files following the **-out** option.</span></span> <span data-ttu-id="03474-110">Anschließend werden alle Quellcodedateien in der von der Option **-out** angegebenen Ausgabedatei kompiliert.</span><span class="sxs-lookup"><span data-stu-id="03474-110">Then, all source code files will be compiled into the output file specified by that **-out** option.</span></span>  
  
 <span data-ttu-id="03474-111">Geben Sie den vollständigen Namen und die Erweiterung der Datei an, die Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="03474-111">Specify the full name and extension of the file you want to create.</span></span>  
  
 <span data-ttu-id="03474-112">Wenn Sie den Namen der Ausgabedatei nicht angeben:</span><span class="sxs-lookup"><span data-stu-id="03474-112">If you do not specify the name of the output file:</span></span>  
  
-   <span data-ttu-id="03474-113">Übernimmt eine EXE-Datei den Namen aus der Quellcodedatei, die die **Main**-Methode enthält.</span><span class="sxs-lookup"><span data-stu-id="03474-113">An .exe will take its name from the source code file that contains the **Main** method.</span></span>  
  
-   <span data-ttu-id="03474-114">Eine DLL- oder NETMODULE-Datei übernimmt den Namen aus der ersten Quellcodedatei.</span><span class="sxs-lookup"><span data-stu-id="03474-114">A .dll or .netmodule will take its name from the first source code file.</span></span>  
  
 <span data-ttu-id="03474-115">Eine Quellcodedatei zum Kompilieren einer Ausgabedatei kann nicht in der gleichen Kompilierung für die Kompilierung einer anderen Ausgabedatei verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="03474-115">A source code file used to compile one output file cannot be used in the same compilation for the compilation of another output file.</span></span>  
  
 <span data-ttu-id="03474-116">Wenn bei einer Befehlszeilenkompilierung mehrere Ausgabedateien erstellt werden, sollten Sie bedenken, dass nur eine der Ausgabedateien eine Assembly sein kann und dass nur die erste angegebene Ausgabedatei (implizit oder explizit mit **-out**) die Assembly sein kann.</span><span class="sxs-lookup"><span data-stu-id="03474-116">When producing multiple output files in a command-line compilation, keep in mind that only one of the output files can be an assembly and that only the first output file specified (implicitly or explicitly with **-out**) can be the assembly.</span></span>  
  
 <span data-ttu-id="03474-117">Alle Module, die als Teil einer Kompilierung erstellt werden, werden Dateien, die jeder Assembly zugeordnet sind, die auch bei der Kompilierung erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="03474-117">Any modules produced as part of a compilation become files associated with any assembly also produced in the compilation.</span></span> <span data-ttu-id="03474-118">Verwenden Sie [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md), um das Assemblymanifest mit den zugehörigen Dateien anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03474-118">Use [ildasm.exe](../../../framework/tools/ildasm-exe-il-disassembler.md) to view the assembly manifest to see the associated files.</span></span>  
  
 <span data-ttu-id="03474-119">Die Compileroption „-out“ ist erforderlich, damit eine EXE-Datei das Ziel einer Friend-Assembly sein kann.</span><span class="sxs-lookup"><span data-stu-id="03474-119">The -out compiler option is required in order for an exe to be the target of a friend assembly.</span></span> <span data-ttu-id="03474-120">Weitere Informationen finden Sie unter [Friend-Assemblys](../../../standard/assembly/friend-assemblies.md).</span><span class="sxs-lookup"><span data-stu-id="03474-120">For more information see [Friend Assemblies](../../../standard/assembly/friend-assemblies.md).</span></span>  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a><span data-ttu-id="03474-121">So legen Sie diese Compileroption in der Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="03474-121">To set this compiler option in the Visual Studio development environment</span></span>  
  
1. <span data-ttu-id="03474-122">Öffnen Sie die Seite **Eigenschaften** des Projekts.</span><span class="sxs-lookup"><span data-stu-id="03474-122">Open the project's **Properties** page.</span></span>  
  
2. <span data-ttu-id="03474-123">Klicken Sie auf die Eigenschaftenseite **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="03474-123">Click the **Application** property page.</span></span>  
  
3. <span data-ttu-id="03474-124">Ändern Sie die Eigenschaft **Assemblyname**.</span><span class="sxs-lookup"><span data-stu-id="03474-124">Modify the **Assembly name** property.</span></span>  
  
     <span data-ttu-id="03474-125">So legen Sie diese Compileroption programmgesteuert fest: <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> ist eine schreibgeschützte Eigenschaft, die durch eine Kombination aus dem Projekttyp (ausführbare Datei, Bibliothek usw.) und dem Namen der Assembly bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="03474-125">To set this compiler option programmatically: the <xref:VSLangProj80.ProjectProperties3.OutputFileName%2A> is a read-only property, which is determined by a combination of the project type (exe, library, and so forth) and the assembly name.</span></span> <span data-ttu-id="03474-126">Das Ändern von einer oder diesen beiden Eigenschaften ist erforderlich, um den Namen der Ausgabedatei festzulegen.</span><span class="sxs-lookup"><span data-stu-id="03474-126">Modifying one or both of these properties will be necessary to set the output file name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03474-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="03474-127">Example</span></span>  
 <span data-ttu-id="03474-128">Kompilieren Sie `t.cs`, und erstellen Sie die Ausgabedatei `t.exe` und die Datei `t2.cs` sowie die Modulausgabedatei `mymodule.netmodule`:</span><span class="sxs-lookup"><span data-stu-id="03474-128">Compile `t.cs` and create output file `t.exe`, as well as build `t2.cs` and create module output file `mymodule.netmodule`:</span></span>  
  
```console  
csc t.cs -out:mymodule.netmodule -target:module t2.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="03474-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="03474-129">See also</span></span>

- [<span data-ttu-id="03474-130">C#-Compileroptionen</span><span class="sxs-lookup"><span data-stu-id="03474-130">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
- [<span data-ttu-id="03474-131">Friend-Assemblys</span><span class="sxs-lookup"><span data-stu-id="03474-131">Friend Assemblies</span></span>](../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="03474-132">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="03474-132">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
