---
title: 'Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hybrid applications [WPF interoperability]
- data binding [WPF interoperability]
ms.assetid: 18997e71-745a-4425-9c69-2cbce1d8669e
ms.openlocfilehash: d497dfd5580f1d2741e0edafa86e9dd39ec374ec
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59191990"
---
# <a name="walkthrough-binding-to-data-in-hybrid-applications"></a>Exemplarische Vorgehensweise: Datenbindung in Hybridanwendungen
Binden einer Datenquelle an ein Steuerelement ist wichtig für die Bereitstellung von Benutzern mit Zugriff auf die zugrunde liegenden Daten, unabhängig davon, ob Sie sind [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] oder [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. In dieser exemplarischen Vorgehensweise wird gezeigt, wie Sie die Datenbindung in hybridanwendungen verwenden können, die beide enthalten [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente.  
  
 In dieser exemplarischen Vorgehensweise werden u. a. folgende Aufgaben veranschaulicht:  
  
-   Erstellen des Projekts.  
  
-   Definieren der Datenvorlage.  
  
-   Angeben des Formularlayouts.  
  
-   Angeben von Datenbindungen.  
  
-   Anzeigen von Daten mithilfe von Interoperation.  
  
-   Hinzufügen der Datenquelle zum Projekt.  
  
-   Bindung an die Datenquelle.  
  
 Eine vollständige codeauflistung der Aufgaben in dieser exemplarischen Vorgehensweise veranschaulicht, finden Sie unter [Datenbindung in Anwendungen Hybridbeispiel](https://go.microsoft.com/fwlink/?LinkID=159983).  
  
 Anschließend werden Sie verstehen, welche Rolle Datenbindungsfunktionen bei Hybridanwendungen spielen.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio.  
  
-   Zugriff auf die Northwind-Beispieldatenbank, die auf Microsoft SQL Server ausgeführt wird.  
  
## <a name="creating-the-project"></a>Erstellen des Projekts  
  
#### <a name="to-create-and-set-up-the-project"></a>So erstellen und richten Sie das Projekt ein  
  
1.  Erstellen einer WPF-Anwendungsprojekt mit dem Namen `WPFWithWFAndDatabinding`.  
  
2.  Fügen Sie im Projektmappen-Explorer Verweise auf die folgenden Assemblys hinzu.  
  
    -   WindowsFormsIntegration  
  
    -   System.Windows.Forms  
  
3.  Öffnen Sie "MainWindow.xaml" in der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
4.  In der <xref:System.Windows.Window> -Element, fügen Sie die folgenden [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Namespacezuordnung.  
  
    ```xaml  
    xmlns:wf="clr-namespace:System.Windows.Forms;assembly=System.Windows.Forms"  
    ```  
  
5.  Nennen Sie das <xref:System.Windows.Controls.Grid> Element `mainGrid` durch Zuweisen der <xref:System.Windows.FrameworkElement.Name%2A> Eigenschaft.  
  
     [!code-xaml[WPFWithWFAndDatabinding#8](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#8)]  
  
## <a name="defining-the-data-template"></a>Definieren der Datenvorlage  
 Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement. Das folgende Codebeispiel definiert eine <xref:System.Windows.DataTemplate> Objekt mit dem Namen `ListItemsTemplate` , die die visuelle Struktur steuert die <xref:System.Windows.Controls.ListBox> Steuerelement. Dies <xref:System.Windows.DataTemplate> zugewiesen wird die <xref:System.Windows.Controls.ListBox> des Steuerelements <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> Eigenschaft.  
  
#### <a name="to-define-the-data-template"></a>Definieren der Datenvorlage  
  
-   Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#3)]  
  
## <a name="specifying-the-form-layout"></a>Angeben des Formularlayouts  
 Das Layout des Formulars wird durch ein Raster mit drei Zeilen und drei Spalten definiert. <xref:System.Windows.Controls.Label> -Steuerelemente werden bereitgestellt, um jede Spalte in der Customers-Tabelle zu identifizieren.  
  
#### <a name="to-set-up-the-grid-layout"></a>Einrichten des Rasterlayouts  
  
-   Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#4)]  
  
#### <a name="to-set-up-the-label-controls"></a>Label-Steuerelemente einrichten  
  
-   Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#5](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#5)]  
  
## <a name="specifying-data-bindings"></a>Angeben von Datenbindungen  
 Die Masterliste der Kunden wird angezeigt, einem <xref:System.Windows.Controls.ListBox> Steuerelement. Der angefügte `ListItemsTemplate` bindet eine <xref:System.Windows.Controls.TextBlock> die Steuerung an die `ContactName` Feld aus der Datenbank.  
  
 Die Details für jeden Kundendatensatz werden angezeigt, in mehreren <xref:System.Windows.Controls.TextBox> Steuerelemente.  
  
#### <a name="to-specify-data-bindings"></a>Datenbindungen angeben  
  
-   Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     Die <xref:System.Windows.Data.Binding> -Klasse bindet die <xref:System.Windows.Controls.TextBox> Steuerelemente an die entsprechenden Felder in der Datenbank.  
  
     [!code-xaml[WPFWithWFAndDatabinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#6)]  
  
## <a name="displaying-data-by-using-interoperation"></a>Anzeigen von Daten mithilfe von Interoperation  
 Die Aufträge an den ausgewählten Kunden entsprechen, werden angezeigt, einem <xref:System.Windows.Forms.DataGridView?displayProperty=nameWithType> Steuerelement mit dem Namen `dataGridView1`. Die `dataGridView1` -Steuerelement an die Datenquelle im Code-Behind-Datei gebunden ist. Ein <xref:System.Windows.Forms.Integration.WindowsFormsHost> Steuerelement ist das übergeordnete Element dieses [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] Steuerelement.  
  
#### <a name="to-display-data-in-the-datagridview-control"></a>Anzeigen von Daten im DataGridView-Steuerelement  
  
-   Kopieren Sie den folgenden XAML in die <xref:System.Windows.Controls.Grid> Deklaration des Elements.  
  
     [!code-xaml[WPFWithWFAndDatabinding#7](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml#7)]  
  
## <a name="adding-the-data-source-to-the-project"></a>Hinzufügen der Datenquelle zum Projekt  
 Mit Visual Studio können Sie problemlos eine Datenquelle zum Projekt hinzufügen. Bei diesem Vorgang wird dem Projekt ein stark typisiertes Dataset hinzugefügt. Mehrere andere Unterstützungsklassen, wie z.B. Tabellenadapter für jede der ausgewählten Tabellen, werden ebenfalls hinzugefügt.  
  
#### <a name="to-add-the-data-source"></a>So fügen Sie die Datenquelle hinzu  
  
1.  Von der **Daten** , wählen Sie im Menü **neue Datenquelle hinzufügen**.  
  
2.  In der **Assistenten zur Datenquellenkonfiguration**, erstellen Sie eine Verbindung zur Northwind-Datenbank mithilfe eines Datasets. Weitere Informationen finden Sie unter [Vorgehensweise: Verbinden mit Daten in einer Datenbank](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/fxk9yw1t(v=vs.120)).  
  
3.  Wenn Sie gefragt werden durch die **Assistenten zur Datenquellenkonfiguration**, speichern Sie die Verbindungszeichenfolge als `NorthwindConnectionString`.  
  
4.  Wenn Sie aufgefordert werden, Ihre Datenbankobjekte auszuwählen, wählen Sie die `Customers` und `Orders` Tabellen und Name der generierten DataSet `NorthwindDataSet`.  
  
## <a name="binding-to-the-data-source"></a>Bindung an die Datenquelle  
 Die <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType> Komponente bietet eine einheitliche Schnittstelle für die Anwendungsdatenquelle. Die Bindung an die Datenquelle wird in der CodeBehind-Datei implementiert.  
  
#### <a name="to-bind-to-the-data-source"></a>Bindung an die Datenquelle  
  
1.  Öffnen Sie die CodeBehind-Datei mit die Namen „MainWindow.Xaml.vb“ bzw. „MainWindow.Xaml.cs“.  
  
2.  Kopieren Sie den folgenden Code der `MainWindow` Definition der Klasse.  
  
     Dieser Code deklariert die <xref:System.Windows.Forms.BindingSource> Komponente und zugeordnete Hilfsklassen, die mit der Datenbank herstellen.  
  
     [!code-csharp[WPFWithWFAndDatabinding#11](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#11)]
     [!code-vb[WPFWithWFAndDatabinding#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#11)]

3.  Kopieren Sie den folgenden Code in den Konstruktor.

     Dieser Code erstellt und initialisiert die <xref:System.Windows.Forms.BindingSource> Komponente.

     [!code-csharp[WPFWithWFAndDatabinding#12](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#12)]
     [!code-vb[WPFWithWFAndDatabinding#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#12)]

4.  Öffnen Sie „MainWindow.xaml“.

5.  Wählen Sie in der Entwurfsansicht oder XAML-Ansicht der <xref:System.Windows.Window> Element.

6.  Klicken Sie im Eigenschaftenfenster auf die **Ereignisse** Registerkarte.

7.  Doppelklicken Sie auf die <xref:System.Windows.FrameworkElement.Loaded> Ereignis.

8.  Kopieren Sie den folgenden Code der <xref:System.Windows.FrameworkElement.Loaded> -Ereignishandler.

     Dieser Code weist die <xref:System.Windows.Forms.BindingSource> -Komponente als Datenkontext und füllt die `Customers` und `Orders` Adapterobjekte.

     [!code-csharp[WPFWithWFAndDatabinding#13](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#13)]
     [!code-vb[WPFWithWFAndDatabinding#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#13)]

9. Kopieren Sie den folgenden Code der `MainWindow` Definition der Klasse.

     Diese Methode verarbeitet das <xref:System.Windows.Data.CollectionView.CurrentChanged> Ereignis und das aktuelle Element der Datenbindung aktualisiert.

     [!code-csharp[WPFWithWFAndDatabinding#14](~/samples/snippets/csharp/VS_Snippets_Wpf/WPFWithWFAndDatabinding/CSharp/WPFWithWFAndDatabinding/Window1.xaml.cs#14)]
     [!code-vb[WPFWithWFAndDatabinding#14](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WPFWithWFAndDatabinding/VisualBasic/WPFWithWFAndDatabinding/Window1.xaml.vb#14)]  
  
10. Drücken Sie F5, um die Anwendung zu erstellen und auszuführen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Entwerfen von XAML-Code in Visual Studio](/visualstudio/designers/designing-xaml-in-visual-studio)
- [Datenbindung im Beispiel für Hybrid-Anwendungen](https://go.microsoft.com/fwlink/?LinkID=159983)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten Windows Forms-Steuerelements in WPF](walkthrough-hosting-a-windows-forms-composite-control-in-wpf.md)
- [Exemplarische Vorgehensweise: Hosten eines zusammengesetzten WPF-Steuerelements in Windows Forms](walkthrough-hosting-a-wpf-composite-control-in-windows-forms.md)
