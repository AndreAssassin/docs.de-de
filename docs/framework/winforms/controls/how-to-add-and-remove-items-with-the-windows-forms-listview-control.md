---
title: 'Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: 8a97d73b9b2c46d02ae0794ad66b20a04db58af6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59327658"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="9a1d3-102">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9a1d3-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="9a1d3-103">Beim Hinzufügen eines Elements zu einer Windows Forms <xref:System.Windows.Forms.ListView> -Steuerelement besteht aus in erster Linie das Element angeben, und Eigenschaften zuweisen.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="9a1d3-104">Hinzufügen oder Entfernen von Elementen kann jederzeit erfolgen.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="9a1d3-105">Elemente programmgesteuert hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-105">To add items programmatically</span></span>  
  
1. <span data-ttu-id="9a1d3-106">Verwenden der <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> Methode der <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="9a1d3-107">Das programmgesteuerte Entfernen von Elementen</span><span class="sxs-lookup"><span data-stu-id="9a1d3-107">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="9a1d3-108">Verwenden der <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> oder <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> Methode der <xref:System.Windows.Forms.ListView.Items%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="9a1d3-109">Die <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> -Methode entfernt ein einzelnes Element; die <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> -Methode entfernt alle Elemente aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="9a1d3-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="9a1d3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a1d3-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="9a1d3-111">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9a1d3-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="9a1d3-112">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="9a1d3-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
