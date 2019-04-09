---
title: 'Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], cell customization
- data grids [Windows Forms], customizing cells
- data grids [Windows Forms], font styles
- data grids [Windows Forms], color styles
ms.assetid: 588f2c57-d963-41b1-9c1d-d02d71818113
ms.openlocfilehash: 737a4b943125245a2916bbf6b24b8abdffa8e371
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215341"
---
# <a name="how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control"></a>Vorgehensweise: Festlegen von Schriftart- und Farbstilen im DataGridView-Steuerelement in Windows Forms
Sie können die visuelle Darstellung von Zellen in einem <xref:System.Windows.Forms.DataGridView>-Steuerelement angeben, indem Sie die Eigenschaften der <xref:System.Windows.Forms.DataGridViewCellStyle>-Klasse festlegen. Sie können Instanzen dieser Klasse aus verschiedenen Eigenschaften der <xref:System.Windows.Forms.DataGridView>-Klasse und deren Assistentenklassen abrufen, oder Sie können <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte instanziieren, um sie diesen Eigenschaften zuzuweisen.  
  
 In den folgenden Vorgehensweisen wird grundsätzlich veranschaulicht, wie die Zellendarstellung mithilfe der <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>-Eigenschaft angepasst werden kann. Jede Zelle in dem Steuerelement erbt die Stile, die über diese Eigenschaft angegeben sind, es sei denn, die Stile werden auf Spalten-, Zeilen- oder Zellenebene überschrieben. Beispielsweise Vererbung von Stilen finden Sie unter [Vorgehensweise: Festlegen von Standardzellenformaten für das Windows-DataGridView-Steuerelement Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). Informationen über weitere Verwendungsmöglichkeiten der <xref:System.Windows.Forms.DataGridViewCellStyle>-Klasse finden Sie in den Themen, die im Abschnitt "Siehe auch" aufgeführt sind.  
  
 Visual Studio bietet umfassende Unterstützung für diese Aufgabe.  Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Festlegen von standardmäßigen Zellenstilen und Datenformaten für die Windows Forms-DataGridView-Steuerelement mithilfe des Designers](default-cell-styles-datagridview.md).  
  
### <a name="to-specify-the-font-used-by-datagridview-cells"></a>So geben Sie die von DataGridView-Zellen verwendete Schriftart an  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewCellStyle.Font%2A>-Eigenschaft einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um die Schriftart für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#101)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#101](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#101)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-datagridview-cells"></a>So geben Sie die Vordergrund- und Hintergrundfarben von DataGridView-Zellen an  
  
-   Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.ForeColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.BackColor%2A> einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um diese Stile für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#102)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#102](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#102)]  
  
### <a name="to-specify-the-foreground-and-background-colors-of-selected-datagridview-cells"></a>So geben Sie die Vordergrund- und Hintergrundfarben von ausgewählten DataGridView-Zellen an  
  
-   Legen Sie die Eigenschaften <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionForeColor%2A> und <xref:System.Windows.Forms.DataGridViewCellStyle.SelectionBackColor%2A> einer <xref:System.Windows.Forms.DataGridViewCellStyle>-Instanz fest. Im folgenden Codebeispiel wird die <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>-Eigenschaft verwendet, um diese Stile für das gesamte Steuerelement festzulegen.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#103)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#103](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#103)]  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#100)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#100)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die Assemblys <xref:System?displayProperty=nameWithType>, <xref:System.Drawing?displayProperty=nameWithType> und <xref:System.Windows.Forms?displayProperty=nameWithType>.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Um maximale Skalierbarkeit zu erreichen, sollten Sie <xref:System.Windows.Forms.DataGridViewCellStyle>-Objekte für mehrere Zeilen, Spalten oder Zellen, in denen dieselben Stile verwendet werden, gemeinsam verwenden, anstatt die Stileigenschaften für jedes einzelne Element festzulegen. Weitere Informationen finden Sie unter [Best Practices für das Skalieren des DataGridView-Steuerelements in Windows Forms](best-practices-for-scaling-the-windows-forms-datagridview-control.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- [Grundlegende Formatierungen und Formate im DataGridView-Steuerelement in Windows Forms](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)
- [Zellstile im DataGridView-Steuerelement in Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
