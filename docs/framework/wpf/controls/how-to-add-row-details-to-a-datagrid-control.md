---
title: 'Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataTemplate [WPF], DataGrid
- row details [WPF], DataGrid
- DataGrid [WPF], row details
ms.assetid: 0bdc6f50-9b4c-483f-9df6-a47a1fde998b
ms.openlocfilehash: d5b6539f3d379088528b9654861267988b6fc69b
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59317888"
---
# <a name="how-to-add-row-details-to-a-datagrid-control"></a><span data-ttu-id="252b2-102">Vorgehensweise: Hinzufügen von Zeilendetails zu einem DataGrid-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="252b2-102">How to: Add Row Details to a DataGrid Control</span></span>
<span data-ttu-id="252b2-103">Bei Verwendung der <xref:System.Windows.Controls.DataGrid> -Steuerelement, Sie können die Darstellung von Daten durch das Hinzufügen einer Zeilendetailabschnitt anpassen.</span><span class="sxs-lookup"><span data-stu-id="252b2-103">When using the <xref:System.Windows.Controls.DataGrid> control, you can customize the data presentation by adding a row details section.</span></span> <span data-ttu-id="252b2-104">Hinzufügen einer Zeilendetailabschnitt ermöglicht Ihnen, einige Daten in einer Vorlage zu gruppieren, die optional sichtbar oder ausgeblendet ist.</span><span class="sxs-lookup"><span data-stu-id="252b2-104">Adding a row details section enables you to group some data in a template that is optionally visible or collapsed.</span></span> <span data-ttu-id="252b2-105">Sie können z. B. Hinzufügen von Zeilendetails zu einem <xref:System.Windows.Controls.DataGrid> bereitstellt, die nur eine Zusammenfassung der Daten für jede Zeile in der <xref:System.Windows.Controls.DataGrid>, weitere Datenfelder angezeigt, wenn der Benutzer eine Zeile auswählt jedoch.</span><span class="sxs-lookup"><span data-stu-id="252b2-105">For example, you can add row details to a <xref:System.Windows.Controls.DataGrid> that presents only a summary of the data for each row in the <xref:System.Windows.Controls.DataGrid>, but presents more data fields when the user selects a row.</span></span> <span data-ttu-id="252b2-106">Definieren Sie die Vorlage für den Zeilendetailabschnitt in die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="252b2-106">You define the template for the row details section in the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property.</span></span> <span data-ttu-id="252b2-107">Die folgende Abbildung zeigt ein Beispiel für eine Zeilendetailabschnitt.</span><span class="sxs-lookup"><span data-stu-id="252b2-107">The following illustration shows an example of a row details section.</span></span>  
  
 <span data-ttu-id="252b2-108">![DataGrid mit Zeilendetails](./media/ndp-rowdetails.png "NDP_RowDetails")</span><span class="sxs-lookup"><span data-stu-id="252b2-108">![DataGrid shown with row details](./media/ndp-rowdetails.png "NDP_RowDetails")</span></span>  
  
 <span data-ttu-id="252b2-109">Sie definieren die Zeilendetailvorlage als XAML Inline oder als Ressource.</span><span class="sxs-lookup"><span data-stu-id="252b2-109">You define the row details template as either inline XAML or as a resource.</span></span> <span data-ttu-id="252b2-110">In den folgenden Verfahren werden beide Ansätze beschrieben.</span><span class="sxs-lookup"><span data-stu-id="252b2-110">Both approaches are shown in the following procedures.</span></span> <span data-ttu-id="252b2-111">Eine Datenvorlage, die hinzugefügt wird, wie eine Ressource im gesamten Projekt verwendet werden kann, ohne Vorlage neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="252b2-111">A data template that is added as a resource can be used throughout the project without re-creating the template.</span></span> <span data-ttu-id="252b2-112">Eine Datenvorlage, die hinzugefügt wird, als Inline-XAML nur aus dem Steuerelement zugegriffen werden kann, wo sie definiert ist.</span><span class="sxs-lookup"><span data-stu-id="252b2-112">A data template that is added as inline XAML is only accessible from the control where it is defined.</span></span>  
  
