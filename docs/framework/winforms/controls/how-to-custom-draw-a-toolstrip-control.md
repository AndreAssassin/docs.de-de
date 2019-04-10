---
title: 'Vorgehensweise: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: 9b3d6b9391971d4c2d012345b96c2ed64d33a998
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59311044"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="f75a8-102">Vorgehensweise: Benutzerdefiniertes Zeichnen eines ToolStrip-Steuerelements</span><span class="sxs-lookup"><span data-stu-id="f75a8-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="f75a8-103">Die <xref:System.Windows.Forms.ToolStrip>-Steuerelemente verfügen über die folgenden zugeordneten Renderingklassen (Zeichnungsklassen):</span><span class="sxs-lookup"><span data-stu-id="f75a8-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripSystemRenderer> <span data-ttu-id="f75a8-104">Stellt das Aussehen und den Stil des Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="f75a8-104">provides the appearance and style of your operating system.</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripProfessionalRenderer> <span data-ttu-id="f75a8-105">Stellt das Aussehen und den Stil von Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="f75a8-105">provides the appearance and style of Microsoft Office.</span></span>  
  
-   <xref:System.Windows.Forms.ToolStripRenderer> <span data-ttu-id="f75a8-106">ist die abstrakte Basisklasse für die beiden anderen Renderingklassen.</span><span class="sxs-lookup"><span data-stu-id="f75a8-106">is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="f75a8-107">Zum benutzerdefinierten Zeichnen (auch als Ownerdrawn bekannt) eines <xref:System.Windows.Forms.ToolStrip> können Sie eine der Renderingklassen überschreiben und einen Aspekt der Renderinglogik ändern.</span><span class="sxs-lookup"><span data-stu-id="f75a8-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="f75a8-108">In den folgenden Verfahren werden verschiedene Aspekte des benutzerdefinierten Zeichnens beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f75a8-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
### <a name="to-switch-between-the-provided-renderers"></a><span data-ttu-id="f75a8-109">So wechseln Sie zwischen den bereitgestellten Renderern</span><span class="sxs-lookup"><span data-stu-id="f75a8-109">To switch between the provided renderers</span></span>  
  
-   <span data-ttu-id="f75a8-110">Legen Sie die <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>-Eigenschaft auf den gewünschten <xref:System.Windows.Forms.ToolStripRenderMode>-Wert fest.</span><span class="sxs-lookup"><span data-stu-id="f75a8-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="f75a8-111">Mit <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> bestimmt der statische <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> den Renderer für die Anwendung.</span><span class="sxs-lookup"><span data-stu-id="f75a8-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="f75a8-112">Die anderen Werte von <xref:System.Windows.Forms.ToolStripRenderMode> lauten <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> und <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="f75a8-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
### <a name="to-change-the-microsoft-officestyle-borders-to-straight"></a><span data-ttu-id="f75a8-113">So ändern Sie die Rahmen im Stil von Microsoft Office in "gerade"</span><span class="sxs-lookup"><span data-stu-id="f75a8-113">To change the Microsoft Office–style borders to straight</span></span>  
  
-   <span data-ttu-id="f75a8-114">Überschreiben Sie <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, rufen Sie jedoch nicht die Basisklasse auf.</span><span class="sxs-lookup"><span data-stu-id="f75a8-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f75a8-115">Für <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> und <xref:System.Windows.Forms.ToolStripProfessionalRenderer> gibt es eine Version dieser Methode.</span><span class="sxs-lookup"><span data-stu-id="f75a8-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
### <a name="to-change-the-professionalcolortable"></a><span data-ttu-id="f75a8-116">So ändern Sie die ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="f75a8-116">To change the ProfessionalColorTable</span></span>  
  
-   <span data-ttu-id="f75a8-117">Überschreiben Sie <xref:System.Windows.Forms.ProfessionalColorTable>, und ändern Sie die gewünschten Farben.</span><span class="sxs-lookup"><span data-stu-id="f75a8-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As _  
    System.EventArgs) Handles Me.Load  
        Dim t As MyColorTable = New MyColorTable  
        ToolStrip1.Renderer = New ToolStripProfessionalRenderer(t)  
    End Sub  
  
    Class MyColorTable   
    Inherits ProfessionalColorTable  
  
    Public Overrides ReadOnly Property ButtonPressedGradientBegin() As Color  
        Get  
            Return Color.Red  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientMiddle() _  
    As System.Drawing.Color  
        Get  
            Return Color.Blue  
        End Get  
            End Property  
  
    Public Overrides ReadOnly Property ButtonPressedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Green  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientBegin() _  
    As Color  
        Get  
            Return Color.Yellow  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color  
        Get  
            Return Color.Orange  
        End Get  
    End Property  
  
    Public Overrides ReadOnly Property ButtonSelectedGradientEnd() _  
    As System.Drawing.Color  
        Get  
            Return Color.Violet  
        End Get  
    End Property  
    End Class  
    ```  
  
### <a name="to-change-the-rendering-for-all-toolstrip-controls-in-your-application"></a><span data-ttu-id="f75a8-118">So ändern Sie das Rendering für alle ToolStrip-Steuerelemente in Ihrer Anwendung</span><span class="sxs-lookup"><span data-stu-id="f75a8-118">To change the rendering for all ToolStrip controls in your application</span></span>  
  
1. <span data-ttu-id="f75a8-119">Verwenden Sie die <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType>-Eigenschaft, um einen der bereitgestellten Renderer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f75a8-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="f75a8-120">Verwenden Sie <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>, um einen benutzerdefinierten Renderer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f75a8-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="f75a8-121">Stellen Sie sicher, dass <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> auf den Standardwert von <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f75a8-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-the-entire-application"></a><span data-ttu-id="f75a8-122">So deaktivieren Sie die Microsoft Office-Farben für die gesamte Anwendung</span><span class="sxs-lookup"><span data-stu-id="f75a8-122">To turn off the Microsoft Office colors for the entire application</span></span>  
  
-   <span data-ttu-id="f75a8-123">Legen Sie <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> auf `false` fest.</span><span class="sxs-lookup"><span data-stu-id="f75a8-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
### <a name="to-turn-off-the-microsoft-office-colors-for-one-toolstrip-control"></a><span data-ttu-id="f75a8-124">So deaktivieren Sie die Microsoft Office-Farben für ein ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f75a8-124">To turn off the Microsoft Office colors for one ToolStrip control</span></span>  
  
-   <span data-ttu-id="f75a8-125">Verwenden Sie ähnlichen Code wie im folgenden Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="f75a8-125">Use code similar to the following code example.</span></span>  
  
    ```vb  
    Dim colorTable As ProfessionalColorTable()  
    colorTable.UseSystemColors = True  
    Dim toolStrip.Renderer As ToolStripProfessionalRenderer(colorTable)  
    ```  
  
    ```csharp  
    ProfessionalColorTable colorTable = new ProfessionalColorTable();  
    colorTable.UseSystemColors = true;  
    toolStrip.Renderer = new ToolStripProfessionalRenderer(colorTable);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f75a8-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f75a8-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="f75a8-127">Steuerelemente mit integrierter Ownerdrawing-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="f75a8-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="f75a8-128">Vorgehensweise: Erstellen und Festlegen eines benutzerdefinierten Renderers für das ToolStrip-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f75a8-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="f75a8-129">Übersicht über das ToolStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f75a8-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
