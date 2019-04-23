---
ms.openlocfilehash: e2d63d85adce64db6e00b62ec17f55ae71ce3052
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59804045"
---
### <a name="calling-datagridcommitedit-from-a-celleditending-handler-drops-focus"></a><span data-ttu-id="a8349-101">Der Aufruf von DataGrid.CommitEdit über einen CellEditEnding-Handler verliert den Fokus</span><span class="sxs-lookup"><span data-stu-id="a8349-101">Calling DataGrid.CommitEdit from a CellEditEnding handler drops focus</span></span>

|   |   |
|---|---|
|<span data-ttu-id="a8349-102">Details</span><span class="sxs-lookup"><span data-stu-id="a8349-102">Details</span></span>|<span data-ttu-id="a8349-103">Wenn das <xref:System.Windows.Controls.DataGrid.CommitEdit>-Element von einem der <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name>-Ereignishandler von <xref:System.Windows.Controls.DataGrid?displayProperty=name> aufgerufen, verliert <xref:System.Windows.Controls.DataGrid?displayProperty=name> den Fokus.</span><span class="sxs-lookup"><span data-stu-id="a8349-103">Calling <xref:System.Windows.Controls.DataGrid.CommitEdit> from one of the <xref:System.Windows.Controls.DataGrid?displayProperty=name>'s <xref:System.Windows.Controls.DataGrid.CellEditEnding?displayProperty=name> event handlers causes the <xref:System.Windows.Controls.DataGrid?displayProperty=name> to lose focus.</span></span>|
|<span data-ttu-id="a8349-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="a8349-104">Suggestion</span></span>|<span data-ttu-id="a8349-105">Dieses Problem wurde in .NET Framework 4.5.2 behoben, daher kann es durch ein Upgrade von .NET Framework vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="a8349-105">This bug has been fixed in the .NET Framework 4.5.2, so it can be avoided by upgrading the .NET Framework.</span></span> <span data-ttu-id="a8349-106">Alternativ kann dies vermieden werden, indem das <xref:System.Windows.Controls.DataGrid?displayProperty=name>-Element nach dem Aufruf von <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name> explizit neu ausgewählt wird.</span><span class="sxs-lookup"><span data-stu-id="a8349-106">Alternatively, it can be avoided by explicitly re-selecting the <xref:System.Windows.Controls.DataGrid?displayProperty=name> after calling <xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=name>.</span></span>|
|<span data-ttu-id="a8349-107">Bereich</span><span class="sxs-lookup"><span data-stu-id="a8349-107">Scope</span></span>|<span data-ttu-id="a8349-108">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a8349-108">Edge</span></span>|
|<span data-ttu-id="a8349-109">Version</span><span class="sxs-lookup"><span data-stu-id="a8349-109">Version</span></span>|<span data-ttu-id="a8349-110">4.5</span><span class="sxs-lookup"><span data-stu-id="a8349-110">4.5</span></span>|
|<span data-ttu-id="a8349-111">Typ</span><span class="sxs-lookup"><span data-stu-id="a8349-111">Type</span></span>|<span data-ttu-id="a8349-112">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="a8349-112">Runtime</span></span>|
|<span data-ttu-id="a8349-113">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="a8349-113">Affected APIs</span></span>|<ul><li><xref:System.Windows.Controls.DataGrid.CommitEdit?displayProperty=nameWithType></li><li><xref:System.Windows.Controls.DataGrid.CommitEdit(System.Windows.Controls.DataGridEditingUnit,System.Boolean)?displayProperty=nameWithType></li></ul>|
