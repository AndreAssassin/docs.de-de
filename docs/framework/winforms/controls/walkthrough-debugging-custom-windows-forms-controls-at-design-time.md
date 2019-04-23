---
title: 'Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- debugging [Visual Studio], walkthroughs
- custom controls [Windows Forms], walkthroughs
- visual editors
- debugging [Visual Studio], Windows Forms
- custom controls [Windows Forms], debugging
- designers
- controls [Windows Forms], debugging
- walkthroughs [Windows Forms], debugging
- design-time debugging
ms.assetid: 1fd83ccd-3798-42fc-85a3-6cba99467387
ms.openlocfilehash: db6266f30c4fb62364f3c40a75a4a11ef853c1cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59325357"
---
# <a name="walkthrough-debugging-custom-windows-forms-controls-at-design-time"></a><span data-ttu-id="072fe-102">Exemplarische Vorgehensweise: Debuggen von benutzerdefinierten Windows Forms-Steuerelementen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-102">Walkthrough: Debugging Custom Windows Forms Controls at Design Time</span></span>
<span data-ttu-id="072fe-103">Wenn Sie ein benutzerdefiniertes Steuerelement erstellen, werden häufig finden Sie es erforderlich, um das Verhalten während der Entwurfszeit zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="072fe-103">When you create a custom control, you will often find it necessary to debug its design-time behavior.</span></span> <span data-ttu-id="072fe-104">Dies ist insbesondere dann, wenn Sie einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement erstellen.</span><span class="sxs-lookup"><span data-stu-id="072fe-104">This is especially true if you are authoring a custom designer for your custom control.</span></span> <span data-ttu-id="072fe-105">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Windows Forms-Steuerelement, das Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="072fe-105">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>  
  
 <span data-ttu-id="072fe-106">Sie können Ihre benutzerdefinierten Steuerelemente mithilfe von Visual Studio debuggen, ebenso wie alle anderen .NET Framework-Klassen Sie debuggen.</span><span class="sxs-lookup"><span data-stu-id="072fe-106">You can debug your custom controls using Visual Studio, just as you would debug any other .NET Framework classes.</span></span> <span data-ttu-id="072fe-107">Der Unterschied besteht darin, dass Sie eine separate Instanz von Visual Studio debuggen, die das benutzerdefinierte Steuerelement Code ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="072fe-107">The difference is that you will debug a separate instance of Visual Studio that is running your custom control's code</span></span>  
  
 <span data-ttu-id="072fe-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="072fe-108">Tasks illustrated in this walkthrough include:</span></span>  
  
-   <span data-ttu-id="072fe-109">Erstellen ein Windows Forms-Projekt, um Ihr benutzerdefiniertes Steuerelement zu hosten.</span><span class="sxs-lookup"><span data-stu-id="072fe-109">Creating a Windows Forms project to host your custom control</span></span>  
  
-   <span data-ttu-id="072fe-110">Erstellen ein Steuerelementbibliothek-Projekt</span><span class="sxs-lookup"><span data-stu-id="072fe-110">Creating a control library project</span></span>  
  
-   <span data-ttu-id="072fe-111">Hinzufügen einer Eigenschaft für Ihr benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="072fe-111">Adding a property to your custom control</span></span>  
  
-   <span data-ttu-id="072fe-112">Das benutzerdefinierte Steuerelement hinzufügen dem Formular host</span><span class="sxs-lookup"><span data-stu-id="072fe-112">Adding your custom control to the host form</span></span>  
  
-   <span data-ttu-id="072fe-113">Einrichten des Projekts für das Debuggen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-113">Setting up the project for design-time debugging</span></span>  
  
-   <span data-ttu-id="072fe-114">Debuggen von benutzerdefinierten Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-114">Debugging your custom control at design time</span></span>  
  
 <span data-ttu-id="072fe-115">Wenn Sie fertig sind, müssen Sie einen Überblick über die Aufgaben, die für das Debuggen eines benutzerdefinierten Steuerelements das Entwurfszeitverhalten erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="072fe-115">When you are finished, you will have an understanding of the tasks necessary for debugging the design-time behavior of a custom control.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="072fe-116">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="072fe-116">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="072fe-117">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="072fe-117">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="072fe-118">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="072fe-118">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