### <a name="to-display-row-details-by-using-inline-xaml"></a><span data-ttu-id="252b2-113">Zum Anzeigen von Details für die Zeile mit Inline-XAML</span><span class="sxs-lookup"><span data-stu-id="252b2-113">To display row details by using inline XAML</span></span>  
  
1. <span data-ttu-id="252b2-114">Erstellen Sie eine <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="252b2-114">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="252b2-115">Fügen Sie im <xref:System.Windows.Controls.DataGrid>-Element ein <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A>-Element hinzu.</span><span class="sxs-lookup"><span data-stu-id="252b2-115">In the <xref:System.Windows.Controls.DataGrid> element, add a <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> element.</span></span>  
  
3. <span data-ttu-id="252b2-116">Erstellen Sie eine <xref:System.Windows.DataTemplate> , die die Darstellung der Zeilendetailabschnitt definiert.</span><span class="sxs-lookup"><span data-stu-id="252b2-116">Create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="252b2-117">Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid> und zum Definieren der <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Inline.</span><span class="sxs-lookup"><span data-stu-id="252b2-117">The following XAML shows the <xref:System.Windows.Controls.DataGrid> and how to define the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> inline.</span></span> <span data-ttu-id="252b2-118">Die <xref:System.Windows.Controls.DataGrid> zeigt drei Werte in jeder Zeile und drei weitere Werte an, wenn die Zeile ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="252b2-118">The <xref:System.Windows.Controls.DataGrid> displays three values in each row and three more values when the row is selected.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#1](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml#1)]  
  
     <span data-ttu-id="252b2-119">Der folgende Code zeigt die Abfrage, die verwendet wird, um die Daten auszuwählen, die in angezeigt wird der <xref:System.Windows.Controls.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="252b2-119">The following code shows the query that is used to select the data that is displayed in the <xref:System.Windows.Controls.DataGrid>.</span></span> <span data-ttu-id="252b2-120">In diesem Beispiel wählt die Abfrage Daten aus einer Entität, die Kundeninformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="252b2-120">In this example, the query selects data from an entity that contains customer information.</span></span>  
  
     [!code-csharp[DataGrid_RowDetails#2](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/mainwindow.xaml.cs#2)]
     [!code-vb[DataGrid_RowDetails#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/datagrid_rowdetails/vb/mainwindow.xaml.vb#2)]  
  
### <a name="to-display-row-details-by-using-a-resource"></a><span data-ttu-id="252b2-121">Details für die Zeile angezeigt wird, mithilfe einer Ressource</span><span class="sxs-lookup"><span data-stu-id="252b2-121">To display row details by using a resource</span></span>  
  
1. <span data-ttu-id="252b2-122">Erstellen Sie eine <xref:System.Windows.Controls.DataGrid> , die Daten aus einer Datenquelle anzeigt.</span><span class="sxs-lookup"><span data-stu-id="252b2-122">Create a <xref:System.Windows.Controls.DataGrid> that displays data from a data source.</span></span>  
  
2. <span data-ttu-id="252b2-123">Hinzufügen einer <xref:System.Windows.FrameworkElement.Resources%2A> Element das Stammelement, wie z. B. eine <xref:System.Windows.Window> Steuerelement oder ein <xref:System.Windows.Controls.Page> steuern, oder fügen eine <xref:System.Windows.Application.Resources%2A> Element der <xref:System.Windows.Application> Klasse in der Datei "App.xaml" (oder "Application.xaml").</span><span class="sxs-lookup"><span data-stu-id="252b2-123">Add a <xref:System.Windows.FrameworkElement.Resources%2A> element to the root element, such as a <xref:System.Windows.Window> control or a <xref:System.Windows.Controls.Page> control, or add a <xref:System.Windows.Application.Resources%2A> element to the <xref:System.Windows.Application> class in the App.xaml (or Application.xaml) file.</span></span>  
  
3. <span data-ttu-id="252b2-124">Erstellen Sie in die Resources-Element, ein <xref:System.Windows.DataTemplate> , die die Darstellung der Zeilendetailabschnitt definiert.</span><span class="sxs-lookup"><span data-stu-id="252b2-124">In the resources element, create a <xref:System.Windows.DataTemplate> that defines the appearance of the row details section.</span></span>  
  
     <span data-ttu-id="252b2-125">Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> definiert, der <xref:System.Windows.Application> Klasse.</span><span class="sxs-lookup"><span data-stu-id="252b2-125">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> defined in the <xref:System.Windows.Application> class.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#3](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/app.xaml#3)]  
  
4. <span data-ttu-id="252b2-126">Auf der <xref:System.Windows.DataTemplate>legen die [X: Key Directive](../../xaml-services/x-key-directive.md) auf einen Wert, der die Datenvorlage eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="252b2-126">On the <xref:System.Windows.DataTemplate>, set the [x:Key Directive](../../xaml-services/x-key-directive.md) to a value that uniquely identifies the data template.</span></span>  
  
5. <span data-ttu-id="252b2-127">In der <xref:System.Windows.Controls.DataGrid> -Element legen Sie die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> Eigenschaft, um die Ressource, die in den vorherigen Schritten definiert.</span><span class="sxs-lookup"><span data-stu-id="252b2-127">In the <xref:System.Windows.Controls.DataGrid> element, set the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property to the resource defined in the previous steps.</span></span> <span data-ttu-id="252b2-128">Weisen Sie die Ressource als statische Ressource.</span><span class="sxs-lookup"><span data-stu-id="252b2-128">Assign the resource as a static resource.</span></span>  
  
     <span data-ttu-id="252b2-129">Das folgende XAML zeigt die <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> -Eigenschaft auf die Ressource aus dem vorherigen Beispiel.</span><span class="sxs-lookup"><span data-stu-id="252b2-129">The following XAML shows the <xref:System.Windows.Controls.DataGrid.RowDetailsTemplate%2A> property set to the resource from the previous example.</span></span>  
  
     [!code-xaml[DataGrid_RowDetails#4](~/samples/snippets/csharp/VS_Snippets_Wpf/datagrid_rowdetails/cs/window2.xaml#4)]  
  
### <a name="to-set-visibility-and-prevent-horizontal-scrolling-for-row-details"></a><span data-ttu-id="252b2-130">Legen Sie Sichtbarkeit und horizontalen Bildlauf für Zeilendetails</span><span class="sxs-lookup"><span data-stu-id="252b2-130">To set visibility and prevent horizontal scrolling for row details</span></span>  
  
1. <span data-ttu-id="252b2-131">Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> Eigenschaft, um eine <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> Wert.</span><span class="sxs-lookup"><span data-stu-id="252b2-131">If needed, set the <xref:System.Windows.Controls.DataGrid.RowDetailsVisibilityMode%2A> property to a <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode> value.</span></span>  
  
     <span data-ttu-id="252b2-132">Der Wert ist standardmäßig auf festgelegt <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span><span class="sxs-lookup"><span data-stu-id="252b2-132">By default, the value is set to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.VisibleWhenSelected>.</span></span> <span data-ttu-id="252b2-133">Sie können sie festlegen, um <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> um die Details für alle Zeilen anzuzeigen oder <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> So blenden Sie die Details für alle Zeilen aus.</span><span class="sxs-lookup"><span data-stu-id="252b2-133">You can set it to <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Visible> to show the details for all of the rows or <xref:System.Windows.Controls.DataGridRowDetailsVisibilityMode.Collapsed> to hide the details for all rows.</span></span>  
  
2. <span data-ttu-id="252b2-134">Legen Sie bei Bedarf die <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> Eigenschaft `true` erläutert, um zu verhindern, dass die Zeile einen horizontalen Bildlauf.</span><span class="sxs-lookup"><span data-stu-id="252b2-134">If needed, set the <xref:System.Windows.Controls.DataGrid.AreRowDetailsFrozen%2A> property to `true` to prevent the row details section from scrolling horizontally.</span></span>
