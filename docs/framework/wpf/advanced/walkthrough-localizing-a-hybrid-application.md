---
title: 'Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung'
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 01530d4ae9779934948bbaff60fbbd392de6e701
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329296"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="441f2-102">Exemplarische Vorgehensweise: Lokalisieren einer Hybridanwendung</span><span class="sxs-lookup"><span data-stu-id="441f2-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="441f2-103">In dieser exemplarischen Vorgehensweise erfahren Sie, wie zum Lokalisieren von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Elemente in einem [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]--basierten hybridanwendung.</span><span class="sxs-lookup"><span data-stu-id="441f2-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="441f2-104">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="441f2-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="441f2-105">Erstellen der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Hostprojekt.</span><span class="sxs-lookup"><span data-stu-id="441f2-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

-   <span data-ttu-id="441f2-106">Lokalisierbaren Inhalt hinzufügen</span><span class="sxs-lookup"><span data-stu-id="441f2-106">Adding localizable content.</span></span>

-   <span data-ttu-id="441f2-107">Lokalisierungsfunktionalität aktivieren</span><span class="sxs-lookup"><span data-stu-id="441f2-107">Enabling localization.</span></span>

-   <span data-ttu-id="441f2-108">Ressourcenbezeichner zuweisen</span><span class="sxs-lookup"><span data-stu-id="441f2-108">Assigning resource identifiers.</span></span>

-   <span data-ttu-id="441f2-109">Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly.</span><span class="sxs-lookup"><span data-stu-id="441f2-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="441f2-110">Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Lokalisieren einer Anwendung Hybridbeispiel](https://go.microsoft.com/fwlink/?LinkID=160015).</span><span class="sxs-lookup"><span data-stu-id="441f2-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="441f2-111">Am Ende werden Sie eine lokalisierte Hybridanwendung haben.</span><span class="sxs-lookup"><span data-stu-id="441f2-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="441f2-112">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="441f2-112">Prerequisites</span></span>

<span data-ttu-id="441f2-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="441f2-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="441f2-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="441f2-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="441f2-115">Erstellen des Windows Forms-Hostprojekts</span><span class="sxs-lookup"><span data-stu-id="441f2-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="441f2-116">Der erste Schritt ist die Erstellung der [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Anwendung Projekt, und fügen eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Element mit dem Inhalt, die Sie lokalisieren werden.</span><span class="sxs-lookup"><span data-stu-id="441f2-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="441f2-117">So erstellen Sie das Hostprojekt</span><span class="sxs-lookup"><span data-stu-id="441f2-117">To create the host project</span></span>

1. <span data-ttu-id="441f2-118">Erstellen Sie eine **WPF-App** Projekt mit dem Namen `LocalizingWpfInWf`.</span><span class="sxs-lookup"><span data-stu-id="441f2-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="441f2-119">(**Datei** > **neue** > **Projekt** > **Visual C#-** oder **Visual Basic**   >  **Klassischer Desktop** > **WPF-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="441f2-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="441f2-120">Hinzufügen einer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> Element namens `SimpleControl` zum Projekt.</span><span class="sxs-lookup"><span data-stu-id="441f2-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="441f2-121">Verwenden der <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement platzieren einer `SimpleControl` Element auf dem Formular.</span><span class="sxs-lookup"><span data-stu-id="441f2-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="441f2-122">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="441f2-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="441f2-123">Hinzufügen von lokalisierbarem Inhalt</span><span class="sxs-lookup"><span data-stu-id="441f2-123">Adding Localizable Content</span></span>

<span data-ttu-id="441f2-124">Als Nächstes fügen Sie eine [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] beschriftungs-Steuerelement, und legen Sie die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt des Elements auf eine lokalisierbare Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="441f2-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="441f2-125">So fügen Sie lokalisierbaren Inhalt hinzu</span><span class="sxs-lookup"><span data-stu-id="441f2-125">To add localizable content</span></span>

