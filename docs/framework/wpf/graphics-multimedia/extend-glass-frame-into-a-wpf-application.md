---
title: Erweitern von Glasframe in eine WPF-Anwendung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- applications [WPF], extending glass frames into
- graphics [WPF], extending glass frames into applications
- extending glass frames into applications [WPF]
- glass frames [WPF], extending into applications
ms.assetid: 74388a3a-4b69-4a9d-ba1f-e107636bd660
ms.openlocfilehash: 8da1f49bf5b7d3daf6319906fb49390c008d209c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61762970"
---
# <a name="extend-glass-frame-into-a-wpf-application"></a><span data-ttu-id="ebfb7-102">Erweitern von Glasframe in eine WPF-Anwendung</span><span class="sxs-lookup"><span data-stu-id="ebfb7-102">Extend Glass Frame Into a WPF Application</span></span>

<span data-ttu-id="ebfb7-103">In diesem Thema veranschaulicht das Erweitern der [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] -Glasframe in den Clientbereich einer Windows Presentation Foundation (WPF)-Anwendung.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-103">This topic demonstrates how to extend the [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)] glass frame into the client area of a Windows Presentation Foundation (WPF) application.</span></span>

> [!NOTE]
> <span data-ttu-id="ebfb7-104">Dieses Beispiel funktioniert nur auf einem [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)]-Computer, auf dem Desktop Window Manager (DWM) mit aktiviertem Glaseffekt ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-104">This example will only work on a [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] machine running the Desktop Window Manager (DWM) with glass enabled.</span></span> [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] <span data-ttu-id="ebfb7-105">Home Basic-Edition unterstützt den transparenten Glaseffekt nicht.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-105">Home Basic edition does not support the transparent glass effect.</span></span> <span data-ttu-id="ebfb7-106">Bereiche, die in der Regel mit dem transparenten Glaseffekt in anderen Editionen von [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] gerendert werden, werden als nicht transparent gerendert.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-106">Areas that would typically render with the transparent glass effect on other editions of [!INCLUDE[TLA2#tla_winvista](../../../../includes/tla2sharptla-winvista-md.md)] are rendered opaque.</span></span>

## <a name="example"></a><span data-ttu-id="ebfb7-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebfb7-107">Example</span></span>

<span data-ttu-id="ebfb7-108">Die folgende Abbildung zeigt den in der Adressleiste von Internet Explorer 7 erweiterten Glasframe:</span><span class="sxs-lookup"><span data-stu-id="ebfb7-108">The following image illustrates the glass frame extended into the address bar of Internet Explorer 7:</span></span>

![Screenshot mit Glasframe hinter die Adressleiste IE7.](./media/extend-glass-frame-into-a-wpf-application/internet-explorer-glass-frame-extended-address-bar.png)

