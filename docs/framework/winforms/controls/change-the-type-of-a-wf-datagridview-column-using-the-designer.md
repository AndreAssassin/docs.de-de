---
title: 'Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: e87017f3698bc88a123d8a0ba0df5dbe2b7bbfd9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61939021"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a>Vorgehensweise: Ändern des Typs einer DataGridView-Spalte in Windows Forms mithilfe des Designers
In einigen Fällen wird der Datentyp einer Spalte ändern möchten, die bereits zu einem Windows Forms hinzugefügt wurde <xref:System.Windows.Forms.DataGridView> Steuerelement. Beispielsweise empfiehlt es sich um die Typen von einigen Spalten zu ändern, die automatisch generiert werden, wenn Sie das Steuerelement an eine Datenquelle binden. Dies ist nützlich, wenn die Tabelle, die Sie anzeigen, Spalten, die Fremdschlüssel für Zeilen in einer verknüpften Tabelle verfügt. In diesem Fall empfiehlt es sich um die Textspalten für das Feld zu ersetzen, die diese Fremdschlüssel Spalten mit Kombinationsfeldern an, die mehr sinnvolle Werte aus der verknüpften Tabelle anzuzeigen.  
  
 Das folgende Verfahren erfordert eine **Windows-Anwendung** Projekt ein Formular mit eine <xref:System.Windows.Forms.DataGridView> Steuerelement. Informationen zum Einrichten eines solchen Projekts finden Sie unter [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project) und [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen. Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern. Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a>So ändern Sie den Datentyp einer Spalte mithilfe des Designers  
  
1. Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) auf der oberen rechten Ecke des der <xref:System.Windows.Forms.DataGridView> steuern, und wählen Sie dann **Spalten bearbeiten**.  
  
2. Wählen Sie eine Spalte aus der **Selected Columns** Liste.  
  
3. In der **Spalteneigenschaften** Raster legen die `ColumnType` Eigenschaft in den Spaltentyp der neuen.  
  
    > [!NOTE]
    >  Die `ColumnType` Eigenschaft ist eine Design-Time-only-Eigenschaft, die die Klasse, die den Spaltentyp darstellt. Es ist keiner vorhandenen Eigenschaft, die in einer Spaltenklasse definiert.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [Vorgehensweise: Erstellen eines Windows Forms-Anwendungsprojekts](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](how-to-add-controls-to-windows-forms.md)
