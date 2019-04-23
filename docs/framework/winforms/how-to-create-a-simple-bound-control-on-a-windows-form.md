---
title: 'Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einer Windows Forms-Instanz'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: fc59e6d5e71bfc69dea0bfc5098a1fa14c97d4b6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322172"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="db3a4-102">Vorgehensweise: Erstellen eines einfach gebundenen Steuerelements in einer Windows Forms-Instanz</span><span class="sxs-lookup"><span data-stu-id="db3a4-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="db3a4-103">Mit *einfache Bindung*, Sie können ein einzelnes Datenelement, z. B. ein Spaltenwert aus einem Dataset-Tabelle in einem Steuerelement anzeigen.</span><span class="sxs-lookup"><span data-stu-id="db3a4-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="db3a4-104">Sie können einfach eine Eigenschaft eines Steuerelements an einen Datenwert binden.</span><span class="sxs-lookup"><span data-stu-id="db3a4-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="db3a4-105">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="db3a4-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="db3a4-106">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="db3a4-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="db3a4-107">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="db3a4-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="db3a4-108">An einfach ein Steuerelement gebunden werden soll</span><span class="sxs-lookup"><span data-stu-id="db3a4-108">To simple-bind a control</span></span>  
  
1. <span data-ttu-id="db3a4-109">Stellen Sie die Verbindung zu einer Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="db3a4-109">Connect to a data source.</span></span> <span data-ttu-id="db3a4-110">Weitere Informationen finden Sie unter [Herstellen einer Verbindung mit einer Datenquelle](../data/adonet/connecting-to-a-data-source.md).</span><span class="sxs-lookup"><span data-stu-id="db3a4-110">For more information, see [Connecting to a Data Source](../data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2. <span data-ttu-id="db3a4-111">Klicken Sie in der Form, wählen Sie das Steuerelement und Anzeigen der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="db3a4-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3. <span data-ttu-id="db3a4-112">Erweitern Sie die **(DataBindings)** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db3a4-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="db3a4-113">Die am häufigsten gebundenen Eigenschaften werden angezeigt, darunter die **(DataBindings)** Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="db3a4-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="db3a4-114">In den meisten Steuerelementen, z. B. die **Text** -Eigenschaft wird am häufigsten gebunden.</span><span class="sxs-lookup"><span data-stu-id="db3a4-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4. <span data-ttu-id="db3a4-115">Die Eigenschaft gewünscht Bindung gehört nicht zu den häufig gebundenen Eigenschaften, klicken Sie auf die **Auslassungspunkte** Schaltfläche (![VisualStudioEllipsesButton-bildschirmabbildung](./media/vbellipsesbutton.png "VbEllipsesButton") ) in der **(Erweitert)** anzuzeigen die **Formatierung und erweiterte Bindung** Dialogfeld mit einer vollständigen Liste der Eigenschaften, die für dieses Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="db3a4-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](./media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5. <span data-ttu-id="db3a4-116">Wählen Sie die Eigenschaft, die Sie binden möchten und klicken Sie auf den Dropdownpfeil unter **Bindung**.</span><span class="sxs-lookup"><span data-stu-id="db3a4-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="db3a4-117">Nun wird eine Liste verfügbarer Datenquellen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="db3a4-117">A list of available data sources is displayed.</span></span>  
  
6. <span data-ttu-id="db3a4-118">Erweitern Sie die Datenquelle, die Sie für die Bindung verwenden möchten, bis Sie das gewünschte einzelne Datenelement finden.</span><span class="sxs-lookup"><span data-stu-id="db3a4-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="db3a4-119">Wenn die Bindung beispielsweise an einen Spaltenwert in einer Dataset-Tabelle erfolgen soll, erweitern Sie den Namen des Datasets, und erweitern sie dann den Tabellennamen, um die Spaltennamen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="db3a4-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7. <span data-ttu-id="db3a4-120">Klicken Sie auf den Namen des Elements, das gebunden werden soll.</span><span class="sxs-lookup"><span data-stu-id="db3a4-120">Click the name of an element to bind to.</span></span>  
  
8. <span data-ttu-id="db3a4-121">Wenn Sie, in bearbeitet haben der **Formatierung und erweiterte Bindung** im Dialogfeld klicken Sie auf **OK** zum Zurückgeben der **Eigenschaften** Fenster.</span><span class="sxs-lookup"><span data-stu-id="db3a4-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="db3a4-122">Wenn Sie zusätzliche Eigenschaften für das Steuerelement binden möchten, wiederholen Sie Schritte 3 bis 7.</span><span class="sxs-lookup"><span data-stu-id="db3a4-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db3a4-123">Da einfach gebundene Steuerelemente nur ein einzelnes Datenelement angezeigt werden, kommt es häufig vor, ein Windows-Formular mit einfachen datengebundenen Steuerelementen Navigationslogik einschließt.</span><span class="sxs-lookup"><span data-stu-id="db3a4-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3a4-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db3a4-124">See also</span></span>

- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="db3a4-125">Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="db3a4-125">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
- [<span data-ttu-id="db3a4-126">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db3a4-126">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
