---
title: Lc.exe (License Compiler-Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Lc.exe
- .licx file
- License Compiler
- control licenses [Windows Forms]
- compiling licenses file
- license file
- .licenses file
- Windows Forms, control licenses
- licensed controls [Windows Forms]
ms.assetid: 2de803b8-495e-4982-b209-19a72aba0460
ms.openlocfilehash: 6c4432d94372ce10ee9ecdf6e441eda3318a20d7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59298967"
---
# <a name="lcexe-license-compiler"></a><span data-ttu-id="d29e5-102">Lc.exe (License Compiler-Tool)</span><span class="sxs-lookup"><span data-stu-id="d29e5-102">Lc.exe (License Compiler)</span></span>
<span data-ttu-id="d29e5-103">Der Lizenzcompiler liest Textdateien mit Informationen über die Lizenzierung und erstellt eine Binärdatei, die als Ressource in eine ausführbare Datei der Common Language Runtime eingebettet werden kann.</span><span class="sxs-lookup"><span data-stu-id="d29e5-103">The License Compiler reads text files that contain licensing information and produces a binary file that can be embedded in a common language runtime executable as a resource.</span></span>  
  
 <span data-ttu-id="d29e5-104">Eine LICX-Textdatei wird vom Windows Forms-Designer automatisch generiert oder aktualisiert, sobald dem Formular ein lizenziertes Steuerelement hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="d29e5-104">A .licx text file is automatically generated or updated by the Windows Forms Designer whenever a licensed control is added to the form.</span></span> <span data-ttu-id="d29e5-105">Bei der Kompilierung wandelt das Projektsystem die LICX-Textdatei in eine binäre LICENSES-Ressource um, die die Lizenzierung des .NET-Steuerelements unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d29e5-105">As part of compilation, the project system will transform the .licx text file into a .licenses binary resource that provides support for .NET control licensing.</span></span> <span data-ttu-id="d29e5-106">Die binäre Ressource wird anschließend in die Projektausgabe eingebettet.</span><span class="sxs-lookup"><span data-stu-id="d29e5-106">The binary resource will then be embedded in the project output.</span></span>  
  
 <span data-ttu-id="d29e5-107">Kreuzkompilierung zwischen 32-Bit und 64-Bit wird nicht unterstützt, wenn Sie beim Erstellen des Projekts den Lizenzcompiler verwenden.</span><span class="sxs-lookup"><span data-stu-id="d29e5-107">Cross compilation between 32-bit and 64-bit is not supported when you use the License Compiler when building your project.</span></span> <span data-ttu-id="d29e5-108">Das liegt daran, dass der Lizenzcompiler Assemblys laden muss und das Laden von 64-Bit-Assemblys aus einer 32-Bit-Anwendung und umgekehrt nicht erlaubt ist.</span><span class="sxs-lookup"><span data-stu-id="d29e5-108">This is because the License Compiler has to load assemblies, and loading 64-bit assemblies from a 32-bit application is not allowed, and vice versa.</span></span> <span data-ttu-id="d29e5-109">Verwenden Sie in diesem Fall den Lizenzcompiler von der Befehlszeile aus, um die Lizenz manuell zu kompilieren, und geben Sie die entsprechende Architektur an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-109">In this case, use the License Compiler from the command line to compile the license manually, and specify the corresponding architecture.</span></span>  
  
 <span data-ttu-id="d29e5-110">Dieses Tool wird automatisch mit Visual Studio installiert.</span><span class="sxs-lookup"><span data-stu-id="d29e5-110">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="d29e5-111">Verwenden Sie die Developer-Eingabeaufforderung für Visual Studio (oder die Visual Studio-Eingabeaufforderung in Windows 7), um das Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d29e5-111">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="d29e5-112">Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span><span class="sxs-lookup"><span data-stu-id="d29e5-112">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="d29e5-113">Geben Sie an der Eingabeaufforderung Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="d29e5-113">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29e5-114">Syntax</span><span class="sxs-lookup"><span data-stu-id="d29e5-114">Syntax</span></span>  
  
```  
      lc /target:  
      targetPE /complist:filename [/outdir:path]  
/i:modules [/nologo] [/v]  
```  
  
|<span data-ttu-id="d29e5-115">Option</span><span class="sxs-lookup"><span data-stu-id="d29e5-115">Option</span></span>|<span data-ttu-id="d29e5-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d29e5-116">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d29e5-117">**/complist:** *filename*</span><span class="sxs-lookup"><span data-stu-id="d29e5-117">**/complist:** *filename*</span></span>|<span data-ttu-id="d29e5-118">Gibt den Namen einer Datei an, die die Liste der lizenzierten Komponenten enthält, die in die LICENSES-Datei eingebunden werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d29e5-118">Specifies the name of a file that contains the list of licensed components to include in the .licenses file.</span></span> <span data-ttu-id="d29e5-119">Auf die einzelnen Komponenten wird mit dem vollständigen Namen verwiesen, wobei pro Zeile jeweils nur eine Komponente aufgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d29e5-119">Each component is referenced using its full name with only one component per line.</span></span><br /><br /> <span data-ttu-id="d29e5-120">Benutzer der Befehlszeile können für jedes Formular des Projekts eine eigene Datei angeben.</span><span class="sxs-lookup"><span data-stu-id="d29e5-120">Command-line users can specify a separate file for each form in the project.</span></span> <span data-ttu-id="d29e5-121">"Lc.exe" akzeptiert mehrere Eingabedateien und erstellt eine einzige LICENSES-Datei.</span><span class="sxs-lookup"><span data-stu-id="d29e5-121">Lc.exe accepts multiple input files and produces a single .licenses file.</span></span>|  
|<span data-ttu-id="d29e5-122">**-h**[**elp**]</span><span class="sxs-lookup"><span data-stu-id="d29e5-122">**/h**[**elp**]</span></span>|<span data-ttu-id="d29e5-123">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-123">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="d29e5-124">**/i:** *module*</span><span class="sxs-lookup"><span data-stu-id="d29e5-124">**/i:** *module*</span></span>|<span data-ttu-id="d29e5-125">Gibt die Module an, die die in der Datei **/complist**aufgelisteten Komponenten enthalten.</span><span class="sxs-lookup"><span data-stu-id="d29e5-125">Specifies the modules that contain the components listed in the **/complist** file.</span></span> <span data-ttu-id="d29e5-126">Verwenden Sie mehrere **/i**-Flags, um mehrere Module anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d29e5-126">To specify more than one module, use multiple **/i** flags.</span></span>|  
|**<span data-ttu-id="d29e5-127">/nologo</span><span class="sxs-lookup"><span data-stu-id="d29e5-127">/nologo</span></span>**|<span data-ttu-id="d29e5-128">Unterdrückt die Anzeige des Startbanners von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d29e5-128">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="d29e5-129">**/outdir:** *path*</span><span class="sxs-lookup"><span data-stu-id="d29e5-129">**/outdir:** *path*</span></span>|<span data-ttu-id="d29e5-130">Gibt das Verzeichnis an, in dem die LICENSES-Ausgabedatei gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d29e5-130">Specifies the directory in which to place the output .licenses file.</span></span>|  
|<span data-ttu-id="d29e5-131">**/target:** *targetPE*</span><span class="sxs-lookup"><span data-stu-id="d29e5-131">**/target:** *targetPE*</span></span>|<span data-ttu-id="d29e5-132">Gibt die ausführbare Datei an, für die die LICENSES-Datei generiert wird.</span><span class="sxs-lookup"><span data-stu-id="d29e5-132">Specifies the executable for which the .licenses file is being generated.</span></span>|  
|**<span data-ttu-id="d29e5-133">/v</span><span class="sxs-lookup"><span data-stu-id="d29e5-133">/v</span></span>**|<span data-ttu-id="d29e5-134">Gibt den ausführlichen Modus an und zeigt Statusinformationen zur Kompilierung an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-134">Specifies verbose mode; displays compilation progress information.</span></span>|  
|<span data-ttu-id="d29e5-135">**@** *file*</span><span class="sxs-lookup"><span data-stu-id="d29e5-135">**@** *file*</span></span>|<span data-ttu-id="d29e5-136">Gibt die Antwortdatei (.rsp) an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-136">Specifies the response (.rsp) file.</span></span>|  
|**<span data-ttu-id="d29e5-137">/?</span><span class="sxs-lookup"><span data-stu-id="d29e5-137">/?</span></span>**|<span data-ttu-id="d29e5-138">Zeigt Befehlssyntax und Optionen für das Tool an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-138">Displays command syntax and options for the tool.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d29e5-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d29e5-139">Example</span></span>  
  
1. <span data-ttu-id="d29e5-140">Wenn Sie das lizenzierte Steuerelement `MyCompany.Samples.LicControl1` verwenden, das in `Samples.DLL` in einer Anwendung namens `HostApp.exe`*,* enthalten ist, können Sie `HostAppLic.txt` mit folgendem Inhalt erstellen.</span><span class="sxs-lookup"><span data-stu-id="d29e5-140">If you are using a licensed control `MyCompany.Samples.LicControl1` contained in `Samples.DLL` in an application called `HostApp.exe`*,* you can create `HostAppLic.txt` that contains the following.</span></span>  
  
    ```  
    MyCompany.Samples.LicControl1, Samples.DLL  
    ```  
  
2. <span data-ttu-id="d29e5-141">Erstellen Sie die LICENSES-Datei `HostApp.exe.licenses` mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="d29e5-141">Create the .licenses file called `HostApp.exe.licenses` using the following command.</span></span>  
  
    ```  
    lc /target:HostApp.exe /complist:hostapplic.txt /i:Samples.DLL /outdir:c:\bindir  
    ```  
  
3. <span data-ttu-id="d29e5-142">Erstellen Sie `HostApp.exe` mit der LICENSES-Datei als Ressource.</span><span class="sxs-lookup"><span data-stu-id="d29e5-142">Build `HostApp.exe` including the .licenses file as a resource.</span></span> <span data-ttu-id="d29e5-143">Wenn Sie eine C#-Anwendung erstellt haben, erstellen Sie die Anwendung mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="d29e5-143">If you were building a C# application you would use the following command to build your application.</span></span>  
  
    ```  
    csc /res:HostApp.exe.licenses /out:HostApp.exe *.cs  
    ```  
  
 <span data-ttu-id="d29e5-144">Mit dem folgenden Befehl wird `myApp.licenses` aus den von `hostapplic.txt`, `hostapplic2.txt` und `hostapplic3.txt` angegebenen Listen lizenzierter Komponenten kompiliert.</span><span class="sxs-lookup"><span data-stu-id="d29e5-144">The following command compiles `myApp.licenses` from the lists of licensed components specified by `hostapplic.txt`, `hostapplic2.txt` and `hostapplic3.txt`.</span></span> <span data-ttu-id="d29e5-145">Das `modulesList`-Argument gibt die Module mit den lizenzierten Komponenten an.</span><span class="sxs-lookup"><span data-stu-id="d29e5-145">The `modulesList` argument specifies the modules that contain the licensed components.</span></span>  
  
```  
lc /target:myApp /complist:hostapplic.txt /complist:hostapplic2.txt /complist: hostapplic3.txt /i:modulesList  
```  
  
## <a name="response-file-example"></a><span data-ttu-id="d29e5-146">Beispiel für eine Antwortdatei</span><span class="sxs-lookup"><span data-stu-id="d29e5-146">Response File Example</span></span>  
 <span data-ttu-id="d29e5-147">Die folgende Auflistung enthält ein Beispiel für eine Antwortdatei namens `response.rsp`.</span><span class="sxs-lookup"><span data-stu-id="d29e5-147">The following listing shows an example of a response file, `response.rsp`.</span></span> <span data-ttu-id="d29e5-148">Weitere Informationen zu Antwortdateien finden Sie unter [Antwortdateien](/visualstudio/msbuild/msbuild-response-files).</span><span class="sxs-lookup"><span data-stu-id="d29e5-148">For more information on response files, see [Response Files](/visualstudio/msbuild/msbuild-response-files).</span></span>  
  
```  
/target:hostapp.exe  
/complist:hostapplic.txt   
/i:WFCPrj.dll   
/outdir:"C:\My Folder"  
```  
  
 <span data-ttu-id="d29e5-149">In der folgenden Befehlszeile wird die `response.rsp` Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="d29e5-149">The following command line uses the `response.rsp` file.</span></span>  
  
```  
lc @response.rsp  
```  
  
## <a name="see-also"></a><span data-ttu-id="d29e5-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d29e5-150">See also</span></span>

- [<span data-ttu-id="d29e5-151">Tools</span><span class="sxs-lookup"><span data-stu-id="d29e5-151">Tools</span></span>](../../../docs/framework/tools/index.md)
- [<span data-ttu-id="d29e5-152">Al.exe (Assembly Linker-Tool)</span><span class="sxs-lookup"><span data-stu-id="d29e5-152">Al.exe (Assembly Linker)</span></span>](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [<span data-ttu-id="d29e5-153">Eingabeaufforderungen</span><span class="sxs-lookup"><span data-stu-id="d29e5-153">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
