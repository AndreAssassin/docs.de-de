---
title: 'Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
ms.openlocfilehash: 8904eff39b7278b2a185cc5e2f738ece1e8e88e4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59306507"
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a>Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms
Sie können das Sortieren und Filtern von Funktion verfügbar machen <xref:System.Windows.Forms.BindingSource> steuern, über die <xref:System.Windows.Forms.BindingSource.Sort%2A> und <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaften. Sie können anwenden, einfache Sortierung, wenn die zugrunde liegende Datenquelle ist ein <xref:System.ComponentModel.IBindingList>, und Sie können Filter anwenden und erweiterte Sortierung, wenn die Datenquelle ist ein <xref:System.ComponentModel.IBindingListView>. Die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft ist erforderlich, Standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] Syntax: eine Zeichenfolge, die den Namen einer Spalte mit Daten in der Datenquelle darstellt, gefolgt von `ASC` oder `DESC` an, ob die Liste in aufsteigender oder absteigender Reihenfolge sortiert werden sollen. Sie können erweiterte Sortierung oder mehrere Spalten zu sortieren, nach jeder Spalte durch ein Komma als Trennzeichen trennen festlegen. Die <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft akzeptiert einen Zeichenfolgenausdruck.  
  
> [!NOTE]
>  Das Speichern vertraulicher Informationen (z. B. eines Kennworts) innerhalb der Verbindungszeichenfolge kann die Sicherheit einer Anwendung beeinträchtigen. Der Zugriff auf eine Datenbank lässt sich mithilfe der Windows-Authentifizierung (wird auch als integrierte Sicherheit bezeichnet) sicherer steuern. Weitere Informationen finden Sie unter [Protecting Connection Information (Schützen von Verbindungsinformationen)](../../data/adonet/protecting-connection-information.md).  
  
### <a name="to-filter-data-with-the-bindingsource"></a>Zum Filtern von Daten mithilfe der BindingSource  
  
-   Legen Sie die <xref:System.Windows.Forms.BindingSource.Filter%2A> Eigenschaft, um den Ausdruck ein, Sie möchten.  
  
     Das folgende Codebeispiel zeigt ist der Ausdruck einen Spaltennamen, gefolgt von dem Wert, der für die Spalte aus.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a>So sortieren Sie Daten mithilfe der BindingSource  
  
1. Legen Sie die <xref:System.Windows.Forms.BindingSource.Sort%2A> Eigenschaft auf den gewünschten gefolgt von Spaltennamen `ASC` oder `DESC` die aufsteigende oder absteigende Reihenfolge an.  
  
2. Trennen Sie mehrere Spalten durch ein Komma.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel lädt Daten aus der Customers-Tabelle der Northwind-Beispieldatenbank in einer <xref:System.Windows.Forms.DataGridView> zu steuern, gefiltert und sortiert die angezeigten Daten.  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um dieses Beispiel auszuführen, fügen Sie den Code in ein Formular enthält ein <xref:System.Windows.Forms.BindingSource> mit dem Namen `BindingSource1` und <xref:System.Windows.Forms.DataGridView> mit dem Namen `dataGridView1`. Behandeln der <xref:System.Windows.Forms.Form.Load> -Ereignis für das Formular, und rufen `InitializeSortedFilteredBindingSource` in die Load-Ereignishandlermethode.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource.Sort%2A>
- <xref:System.Windows.Forms.BindingSource.Filter%2A>
- [Vorgehensweise: Installieren von Beispieldatenbanken](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/8b6y4c7s(v=vs.120))
- [BindingSource-Komponente](bindingsource-component.md)