<span data-ttu-id="ebfb7-110">Um ein Glasframe auf einer [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]-Anwendung zu erweitern, benötige Sie Zugriff auf nicht verwaltete [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ebfb7-110">To extend the glass frame on a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application, access to unmanaged [!INCLUDE[TLA#tla_api](../../../../includes/tlasharptla-api-md.md)] is needed.</span></span> <span data-ttu-id="ebfb7-111">Das folgende Codebeispiel führt einen Plattformaufruf (Pinvoke) für die beiden [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] durch, der erforderlich ist, um den Frame in den Clientbereich zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-111">The following code example does a Platform Invoke (pinvoke) for the two [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] needed to extend the frame into the client area.</span></span> <span data-ttu-id="ebfb7-112">Jede dieser [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] werden in einer Klasse namens **NonClientRegionAPI** deklariert.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-112">Each of these [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] are declared in a class called **NonClientRegionAPI**.</span></span>

```csharp
[StructLayout(LayoutKind.Sequential)]
public struct MARGINS
{
    public int cxLeftWidth;      // width of left border that retains its size
    public int cxRightWidth;     // width of right border that retains its size
    public int cyTopHeight;      // height of top border that retains its size
    public int cyBottomHeight;   // height of bottom border that retains its size
};

[DllImport("DwmApi.dll")]
public static extern int DwmExtendFrameIntoClientArea(
    IntPtr hwnd,
    ref MARGINS pMarInset);
```

```vb
<StructLayout(LayoutKind.Sequential)>
Public Structure MARGINS
    Public cxLeftWidth As Integer ' width of left border that retains its size
    Public cxRightWidth As Integer ' width of right border that retains its size
    Public cyTopHeight As Integer ' height of top border that retains its size
    Public cyBottomHeight As Integer ' height of bottom border that retains its size
End Structure

<DllImport("DwmApi.dll")>
Public Shared Function DwmExtendFrameIntoClientArea(ByVal hwnd As IntPtr, ByRef pMarInset As MARGINS) As Integer
End Function
```

<span data-ttu-id="ebfb7-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) ist die DWM-Funktion, die den Frame in den Clientbereich erweitert.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-113">[DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) is the DWM function that extends the frame into the client area.</span></span> <span data-ttu-id="ebfb7-114">Es werden zwei Parameter benötigt; ein Fensterhandle und eine [RÄNDER](/windows/desktop/api/uxtheme/ns-uxtheme-_margins)-Struktur.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-114">It takes two parameters; a window handle and a [MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) structure.</span></span> <span data-ttu-id="ebfb7-115">[RÄNDER](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) wird verwendet, um den DWM zu zeigen, wie weit der Frame in den Clientbereich erweitert werden soll.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-115">[MARGINS](/windows/desktop/api/uxtheme/ns-uxtheme-_margins) is used to tell the DWM how much extra the frame should be extended into the client area.</span></span>

## <a name="example"></a><span data-ttu-id="ebfb7-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebfb7-116">Example</span></span>

<span data-ttu-id="ebfb7-117">Ein Fensterhandle muss abgerufen werden, damit die [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)-Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-117">To use the [DwmExtendFrameIntoClientArea](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea) function, a window handle must be obtained.</span></span> <span data-ttu-id="ebfb7-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], das das Fensterhandle aus abgerufen werden kann die <xref:System.Windows.Interop.HwndSource.Handle%2A> Eigenschaft eine <xref:System.Windows.Interop.HwndSource>.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-118">In [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], the window handle can be obtained from the <xref:System.Windows.Interop.HwndSource.Handle%2A> property of an <xref:System.Windows.Interop.HwndSource>.</span></span> <span data-ttu-id="ebfb7-119">Im folgenden Beispiel der Frame auf in den Clientbereich erweitert die <xref:System.Windows.FrameworkElement.Loaded> -Ereignis des Fensters.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-119">In the following example, the frame is extended into the client area on the <xref:System.Windows.FrameworkElement.Loaded> event of the window.</span></span>

```csharp
void OnLoaded(object sender, RoutedEventArgs e)
{
   try
   {
      // Obtain the window handle for WPF application
      IntPtr mainWindowPtr = new WindowInteropHelper(this).Handle;
      HwndSource mainWindowSrc = HwndSource.FromHwnd(mainWindowPtr);
      mainWindowSrc.CompositionTarget.BackgroundColor = Color.FromArgb(0, 0, 0, 0);

      // Get System Dpi
      System.Drawing.Graphics desktop = System.Drawing.Graphics.FromHwnd(mainWindowPtr);
      float DesktopDpiX = desktop.DpiX;
      float DesktopDpiY = desktop.DpiY;

      // Set Margins
      NonClientRegionAPI.MARGINS margins = new NonClientRegionAPI.MARGINS();

      // Extend glass frame into client area
      // Note that the default desktop Dpi is 96dpi. The  margins are
      // adjusted for the system Dpi.
      margins.cxLeftWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cxRightWidth = Convert.ToInt32(5 * (DesktopDpiX / 96));
      margins.cyTopHeight = Convert.ToInt32(((int)topBar.ActualHeight + 5) * (DesktopDpiX / 96));
      margins.cyBottomHeight = Convert.ToInt32(5 * (DesktopDpiX / 96));

      int hr = NonClientRegionAPI.DwmExtendFrameIntoClientArea(mainWindowSrc.Handle, ref margins);
      //
      if (hr < 0)
      {
         //DwmExtendFrameIntoClientArea Failed
      }
   }
   // If not Vista, paint background white.
   catch (DllNotFoundException)
   {
      Application.Current.MainWindow.Background = Brushes.White;
   }
}
```

