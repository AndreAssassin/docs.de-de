---
title: 'Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data grids [Windows Forms], customizing rows
- DataGridView control [Windows Forms], customizing rows
ms.assetid: 6db61607-7e57-4a84-8d63-9d6a7ed7f9ff
ms.openlocfilehash: 0dba318e6aa35761f4e9471fdb13b65644747b57
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966494"
---
# <a name="how-to-use-the-row-template-to-customize-rows-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Verwenden der Zeilenvorlage zum Anpassen von Zeilen im DataGridView-Steuerelement in Windows Forms
Das <xref:System.Windows.Forms.DataGridView> -Steuerelement verwendet die Zeilen Vorlage als Grundlage für alle Zeilen, die dem Steuerelement entweder über die Datenbindung hinzugefügt werden, <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A?displayProperty=nameWithType> oder wenn die-Methode aufgerufen wird, ohne eine vorhandene zu verwendende Zeile anzugeben.  
  
 Mit der Zeilen Vorlage können Sie die Darstellung und das Verhalten von Zeilen besser steuern, <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A> als die-Eigenschaft bereitstellt. Mit der Zeilen Vorlage können Sie alle <xref:System.Windows.Forms.DataGridViewRow> Eigenschaften festlegen, einschließlich. <xref:System.Windows.Forms.DataGridViewRow.DefaultCellStyle%2A>  
  
 Es gibt einige Situationen, in denen Sie die Zeilen Vorlage verwenden müssen, um einen bestimmten Effekt zu erzielen. Beispielsweise können Informationen zur Zeilenhöhe nicht in einem <xref:System.Windows.Forms.DataGridViewCellStyle>gespeichert werden. Daher müssen Sie eine Zeilen Vorlage verwenden, um die von allen Zeilen verwendete Standardhöhe zu ändern. Die Zeilen Vorlage ist auch nützlich, wenn Sie Ihre eigenen Klassen erstellen, <xref:System.Windows.Forms.DataGridViewRow> die von abgeleitet sind, und Sie möchten, dass der benutzerdefinierte Typ verwendet wird, wenn dem Steuerelement neue Zeilen hinzugefügt werden  
  
> [!NOTE]
> Die Zeilen Vorlage wird nur verwendet, wenn Zeilen hinzugefügt werden. Vorhandene Zeilen können nicht durch Ändern der Zeilen Vorlage geändert werden.  
  
### <a name="to-use-the-row-template"></a>So verwenden Sie die Zeilen Vorlage  
  
- Legen Sie Eigenschaften für das von der <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> -Eigenschaft abgerufene Objekt fest.  
  
     [!code-cpp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CPP/datagridviewrowtemplate.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/CS/datagridviewrowtemplate.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridView.RowTemplate#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.RowTemplate/VB/datagridviewrowtemplate.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
- Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridViewRow>
- <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
