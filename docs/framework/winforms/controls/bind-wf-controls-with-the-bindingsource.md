---
title: 'Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: a4f87303954494e8e32d32e68fb3f1244f25680a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304557"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="96359-102">Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="96359-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="96359-103">Nachdem Sie dem Formular Steuerelemente hinzugefügt und die Benutzeroberfläche für Ihre Anwendung bestimmt, können Sie die Steuerelemente an eine Datenquelle binden, damit Benutzer können zur Laufzeit ändern und Speichern von Daten, die im Zusammenhang mit der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="96359-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="96359-104">Binden ein Steuerelement oder eine Reihe von Steuerelementen in Windows Forms am einfachsten erfolgt mithilfe der <xref:System.Windows.Forms.BindingSource> Steuerelement als Brücke zwischen den Steuerelementen im Formular und die Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="96359-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="96359-105">Ein oder mehrere Steuerelemente in einem Formular können an Daten gebunden werden. Im folgenden Verfahren eine <xref:System.Windows.Forms.TextBox> -Steuerelement an eine Datenquelle gebunden ist.</span><span class="sxs-lookup"><span data-stu-id="96359-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="96359-106">Um den Vorgang abzuschließen, wird davon ausgegangen, dass Sie an eine Datenquelle aus einer Datenbank abgeleitet binden.</span><span class="sxs-lookup"><span data-stu-id="96359-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="96359-107">Weitere Informationen zum Erstellen von Datenquellen aus anderen Datenspeichern finden Sie unter [neue Datenquellen hinzufügen](/visualstudio/data-tools/add-new-data-sources).</span><span class="sxs-lookup"><span data-stu-id="96359-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="96359-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="96359-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="96359-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="96359-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="96359-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="96359-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="96359-111">Zum Binden eines Steuerelements zur Entwurfszeit</span><span class="sxs-lookup"><span data-stu-id="96359-111">To bind a control at design time</span></span>  
  
1. <span data-ttu-id="96359-112">Ziehen Sie eine <xref:System.Windows.Forms.TextBox> -Steuerelement in das Formular.</span><span class="sxs-lookup"><span data-stu-id="96359-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2. <span data-ttu-id="96359-113">In der **Eigenschaften** Fenster:</span><span class="sxs-lookup"><span data-stu-id="96359-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="96359-114">Erweitern Sie die **(DataBindings)** Knoten.</span><span class="sxs-lookup"><span data-stu-id="96359-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="96359-115">Klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="96359-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="96359-116">Die **DataSource** UI-Typ-Editor wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="96359-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="96359-117">Wenn eine Datenquelle für das Projekt oder Formular zuvor konfiguriert wurde, wird es angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96359-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3. <span data-ttu-id="96359-118">Klicken Sie auf **Projektdatenquelle hinzufügen**, um die Daten zu verbinden und die Datenquelle zu erzeugen.</span><span class="sxs-lookup"><span data-stu-id="96359-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4. <span data-ttu-id="96359-119">Klicken Sie auf der Startseite des **Assistenten zum Konfigurieren von Datenquellen** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="96359-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5. <span data-ttu-id="96359-120">Auf der **wählen Sie einen Datenquellentyp** Seite **Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="96359-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6. <span data-ttu-id="96359-121">Auf der **wählen Sie Ihre Datenverbindung** Seite, wählen Sie eine Datenverbindung aus der Liste der verfügbaren Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="96359-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="96359-122">Wenn die gewünschte Datenverbindung nicht verfügbar-Option ist **neue Verbindung** um eine neue Datenverbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="96359-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7. <span data-ttu-id="96359-123">Wählen Sie **Ja, Verbindung speichern** so speichern die Verbindungszeichenfolge in der Konfigurationsdatei der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="96359-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8. <span data-ttu-id="96359-124">Wählen Sie die Datenbankobjekte, die in die Anwendung gebracht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="96359-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="96359-125">In diesem Fall wählen Sie ein Feld in einer Tabelle, die Sie möchten die <xref:System.Windows.Forms.TextBox> angezeigt.</span><span class="sxs-lookup"><span data-stu-id="96359-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="96359-126">Ersetzen Sie den Standardnamen des Datasets falls gewünscht.</span><span class="sxs-lookup"><span data-stu-id="96359-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="96359-127">Klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="96359-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="96359-128">In der **Eigenschaften** Fenster, klicken Sie auf den Pfeil neben der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft erneut aus.</span><span class="sxs-lookup"><span data-stu-id="96359-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="96359-129">In der **DataSource** Typeditor, wählen Sie den Namen des Felds, das Binden der <xref:System.Windows.Forms.TextBox> auf.</span><span class="sxs-lookup"><span data-stu-id="96359-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="96359-130">Die **DataSource** Benutzeroberflächentyp-Editor geschlossen wird und das Dataset <xref:System.Windows.Forms.BindingSource> und Tabellenadapter, die spezifisch für Datenverbindung zum Formular hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="96359-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96359-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="96359-131">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="96359-132">Neue Datenquelle hinzufügen</span><span class="sxs-lookup"><span data-stu-id="96359-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="96359-133">[Datenquellenfenster](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="96359-133">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>