1. <span data-ttu-id="441f2-126">In **Projektmappen-Explorer**, doppelklicken Sie auf **SimpleControl.xaml** zum Öffnen der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="441f2-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="441f2-127">Legen Sie den Inhalt von der <xref:System.Windows.Controls.Button> mithilfe des folgenden Codes zu steuern.</span><span class="sxs-lookup"><span data-stu-id="441f2-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="441f2-128">In **Projektmappen-Explorer**, doppelklicken Sie auf **Form1** um es im Windows Forms-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="441f2-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="441f2-129">Öffnen der **Toolbox** und doppelklicken Sie auf **Bezeichnung** auf dem Formular ein Label-Steuerelement hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="441f2-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="441f2-130">Legen Sie den Wert von dessen <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft auf `"Hello"` fest.</span><span class="sxs-lookup"><span data-stu-id="441f2-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="441f2-131">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="441f2-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="441f2-132">Sowohl die `SimpleControl` Element und das Label-Steuerelement zeigt den Text **"Hello"**.</span><span class="sxs-lookup"><span data-stu-id="441f2-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="441f2-133">Aktivieren der Lokalisierungsfunktionalität</span><span class="sxs-lookup"><span data-stu-id="441f2-133">Enabling Localization</span></span>

<span data-ttu-id="441f2-134">Windows Forms-Designer bietet Einstellungen für das Aktivieren der Lokalisierungsfunktionalität in einer Satellitenassembly.</span><span class="sxs-lookup"><span data-stu-id="441f2-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="441f2-135">So aktivieren Sie die Lokalisierungsfunktionalität</span><span class="sxs-lookup"><span data-stu-id="441f2-135">To enable localization</span></span>

