---
title: 'Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- lists [Windows Forms], grouping items
- grouping
- list views [Windows Forms], grouping items
- groups
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 610416a1-8da4-436c-af19-5f19e654769b
ms.openlocfilehash: f616436671da449e4f7b47c0a5d0c1b576584a1a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59312305"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control"></a><span data-ttu-id="85885-102">Vorgehensweise: Gruppieren von Elementen in einem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85885-102">How to: Group Items in a Windows Forms ListView Control</span></span>
<span data-ttu-id="85885-103">Mit der Grouping-Funktion von der <xref:System.Windows.Forms.ListView> -Steuerelement, können Sie verwandte Elemente in Gruppen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="85885-103">With the grouping feature of the <xref:System.Windows.Forms.ListView> control, you can display related sets of items in groups.</span></span> <span data-ttu-id="85885-104">Diese Gruppen werden auf dem Bildschirm durch horizontale Gruppenheader getrennt, die die Gruppentitel enthalten.</span><span class="sxs-lookup"><span data-stu-id="85885-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="85885-105">Sie können <xref:System.Windows.Forms.ListView> Gruppen zum Navigieren in umfangreichen Listen einfacher durch Gruppieren von Elementen alphabetisch nach Datum oder eine beliebige andere logische Gruppierung.</span><span class="sxs-lookup"><span data-stu-id="85885-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="85885-106">Die folgende Abbildung zeigt einige gruppierte Elemente.</span><span class="sxs-lookup"><span data-stu-id="85885-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="85885-107">![ListView-Gruppen](./media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="85885-107">![ListView Groups](./media/listviewgroups.gif "ListViewGroups")</span></span>  
<span data-ttu-id="85885-108">ListView in gruppierten Elementen</span><span class="sxs-lookup"><span data-stu-id="85885-108">ListView grouped items</span></span>  
  
 <span data-ttu-id="85885-109">Aktivieren der Gruppierung, müssen Sie zunächst eine oder mehrere Gruppen im Designer oder programmgesteuert erstellen.</span><span class="sxs-lookup"><span data-stu-id="85885-109">To enable grouping, you must first create one or more groups either in the designer or programmatically.</span></span> <span data-ttu-id="85885-110">Nachdem eine Gruppe definiert wurde, können Sie zuweisen <xref:System.Windows.Forms.ListView> Elemente, die Gruppen.</span><span class="sxs-lookup"><span data-stu-id="85885-110">After a group has been defined, you can assign <xref:System.Windows.Forms.ListView> items to groups.</span></span> <span data-ttu-id="85885-111">Sie können auch Elemente aus einer Gruppe in eine andere programmgesteuert verschieben.</span><span class="sxs-lookup"><span data-stu-id="85885-111">You can also move items from one group to another programmatically.</span></span>  
  
> [!NOTE]
>  <xref:System.Windows.Forms.ListView> <span data-ttu-id="85885-112">Gruppen stehen nur auf [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] bei einem Aufruf der <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="85885-112">groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="85885-113">Unter früheren Betriebssystemen Code im Zusammenhang mit Gruppen hat keine Auswirkungen, und die Gruppen werden nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="85885-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="85885-114">Weitere Informationen finden Sie unter <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="85885-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="to-add-groups"></a><span data-ttu-id="85885-115">Beim Hinzufügen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="85885-115">To add groups</span></span>  
  
1. <span data-ttu-id="85885-116">Verwenden Sie die <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> -Methode der <xref:System.Windows.Forms.ListView.Groups%2A> -Auflistung.</span><span class="sxs-lookup"><span data-stu-id="85885-116">Use the <xref:System.Windows.Forms.ListViewGroupCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#21)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#21)]  
  
### <a name="to-remove-groups"></a><span data-ttu-id="85885-117">Gruppen entfernen</span><span class="sxs-lookup"><span data-stu-id="85885-117">To remove groups</span></span>  
  
1. <span data-ttu-id="85885-118">Verwenden der <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> oder <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> Methode der <xref:System.Windows.Forms.ListView.Groups%2A> Auflistung.</span><span class="sxs-lookup"><span data-stu-id="85885-118">Use the <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Groups%2A> collection.</span></span>  
  
     <span data-ttu-id="85885-119">Die <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> Methode wird eine einzelne Gruppe entfernt; die <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> -Methode entfernt alle Gruppen aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="85885-119">The <xref:System.Windows.Forms.ListViewGroupCollection.RemoveAt%2A> method removes a single group; the <xref:System.Windows.Forms.ListViewGroupCollection.Clear%2A> method removes all groups from the list.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="85885-120">Eine Gruppe entfernen, wird die Elemente in dieser Gruppe nicht entfernt.</span><span class="sxs-lookup"><span data-stu-id="85885-120">Removing a group does not remove the items within that group.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#22)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#22)]  
  
### <a name="to-assign-items-to-groups-or-move-items-between-groups"></a><span data-ttu-id="85885-121">Zuweisen zu Gruppen von Elementen oder Elemente zwischen den Gruppen verschieben.</span><span class="sxs-lookup"><span data-stu-id="85885-121">To assign items to groups or move items between groups</span></span>  
  
1. <span data-ttu-id="85885-122">Legen Sie die <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> -Eigenschaft einzelner Elemente.</span><span class="sxs-lookup"><span data-stu-id="85885-122">Set the <xref:System.Windows.Forms.ListViewItem.Group%2A?displayProperty=nameWithType> property of individual items.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#23)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#23)]  
  
## <a name="see-also"></a><span data-ttu-id="85885-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="85885-123">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="85885-124">ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="85885-124">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="85885-125">Übersicht über das ListView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="85885-125">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
- [<span data-ttu-id="85885-126">Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="85885-126">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