## <a name="creating-the-project"></a><span data-ttu-id="072fe-119">Erstellen des Projekts</span><span class="sxs-lookup"><span data-stu-id="072fe-119">Creating the Project</span></span>  
 <span data-ttu-id="072fe-120">Der erste Schritt ist das Anwendungsprojekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="072fe-120">The first step is to create the application project.</span></span> <span data-ttu-id="072fe-121">Sie können dieses Projekt zum Erstellen der Anwendung, die das benutzerdefinierte Steuerelement hostet.</span><span class="sxs-lookup"><span data-stu-id="072fe-121">You will use this project to build the application that hosts the custom control.</span></span>  
  
#### <a name="to-create-the-project"></a><span data-ttu-id="072fe-122">So erstellen Sie das Projekt</span><span class="sxs-lookup"><span data-stu-id="072fe-122">To create the project</span></span>  
  
-   <span data-ttu-id="072fe-123">Erstellen Sie eine Windows-Anwendungsprojekt mit dem Namen "DebuggingExample" (**Datei** > **neu** > **Projekt**  >  **Visual C#-** oder **Visual Basic** > **Klassischer Desktop** > **Windows Forms-Anwendung**).</span><span class="sxs-lookup"><span data-stu-id="072fe-123">Create a Windows Application project called "DebuggingExample" (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
## <a name="creating-a-control-library-project"></a><span data-ttu-id="072fe-124">Erstellen ein Steuerelementbibliothek-Projekt</span><span class="sxs-lookup"><span data-stu-id="072fe-124">Creating a Control Library Project</span></span>  
 <span data-ttu-id="072fe-125">Der nächste Schritt ist das Steuerelementbibliothek-Projekt erstellen, und richten Sie das benutzerdefinierte Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="072fe-125">The next step is to create the control library project and set up the custom control.</span></span>  
  
#### <a name="to-create-the-control-library-project"></a><span data-ttu-id="072fe-126">Um die Steuerelementbibliothek-Projekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="072fe-126">To create the control library project</span></span>  
  
1. <span data-ttu-id="072fe-127">Hinzufügen einer **Windows-Steuerelementbibliothek** Projekt der Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="072fe-127">Add a **Windows Control Library** project to the solution.</span></span>  
  
2. <span data-ttu-id="072fe-128">Fügen Sie einen neuen **UserControl** dem DebugControlLibrary-Projekt.</span><span class="sxs-lookup"><span data-stu-id="072fe-128">Add a new **UserControl** item to the DebugControlLibrary project.</span></span> <span data-ttu-id="072fe-129">Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen neuer Projektelemente](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="072fe-129">For details, see [How to: Add New Project Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).</span></span> <span data-ttu-id="072fe-130">Weisen Sie der neuen Quelldatei einen Basisnamen "DebugControl".</span><span class="sxs-lookup"><span data-stu-id="072fe-130">Give the new source file a base name of "DebugControl".</span></span>  
  
3. <span data-ttu-id="072fe-131">Mithilfe der **Projektmappen-Explorer**, löschen Sie das standardmäßige Steuerelement des Projekts durch Löschen der Codedatei mit dem Basisnamen der "`UserControl1`".</span><span class="sxs-lookup"><span data-stu-id="072fe-131">Using the **Solution Explorer**, delete the project's default control by deleting the code file with a base name of "`UserControl1`".</span></span> <span data-ttu-id="072fe-132">Weitere Informationen finden Sie unter [Vorgehensweise: Entfernen, löschen und Ausschließen von Elementen](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="072fe-132">For details, see [How to: Remove, Delete, and Exclude Items](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/0ebzhwsk(v=vs.100)).</span></span>  
  
4. <span data-ttu-id="072fe-133">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="072fe-133">Build the solution.</span></span>  
  
## <a name="checkpoint"></a><span data-ttu-id="072fe-134">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="072fe-134">Checkpoint</span></span>  
 <span data-ttu-id="072fe-135">Können Sie das benutzerdefinierte Steuerelement in an diesem Punkt werden die **Toolbox**.</span><span class="sxs-lookup"><span data-stu-id="072fe-135">At this point, you will be able to see your custom control in the **Toolbox**.</span></span>  
  
#### <a name="to-check-your-progress"></a><span data-ttu-id="072fe-136">Um den Status zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="072fe-136">To check your progress</span></span>  
  
-   <span data-ttu-id="072fe-137">Suchen Sie die neue Registerkarte **DebugControlLibrary Komponenten** und klicken Sie auf, um es auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="072fe-137">Find the new tab called **DebugControlLibrary Components** and click to select it.</span></span> <span data-ttu-id="072fe-138">Wenn sie geöffnet wird, sehen Sie das Steuerelement als aufgeführt **DebugControl** mit dem Standardsymbol daneben.</span><span class="sxs-lookup"><span data-stu-id="072fe-138">When it opens, you will see your control listed as **DebugControl** with the default icon beside it.</span></span>  
  
## <a name="adding-a-property-to-your-custom-control"></a><span data-ttu-id="072fe-139">Hinzufügen einer Eigenschaft für Ihr benutzerdefiniertes Steuerelement</span><span class="sxs-lookup"><span data-stu-id="072fe-139">Adding a Property to Your Custom Control</span></span>  
 <span data-ttu-id="072fe-140">Um zu veranschaulichen, dass Ihr Code des benutzerdefinierten Steuerelements zur Entwurfszeit ausgeführt wird, Sie fügen eine Eigenschaft hinzu und legen Sie einen Haltepunkt im Code, der die Eigenschaft implementiert.</span><span class="sxs-lookup"><span data-stu-id="072fe-140">To demonstrate that your custom control's code is running at design-time, you will add a property and set a breakpoint in the code that implements the property.</span></span>  
  
#### <a name="to-add-a-property-to-your-custom-control"></a><span data-ttu-id="072fe-141">Eine Eigenschaft für Ihr benutzerdefiniertes Steuerelement hinzufügen</span><span class="sxs-lookup"><span data-stu-id="072fe-141">To add a property to your custom control</span></span>  
  
1. <span data-ttu-id="072fe-142">Open **DebugControl** in die **Code-Editor**.</span><span class="sxs-lookup"><span data-stu-id="072fe-142">Open **DebugControl** in the **Code Editor**.</span></span> <span data-ttu-id="072fe-143">Fügen Sie den folgenden Code zur Klassendefinition hinzu:</span><span class="sxs-lookup"><span data-stu-id="072fe-143">Add the following code to the class definition:</span></span>  
  
    ```vb  
    Private demoStringValue As String = Nothing  
    <BrowsableAttribute(true)>  
    Public Property DemoString() As String  
  
        Get  
            Return Me.demoStringValue  
        End Get  
  
        Set(ByVal value As String)  
            Me.demoStringValue = value  
        End Set  
  
    End Property  
    ```  
  
    ```csharp  
    private string demoStringValue = null;  
    [Browsable(true)]  
    public string DemoString  
    {  
        get  
        {  
            return this.demoStringValue;  
        }  
        set  
        {  
            demoStringValue = value;  
        }  
    }  
    ```  
  
2. <span data-ttu-id="072fe-144">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="072fe-144">Build the solution.</span></span>  
  
## <a name="adding-your-custom-control-to-the-host-form"></a><span data-ttu-id="072fe-145">Das benutzerdefinierte Steuerelement hinzufügen dem Formular Host</span><span class="sxs-lookup"><span data-stu-id="072fe-145">Adding Your Custom Control to the Host Form</span></span>  
 <span data-ttu-id="072fe-146">Um das Verhalten während der Entwurfszeit des benutzerdefinierten Steuerelements zu debuggen, geben Sie eine Instanz der Klasse des benutzerdefinierten Steuerelements in einem Hostformular an.</span><span class="sxs-lookup"><span data-stu-id="072fe-146">To debug the design-time behavior of your custom control, you will place an instance of the custom control class on a host form.</span></span>  
  
#### <a name="to-add-your-custom-control-to-the-host-form"></a><span data-ttu-id="072fe-147">Das benutzerdefinierte Steuerelement dem Formular hinzu</span><span class="sxs-lookup"><span data-stu-id="072fe-147">To add your custom control to the host form</span></span>  
  
1. <span data-ttu-id="072fe-148">Öffnen Sie im Projekt "DebuggingExample" Form1 im der **Windows Forms-Designer**.</span><span class="sxs-lookup"><span data-stu-id="072fe-148">In the "DebuggingExample" project, open Form1 in the **Windows Forms Designer**.</span></span>  
  
2. <span data-ttu-id="072fe-149">In der **Toolbox**öffnen die **DebugControlLibrary Komponenten** Registerkarte, und ziehen Sie eine **DebugControl** Instanz auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="072fe-149">In the **Toolbox**, open the **DebugControlLibrary Components** tab and drag a **DebugControl** instance onto the form.</span></span>  
  
3. <span data-ttu-id="072fe-150">Suchen der `DemoString` benutzerdefinierte Eigenschaft in der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="072fe-150">Find the `DemoString` custom property in the **Properties** window.</span></span> <span data-ttu-id="072fe-151">Beachten Sie, dass Sie den Wert ändern können, wie Sie eine andere Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="072fe-151">Note that you can change its value as you would any other property.</span></span> <span data-ttu-id="072fe-152">Beachten Sie außerdem, dass bei der `DemoString` Eigenschaft ausgewählt ist, wird der Eigenschaftenwert Beschreibungszeichenfolge angezeigt wird, am unteren Rand der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="072fe-152">Also note that when the `DemoString` property is selected, the property's description string appears at the bottom of the **Properties** window.</span></span>  
  
## <a name="setting-up-the-project-for-design-time-debugging"></a><span data-ttu-id="072fe-153">Einrichten des Projekts für das Debuggen zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-153">Setting Up the Project for Design-Time Debugging</span></span>  
 <span data-ttu-id="072fe-154">Um Entwurfszeitverhalten für das benutzerdefinierte Steuerelement zu debuggen, Debuggen Sie eine separate Instanz von Visual Studio, die das benutzerdefinierte Steuerelement Code ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="072fe-154">To debug your custom control's design-time behavior, you will debug a separate instance of Visual Studio that is running your custom control's code.</span></span>  
  
#### <a name="to-set-up-the-project-for-design-time-debugging"></a><span data-ttu-id="072fe-155">Zum Einrichten des Projekts für Design-Time-Debuggen</span><span class="sxs-lookup"><span data-stu-id="072fe-155">To set up the project for design-time debugging</span></span>  
  
1. <span data-ttu-id="072fe-156">Mit der rechten Maustaste auf die **DebugControlLibrary** -Projekt in der **Projektmappen-Explorer** , und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="072fe-156">Right-click on the **DebugControlLibrary** project in the **Solution Explorer** and select **Properties**.</span></span>  
  
2. <span data-ttu-id="072fe-157">In der **DebugControlLibrary** Eigenschaftenblatt, wählen die **Debuggen** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="072fe-157">In the **DebugControlLibrary** property sheet, select the **Debug** tab.</span></span>  
  
     <span data-ttu-id="072fe-158">In der **Startaktion** wählen Sie im Abschnitt **externes Programm starten**.</span><span class="sxs-lookup"><span data-stu-id="072fe-158">In the **Start Action** section, select **Start external program**.</span></span> <span data-ttu-id="072fe-159">Sie Debuggen eine separate Instanz von Visual Studio, klicken Sie auf die Auslassungspunkte (![VisualStudioEllipsesButton-bildschirmabbildung](../media/vbellipsesbutton.png "VbEllipsesButton")) Schaltfläche, um für die Visual Studio-IDE navigieren.</span><span class="sxs-lookup"><span data-stu-id="072fe-159">You will be debugging a separate instance of Visual Studio, so click the ellipsis (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) button to browse for the Visual Studio IDE.</span></span> <span data-ttu-id="072fe-160">Der Name der ausführbaren Datei ist **devenv.exe**, und wenn Sie am Standardspeicherort installiert haben, lautet %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span><span class="sxs-lookup"><span data-stu-id="072fe-160">The name of the executable file is **devenv.exe**, and if you installed to the default location, its path is %programfiles%\Microsoft Visual Studio 9.0\Common7\IDE\devenv.exe.</span></span>  
  
3. <span data-ttu-id="072fe-161">Klicken Sie auf **OK**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="072fe-161">Click **OK** to close the dialog box.</span></span>  
  
4. <span data-ttu-id="072fe-162">Mit der rechten Maustaste die **DebugControlLibrary** Projekt, und wählen **als Startprojekt festlegen** So aktivieren Sie diese Konfiguration für Remotedebugging.</span><span class="sxs-lookup"><span data-stu-id="072fe-162">Right-click the **DebugControlLibrary** project and select **Set as StartUp Project** to enable this debugging configuration.</span></span>  
  
## <a name="debugging-your-custom-control-at-design-time"></a><span data-ttu-id="072fe-163">Debuggen von benutzerdefinierten Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-163">Debugging Your Custom Control at Design Time</span></span>  
 <span data-ttu-id="072fe-164">Jetzt können Sie Ihr benutzerdefinierte Steuerelement zu debuggen, während der Ausführung im Entwurfsmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="072fe-164">Now you are ready to debug your custom control as it runs in design mode.</span></span> <span data-ttu-id="072fe-165">Wenn Sie die Debugsitzung starten, wird eine neue Instanz von Visual Studio erstellt werden, und Sie verwenden es zum Laden der Projektmappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="072fe-165">When you start the debugging session, a new instance of Visual Studio will be created, and you will use it to load the "DebuggingExample" solution.</span></span> <span data-ttu-id="072fe-166">Wenn öffnen Sie Form1 in der **Formulardesigner**, eine Instanz des benutzerdefinierten Steuerelements erstellt werden, und die Ausführung beginnt.</span><span class="sxs-lookup"><span data-stu-id="072fe-166">When you open Form1 in the **Forms Designer**, an instance of your custom control will be created and will start running.</span></span>  
  
#### <a name="to-debug-your-custom-control-at-design-time"></a><span data-ttu-id="072fe-167">So debuggen Sie das benutzerdefinierte Steuerelement zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="072fe-167">To debug your custom control at design time</span></span>  
  
1. <span data-ttu-id="072fe-168">Öffnen der **DebugControl** Quelldatei in die **Code-Editor** und platzieren Sie einen Haltepunkt auf der `Set` Accessor die `DemoString` Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="072fe-168">Open the **DebugControl** source file in the **Code Editor** and place a breakpoint on the `Set` accessor of the `DemoString` property.</span></span>  
  
2. <span data-ttu-id="072fe-169">Drücken Sie F5, um die Debugsitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="072fe-169">Press F5 to start the debugging session.</span></span> <span data-ttu-id="072fe-170">Beachten Sie, dass eine neue Instanz von Visual Studio erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="072fe-170">Note that a new instance of Visual Studio is created.</span></span> <span data-ttu-id="072fe-171">Sie können zwischen den Instanzen auf zwei Arten unterschieden:</span><span class="sxs-lookup"><span data-stu-id="072fe-171">You can distinguish between the instances in two ways:</span></span>  
  
    -   <span data-ttu-id="072fe-172">Die Debuginstanz enthält das Wort **ausführen** auf dessen eigener Titelleiste</span><span class="sxs-lookup"><span data-stu-id="072fe-172">The debugging instance has the word **Running** in its title bar</span></span>  
  
    -   <span data-ttu-id="072fe-173">Die Debuginstanz enthält die **starten** Schaltfläche seine **Debuggen** Symbolleiste deaktiviert</span><span class="sxs-lookup"><span data-stu-id="072fe-173">The debugging instance has the **Start** button on its **Debug** toolbar disabled</span></span>  
  
     <span data-ttu-id="072fe-174">Der Haltepunkt wird in der Debuginstanz festgelegt.</span><span class="sxs-lookup"><span data-stu-id="072fe-174">Your breakpoint is set in the debugging instance.</span></span>  
  
3. <span data-ttu-id="072fe-175">Öffnen Sie in der neuen Instanz von Visual Studio die Projektmappe "DebuggingExample".</span><span class="sxs-lookup"><span data-stu-id="072fe-175">In the new instance of Visual Studio, open the "DebuggingExample" solution.</span></span> <span data-ttu-id="072fe-176">Finden Sie die Projektmappe durch Auswahl **zuletzt geöffnete Projekte** aus der **Datei** Menü.</span><span class="sxs-lookup"><span data-stu-id="072fe-176">You can easily find the solution by selecting **Recent Projects** from the **File** menu.</span></span> <span data-ttu-id="072fe-177">Die Projektmappendatei "DebuggingExample.sln" wird als die zuletzt Datei verwendete aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="072fe-177">The "DebuggingExample.sln" solution file will be listed as the most recently used file.</span></span>  
  
4. <span data-ttu-id="072fe-178">Öffnen Sie Form1 in der **Formulardesigner** , und wählen Sie die **DebugControl** Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="072fe-178">Open Form1 in the **Forms Designer** and select the **DebugControl** control.</span></span>  
  
5. <span data-ttu-id="072fe-179">Ändern Sie den Wert der `DemoString` -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="072fe-179">Change the value of the `DemoString` property.</span></span> <span data-ttu-id="072fe-180">Beachten Sie, dass Sie die Änderung zu übernehmen, die Debuginstanz von Visual Studio aktiviert und die Ausführung am Breakpoint hält.</span><span class="sxs-lookup"><span data-stu-id="072fe-180">Note that when you commit the change, the debugging instance of Visual Studio acquires focus and execution stops at your breakpoint.</span></span> <span data-ttu-id="072fe-181">Können Sie Schritt für Schritt durch den Eigenschaftenaccessor ebenso wie Ihre anderen Code würde.</span><span class="sxs-lookup"><span data-stu-id="072fe-181">You can single-step through the property accessor just as your would any other code.</span></span>  
  
6. <span data-ttu-id="072fe-182">Wenn Sie mit der Debugsitzung abgeschlossen haben, können Sie beenden, schließen die gehostete Instanz von Visual Studio oder durch Klicken auf die **Debuggen beenden** Schaltfläche in der Debuginstanz.</span><span class="sxs-lookup"><span data-stu-id="072fe-182">When you are finished with your debugging session, you can exit by dismissing the hosted instance of Visual Studio or by clicking the **Stop Debugging** button in the debugging instance.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="072fe-183">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="072fe-183">Next Steps</span></span>  
 <span data-ttu-id="072fe-184">Nun, dass Sie Ihre benutzerdefinierten Steuerelemente zur Entwurfszeit Debuggen können, gibt es viele Möglichkeiten zum Erweitern des Steuerelements-Interaktion mit Visual Studio-IDE.</span><span class="sxs-lookup"><span data-stu-id="072fe-184">Now that you can debug your custom controls at design time, there are many possibilities for expanding your control's interaction with the Visual Studio IDE.</span></span>  
  
-   <span data-ttu-id="072fe-185">Können Sie die <xref:System.ComponentModel.Component.DesignMode%2A> Eigenschaft der <xref:System.ComponentModel.Component> Klasse zum Schreiben von Code, der nur zur Entwurfszeit ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="072fe-185">You can use the <xref:System.ComponentModel.Component.DesignMode%2A> property of the <xref:System.ComponentModel.Component> class to write code that will only execute at design time.</span></span> <span data-ttu-id="072fe-186">Ausführliche Informationen finden Sie unter <xref:System.ComponentModel.Component.DesignMode%2A>.</span><span class="sxs-lookup"><span data-stu-id="072fe-186">For details, see <xref:System.ComponentModel.Component.DesignMode%2A>.</span></span>  
  
-   <span data-ttu-id="072fe-187">Es gibt mehrere Attribute können Sie auf die Eigenschaften des Steuerelements zum Bearbeiten des benutzerdefinierten Steuerelements Interaktion mit dem Designer anwenden.</span><span class="sxs-lookup"><span data-stu-id="072fe-187">There are several attributes you can apply to your control's properties to manipulate your custom control's interaction with the designer.</span></span> <span data-ttu-id="072fe-188">Sie finden diese Attribute in der <xref:System.ComponentModel?displayProperty=nameWithType> Namespace.</span><span class="sxs-lookup"><span data-stu-id="072fe-188">You can find these attributes in the <xref:System.ComponentModel?displayProperty=nameWithType> namespace.</span></span>  
  
-   <span data-ttu-id="072fe-189">Sie können einen benutzerdefinierten Designer für das benutzerdefinierte Steuerelement schreiben.</span><span class="sxs-lookup"><span data-stu-id="072fe-189">You can write a custom designer for your custom control.</span></span> <span data-ttu-id="072fe-190">Dies bietet Ihnen vollständige Kontrolle über die entwurfsumgebung, die mithilfe der erweiterbaren Designer-Infrastruktur, die von Visual Studio verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="072fe-190">This gives you complete control over the design experience using the extensible designer infrastructure exposed by Visual Studio.</span></span> <span data-ttu-id="072fe-191">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine Windows Forms-Steuerelement, das Visual Studio-Entwurfszeitfunktionen nutzt](creating-a-wf-control-design-time-features.md).</span><span class="sxs-lookup"><span data-stu-id="072fe-191">For details, see [Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features](creating-a-wf-control-design-time-features.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="072fe-192">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="072fe-192">See also</span></span>

- [<span data-ttu-id="072fe-193">Exemplarische Vorgehensweise: Erstellen eines Windows Forms-Steuerelements, das von Visual Studio-Entwurfszeitfunktionen nutzt</span><span class="sxs-lookup"><span data-stu-id="072fe-193">Walkthrough: Creating a Windows Forms Control That Takes Advantage of Visual Studio Design-Time Features</span></span>](creating-a-wf-control-design-time-features.md)
- <span data-ttu-id="072fe-194">[Vorgehensweise: Während der Entwurfszeit von Access Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="072fe-194">[How to: Access Design-Time Services](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171822(v=vs.120))</span></span>
- <span data-ttu-id="072fe-195">[Vorgehensweise: Zugriff während der Entwurfszeit-Unterstützung in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="072fe-195">[How to: Access Design-Time Support in Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171827(v=vs.120))</span></span>
