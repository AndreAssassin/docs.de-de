---
title: 'Vorgehensweise: Lokalisieren einer Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- localization [WPF], applications
- LocBaml tool [WPF]
- applications [WPF], localizing
ms.assetid: 5001227e-9326-48a4-9dcd-ba1b89ee6653
ms.openlocfilehash: d08f991204b2d74899cbd1aee82c0cc23e175dd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59298317"
---
# <a name="how-to-localize-an-application"></a><span data-ttu-id="11e98-102">Vorgehensweise: Lokalisieren einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="11e98-102">How to: Localize an Application</span></span>
<span data-ttu-id="11e98-103">In diesem Lernprogramm wird erläutert, wie eine lokalisierte Anwendung mit dem LocBaml-Tool erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-103">This tutorial explains how to create a localized application by using the LocBaml tool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="11e98-104">Das LocBaml-Tool ist keine einsatzfertige Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11e98-104">The LocBaml tool is not a production-ready application.</span></span> <span data-ttu-id="11e98-105">Es wird als Beispiel präsentiert, das einen Teil der Lokalisierungs-APIs verwendet und veranschaulicht, wie Sie ein Lokalisierungstool schreiben können.</span><span class="sxs-lookup"><span data-stu-id="11e98-105">It is presented as a sample that uses some of the localization APIs and illustrates how you might write a localization tool.</span></span>  
  
<a name="Introduction"></a>   
## <a name="overview"></a><span data-ttu-id="11e98-106">Übersicht</span><span class="sxs-lookup"><span data-stu-id="11e98-106">Overview</span></span>  
 <span data-ttu-id="11e98-107">Diese Diskussion bietet einen schrittweisen Ansatz zum Lokalisieren einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11e98-107">This discussion gives you a step-by-step approach to localizing an application.</span></span> <span data-ttu-id="11e98-108">Zuerst bereiten Sie Ihre Anwendung so vor, dass der zu übersetzende Text extrahiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e98-108">First, you will prepare your application so that the text that will be translated can be extracted.</span></span> <span data-ttu-id="11e98-109">Nachdem der Text übersetzt wurde, führen Sie den übersetzten Text mit einer neuen Kopie der ursprünglichen Anwendung zusammen.</span><span class="sxs-lookup"><span data-stu-id="11e98-109">After the text is translated, you will merge the translated text into a new copy of the original application.</span></span>  
  
<a name="Requirements"></a>   
## <a name="requirements"></a><span data-ttu-id="11e98-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11e98-110">Requirements</span></span>  
 <span data-ttu-id="11e98-111">Im Verlauf dieser Diskussion verwenden Sie [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], ein Compiler, der über die Befehlszeile ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-111">Over the course of this discussion, you will use [!INCLUDE[TLA#tla_msbuild](../../../../includes/tlasharptla-msbuild-md.md)], which is a compiler that runs from the command line.</span></span>  
  
 <span data-ttu-id="11e98-112">Darüber hinaus werden Sie aufgefordert, eine Projektdatei zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="11e98-112">Also, you will be instructed to use a project file.</span></span> <span data-ttu-id="11e98-113">Anweisungen zur Verwendung von [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] und Projektdateien, finden Sie unter [erstellen und Bereitstellen von](../app-development/building-and-deploying-wpf-applications.md).</span><span class="sxs-lookup"><span data-stu-id="11e98-113">For instructions on how to use [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] and project files, see [Build and Deploy](../app-development/building-and-deploying-wpf-applications.md).</span></span>  
  
 <span data-ttu-id="11e98-114">Alle Beispiele in dieser Diskussion verwenden als Kultur US-amerikanisches Englisch (en-US, Englisch-US).</span><span class="sxs-lookup"><span data-stu-id="11e98-114">All the examples in this discussion use en-US (English-US) as the culture.</span></span> <span data-ttu-id="11e98-115">Dies ermöglicht es Ihnen, die Beispielschritte durchzuarbeiten, ohne eine andere Sprache installieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="11e98-115">This enables you to work through the steps of the examples without installing a different language.</span></span>  
  
<a name="create_sample_app"></a>   
## <a name="create-a-sample-application"></a><span data-ttu-id="11e98-116">Erstellen einer Beispielanwendung</span><span class="sxs-lookup"><span data-stu-id="11e98-116">Create a Sample Application</span></span>  
 <span data-ttu-id="11e98-117">In diesem Schritt bereiten Sie Ihre Anwendung für die Lokalisierung vor.</span><span class="sxs-lookup"><span data-stu-id="11e98-117">In this step, you will prepare your application for localization.</span></span> <span data-ttu-id="11e98-118">In den [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]-Beispielen wird die Beispielanwendung HelloApp bereitgestellt, die für die Codebeispiele in dieser Diskussion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-118">In the [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] samples, a HelloApp sample is supplied that will be used for the code examples in this discussion.</span></span> <span data-ttu-id="11e98-119">Wenn Sie dieses Beispiel verwenden möchten, laden Sie die [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Dateien aus dem [Beispieltool LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016).</span><span class="sxs-lookup"><span data-stu-id="11e98-119">If you would like to use this sample, download the [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
