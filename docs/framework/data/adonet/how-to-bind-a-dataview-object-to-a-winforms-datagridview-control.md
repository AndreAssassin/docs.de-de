---
title: 'Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 3a3089073cdc5afb4ee51caca9114b401c740b45
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795004"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>Vorgehensweise: Binden eines DataView-Objekts an ein Windows Forms-DataGridView-Steuerelement
Das <xref:System.Windows.Forms.DataGridView>-Steuerelement ermöglicht die flexible Anzeige von Daten in tabellarischer Form. Das <xref:System.Windows.Forms.DataGridView> unterstützt das Standard-Datenbindungsmodell von Windows Forms und ermöglicht so die Bindung an eine <xref:System.Data.DataView> und eine Vielzahl anderer Datenquellen. In den meisten Fällen dürfte jedoch eine Bindung an eine <xref:System.Windows.Forms.BindingSource>-Komponente erfolgen, die sich um die Details der Interaktion mit der Datenquelle kümmert.  
  
 Weitere Informationen zum-Steuer <xref:System.Windows.Forms.DataGridView> Element finden Sie unter Übersicht über das [DataGridView-Steuer](../../winforms/controls/datagridview-control-overview-windows-forms.md)Element.  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>So verbinden Sie ein "DataGridView"-Steuerelement mit einer "DataView"  
  
1. Implementieren Sie eine Methode, mit der die Details des Abrufens von Daten aus einer Datenbank behandelt werden. Das folgende Codebeispiel implementiert eine `GetData`-Methode, die eine <xref:System.Data.SqlClient.SqlDataAdapter>-Komponente initialisiert, und verwendet diese, um ein <xref:System.Data.DataSet> aufzufüllen. Sorgen Sie dafür, dass die `connectionString`-Variable auf einen Wert gesetzt wird, der für Ihre Datenbank geeignet ist. Sie benötigen Zugriff auf einen Server, auf dem die SQL Server-AdventureWorks-Beispieldatenbank installiert ist.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. Binden Sie im <xref:System.Windows.Forms.Form.Load>-Ereignishandler Ihres Formulars das <xref:System.Windows.Forms.DataGridView>-Steuerelement an die <xref:System.Windows.Forms.BindingSource>-Komponente, und verwenden Sie die `GetData`-Methode, um Daten aus der Datenbank abzurufen. Der <xref:System.Data.DataView> wird aus einer LINQ to DataSet Abfrage über den Kontakt <xref:System.Data.DataTable> erstellt und dann an die <xref:System.Windows.Forms.BindingSource> -Komponente gebunden.  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung und LINQ to DataSet](data-binding-and-linq-to-dataset.md)