1. <span data-ttu-id="441f2-136">In **Projektmappen-Explorer**, doppelklicken Sie auf **"Form1.cs"** um es im Windows Forms-Designer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="441f2-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="441f2-137">In der **Eigenschaften** legen den Wert des Formulars **Localizable** Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="441f2-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="441f2-138">In der **Eigenschaften** legen den Wert des der **Sprache** Eigenschaft **Spanisch (Spanien)**.</span><span class="sxs-lookup"><span data-stu-id="441f2-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="441f2-139">Wählen Sie im Windows Forms-Designer das Steuerelement „Label”.</span><span class="sxs-lookup"><span data-stu-id="441f2-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="441f2-140">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.Forms.Control.Text%2A> Eigenschaft `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="441f2-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="441f2-141">Dem Projekt wird eine neue Ressourcendatei mit dem Namen Form1.es-ES.resx hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="441f2-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="441f2-142">In **Projektmappen-Explorer**, mit der rechten Maustaste **"Form1.cs"** , und klicken Sie auf **Ansichtscode** um ihn im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="441f2-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="441f2-143">Kopieren Sie den folgenden Code der `Form1` Konstruktor vor dem Aufruf von `InitializeComponent`.</span><span class="sxs-lookup"><span data-stu-id="441f2-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="441f2-144">In **Projektmappen-Explorer**, mit der rechten Maustaste **LocalizingWpfInWf** , und klicken Sie auf **Projekt entladen**.</span><span class="sxs-lookup"><span data-stu-id="441f2-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="441f2-145">Der Projektname ist mit der Bezeichnung **(nicht verfügbar)**.</span><span class="sxs-lookup"><span data-stu-id="441f2-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="441f2-146">Mit der rechten Maustaste **LocalizingWpfInWf**, und klicken Sie auf **bearbeiten LocalizingWpfInWf.csproj**.</span><span class="sxs-lookup"><span data-stu-id="441f2-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="441f2-147">Die Projektdatei wird im Code-Editor angezeigt.</span><span class="sxs-lookup"><span data-stu-id="441f2-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="441f2-148">Kopieren Sie die folgende Zeile in der ersten `PropertyGroup` in der Projektdatei.</span><span class="sxs-lookup"><span data-stu-id="441f2-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="441f2-149">Speichern Sie die Projektdatei und schließen Sie sie.</span><span class="sxs-lookup"><span data-stu-id="441f2-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="441f2-150">In **Projektmappen-Explorer**, mit der rechten Maustaste **LocalizingWpfInWf** , und klicken Sie auf **Projekt erneut laden**.</span><span class="sxs-lookup"><span data-stu-id="441f2-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="441f2-151">Ressourcenbezeichner zuweisen</span><span class="sxs-lookup"><span data-stu-id="441f2-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="441f2-152">Sie können mithilfe von Ressourcenbezeichnern eine Zuordnung von lokalisierbarem Inhalt zu Ressourcenassemblys erstellen.</span><span class="sxs-lookup"><span data-stu-id="441f2-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="441f2-153">Die MsBuild.exe-Anwendung weist automatisch Ressourcenbezeichner, bei der Angabe der `updateuid` Option.</span><span class="sxs-lookup"><span data-stu-id="441f2-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="441f2-154">So weisen Sie Ressourcenbezeichner zu</span><span class="sxs-lookup"><span data-stu-id="441f2-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="441f2-155">Öffnen Sie die Developer-Eingabeaufforderung für Visual Studio, über das Startmenü.</span><span class="sxs-lookup"><span data-stu-id="441f2-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="441f2-156">Verwenden Sie den folgenden Befehl, um ihrem lokalisierbaren Inhalt Ressourcenbezeichner zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="441f2-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="441f2-157">In **Projektmappen-Explorer**, doppelklicken Sie auf **SimpleControl.xaml** um ihn im Code-Editor zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="441f2-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="441f2-158">Sie sehen, dass die `msbuild` Befehl wurde hinzugefügt, die `Uid` Attribut auf alle Elemente.</span><span class="sxs-lookup"><span data-stu-id="441f2-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="441f2-159">Dies erleichtert die Lokalisierung durch Zuweisung von Ressourcenbezeichnern.</span><span class="sxs-lookup"><span data-stu-id="441f2-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="441f2-160">Drücken Sie **F6** zum Erstellen der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="441f2-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="441f2-161">Verwenden des LocBaml-Tools zum Erzeugen einer Satellitenassembly</span><span class="sxs-lookup"><span data-stu-id="441f2-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="441f2-162">Ihr lokalisierte Inhalt befindet sich in einer reinen Ressourcen- *Satellitenassembly*.</span><span class="sxs-lookup"><span data-stu-id="441f2-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="441f2-163">Verwenden Sie das Befehlszeilentool LocBaml.exe, erstellen Sie eine lokalisierte Assembly für Ihre [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.</span><span class="sxs-lookup"><span data-stu-id="441f2-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="441f2-164">So erzeugen Sie eine Satellitenassembly</span><span class="sxs-lookup"><span data-stu-id="441f2-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="441f2-165">Kopieren Sie LocBaml.exe in den Projektordner obj\Debug.</span><span class="sxs-lookup"><span data-stu-id="441f2-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="441f2-166">Weitere Informationen finden Sie unter [Lokalisieren einer Anwendung](how-to-localize-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="441f2-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="441f2-167">Führen Sie im Eingabeaufforderungsfenster den folgenden Befehl aus, um Ressourcenzeichenfolgen in eine temporäre Datei zu extrahieren.</span><span class="sxs-lookup"><span data-stu-id="441f2-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="441f2-168">Öffnen Sie die Datei "temp.csv" mit Visual Studio oder einem anderen Texteditor ein.</span><span class="sxs-lookup"><span data-stu-id="441f2-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="441f2-169">Ersetzen Sie die Zeichenfolge `"Hello"` mit entsprechende spanische Übersetzung `"Hola"`.</span><span class="sxs-lookup"><span data-stu-id="441f2-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="441f2-170">Speichern Sie die Datei „temp.csv”.</span><span class="sxs-lookup"><span data-stu-id="441f2-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="441f2-171">Verwenden Sie den folgenden Befehl, um die lokalisierte Ressourcendatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="441f2-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="441f2-172">Die Datei „LocalizingWpfInWf.g.es-es.resources” wird im Ordner obj\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="441f2-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="441f2-173">Verwenden Sie den folgenden Befehl, um die lokalisierte Satellitenassembly zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="441f2-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="441f2-174">Die Datei „LocalizingWpfInWf.resources.dll” wird im Ordner obj\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="441f2-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="441f2-175">Kopieren Sie die Datei LocalizingWpfInWf.Resources.dll in den Projektordner nach \bin\Debug\es-ES.</span><span class="sxs-lookup"><span data-stu-id="441f2-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="441f2-176">Ersetzen Sie die vorhandene Datei.</span><span class="sxs-lookup"><span data-stu-id="441f2-176">Replace the existing file.</span></span>

8. <span data-ttu-id="441f2-177">Führen Sie die Datei „LocalizingWpfInWf.exe” aus, die sich im Projektordner unter "\bin\Debug" befindet.</span><span class="sxs-lookup"><span data-stu-id="441f2-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="441f2-178">Erstellen Sie die Anwendung nicht neu, da dies die Satellitenassembly überschreiben würde.</span><span class="sxs-lookup"><span data-stu-id="441f2-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="441f2-179">Die Anwendung zeigt nun die lokalisierten Zeichenfolgen statt der englischen Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="441f2-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="441f2-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="441f2-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="441f2-181">Lokalisieren einer Anwendung</span><span class="sxs-lookup"><span data-stu-id="441f2-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- [<span data-ttu-id="441f2-182">Exemplarische Vorgehensweise: Lokalisieren von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="441f2-182">Walkthrough: Localizing Windows Forms</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [<span data-ttu-id="441f2-183">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="441f2-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
