---
title: Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], basic features
- columns [Windows Forms], DataGridView control
- data grids [Windows Forms], examples
- DataGridView control [Windows Forms], examples
ms.assetid: 78085f26-d5d2-4b75-813e-e932b72fd06f
ms.openlocfilehash: 4c755d5f0c2e134b83beb27ebbd06080bad620b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59115231"
---
# <a name="basic-column-row-and-cell-features-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="2b181-102">Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-102">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2b181-103">Viele grundlegende Verhaltensweisen von `DataGridView` Zellen, Zeilen und Spalten können durch das Festlegen einzelner Eigenschaften geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2b181-103">Many basic behaviors of `DataGridView` cells, rows, and columns can be modified by setting single properties.</span></span> <span data-ttu-id="2b181-104">Die Themen in diesem Abschnitt werden einige der am häufigsten verwendeten Features beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b181-104">The topics in this section describe several of the most commonly used of these features.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2b181-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2b181-105">In This Section</span></span>  
 [<span data-ttu-id="2b181-106">Vorgehensweise: Ausblenden von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-106">How to: Hide Columns in the Windows Forms DataGridView Control</span></span>](how-to-hide-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-107">Beschreibt, wie ein, um zu verhindern, dass bestimmte Spalten im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2b181-107">Describes how to prevent specific columns from appearing in the control.</span></span>  
  
 [<span data-ttu-id="2b181-108">Vorgehensweise: Ausblenden von Spaltenüberschriften in der DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-108">How to: Hide Column Headers in the Windows Forms DataGridView Control</span></span>](how-to-hide-column-headers-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-109">Beschreibt, wie ein, um zu verhindern, dass die Spaltenheader im Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2b181-109">Describes how to prevent the column headers from appearing in the control.</span></span>  
  
 [<span data-ttu-id="2b181-110">Vorgehensweise: Aktivieren der Neuanordnung von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-110">How to: Enable Column Reordering in the Windows Forms DataGridView Control</span></span>](how-to-enable-column-reordering-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-111">Beschreibt, wie Benutzer zum Neuanordnen von Spalten im Steuerelement zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2b181-111">Describes how to enable users to rearrange columns in the control.</span></span>  
  
 [<span data-ttu-id="2b181-112">Vorgehensweise: Einfrieren von Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-112">How to: Freeze Columns in the Windows Forms DataGridView Control</span></span>](how-to-freeze-columns-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-113">Beschreibt, wie verhindern, dass eine oder mehrere angrenzende Spalten scrollen.</span><span class="sxs-lookup"><span data-stu-id="2b181-113">Describes how prevent one or more adjacent columns from scrolling.</span></span>  
  
 [<span data-ttu-id="2b181-114">Vorgehensweise: Schreibschutz Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-114">How to: Make Columns Read-Only in the Windows Forms DataGridView Control</span></span>](how-to-make-columns-read-only-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-115">Beschreibt, wie Sie verhindern, dass Benutzer bestimmte Spalten im Steuerelement bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2b181-115">Describes how to prevent users from editing specific columns in the control.</span></span>  
  
 [<span data-ttu-id="2b181-116">Vorgehensweise: Zu verhindern, dass Hinzufügens und Löschens im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-116">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>](prevent-row-addition-and-deletion-datagridview.md)  
 <span data-ttu-id="2b181-117">Beschreibt, wie die Zeile für neue Datensätze am unteren Rand das Steuerelement, um Benutzer daran zu hindern, Hinzufügen von Zeilen zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="2b181-117">Describes how to remove the row for new records at the bottom of the control to prevent users from adding rows.</span></span> <span data-ttu-id="2b181-118">Beschreibt außerdem, wie Sie verhindern, dass Benutzer das Löschen von Zeilen.</span><span class="sxs-lookup"><span data-stu-id="2b181-118">Also describes how to prevent users from deleting rows.</span></span>  
  
 [<span data-ttu-id="2b181-119">Vorgehensweise: Abrufen und Festlegen der aktuellen Zelle im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-119">How to: Get and Set the Current Cell in the Windows Forms DataGridView Control</span></span>](get-and-set-the-current-cell-wf-datagridview-control.md)  
 <span data-ttu-id="2b181-120">Beschreibt, wie auf die Zelle, die gerade den Fokus in das Steuerelement besitzt.</span><span class="sxs-lookup"><span data-stu-id="2b181-120">Describes how to access the cell that currently has focus in the control.</span></span>  
  
 [<span data-ttu-id="2b181-121">Vorgehensweise: Anzeigen von Bildern in Zellen des DataGridView-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-121">How to: Display Images in Cells of the Windows Forms DataGridView Control</span></span>](how-to-display-images-in-cells-of-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-122">Beschreibt, wie eine Image-Spalte zu erstellen, die in jede Zelle ein Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b181-122">Describes how to create an image column that displays an icon in every cell.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2b181-123">Referenz</span><span class="sxs-lookup"><span data-stu-id="2b181-123">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2b181-124">Enthält die Referenzdokumentation für das Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="2b181-124">Provides reference documentation for the control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="2b181-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="2b181-125">Related Sections</span></span>  
 [<span data-ttu-id="2b181-126">Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="2b181-127">Enthält Themen, in denen erörtert wird, wie die grundlegende Darstellung des Steuerelements sowie das Anzeigeformat von Zelldaten geändert werden.</span><span class="sxs-lookup"><span data-stu-id="2b181-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="2b181-128">Programmieren mit Zellen, Zeilen und Spalten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-128">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="2b181-129">Enthält Themen, in denen die Programmierung mit Zellen-, Zeilen- und Spaltenobjekten beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="2b181-129">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b181-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b181-130">See also</span></span>

- [<span data-ttu-id="2b181-131">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="2b181-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="2b181-132">Spaltentypen im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b181-132">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
