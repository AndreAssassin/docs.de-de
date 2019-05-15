---
title: 'Vorgehensweise: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- object binding [Windows Forms], accessing bound objects
- data grids [Windows Forms], accessing bound objects
- DataGridView control [Windows Forms], accessing objects bound to rows
ms.assetid: 0e05748f-4403-4eb8-8b2f-b098108181b5
ms.openlocfilehash: 244047f27b0eb109aba599bd26881046eb538163
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582623"
---
# <a name="how-to-access-objects-bound-to-windows-forms-datagridview-rows"></a><span data-ttu-id="2b59b-102">Vorgehensweise: Aufrufen von Objekten, die an DataGridView-Zeilen in Windows Forms gebunden sind</span><span class="sxs-lookup"><span data-stu-id="2b59b-102">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>
<span data-ttu-id="2b59b-103">Manchmal ist es hilfreich, eine Tabelle mit Informationen anzuzeigen, die in einer Auflistung von Geschäftsobjekten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="2b59b-103">Sometimes it is useful to display a table of information stored in a collection of business objects.</span></span> <span data-ttu-id="2b59b-104">Beim Binden eines <xref:System.Windows.Forms.DataGridView>-Steuerelements an eine solche Auflistung wird jede öffentliche Eigenschaft in einer eigenen Spalte angezeigt, es sei denn, die Eigenschaft wurde mit <xref:System.ComponentModel.BrowsableAttribute> als nicht durchsuchbar markiert.</span><span class="sxs-lookup"><span data-stu-id="2b59b-104">When you bind a <xref:System.Windows.Forms.DataGridView> control to such a collection, each public property is displayed in its own column unless the property has been marked non-browsable with a <xref:System.ComponentModel.BrowsableAttribute>.</span></span> <span data-ttu-id="2b59b-105">Angenommen, eine Auflistung von `Customer`-Objekten hätte Spalten wie **Name** und **Adresse**.</span><span class="sxs-lookup"><span data-stu-id="2b59b-105">For example, a collection of `Customer` objects would have columns such as **Name** and **Address**.</span></span>  
  
 <span data-ttu-id="2b59b-106">Wenn diese Objekte zusätzliche Informationen und Code enthalten, auf die Sie zugreifen möchten, können Sie dies über Zeilenobjekte erreichen.</span><span class="sxs-lookup"><span data-stu-id="2b59b-106">If these objects contain additional information and code that you want to access, you can reach it through row objects.</span></span> <span data-ttu-id="2b59b-107">Im folgenden Codebeispiel können Benutzer mehrere Zeilen auswählen und auf eine Schaltfläche klicken, um eine Rechnung an jeden der entsprechenden Kunden zu senden.</span><span class="sxs-lookup"><span data-stu-id="2b59b-107">In the following code example, users can select multiple rows and click a button to send an invoice to each of the corresponding customers.</span></span>  
  
### <a name="to-access-row-bound-objects"></a><span data-ttu-id="2b59b-108">So greifen Sie auf zeilengebundene Objekte zu</span><span class="sxs-lookup"><span data-stu-id="2b59b-108">To access row-bound objects</span></span>  
  
- <span data-ttu-id="2b59b-109">Verwenden Sie die <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2b59b-109">Use the <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="2b59b-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b59b-110">Example</span></span>  
 <span data-ttu-id="2b59b-111">Das vollständige Codebeispiel beinhaltet eine einfache `Customer`-Implementierung und bindet die <xref:System.Windows.Forms.DataGridView> an eine <xref:System.Collections.ArrayList>, die ein paar `Customer`-Objekte enthält.</span><span class="sxs-lookup"><span data-stu-id="2b59b-111">The complete code example includes a simple `Customer` implementation and binds the <xref:System.Windows.Forms.DataGridView> to an <xref:System.Collections.ArrayList> containing a few `Customer` objects.</span></span> <span data-ttu-id="2b59b-112">Der <xref:System.Windows.Forms.Control.Click>-Ereignishandler der <xref:System.Windows.Forms.Button?displayProperty=nameWithType> muss über die Zeilen auf die `Customer`-Objekte zugreifen, weil außerhalb des <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType>-Ereignishandlers nicht auf die Kundenauflistung zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="2b59b-112">The <xref:System.Windows.Forms.Control.Click> event handler of the <xref:System.Windows.Forms.Button?displayProperty=nameWithType> must access the `Customer` objects through the rows, because the customer collection is not accessible outside the <xref:System.Windows.Forms.Form.Load?displayProperty=nameWithType> event handler.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/CS/datagridviewobjectbinding.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewObjectBinding#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewObjectBinding/VB/datagridviewobjectbinding.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2b59b-113">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2b59b-113">Compiling the Code</span></span>  
 <span data-ttu-id="2b59b-114">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2b59b-114">This example requires:</span></span>  
  
- <span data-ttu-id="2b59b-115">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2b59b-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b59b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b59b-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridViewRow.DataBoundItem%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2b59b-117">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2b59b-117">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2b59b-118">Vorgehensweise: Binden von Objekten an Windows Forms-DataGridView-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="2b59b-118">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>](how-to-bind-objects-to-windows-forms-datagridview-controls.md)
