---
title: 'Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e0bbb24b07fdc1c362e2be43d69d189defbc27a4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59346183"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="55aaa-102">Vorgehensweise: Verwenden des Master-/Detailmusters mit hierarchischen Daten</span><span class="sxs-lookup"><span data-stu-id="55aaa-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="55aaa-103">Dieses Beispiel zeigt, wie Sie das Master / Detail-Szenario zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="55aaa-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="55aaa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="55aaa-104">Example</span></span>  
 <span data-ttu-id="55aaa-105">In diesem Beispiel `LeagueList` ist eine Sammlung von `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="55aaa-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="55aaa-106">Jede `League` verfügt über eine `Name` und eine Sammlung von `Divisions`, und jede `Division` hat einen Namen und eine Auflistung von `Teams`.</span><span class="sxs-lookup"><span data-stu-id="55aaa-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="55aaa-107">Jede `Team` verfügt über ein Teamname.</span><span class="sxs-lookup"><span data-stu-id="55aaa-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="55aaa-108">Im Folgenden finden Sie ein Bildschirmfoto des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="55aaa-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="55aaa-109">Die `Divisions` <xref:System.Windows.Controls.ListBox> verfolgt automatisch die Auswahlmöglichkeiten in den `Leagues` <xref:System.Windows.Controls.ListBox> und die entsprechenden Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="55aaa-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="55aaa-110">Die `Teams` <xref:System.Windows.Controls.ListBox> verfolgt die Auswahlmöglichkeiten in den anderen beiden <xref:System.Windows.Controls.ListBox> Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="55aaa-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Screenshot mit einem Masterauftrag für den&#45;Beispiel für Detail-Szenario.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="55aaa-112">Die beiden in diesem Beispiel sind zu beachten:</span><span class="sxs-lookup"><span data-stu-id="55aaa-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="55aaa-113">Die drei <xref:System.Windows.Controls.ListBox> Steuerelemente an dieselbe Quelle binden.</span><span class="sxs-lookup"><span data-stu-id="55aaa-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="55aaa-114">Festlegen der <xref:System.Windows.Data.Binding.Path%2A> -Eigenschaft der Bindung angeben, welche Ebene der Daten sollen die <xref:System.Windows.Controls.ListBox> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55aaa-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="55aaa-115">Müssen Sie festlegen, die <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> Eigenschaft `true` auf die <xref:System.Windows.Controls.ListBox> Steuerelemente, von denen die Auswahl, die Sie verfolgen.</span><span class="sxs-lookup"><span data-stu-id="55aaa-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="55aaa-116">Durch Festlegen dieser Eigenschaft wird sichergestellt, dass das ausgewählte Element immer, als festgelegt ist die <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="55aaa-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="55aaa-117">Auch wenn die <xref:System.Windows.Controls.ListBox> ruft es die Daten aus einer <xref:System.Windows.Data.CollectionViewSource>, diese Auswahl und Aktualität wird automatisch synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="55aaa-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="55aaa-118">Das Verfahren unterscheidet sich geringfügig bei Verwendung von [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] Daten.</span><span class="sxs-lookup"><span data-stu-id="55aaa-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="55aaa-119">Ein Beispiel finden Sie unter [verwenden Sie die Master-/ Detailmusters mit hierarchischen XML-Daten](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="55aaa-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55aaa-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="55aaa-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="55aaa-121">Binden an eine Auflistung und Anzeigen von Informationen auf Grundlage der Auswahl</span><span class="sxs-lookup"><span data-stu-id="55aaa-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="55aaa-122">Übersicht zur Datenbindung</span><span class="sxs-lookup"><span data-stu-id="55aaa-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="55aaa-123">Übersicht über Datenvorlagen</span><span class="sxs-lookup"><span data-stu-id="55aaa-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="55aaa-124">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="55aaa-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
