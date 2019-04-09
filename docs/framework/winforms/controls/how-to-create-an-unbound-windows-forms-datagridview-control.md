---
title: 'Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 9bfffac3d6970aceea3842df95f4bcae970b42e7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167907"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="2f996-102">Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f996-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2f996-103">Im folgenden Codebeispiel wird veranschaulicht, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement programmgesteuert mit Daten aufgefüllt wird, ohne dass das Element an eine Datenquelle gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="2f996-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="2f996-104">Dies ist hilfreich, wenn Sie über eine kleine Menge Daten verfügen, die Sie in einem Tabellenformat anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="2f996-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="2f996-105">Eine vollständige Erläuterung dieses Codebeispiels, finden Sie unter [Exemplarische Vorgehensweise: Erstellen eine nicht gebundene Windows Forms-DataGridView-Steuerelement](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="2f996-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f996-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2f996-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2f996-107">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="2f996-107">Compiling the Code</span></span>  
 <span data-ttu-id="2f996-108">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2f996-108">This example requires:</span></span>  
  
-   <span data-ttu-id="2f996-109">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="2f996-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="2f996-110">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="2f996-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="2f996-111">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="2f996-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2f996-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2f996-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="2f996-113">Exemplarische Vorgehensweise: Erstellen eines ungebundenen DataGridView-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f996-113">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2f996-114">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f996-114">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="2f996-115">Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2f996-115">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
