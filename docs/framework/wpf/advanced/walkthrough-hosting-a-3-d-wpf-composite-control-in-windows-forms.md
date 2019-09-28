---
title: 'Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms'
ms.date: 08/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hosting WPF content in Windows Forms [WPF]
- composite controls [WPF], hosting WPF in
ms.assetid: 486369a9-606a-4a3b-b086-a06f2119c7b0
ms.openlocfilehash: a35f2b4062edb18914c55046a69dcd9b8825d778
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71353842"
---
# <a name="walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms"></a><span data-ttu-id="e1690-102">Exemplarische Vorgehensweise: Hosten eines zusammengesetzten 3D-WPF-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1690-102">Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms</span></span>

<span data-ttu-id="e1690-103">Diese exemplarische Vorgehensweise veranschaulicht, wie Sie ein zusammengesetztes [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Steuerelement erstellen und es in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-Steuerelementen und-Formularen mit dem <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement hosten.</span><span class="sxs-lookup"><span data-stu-id="e1690-103">This walkthrough demonstrates how you can create a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] composite control and host it in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] controls and forms by using the <xref:System.Windows.Forms.Integration.ElementHost> control.</span></span>

<span data-ttu-id="e1690-104">In dieser exemplarischen Vorgehensweise implementieren Sie einen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-<xref:System.Windows.Controls.UserControl>, der zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="e1690-104">In this walkthrough, you will implement a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> that contains two child controls.</span></span> <span data-ttu-id="e1690-105">Der <xref:System.Windows.Controls.UserControl> zeigt einen dreidimensionalen (3D-) Kegel an.</span><span class="sxs-lookup"><span data-stu-id="e1690-105">The <xref:System.Windows.Controls.UserControl> displays a three-dimensional (3-D) cone.</span></span> <span data-ttu-id="e1690-106">Das Rendern von 3D-Objekten ist mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] wesentlich einfacher als bei [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1690-106">Rendering 3-D objects is much easier with the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] than with [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span> <span data-ttu-id="e1690-107">Daher ist es sinnvoll, eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-<xref:System.Windows.Controls.UserControl>-Klasse zu hosten, um 3D-Grafiken in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1690-107">Therefore, it makes sense to host a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl> class to create 3-D graphics in [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)].</span></span>

<span data-ttu-id="e1690-108">In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="e1690-108">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="e1690-109">Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-<xref:System.Windows.Controls.UserControl> wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1690-109">Creating the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

- <span data-ttu-id="e1690-110">Das Windows Forms Host Projekt wird erstellt.</span><span class="sxs-lookup"><span data-stu-id="e1690-110">Creating the Windows Forms host project.</span></span>

- <span data-ttu-id="e1690-111">Das Hosting des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-<xref:System.Windows.Controls.UserControl>.</span><span class="sxs-lookup"><span data-stu-id="e1690-111">Hosting the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Controls.UserControl>.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e1690-112">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="e1690-112">Prerequisites</span></span>

<span data-ttu-id="e1690-113">Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="e1690-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="e1690-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="e1690-114">Visual Studio 2017</span></span>

<a name="To_Create_the_UserControl"></a>
## <a name="create-the-usercontrol"></a><span data-ttu-id="e1690-115">Erstellen des UserControl-Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="e1690-115">Create the UserControl</span></span>

1. <span data-ttu-id="e1690-116">Erstellen Sie ein **WPF-Benutzer Steuer** Element-Bibliotheksprojekt mit dem Namen `HostingWpfUserControlInWf`.</span><span class="sxs-lookup"><span data-stu-id="e1690-116">Create a **WPF User Control Library** project named `HostingWpfUserControlInWf`.</span></span>

2. <span data-ttu-id="e1690-117">Öffnen Sie UserControl1. XAML in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e1690-117">Open UserControl1.xaml in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

