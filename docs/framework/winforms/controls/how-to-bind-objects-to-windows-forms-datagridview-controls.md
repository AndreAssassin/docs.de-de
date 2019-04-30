---
title: 'Vorgehensweise: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 02c4f94eddfcf782d7d2323787d9b6a9b18db2d5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948056"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="c94b6-102">Vorgehensweise: Binden von Objekten an das DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c94b6-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="c94b6-103">Im folgenden Codebeispiel wird gezeigt, wie eine Auflistung von Objekten so an ein <xref:System.Windows.Forms.DataGridView>-Steuerelement gebunden wird, dass jedes Objekt als eine separate Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c94b6-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="c94b6-104">Das Beispiel zeigt darüber hinaus, wie eine Eigenschaft mit einem Enumerationstyp in einer <xref:System.Windows.Forms.DataGridViewComboBoxColumn> angezeigt wird, sodass die Dropdownliste des Kombinationsfelds die Enumerationswerte enthält.</span><span class="sxs-lookup"><span data-stu-id="c94b6-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c94b6-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c94b6-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c94b6-106">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="c94b6-106">Compiling the Code</span></span>  
 <span data-ttu-id="c94b6-107">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c94b6-107">This example requires:</span></span>  
  
- <span data-ttu-id="c94b6-108">Verweise auf die Assemblys "System" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="c94b6-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="c94b6-109">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="c94b6-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="c94b6-110">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="c94b6-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c94b6-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c94b6-111">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="c94b6-112">Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="c94b6-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="c94b6-113">Vorgehensweise: Zugreifen auf Objekte an in Windows Forms DataGridView-Zeilen gebunden.</span><span class="sxs-lookup"><span data-stu-id="c94b6-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