1. <span data-ttu-id="11e98-120">Entwickeln Sie Ihre Anwendung bis zu dem Punkt, an dem Sie die Lokalisierung starten möchten.</span><span class="sxs-lookup"><span data-stu-id="11e98-120">Develop your application to the point where you want to start localization.</span></span>  
  
2. <span data-ttu-id="11e98-121">Geben Sie die Entwicklungssprache in der Projektdatei so an, dass [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] eine Hauptassembly und eine Satellitenassembly (eine Datei mit der Erweiterung ".resources.dll") generiert, die die neutralen Sprachressourcen enthält.</span><span class="sxs-lookup"><span data-stu-id="11e98-121">Specify the development language in the project file so that [!INCLUDE[TLA2#tla_msbuild](../../../../includes/tla2sharptla-msbuild-md.md)] generates a main assembly and a satellite assembly (a file with the .resources.dll extension) to contain the neutral language resources.</span></span> <span data-ttu-id="11e98-122">Die Projektdatei im HelloApp-Beispiel ist "HelloApp.csproj".</span><span class="sxs-lookup"><span data-stu-id="11e98-122">The project file in the HelloApp sample is HelloApp.csproj.</span></span> <span data-ttu-id="11e98-123">In dieser Datei finden Sie die Entwicklungssprache wie folgt gekennzeichnet:</span><span class="sxs-lookup"><span data-stu-id="11e98-123">In that file, you will find the development language identified as follows:</span></span>  
  
     `<UICulture>en-US</UICulture>`  
  
3. <span data-ttu-id="11e98-124">Fügen Sie den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]-Dateien UIDs hinzu.</span><span class="sxs-lookup"><span data-stu-id="11e98-124">Add Uids to your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] files.</span></span> <span data-ttu-id="11e98-125">UIDs werden verwendet, um Änderungen an Dateien nachzuverfolgen und die Elemente zu identifizieren, die übersetzt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="11e98-125">Uids are used to keep track of changes to files and to identify items that must be translated.</span></span> <span data-ttu-id="11e98-126">Um Ihre Dateien Uids hinzuzufügen, führen Sie **Updateuid** in Ihrer Projektdatei hinzu:</span><span class="sxs-lookup"><span data-stu-id="11e98-126">To add Uids to your files, run **updateuid** on your project file:</span></span>  
  
     <span data-ttu-id="11e98-127">**msbuild -t:updateuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="11e98-127">**msbuild -t:updateuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="11e98-128">Führen Sie zum Überprüfen, dass Sie keine fehlen bzw. doppelt Uids vorhanden **Checkuid**:</span><span class="sxs-lookup"><span data-stu-id="11e98-128">To verify that you have no missing or duplicate Uids, run **checkuid**:</span></span>  
  
     <span data-ttu-id="11e98-129">**msbuild -t:checkuid helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="11e98-129">**msbuild -t:checkuid helloapp.csproj**</span></span>  
  
     <span data-ttu-id="11e98-130">Nach der Ausführung **Updateuid**, sollten Ihre Dateien Uids enthalten.</span><span class="sxs-lookup"><span data-stu-id="11e98-130">After running **updateuid**, your files should contain Uids.</span></span> <span data-ttu-id="11e98-131">Beispielsweise sollten Sie in der Datei "Pane1.xaml" von HelloApp Folgendes finden:</span><span class="sxs-lookup"><span data-stu-id="11e98-131">For example, in the Pane1.xaml file of HelloApp, you should find the following:</span></span>  
  
     `<StackPanel x:Uid="StackPanel_1">`  
  
     `<TextBlock x:Uid="TextBlock_1">Hello World</TextBlock>`  
  
     `<TextBlock x:Uid="TextBlock_2">Goodbye World</TextBlock>`  
  
     `</StackPanel>`  
  
<a name="create_dll"></a>   
## <a name="create-the-neutral-language-resources-satellite-assembly"></a><span data-ttu-id="11e98-132">Erstellen der Satellitenassembly mit den neutralen Sprachressourcen</span><span class="sxs-lookup"><span data-stu-id="11e98-132">Create the Neutral Language Resources Satellite Assembly</span></span>  
 <span data-ttu-id="11e98-133">Nachdem die Anwendung so konfiguriert ist, dass eine Satellitenassembly mit den neutralen Sprachressourcen generiert wird, erstellen Sie die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="11e98-133">After the application is configured to generate a neutral language resources satellite assembly, you build the application.</span></span> <span data-ttu-id="11e98-134">Auf diese Weise werden die Hauptassembly der Anwendung und die Satellitenassembly mit den neutralen Sprachressourcen generiert, die LocBaml für die Lokalisierung benötigt.</span><span class="sxs-lookup"><span data-stu-id="11e98-134">This generates the main application assembly, as well as the neutral language resources satellite assembly that is required by LocBaml for localization.</span></span> <span data-ttu-id="11e98-135">So erstellen Sie die Anwendung:</span><span class="sxs-lookup"><span data-stu-id="11e98-135">To build the application:</span></span>  
  
