---
title: Layout in Windows Forms-Steuerelementen
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- sizing [Windows Forms], automatic [Windows Forms]
- Margin property [Windows Forms]
- Padding property [Windows Forms]
ms.assetid: 99400e3a-720e-4f56-b68f-89df911a251c
ms.openlocfilehash: d1a3954c8eda87bdda9fa17df1bd2b3858c43619
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012827"
---
# <a name="layout-in-windows-forms-controls"></a><span data-ttu-id="84e89-102">Layout in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="84e89-102">Layout in Windows Forms Controls</span></span>

<span data-ttu-id="84e89-103">Die präzise Platzierung von Steuerelementen auf dem Formular hat für viele Anwendungen einen hohen Stellenwert.</span><span class="sxs-lookup"><span data-stu-id="84e89-103">Precise placement of controls on your form is a high priority for many applications.</span></span> <span data-ttu-id="84e89-104">Die <xref:System.Windows.Forms?displayProperty=nameWithType> Namespace bietet Ihnen viele Layouttools, um dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="84e89-104">The <xref:System.Windows.Forms?displayProperty=nameWithType> namespace gives you many layout tools to accomplish this.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="84e89-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="84e89-105">In This Section</span></span>

<span data-ttu-id="84e89-106">[Übersicht über die AutoSize-Eigenschaft](autosize-property-overview.md)\\</span><span class="sxs-lookup"><span data-stu-id="84e89-106">[AutoSize Property Overview](autosize-property-overview.md)\\</span></span>
<span data-ttu-id="84e89-107">Beschreibt die <xref:System.Windows.Forms.Control.AutoSize%2A> -Eigenschaft und die Rolle im Layout.</span><span class="sxs-lookup"><span data-stu-id="84e89-107">Describes the <xref:System.Windows.Forms.Control.AutoSize%2A> property and its role in layout.</span></span>

<span data-ttu-id="84e89-108">[Rand und Abstand in Windows Forms-Steuerelementen](margin-and-padding-in-windows-forms-controls.md)\\</span><span class="sxs-lookup"><span data-stu-id="84e89-108">[Margin and Padding in Windows Forms Controls](margin-and-padding-in-windows-forms-controls.md)\\</span></span>
<span data-ttu-id="84e89-109">Beschreibt die <xref:System.Windows.Forms.Control.Margin%2A> und <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaften und ihre Aufgaben im Layout.</span><span class="sxs-lookup"><span data-stu-id="84e89-109">Describes the <xref:System.Windows.Forms.Control.Margin%2A> and <xref:System.Windows.Forms.Control.Padding%2A> properties and their roles in layout.</span></span>

<span data-ttu-id="84e89-110">[Vorgehensweise: Ausrichten eines Steuerelements an Formularrändern](how-to-align-a-control-to-the-edges-of-forms.md)\\</span><span class="sxs-lookup"><span data-stu-id="84e89-110">[How to: Align a Control to the Edges of Forms](how-to-align-a-control-to-the-edges-of-forms.md)\\</span></span>
<span data-ttu-id="84e89-111">Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Dock%2A> Eigenschaft, um das Steuerelement an den Rand des Formulars auszurichten, es belegt.</span><span class="sxs-lookup"><span data-stu-id="84e89-111">Demonstrates how to use the <xref:System.Windows.Forms.Control.Dock%2A> property to align your control to the edge of the form it occupies.</span></span>

<span data-ttu-id="84e89-112">[Vorgehensweise: Erstellen eines Rahmens um ein Windows Forms Steuerelement mithilfe von Abständen](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span><span class="sxs-lookup"><span data-stu-id="84e89-112">[How to: Create a Border Around a Windows Forms Control Using Padding](how-to-create-a-border-around-a-windows-forms-control-using-padding.md)\\</span></span>
<span data-ttu-id="84e89-113">Veranschaulicht, wie die <xref:System.Windows.Forms.Control.Padding%2A> Eigenschaft, um ein Steuerelement zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="84e89-113">Demonstrates how to use the <xref:System.Windows.Forms.Control.Padding%2A> property to outline a control.</span></span>

<span data-ttu-id="84e89-114">[Vorgehensweise: Implementieren eines benutzerdefinierten Layoutmoduls](how-to-implement-a-custom-layout-engine.md)\\</span><span class="sxs-lookup"><span data-stu-id="84e89-114">[How to: Implement a Custom Layout Engine](how-to-implement-a-custom-layout-engine.md)\\</span></span>
<span data-ttu-id="84e89-115">Veranschaulicht das Implementieren einer <xref:System.Windows.Forms.Layout.LayoutEngine> zum Anordnen von Windows Forms-Steuerelementen.</span><span class="sxs-lookup"><span data-stu-id="84e89-115">Demonstrates how to implement a <xref:System.Windows.Forms.Layout.LayoutEngine> for arranging Windows Forms controls.</span></span>

## <a name="reference"></a><span data-ttu-id="84e89-116">Referenz</span><span class="sxs-lookup"><span data-stu-id="84e89-116">Reference</span></span>

<xref:System.Windows.Forms.TableLayoutPanel>\
<span data-ttu-id="84e89-117">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.TableLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="84e89-117">Provides reference documentation for the <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span>

<xref:System.Windows.Forms.FlowLayoutPanel>\
<span data-ttu-id="84e89-118">Enthält die Referenzdokumentation für das <xref:System.Windows.Forms.FlowLayoutPanel>-Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="84e89-118">Provides reference documentation for the <xref:System.Windows.Forms.FlowLayoutPanel> control.</span></span>

## <a name="see-also"></a><span data-ttu-id="84e89-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="84e89-119">See also</span></span>

- [<span data-ttu-id="84e89-120">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem FlowLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84e89-120">How to: Anchor and Dock Child Controls in a FlowLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-flowlayoutpanel-control.md)
- [<span data-ttu-id="84e89-121">Vorgehensweise: Verankern und Andocken von untergeordneten Steuerelementen in einem TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84e89-121">How to: Anchor and Dock Child Controls in a TableLayoutPanel Control</span></span>](how-to-anchor-and-dock-child-controls-in-a-tablelayoutpanel-control.md)
- [<span data-ttu-id="84e89-122">Vorgehensweise: Entwerfen eines Windows Forms-Layouts, das zur Lokalisierung gut geeignet ist</span><span class="sxs-lookup"><span data-stu-id="84e89-122">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>](how-to-design-a-windows-forms-layout-that-responds-well-to-localization.md)
- [<span data-ttu-id="84e89-123">Das AutoSize-Verhalten im TableLayoutPanel-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="84e89-123">AutoSize Behavior in the TableLayoutPanel Control</span></span>](autosize-behavior-in-the-tablelayoutpanel-control.md)
