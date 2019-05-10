---
title: 'Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- background colors [Windows Forms], Windows Forms Panel controls
- background images [Windows Forms], Windows Forms Panel controls
- Panel control [Windows Forms], background
- colors [Windows Forms], Windows Forms Panel controls
ms.assetid: db83cf54-3c69-4b08-ac6c-25b9b5abb1b0
ms.openlocfilehash: 6927a7118c43ced03623a9764a3ef1e0814c95cb
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211640"
---
# <a name="how-to-set-the-background-of-a-windows-forms-panel-using-the-designer"></a><span data-ttu-id="21e96-102">Vorgehensweise: Festlegen des Hintergrunds eines Windows Forms-Bereichs, der mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="21e96-102">How to: Set the background of a Windows Forms panel using the Designer</span></span>

<span data-ttu-id="21e96-103">Ein Windows Forms <xref:System.Windows.Forms.Panel> Steuerelement kann sowohl eine Hintergrundfarbe und ein Bild als Hintergrund anzeigen.</span><span class="sxs-lookup"><span data-stu-id="21e96-103">A Windows Forms <xref:System.Windows.Forms.Panel> control can display both a background color and a background image.</span></span> <span data-ttu-id="21e96-104">Die <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft legt die Hintergrundfarbe für Steuerelemente, die in den Bereich, z. B. Bezeichnungen enthalten sind, und Optionsfelder fest.</span><span class="sxs-lookup"><span data-stu-id="21e96-104">The <xref:System.Windows.Forms.Control.BackColor%2A> property sets the background color for controls that are contained in the panel, such as labels and radio buttons.</span></span> <span data-ttu-id="21e96-105">Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft nicht festgelegt ist, die <xref:System.Windows.Forms.Control.BackColor%2A> Auswahl werden alle im Bereich ausfüllen.</span><span class="sxs-lookup"><span data-stu-id="21e96-105">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is not set, the <xref:System.Windows.Forms.Control.BackColor%2A> selection will fill all of the panel.</span></span> <span data-ttu-id="21e96-106">Wenn die <xref:System.Windows.Forms.Control.BackgroundImage%2A> -Eigenschaft festgelegt ist, erscheint das Bild hinter den Steuerelementen, die im Bereich enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="21e96-106">If the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property is set, the image will be displayed behind the controls that are contained in the panel.</span></span>

<span data-ttu-id="21e96-107">Das folgende Verfahren benötigt eine **Windows-Anwendung** -Projekt mit einem Formular, enthält eine <xref:System.Windows.Forms.Panel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="21e96-107">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.Panel> control.</span></span> <span data-ttu-id="21e96-108">Informationen zum Festlegen eines solchen Projekts in Visual Studio finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="21e96-108">For information about how to set up such a project in Visual Studio, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="set-the-background-in-the-windows-forms-designer"></a><span data-ttu-id="21e96-109">Festlegen des Hintergrunds im Windows Forms-Designer</span><span class="sxs-lookup"><span data-stu-id="21e96-109">Set the background in the Windows Forms Designer</span></span>

1. <span data-ttu-id="21e96-110">Öffnen Sie das Projekt in Visual Studio, und wählen Sie die <xref:System.Windows.Forms.Panel> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="21e96-110">Open the project in Visual Studio and select the <xref:System.Windows.Forms.Panel> control.</span></span>

2. <span data-ttu-id="21e96-111">In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackColor%2A> Eigenschaft, um ein Fenster mit drei Registerkarten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="21e96-111">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackColor%2A> property to display a window with three tabs.</span></span>

3. <span data-ttu-id="21e96-112">Wählen Sie die **benutzerdefinierte** Tab, um ein Farben-Palette anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="21e96-112">Select the **Custom** tab to display a palette of colors.</span></span>

4. <span data-ttu-id="21e96-113">Wählen Sie die **Web** oder **System** Registerkarte, um eine Liste der vordefinierten Namen für Farben anzuzeigen, und klicken Sie dann eine andere Farbe auswählen.</span><span class="sxs-lookup"><span data-stu-id="21e96-113">Select the **Web** or **System** tab to display a list of predefined names for colors, and then select a color.</span></span>

5. <span data-ttu-id="21e96-114">In der **Eigenschaften** Fenster, klicken Sie auf der Pfeil-Schaltfläche neben dem <xref:System.Windows.Forms.Control.BackgroundImage%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="21e96-114">In the **Properties** window, click the arrow button next to the <xref:System.Windows.Forms.Control.BackgroundImage%2A> property.</span></span>

6. <span data-ttu-id="21e96-115">In der **öffnen** Dialogfeld Feld, wählen Sie die Datei, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="21e96-115">In the **Open** dialog box, select the file that you want to display.</span></span>

## <a name="see-also"></a><span data-ttu-id="21e96-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21e96-116">See also</span></span>

- <xref:System.Windows.Forms.Control.BackColor%2A>
- <xref:System.Windows.Forms.Control.BackgroundImage%2A>
- [<span data-ttu-id="21e96-117">Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="21e96-117">Panel Control</span></span>](panel-control-windows-forms.md)
- [<span data-ttu-id="21e96-118">Übersicht über das Panel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="21e96-118">Panel Control Overview</span></span>](panel-control-overview-windows-forms.md)
- [<span data-ttu-id="21e96-119">Vorgehensweise: Gruppieren von Steuerelementen mit dem Panel-Steuerelement in Windows Forms mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="21e96-119">How to: Group Controls with the Windows Forms Panel Control Using the Designer</span></span>](group-controls-with-wf-panel-control-using-the-designer.md)