3. <span data-ttu-id="e1690-118">Ersetzen Sie den generierten Code durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="e1690-118">Replace the generated code with the following code:</span></span>

     [!code-xaml[HostingWpfUserControlInWf#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/HostingWpfUserControlInWf/ConeControl.xaml#1)]

     <span data-ttu-id="e1690-119">Mit diesem Code wird ein <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> definiert, das zwei untergeordnete Steuerelemente enthält.</span><span class="sxs-lookup"><span data-stu-id="e1690-119">This code defines a <xref:System.Windows.Controls.UserControl?displayProperty=nameWithType> that contains two child controls.</span></span> <span data-ttu-id="e1690-120">Das erste untergeordnete Steuerelement ist ein <xref:System.Windows.Controls.Label?displayProperty=nameWithType>-Steuerelement. bei der zweiten handelt es sich um ein <xref:System.Windows.Controls.Viewport3D>-Steuerelement, das einen 3D-Kegel anzeigt.</span><span class="sxs-lookup"><span data-stu-id="e1690-120">The first child control is a <xref:System.Windows.Controls.Label?displayProperty=nameWithType> control; the second is a <xref:System.Windows.Controls.Viewport3D> control that displays a 3-D cone.</span></span>

<a name="To_Create_the_Windows_Forms_Host_Project"></a>
## <a name="create-the-host-project"></a><span data-ttu-id="e1690-121">Erstellen des Host Projekts</span><span class="sxs-lookup"><span data-stu-id="e1690-121">Create the host project</span></span>

1. <span data-ttu-id="e1690-122">Fügen Sie der Projekt Mappe ein **Windows Forms App-Projekt (.NET Framework)** mit dem Namen `WpfUserControlHost` hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1690-122">Add a **Windows Forms App (.NET Framework)** project named `WpfUserControlHost` to the solution.</span></span>

2. <span data-ttu-id="e1690-123">Fügen Sie in **Projektmappen-Explorer**einen Verweis auf die WindowsFormsIntegration-Assembly mit dem Namen "WindowsFormsIntegration. dll" hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1690-123">In **Solution Explorer**, add a reference to the WindowsFormsIntegration assembly, which is named WindowsFormsIntegration.dll.</span></span>

3. <span data-ttu-id="e1690-124">Fügen Sie Verweise auf die folgenden [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Assemblys hinzu:</span><span class="sxs-lookup"><span data-stu-id="e1690-124">Add references to the following [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] assemblies:</span></span>

    - <span data-ttu-id="e1690-125">PresentationCore</span><span class="sxs-lookup"><span data-stu-id="e1690-125">PresentationCore</span></span>

    - <span data-ttu-id="e1690-126">PresentationFramework</span><span class="sxs-lookup"><span data-stu-id="e1690-126">PresentationFramework</span></span>

    - <span data-ttu-id="e1690-127">WindowsBase</span><span class="sxs-lookup"><span data-stu-id="e1690-127">WindowsBase</span></span>

4. <span data-ttu-id="e1690-128">Fügen einen Verweis auf das `HostingWpfUserControlInWf`-Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1690-128">Add a reference to the `HostingWpfUserControlInWf` project.</span></span>

5. <span data-ttu-id="e1690-129">Legen Sie in Projektmappen-Explorer das Projekt `WpfUserControlHost` als Startprojekt fest.</span><span class="sxs-lookup"><span data-stu-id="e1690-129">In Solution Explorer, set the `WpfUserControlHost` project to be the startup project.</span></span>

<a name="To_Host_the_Windows_Presentation_Foundation"></a>
## <a name="host-the-usercontrol"></a><span data-ttu-id="e1690-130">Hosten von UserControl</span><span class="sxs-lookup"><span data-stu-id="e1690-130">Host the UserControl</span></span>

1. <span data-ttu-id="e1690-131">Öffnen Sie in der Windows Forms-Designer Form1.</span><span class="sxs-lookup"><span data-stu-id="e1690-131">In the Windows Forms Designer, open Form1.</span></span>

2. <span data-ttu-id="e1690-132">Klicken Sie im Eigenschaftenfenster auf **Ereignisse**, und doppelklicken Sie dann auf das Ereignis <xref:System.Windows.Forms.Form.Load>, um einen Ereignishandler zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e1690-132">In the Properties window, click **Events**, and then double-click the <xref:System.Windows.Forms.Form.Load> event to create an event handler.</span></span>

     <span data-ttu-id="e1690-133">Der Code-Editor wird mit dem neu generierten `Form1_Load`-Ereignishandler geöffnet.</span><span class="sxs-lookup"><span data-stu-id="e1690-133">The Code Editor opens to the newly generated `Form1_Load` event handler.</span></span>

3. <span data-ttu-id="e1690-134">Ersetzen Sie den Code in Form1.cs durch den folgenden Code.</span><span class="sxs-lookup"><span data-stu-id="e1690-134">Replace the code in Form1.cs with the following code.</span></span>

     <span data-ttu-id="e1690-135">Der `Form1_Load`-Ereignishandler erstellt eine Instanz von `UserControl1` und fügt die Auflistung der untergeordneten Steuerelemente des <xref:System.Windows.Forms.Integration.ElementHost>-Steuer Elements hinzu.</span><span class="sxs-lookup"><span data-stu-id="e1690-135">The `Form1_Load` event handler creates an instance of `UserControl1` and adds itto the <xref:System.Windows.Forms.Integration.ElementHost> control's collection of child controls.</span></span> <span data-ttu-id="e1690-136">Das <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement wird der Auflistung von untergeordneten Steuerelementen des Formulars hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="e1690-136">The <xref:System.Windows.Forms.Integration.ElementHost> control is added to the form's collection of child controls.</span></span>

     [!code-csharp[HostingWpfUserControlInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HostingWpfUserControlInWf/CSharp/WpfUserControlHost/Form1.cs#10)]
     [!code-vb[HostingWpfUserControlInWf#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HostingWpfUserControlInWf/VisualBasic/WpfUserControlHost/Form1.vb#10)]

4. <span data-ttu-id="e1690-137">Drücken Sie **F5**, um die Anwendung zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="e1690-137">Press **F5** to build and run the application.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1690-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1690-138">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="e1690-139">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e1690-139">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
- [<span data-ttu-id="e1690-140">Exemplarische Vorgehensweise: Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e1690-140">Walkthrough: Hosting a WPF Composite Control in Windows Forms</span></span>](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
- [<span data-ttu-id="e1690-141">Exemplarische Vorgehensweise: Hosting eines Windows Forms zusammengesetzten Steuer Elements in WPF</span><span class="sxs-lookup"><span data-stu-id="e1690-141">Walkthrough: Hosting a Windows Forms Composite Control in WPF</span></span>](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [<span data-ttu-id="e1690-142">Hosting eines zusammengesetzten WPF-Steuer Elements in Windows Forms Beispiel</span><span class="sxs-lookup"><span data-stu-id="e1690-142">Hosting a WPF Composite Control in Windows Forms Sample</span></span>](https://go.microsoft.com/fwlink/?LinkID=160001)