1. <span data-ttu-id="11e98-136">Kompilieren Sie HelloApp, damit eine [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="11e98-136">Compile HelloApp to create a [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)]:</span></span>  
  
     <span data-ttu-id="11e98-137">**msbuild helloapp.csproj**</span><span class="sxs-lookup"><span data-stu-id="11e98-137">**msbuild helloapp.csproj**</span></span>  
  
2. <span data-ttu-id="11e98-138">Die neu erstellte Hauptanwendungsassembly, "HelloApp.exe", wird im folgenden Ordner erstellt:</span><span class="sxs-lookup"><span data-stu-id="11e98-138">The newly created main application assembly, HelloApp.exe, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\`  
  
3. <span data-ttu-id="11e98-139">Die neu erstellte Satellitenassembly mit den neutralen Sprachressourcen, "HelloApp.resources.dll", wird im folgenden Ordner erstellt:</span><span class="sxs-lookup"><span data-stu-id="11e98-139">The newly created neutral language resources satellite assembly, HelloApp.resources.dll, is created in the following folder:</span></span>  
  
     `C:\HelloApp\Bin\Debug\en-US\`  
  
<a name="build_locbaml"></a>   
## <a name="build-the-locbaml-tool"></a><span data-ttu-id="11e98-140">Erstellen des LocBaml-Tools</span><span class="sxs-lookup"><span data-stu-id="11e98-140">Build the LocBaml Tool</span></span>  
  
1. <span data-ttu-id="11e98-141">Alle für das Erstellen von LocBaml notwendigen Dateien befinden sich in den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Beispielen.</span><span class="sxs-lookup"><span data-stu-id="11e98-141">All the files necessary to build LocBaml are located in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] samples.</span></span> <span data-ttu-id="11e98-142">Laden Sie die C#-Dateien aus dem [Beispieltool LocBaml](https://go.microsoft.com/fwlink/?LinkID=160016).</span><span class="sxs-lookup"><span data-stu-id="11e98-142">Download the C# files from the [LocBaml Tool Sample](https://go.microsoft.com/fwlink/?LinkID=160016).</span></span>  
  
2. <span data-ttu-id="11e98-143">Führen Sie über die Befehlszeile die Projektdatei (locbaml.csproj) aus, um das Tool zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="11e98-143">From the command line, run the project file (locbaml.csproj) to build the tool:</span></span>  
  
     <span data-ttu-id="11e98-144">**msbuild locbaml.csproj**</span><span class="sxs-lookup"><span data-stu-id="11e98-144">**msbuild locbaml.csproj**</span></span>  
  
3. <span data-ttu-id="11e98-145">Wechseln Sie zum Verzeichnis "Bin\Release", um die neu erstellte ausführbare Datei (locbaml.exe) zu finden.</span><span class="sxs-lookup"><span data-stu-id="11e98-145">Go to the Bin\Release directory to find the newly created executable file (locbaml.exe).</span></span> <span data-ttu-id="11e98-146">Beispiel: C:\LocBaml\Bin\Release\locbaml.exe.</span><span class="sxs-lookup"><span data-stu-id="11e98-146">Example:C:\LocBaml\Bin\Release\locbaml.exe.</span></span>  
  
4. <span data-ttu-id="11e98-147">Für ein Ausführen von LocBaml können Sie folgende Optionen angeben:</span><span class="sxs-lookup"><span data-stu-id="11e98-147">The options that you can specify when you run LocBaml are as follows:</span></span>  
  
    -   <span data-ttu-id="11e98-148">**Analysieren von** oder **-p:** Analysiert BAML-, oder [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] Dateien, um eine CSV- oder TXT-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11e98-148">**parse** or **-p:** Parses Baml, resources, or [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] files to generate a .csv or .txt file.</span></span>  
  
    -   <span data-ttu-id="11e98-149">**Generieren von** oder **-g:** Generiert eine lokalisierte Binärdatei, indem eine übersetzte Datei.</span><span class="sxs-lookup"><span data-stu-id="11e98-149">**generate** or **-g:** Generates a localized binary file by using a translated file.</span></span>  
  
    -   <span data-ttu-id="11e98-150">**out** oder **- e/a** {*Dateiverzeichnis*] **:** Name der Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="11e98-150">**out** or **-o** {*filedirectory*] **:** Output file name.</span></span>  
  
    -   <span data-ttu-id="11e98-151">**Kultur** oder **- Cul** {*Kultur*] **:** Gebietsschema der Ausgabeassemblys.</span><span class="sxs-lookup"><span data-stu-id="11e98-151">**culture** or **-cul** {*culture*] **:** Locale of output assemblies.</span></span>  
  
    -   <span data-ttu-id="11e98-152">**Übersetzung** oder **- Trans** {*translation.csv*] **:** Übersetzte oder lokalisierte Datei.</span><span class="sxs-lookup"><span data-stu-id="11e98-152">**translation** or **-trans** {*translation.csv*] **:** Translated or localized file.</span></span>  
  
    -   <span data-ttu-id="11e98-153">**Asmpath** oder **- Asmpath:** {*Dateiverzeichnis*] **:** Wenn Ihre [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -Code benutzerdefinierte Steuerelemente enthält, geben Sie an der **Asmpath** für die benutzerdefinierte Steuerelementassembly.</span><span class="sxs-lookup"><span data-stu-id="11e98-153">**asmpath** or **-asmpath:** {*filedirectory*] **:** If your [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] code contains custom controls, you must supply the **asmpath** to the custom control assembly.</span></span>  
  
    -   <span data-ttu-id="11e98-154">**nologo:** Werden keine Informationen Logo noch Copyrightinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="11e98-154">**nologo:** Displays no logo or copyright information.</span></span>  
  
    -   <span data-ttu-id="11e98-155">**verbose:** Zeigt Informationen im ausführlichen Modus an.</span><span class="sxs-lookup"><span data-stu-id="11e98-155">**verbose:** Displays verbose mode information.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11e98-156">Wenn Sie eine Liste der Optionen benötigen, wenn Sie das Tool ausgeführt werden, geben Sie **LocBaml.exe** und drücken Sie EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="11e98-156">If you need a list of the options when you are running the tool, type     **LocBaml.exe** and press ENTER.</span></span>  
  
<a name="parse_dll"></a>   
## <a name="use-locbaml-to-parse-a-file"></a><span data-ttu-id="11e98-157">Verwenden von LocBaml zum Analysieren einer Datei</span><span class="sxs-lookup"><span data-stu-id="11e98-157">Use LocBaml to Parse a File</span></span>  
 <span data-ttu-id="11e98-158">Nachdem Sie das LocBaml-Tool erstellt haben, können Sie es verwenden, um "HelloApp.resources.dll" zu analysieren, um den Textinhalt zu extrahieren, der lokalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-158">Now that you have created the LocBaml tool, you are ready to use it to parse HelloApp.resources.dll to extract the text content that will be localized.</span></span>  
  
1. <span data-ttu-id="11e98-159">Kopieren Sie "LocBaml.exe" in den "bin\debug"-Ordner Ihrer Anwendung, in dem die Hauptanwendungsassembly erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="11e98-159">Copy LocBaml.exe to your application's bin\debug folder, where the main application assembly was created.</span></span>  
  
2. <span data-ttu-id="11e98-160">Um die Satellitenassemblydatei zu analysieren und die Ausgabe als CSV-Datei zu speichern, verwenden Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="11e98-160">To parse the satellite assembly file and store the output as a .csv file, use the following command:</span></span>  
  
     <span data-ttu-id="11e98-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span><span class="sxs-lookup"><span data-stu-id="11e98-161">**LocBaml.exe /parse HelloApp.resources.dll /out:Hello.csv**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11e98-162">Wenn sich die Eingabedatei "HelloApp.resources.dll" nicht im selben Ordner wie "LocBaml.exe" befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="11e98-162">If the input file, HelloApp.resources.dll, is not in the same directory as LocBaml.exe move one of the files so that both files are in the same directory.</span></span>  
  
3. <span data-ttu-id="11e98-163">Wenn Sie LocBaml ausführen, um Dateien zu analysieren, besteht die Ausgabe aus sieben Feldern, die jeweils durch Kommas (CSV-Dateien) oder Tabulatoren (TXT-Dateien) getrennt sind.</span><span class="sxs-lookup"><span data-stu-id="11e98-163">When you run LocBaml to parse files, the output consists of seven fields delimited by commas (.csv files) or tabs (.txt files).</span></span> <span data-ttu-id="11e98-164">Nachstehend ist die bei der Analyse erstellte CSV-Datei für "HelloApp.Resources.dll" gezeigt:</span><span class="sxs-lookup"><span data-stu-id="11e98-164">The following shows the parsed .csv file for the HelloApp.resources.dll:</span></span>

   | |
   |-|
   |<span data-ttu-id="11e98-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span><span class="sxs-lookup"><span data-stu-id="11e98-165">HelloApp.g.en-US.resources:window1.baml,Stack1:System.Windows.Controls.StackPanel.$Content,Ignore,FALSE, FALSE,,#Text1;#Text2;</span></span>|
   |<span data-ttu-id="11e98-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span><span class="sxs-lookup"><span data-stu-id="11e98-166">HelloApp.g.en-US.resources:window1.baml,Text1:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Hello World</span></span>|
   |<span data-ttu-id="11e98-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span><span class="sxs-lookup"><span data-stu-id="11e98-167">HelloApp.g.en-US.resources:window1.baml,Text2:System.Windows.Controls.TextBlock.$Content,None,TRUE, TRUE,,Goodbye World</span></span>|

   <span data-ttu-id="11e98-168">Die sieben Felder sind:</span><span class="sxs-lookup"><span data-stu-id="11e98-168">The seven fields are:</span></span>  
  
   1.  <span data-ttu-id="11e98-169">**BAML-Name**.</span><span class="sxs-lookup"><span data-stu-id="11e98-169">**BAML Name**.</span></span> <span data-ttu-id="11e98-170">Der Name der BAML-Ressource bezogen auf die Satellitenassembly für die Ausgangssprache.</span><span class="sxs-lookup"><span data-stu-id="11e98-170">The name of the BAML resource with respect to the source language satellite assembly.</span></span>  
  
   2.  <span data-ttu-id="11e98-171">**Ressourcenschlüssel**.</span><span class="sxs-lookup"><span data-stu-id="11e98-171">**Resource Key**.</span></span> <span data-ttu-id="11e98-172">Der lokalisierte Ressourcenbezeichner.</span><span class="sxs-lookup"><span data-stu-id="11e98-172">The localized resource identifier.</span></span>  
  
   3.  <span data-ttu-id="11e98-173">**Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="11e98-173">**Category**.</span></span> <span data-ttu-id="11e98-174">Der Werttyp.</span><span class="sxs-lookup"><span data-stu-id="11e98-174">The value type.</span></span> <span data-ttu-id="11e98-175">Finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="11e98-175">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   4.  <span data-ttu-id="11e98-176">**Lesbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="11e98-176">**Readability**.</span></span> <span data-ttu-id="11e98-177">Gibt an, ob der Wert von einem Lokalisierungstool gelesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e98-177">Whether the value can be read by a localizer.</span></span> <span data-ttu-id="11e98-178">Finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="11e98-178">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   5.  <span data-ttu-id="11e98-179">**Änderbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="11e98-179">**Modifiability**.</span></span> <span data-ttu-id="11e98-180">Gibt an, ob der Wert von einem Lokalisierungstool geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e98-180">Whether the value can be modified by a localizer.</span></span> <span data-ttu-id="11e98-181">Finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="11e98-181">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   6.  <span data-ttu-id="11e98-182">**Kommentare**.</span><span class="sxs-lookup"><span data-stu-id="11e98-182">**Comments**.</span></span> <span data-ttu-id="11e98-183">Zusätzliche Beschreibung des Werts, um zu ermitteln, wie ein Wert lokalisiert wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-183">Additional description of the value to help determine how a value is localized.</span></span> <span data-ttu-id="11e98-184">Finden Sie unter [Lokalisierungsattribute und-Kommentare](localization-attributes-and-comments.md).</span><span class="sxs-lookup"><span data-stu-id="11e98-184">See [Localization Attributes and Comments](localization-attributes-and-comments.md).</span></span>  
  
   7.  <span data-ttu-id="11e98-185">**Wert**.</span><span class="sxs-lookup"><span data-stu-id="11e98-185">**Value**.</span></span> <span data-ttu-id="11e98-186">Der Textwert, der in die gewünschte Sprache übersetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="11e98-186">The text value to translate to the desired culture.</span></span>  
  
   <span data-ttu-id="11e98-187">Die folgende Tabelle zeigt, wie diese Felder den durch Trennzeichen getrennten Werten der CSV-Datei zugeordnet sind:</span><span class="sxs-lookup"><span data-stu-id="11e98-187">The following table shows how these fields map to the delimited values of the .csv file:</span></span>  
  
   |<span data-ttu-id="11e98-188">BAML-Name</span><span class="sxs-lookup"><span data-stu-id="11e98-188">BAML name</span></span>|<span data-ttu-id="11e98-189">Ressourcenschlüssel</span><span class="sxs-lookup"><span data-stu-id="11e98-189">Resource key</span></span>|<span data-ttu-id="11e98-190">Kategorie</span><span class="sxs-lookup"><span data-stu-id="11e98-190">Category</span></span>|<span data-ttu-id="11e98-191">Lesbarkeit</span><span class="sxs-lookup"><span data-stu-id="11e98-191">Readability</span></span>|<span data-ttu-id="11e98-192">Änderbarkeit</span><span class="sxs-lookup"><span data-stu-id="11e98-192">Modifiability</span></span>|<span data-ttu-id="11e98-193">Kommentare</span><span class="sxs-lookup"><span data-stu-id="11e98-193">Comments</span></span>|<span data-ttu-id="11e98-194">Wert</span><span class="sxs-lookup"><span data-stu-id="11e98-194">Value</span></span>|  
   |---------------|------------------|--------------|-----------------|-------------------|--------------|-----------|
   |<span data-ttu-id="11e98-195">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="11e98-195">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="11e98-196">Stack1:System.Windows.Controls.StackPanel.$Content</span><span class="sxs-lookup"><span data-stu-id="11e98-196">Stack1:System.Windows.Controls.StackPanel.$Content</span></span>|<span data-ttu-id="11e98-197">Ignorieren</span><span class="sxs-lookup"><span data-stu-id="11e98-197">Ignore</span></span>|<span data-ttu-id="11e98-198">false</span><span class="sxs-lookup"><span data-stu-id="11e98-198">FALSE</span></span>|<span data-ttu-id="11e98-199">false</span><span class="sxs-lookup"><span data-stu-id="11e98-199">FALSE</span></span>||<span data-ttu-id="11e98-200">#Text1;#Text2</span><span class="sxs-lookup"><span data-stu-id="11e98-200">#Text1;#Text2</span></span>|
   |<span data-ttu-id="11e98-201">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="11e98-201">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="11e98-202">Text1:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="11e98-202">Text1:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="11e98-203">Keiner</span><span class="sxs-lookup"><span data-stu-id="11e98-203">None</span></span>|<span data-ttu-id="11e98-204">true</span><span class="sxs-lookup"><span data-stu-id="11e98-204">TRUE</span></span>|<span data-ttu-id="11e98-205">true</span><span class="sxs-lookup"><span data-stu-id="11e98-205">TRUE</span></span>||<span data-ttu-id="11e98-206">Hello World</span><span class="sxs-lookup"><span data-stu-id="11e98-206">Hello World</span></span>|
   |<span data-ttu-id="11e98-207">HelloApp.g.en-US.resources:window1.baml</span><span class="sxs-lookup"><span data-stu-id="11e98-207">HelloApp.g.en-US.resources:window1.baml</span></span>|<span data-ttu-id="11e98-208">Text2:System.Windows.Controls.TextBlock.$Content</span><span class="sxs-lookup"><span data-stu-id="11e98-208">Text2:System.Windows.Controls.TextBlock.$Content</span></span>|<span data-ttu-id="11e98-209">Keiner</span><span class="sxs-lookup"><span data-stu-id="11e98-209">None</span></span>|<span data-ttu-id="11e98-210">true</span><span class="sxs-lookup"><span data-stu-id="11e98-210">TRUE</span></span>|<span data-ttu-id="11e98-211">true</span><span class="sxs-lookup"><span data-stu-id="11e98-211">TRUE</span></span>||<span data-ttu-id="11e98-212">Goodbye World</span><span class="sxs-lookup"><span data-stu-id="11e98-212">Goodbye World</span></span>|
  
   <span data-ttu-id="11e98-213">Beachten Sie, dass alle Werte für die **Kommentare** Feld keine Werte enthalten, wenn ein Feld einen Wert besitzt, ist es leer.</span><span class="sxs-lookup"><span data-stu-id="11e98-213">Notice that all the values for the **Comments** field contain no values; if a field doesn't have a value, it is empty.</span></span> <span data-ttu-id="11e98-214">Beachten Sie auch, dass das Element in der ersten Zeile weder lesbar noch änderbar ist und "ignorieren" als seine **Kategorie** Wert, der angegeben ist, dass der Wert nicht lokalisierbar ist.</span><span class="sxs-lookup"><span data-stu-id="11e98-214">Also notice that the item in the first row is neither readable nor modifiable, and has "Ignore" as its **Category** value, all of which indicates that the value is not localizable.</span></span>  
  
4. <span data-ttu-id="11e98-215">Zum Erkennen von lokalisierbaren Elementen in analysierten Dateien, insbesondere in großen Dateien zu vereinfachen, können Sie sortieren oder filtern Sie die Elemente nach **Kategorie**, **Lesbarkeit**, und **Änderbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="11e98-215">To facilitate discovery of localizable items in parsed files, particularly in large files, you can sort or filter the items by **Category**, **Readability**, and **Modifiability**.</span></span> <span data-ttu-id="11e98-216">Beispielsweise können Sie nicht lesbare und nicht änderbare Werte herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="11e98-216">For example, you can filter out unreadable and unmodifiable values.</span></span>  
  
<a name="translate_loc_content"></a>   
## <a name="translate-the-localizable-content"></a><span data-ttu-id="11e98-217">Übersetzen des lokalisierbaren Inhalts</span><span class="sxs-lookup"><span data-stu-id="11e98-217">Translate the Localizable Content</span></span>  
 <span data-ttu-id="11e98-218">Verwenden Sie ein beliebiges Tool, das Ihnen zur Verfügung steht, um den extrahierten Inhalt zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="11e98-218">Use any tool that you have available to translate the extracted content.</span></span> <span data-ttu-id="11e98-219">Eine gute Vorgehensweise besteht darin, die Ressourcen in eine CSV-Datei zu schreiben, diese in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)] anzuzeigen und die Einträge in der letzten Spalte (Value) zu übersetzen.</span><span class="sxs-lookup"><span data-stu-id="11e98-219">A good way to do this is to write the resources to a .csv file and view them in [!INCLUDE[TLA#tla_xl](../../../../includes/tlasharptla-xl-md.md)], making translation changes to the last column (value).</span></span>  
  
<a name="merge_translations"></a>   
## <a name="use-locbaml-to-generate-a-new-resourcesdll-file"></a><span data-ttu-id="11e98-220">Verwenden von LocBaml zum Generieren einer neuen .resources.dll-Datei</span><span class="sxs-lookup"><span data-stu-id="11e98-220">Use LocBaml to Generate a New .resources.dll File</span></span>  
 <span data-ttu-id="11e98-221">Die Inhalte, die durch das Analysieren von "HelloApp.resources.dll" mit LocBaml erkannt wurden, sind nun übersetzt und müssen wieder mit der ursprünglichen Anwendung zusammengeführt werden.</span><span class="sxs-lookup"><span data-stu-id="11e98-221">The content that was identified by parsing HelloApp.resources.dll with LocBaml has been translated and must be merged back into the original application.</span></span> <span data-ttu-id="11e98-222">Verwenden der **generieren** oder **-g** Option aus, um eine neue. resources.dll-Datei.</span><span class="sxs-lookup"><span data-stu-id="11e98-222">Use the **generate** or **-g** option to generate a new .resources.dll file.</span></span>  
  
1. <span data-ttu-id="11e98-223">Verwenden Sie die folgende Syntax, um eine neue "HelloApp.resources.dll"-Datei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="11e98-223">Use the following syntax to generate a new HelloApp.resources.dll file.</span></span> <span data-ttu-id="11e98-224">Kennzeichnen Sie die Kultur als "en-US" (/cul:en-US).</span><span class="sxs-lookup"><span data-stu-id="11e98-224">Mark the culture as en-US (/cul:en-US).</span></span>  
  
     <span data-ttu-id="11e98-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span><span class="sxs-lookup"><span data-stu-id="11e98-225">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hello.csv /out:c:\ /cul:en-US**</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="11e98-226">Wenn sich die Eingabedatei, "HelloApp.resources.dll", nicht im selben Ordner wie die ausführbare Datei, "LocBaml.exe", befindet, verschieben Sie eine der Dateien, damit sich beide Dateien im selben Verzeichnis befinden.</span><span class="sxs-lookup"><span data-stu-id="11e98-226">If the input file, Hello.csv, is not in the same directory as the executable, LocBaml.exe, move one of the files so that both files are in the same directory.</span></span>  
  
2. <span data-ttu-id="11e98-227">Ersetzen Sie die alte "HelloApp.resources.dll"-Datei im Verzeichnis "C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll" durch die neu erstellte "HelloApp.resources.dll"-Datei.</span><span class="sxs-lookup"><span data-stu-id="11e98-227">Replace the old HelloApp.resources.dll file in the C:\HelloApp\Bin\Debug\en-US\HelloApp.resources.dll directory with your newly created HelloApp.resources.dll file.</span></span>  
  
3. <span data-ttu-id="11e98-228">"Hello World" und "Goodbye World" sollten jetzt in Ihrer Anwendung übersetzt sein.</span><span class="sxs-lookup"><span data-stu-id="11e98-228">"Hello World" and "Goodbye World" should now be translated in your application.</span></span>  
  
4. <span data-ttu-id="11e98-229">Um in eine andere Kultur zu übersetzen, verwenden Sie die Kultur der Sprache, in die Sie übersetzen.</span><span class="sxs-lookup"><span data-stu-id="11e98-229">To translate to a different culture, use the culture of the language that you are translating to.</span></span> <span data-ttu-id="11e98-230">Das folgende Beispiel zeigt, wie in kanadisches Französisch übersetzt wird:</span><span class="sxs-lookup"><span data-stu-id="11e98-230">The following example shows how to translate to French-Canadian:</span></span>  
  
     <span data-ttu-id="11e98-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span><span class="sxs-lookup"><span data-stu-id="11e98-231">**LocBaml.exe /generate HelloApp.resources.dll /trans:Hellofr-CA.csv /out:c:\ /cul:fr-CA**</span></span>  
  
5. <span data-ttu-id="11e98-232">Erstellen Sie in dem Ordner, in dem sich die Hauptanwendungsassembly befindet, einen neuen kulturspezifischen Ordner, der die neue Satellitenassembly aufnehmen soll.</span><span class="sxs-lookup"><span data-stu-id="11e98-232">In the same assembly as the main application assembly, create a new culture-specific folder to house the new satellite assembly.</span></span> <span data-ttu-id="11e98-233">Für kanadisches Französisch ist dies der Ordner "fr-CA".</span><span class="sxs-lookup"><span data-stu-id="11e98-233">For French-Canadian, the folder would be fr-CA.</span></span>  
  
6. <span data-ttu-id="11e98-234">Kopieren Sie die generierte Satellitenassembly in den neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="11e98-234">Copy the generated satellite assembly to the new folder.</span></span>  
  
7. <span data-ttu-id="11e98-235">Um die neue Satellitenassembly zu testen, müssen Sie die Kultur ändern, unter der Ihre Anwendung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="11e98-235">To test the new satellite assembly, you need to change the culture under which your application will run.</span></span> <span data-ttu-id="11e98-236">Dazu haben Sie zwei Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="11e98-236">You can do this in one of two ways:</span></span>  
  
    -   <span data-ttu-id="11e98-237">Ändern Sie die regionalen Einstellungen des Betriebssystems (**starten** &#124; **Systemsteuerung** &#124; **Regions- und Sprachoptionen**).</span><span class="sxs-lookup"><span data-stu-id="11e98-237">Change your operating system's regional settings (**Start** &#124; **Control Panel** &#124; **Regional and Language Options**).</span></span>  
  
    -   <span data-ttu-id="11e98-238">Fügen Sie in Ihrer Anwendung den folgenden Code in "App.xaml.cs" hinzu:</span><span class="sxs-lookup"><span data-stu-id="11e98-238">In your application, add the following code to App.xaml.cs:</span></span>  
  
   [!code-xaml[LocBamlChangeCultureSnippets#LocBamlChangeCultureMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml#locbamlchangeculturemarkup)]
   [!code-csharp[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/CSharp/App.xaml.cs#locbamlchangeculturecodebehind)]
   [!code-vb[LocBamlChangeCultureSnippets#LocBamlChangeCultureCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/LocBamlChangeCultureSnippets/VisualBasic/Application.xaml.vb#locbamlchangeculturecodebehind)]  
  
<a name="Some_Tips_for_Using_LocBaml"></a>   
## <a name="some-tips-for-using-locbaml"></a><span data-ttu-id="11e98-239">Einige Tipps zum Verwenden von LocBaml</span><span class="sxs-lookup"><span data-stu-id="11e98-239">Some Tips for Using LocBaml</span></span>  
  
-   <span data-ttu-id="11e98-240">Alle abhängigen Assemblys, die benutzerdefinierte Steuerelemente definieren, müssen in das lokale Verzeichnis von LocBaml kopiert oder im globalen Assemblycache (GAC) installiert werden.</span><span class="sxs-lookup"><span data-stu-id="11e98-240">All dependent assemblies that define custom controls must be copied into the local directory of LocBaml or installed into the GAC.</span></span> <span data-ttu-id="11e98-241">Dies ist notwendig, da die Lokalisierungs-API Zugriff auf die abhängigen Assemblys haben muss, wenn sie die [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)] liest.</span><span class="sxs-lookup"><span data-stu-id="11e98-241">This is necessary because the localization API must have access to the dependent assemblies when it reads the [!INCLUDE[TLA#tla_baml](../../../../includes/tlasharptla-baml-md.md)].</span></span>  
  
-   <span data-ttu-id="11e98-242">Wenn die Hauptassembly signiert ist, muss auch die generierte Ressourcen-DLL signiert sein, damit sie geladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e98-242">If the main assembly is signed, the generated resource DLL must also be signed in order for it to be loaded.</span></span>  
  
-   <span data-ttu-id="11e98-243">Die Version der lokalisierten Ressourcen-DLL muss mit der Hauptassembly synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="11e98-243">The version of the localized resource DLL needs to be synchronized with the main assembly.</span></span>  
  
<a name="Whats_Next"></a>   
## <a name="whats-next"></a><span data-ttu-id="11e98-244">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11e98-244">What's Next</span></span>  
 <span data-ttu-id="11e98-245">Sie wissen nun in Grundzügen, wie das LocBaml-Tool verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="11e98-245">You should now have a basic understanding of how to use the LocBaml tool.</span></span>  <span data-ttu-id="11e98-246">Sie sollten in der Lage sein, eine Datei zu erstellen, die UIDs enthält.</span><span class="sxs-lookup"><span data-stu-id="11e98-246">You should be able to make a file that contains Uids.</span></span> <span data-ttu-id="11e98-247">Mit dem LocBaml-Tool sollten Sie in der Lage sein, eine Datei zu analysieren, um den lokalisierbaren Inhalt zu extrahieren, und nach der Übersetzung des Inhalts sollten Sie eine .resources.dll-Datei generieren können, die den übersetzten Inhalt zusammenführt.</span><span class="sxs-lookup"><span data-stu-id="11e98-247">By using the LocBaml tool, you should be able to parse a file to extract the localizable content, and after the content is translated, you should be able to generate a .resources.dll file that merges the translated content.</span></span> <span data-ttu-id="11e98-248">Dieses Thema beinhaltet nicht jedes mögliche Detail, aber Sie verfügen nun über das notwendige Wissen, um LocBaml zur Lokalisierung Ihrer Anwendungen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="11e98-248">This topic does not include every possible detail, but you now have the knowledge necessary to use LocBaml for localizing your applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11e98-249">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11e98-249">See also</span></span>

- [<span data-ttu-id="11e98-250">Globalisierung für WPF</span><span class="sxs-lookup"><span data-stu-id="11e98-250">Globalization for WPF</span></span>](globalization-for-wpf.md)
- [<span data-ttu-id="11e98-251">Übersicht über die Verwendung eines automatischen Layouts</span><span class="sxs-lookup"><span data-stu-id="11e98-251">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
