---
title: 'Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 0f3367deaaec04744a3f812d7f2d08047d7eb588
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211397"
---
# <a name="how-to-copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="bce89-102">Vorgehensweise: Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="bce89-102">How to: Copy and Paste an ElementHost Control at Design Time</span></span>

<span data-ttu-id="bce89-103">Dieses Verfahren zeigt, wie Sie ein Windows Presentation Foundation (WPF)-Steuerelement in Windows Forms in Visual Studio zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bce89-103">This procedure shows you how to copy a Windows Presentation Foundation (WPF) control on a Windows Form in Visual Studio.</span></span>

## <a name="copy-and-paste-an-elementhost-control-at-design-time"></a><span data-ttu-id="bce89-104">Kopieren und Einfügen eines ElementHost-Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="bce89-104">Copy and paste an ElementHost control at design time</span></span>

1. <span data-ttu-id="bce89-105">Fügen Sie eine neue WPF <xref:System.Windows.Controls.UserControl> zu Ihrer Windows Forms-Projekt.</span><span class="sxs-lookup"><span data-stu-id="bce89-105">Add a new WPF <xref:System.Windows.Controls.UserControl> to your Windows Forms project.</span></span> <span data-ttu-id="bce89-106">Verwenden Sie den Standardnamen, `UserControl1.xaml`, für den Steuerelementtyp.</span><span class="sxs-lookup"><span data-stu-id="bce89-106">Use the default name for the control type, `UserControl1.xaml`.</span></span> <span data-ttu-id="bce89-107">Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Erstellen von neuen WPF-Inhalts in Windows Forms zur Entwurfszeit](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span><span class="sxs-lookup"><span data-stu-id="bce89-107">For more information, see [Walkthrough: Creating New WPF Content on Windows Forms at Design Time](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).</span></span>

2. <span data-ttu-id="bce89-108">In der **Eigenschaften** legen den Wert des der <xref:System.Windows.FrameworkElement.Width%2A> und <xref:System.Windows.FrameworkElement.Height%2A> Eigenschaften `UserControl1` zu `200`.</span><span class="sxs-lookup"><span data-stu-id="bce89-108">In the **Properties** window, set the value of the <xref:System.Windows.FrameworkElement.Width%2A> and <xref:System.Windows.FrameworkElement.Height%2A> properties of `UserControl1` to `200`.</span></span>

3. <span data-ttu-id="bce89-109">Legen Sie den Wert der <xref:System.Windows.Controls.Control.Background%2A>-Eigenschaft auf `Blue` fest.</span><span class="sxs-lookup"><span data-stu-id="bce89-109">Set the value of the <xref:System.Windows.Controls.Control.Background%2A> property to `Blue`.</span></span>

4. <span data-ttu-id="bce89-110">Erstellen Sie das Projekt.</span><span class="sxs-lookup"><span data-stu-id="bce89-110">Build the project.</span></span>

5. <span data-ttu-id="bce89-111">Öffnen Sie `Form1` im Windows Forms-Designer.</span><span class="sxs-lookup"><span data-stu-id="bce89-111">Open `Form1` in the Windows Forms Designer.</span></span>

6. <span data-ttu-id="bce89-112">Von der **Toolbox**, ziehen Sie eine Instanz des `UserControl1` auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bce89-112">From the **Toolbox**, drag an instance of `UserControl1` onto the form.</span></span>

   <span data-ttu-id="bce89-113">Eine Instanz von `UserControl1` wird in einem neuen <xref:System.Windows.Forms.Integration.ElementHost>-Steuerelement namens `elementHost1` gehostet.</span><span class="sxs-lookup"><span data-stu-id="bce89-113">An instance of `UserControl1` is hosted in a new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost1`.</span></span>

7. <span data-ttu-id="bce89-114">Während `elementHost1` ausgewählt ist, drücken Sie STRG + C, um das Steuerelement in die Zwischenablage zu kopieren.</span><span class="sxs-lookup"><span data-stu-id="bce89-114">With `elementHost1` selected, press CTRL+C to copy it to the clipboard.</span></span>

8. <span data-ttu-id="bce89-115">Drücken Sie STRG + V, um die Kopie des Steuerelements auf das Formular einfügen.</span><span class="sxs-lookup"><span data-stu-id="bce89-115">Press CTRL+V to paste the copied control onto the form.</span></span>

   <span data-ttu-id="bce89-116">Ein neues <xref:System.Windows.Forms.Integration.ElementHost> Steuerelement mit dem Namen `elementHost2` wird auf dem Formular erstellt.</span><span class="sxs-lookup"><span data-stu-id="bce89-116">A new <xref:System.Windows.Forms.Integration.ElementHost> control named `elementHost2` is created on the form.</span></span>

## <a name="see-also"></a><span data-ttu-id="bce89-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bce89-117">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="bce89-118">Migration und Interoperabilität</span><span class="sxs-lookup"><span data-stu-id="bce89-118">Migration and Interoperability</span></span>](../../wpf/advanced/migration-and-interoperability.md)
- [<span data-ttu-id="bce89-119">Verwenden von WPF-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="bce89-119">Using WPF Controls</span></span>](using-wpf-controls.md)
- [<span data-ttu-id="bce89-120">Entwerfen von XAML-Code in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bce89-120">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