## <a name="example"></a><span data-ttu-id="ebfb7-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ebfb7-120">Example</span></span>

<span data-ttu-id="ebfb7-121">Das folgende Beispiel zeigt ein einfaches Fenster, in dem der Frame in den Clientbereich erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-121">The following example shows a simple window in which the frame is extended into the client area.</span></span> <span data-ttu-id="ebfb7-122">Der Frame wird hinter dem oberen Rand, der die beiden enthält erweitert <xref:System.Windows.Controls.TextBox> Objekte.</span><span class="sxs-lookup"><span data-stu-id="ebfb7-122">The frame is extended behind the top border that contains the two <xref:System.Windows.Controls.TextBox> objects.</span></span>

```xaml
<Window x:Class="SDKSample.Window1"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    Title="Extended Glass in WPF" Height="300" Width="400"
    Loaded="OnLoaded" Background="Transparent"
    >
  <Grid ShowGridLines="True">
    <DockPanel Name="mainDock">
      <!-- The border is used to compute the rendered height with margins.
           topBar contents will be displayed on the extended glass frame.-->
      <Border Name="topBar" DockPanel.Dock="Top" >
        <Grid Name="grid">
          <Grid.ColumnDefinitions>
            <ColumnDefinition MinWidth="100" Width="*"/>
            <ColumnDefinition Width="Auto"/>
          </Grid.ColumnDefinitions>
          <TextBox Grid.Column="0" MinWidth="100" Margin="0,0,10,5">Path</TextBox>
          <TextBox Grid.Column="1" MinWidth="75" Margin="0,0,0,5">Search</TextBox>
        </Grid>
      </Border>
      <Grid DockPanel.Dock="Top" >
        <Grid.ColumnDefinitions>
          <ColumnDefinition/>
        </Grid.ColumnDefinitions>
        <TextBox Grid.Column="0" AcceptsReturn="True"/>
      </Grid>
    </DockPanel>
  </Grid>
</Window>
```

<span data-ttu-id="ebfb7-123">Die folgende Abbildung zeigt die in erweiterten Glasframe eine [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] Anwendung:</span><span class="sxs-lookup"><span data-stu-id="ebfb7-123">The following image illustrates the glass frame extended into a [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)] application:</span></span>

![Screenshot der eine in einer WPF-Anwendung erweiterter Glasframe.](./media/extend-glass-frame-into-a-wpf-application/glass-frame-extended-wpf-application.png)

## <a name="see-also"></a><span data-ttu-id="ebfb7-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ebfb7-125">See also</span></span>

- [<span data-ttu-id="ebfb7-126">Übersicht über Desktop Window Manager</span><span class="sxs-lookup"><span data-stu-id="ebfb7-126">Desktop Window Manager Overview</span></span>](/windows/desktop/dwm/dwm-overview)
- [<span data-ttu-id="ebfb7-127">Desktop Window Manager Blur-Übersicht</span><span class="sxs-lookup"><span data-stu-id="ebfb7-127">Desktop Window Manager Blur Overview</span></span>](/windows/desktop/dwm/blur-ovw)
- [<span data-ttu-id="ebfb7-128">DwmExtendFrameIntoClientArea</span><span class="sxs-lookup"><span data-stu-id="ebfb7-128">DwmExtendFrameIntoClientArea</span></span>](/windows/desktop/api/dwmapi/nf-dwmapi-dwmextendframeintoclientarea)
