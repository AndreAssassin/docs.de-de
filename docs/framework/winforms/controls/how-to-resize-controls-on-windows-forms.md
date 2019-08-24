---
title: 'Vorgehensweise: Ändern der Größe von Steuerelementen in Windows Forms'
ms.date: 03/30/2017
f1_keywords:
- Size.Height
- Size.Width
helpviewer_keywords:
- controls [Windows Forms], resizing
- size [Windows Forms], controls
- Windows Forms controls, size
ms.assetid: d2dba441-a8c0-4705-b8e8-2e5d86d6e7ec
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 7e659bf02ea079afc10561e1d83f7ab7cef29a2e
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/23/2019
ms.locfileid: "69987053"
---
# <a name="how-to-resize-controls-on-windows-forms"></a><span data-ttu-id="fee1a-102">Vorgehensweise: Ändern der Größe von Steuerelementen auf Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fee1a-102">How to: Resize controls on Windows Forms</span></span>

<span data-ttu-id="fee1a-103">Sie können die Größe einzelner Steuerelemente ändern, und Sie können die Größe mehrerer Steuerelemente derselben oder einer anderen Art ändern <xref:System.Windows.Forms.Button> , <xref:System.Windows.Forms.GroupBox> z. b.-und-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="fee1a-103">You can resize individual controls, and you can resize multiple controls of the same or different kind, such as <xref:System.Windows.Forms.Button> and <xref:System.Windows.Forms.GroupBox> controls.</span></span>

## <a name="to-resize-a-control"></a><span data-ttu-id="fee1a-104">So ändern Sie die Größe eines Steuer Elements</span><span class="sxs-lookup"><span data-stu-id="fee1a-104">To resize a control</span></span>

<span data-ttu-id="fee1a-105">Wählen Sie in Visual Studio das Steuerelement aus, dessen Größe Sie ändern möchten, und ziehen Sie eines der acht Zieh Punkte.</span><span class="sxs-lookup"><span data-stu-id="fee1a-105">In Visual Studio, select the control to be resized and drag one of the eight sizing handles.</span></span>

> [!NOTE]
> <span data-ttu-id="fee1a-106">Wählen Sie das Steuerelement aus, und drücken Sie die **Pfeil** Tasten, während Sie die **UMSCHALT** Taste gedrückt halten, um die Größe des Steuer Elements jeweils ein Pixel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fee1a-106">Select the control and press the **arrow** keys while holding down the **Shift** key to resize the control one pixel at a time.</span></span> <span data-ttu-id="fee1a-107">Drücken **Sie die nach-unten** -oder nach- **Rechts** -Taste, und halten Sie die **UMSCHALT** Taste gedrückt, um die Größe des Steuer Elements in großen Schritten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="fee1a-107">Press the **down arrow** or **right arrow** keys while holding down the **Shift** and **Ctrl** keys to resize the control in large increments.</span></span>

## <a name="to-resize-multiple-controls-on-a-form"></a><span data-ttu-id="fee1a-108">So ändern Sie die Größe mehrerer Steuerelemente in einem Formular</span><span class="sxs-lookup"><span data-stu-id="fee1a-108">To resize multiple controls on a form</span></span>

1. <span data-ttu-id="fee1a-109">Halten Sie in Visual Studio die **STRG** -oder **UMSCHALT** Taste gedrückt, und wählen Sie die Steuerelemente aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="fee1a-109">In Visual Studio, hold down the **Ctrl** or **Shift** key and select the controls you want to resize.</span></span> <span data-ttu-id="fee1a-110">Die Größe des ersten Steuer Elements, das Sie auswählen, wird für die anderen Steuerelemente verwendet.</span><span class="sxs-lookup"><span data-stu-id="fee1a-110">The size of the first control you select is used for the other controls.</span></span>

2. <span data-ttu-id="fee1a-111">Wählen Sie im Menü **Format** die Option **Größe angleichen**, und wählen Sie eine der vier Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="fee1a-111">On the **Format** menu, choose **Make Same Size**, and select one of the four options.</span></span> <span data-ttu-id="fee1a-112">Die ersten drei Befehle ändern die Dimensionen der Steuerelemente so, dass Sie dem ersten ausgewählten Steuerelement entsprechen.</span><span class="sxs-lookup"><span data-stu-id="fee1a-112">The first three commands change the dimensions of the controls to match the first-selected control.</span></span>

## <a name="see-also"></a><span data-ttu-id="fee1a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fee1a-113">See also</span></span>

- [<span data-ttu-id="fee1a-114">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="fee1a-114">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="fee1a-115">Beschriften einzelner Steuerelemente für Windows Forms und Konfigurieren von Shortcuts für diese Elemente</span><span class="sxs-lookup"><span data-stu-id="fee1a-115">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="fee1a-116">Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="fee1a-116">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="fee1a-117">Windows Forms-Steuerelemente nach Funktion</span><span class="sxs-lookup"><span data-stu-id="fee1a-117">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
- <span data-ttu-id="fee1a-118">[Vorgehensweise: Ändern der Größe Windows Forms mithilfe des Designers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="fee1a-118">[How to: Resize Windows Forms Using the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/37k2zkwx(v=vs.100))</span></span>
