---
title: Übersicht über das ListView-Steuerelement (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ListView
helpviewer_keywords:
- lists
- ListView control [Windows Forms], about ListView control
- list views
ms.assetid: c9ef56c1-3bb1-4101-9f4e-e95e720f2756
ms.openlocfilehash: a60c415427a1be994f8081725f20e867dca66aa1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012801"
---
# <a name="listview-control-overview-windows-forms"></a>Übersicht über das ListView-Steuerelement (Windows Forms)
Mit dem <xref:System.Windows.Forms.ListView>-Steuerelement in Windows Forms wird eine Liste von Elementen mit Symbolen angezeigt. Mit einer Listenansicht können Sie eine Benutzeroberfläche erstellen, deren Darstellung dem rechten Fensterbereich von Windows Explorer ähnelt. Das Steuerelement hat vier Anzeigemodi an: LargeIcon "," SmallIcon "," Liste, und "Details".  
  
## <a name="what-you-can-do-with-the-listview-control"></a>Was können Sie mit dem ListView-Steuerelement tun.  
  
> [!NOTE]
>  Eine zusätzliche Ansicht nebeneinander, ist nur unter Windows XP und das Betriebssystem Windows Server 2003 zur Verfügung. Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren von Tile-Ansicht in einer Windows Forms-ListView-Steuerelement](how-to-enable-tile-view-in-a-windows-forms-listview-control.md).  
  
 Der Modus LargeIcon Anzeigen großer Symbole neben den Elementtext im; die Elemente werden in mehreren Spalten auf, wenn das Steuerelement groß genug ist. Der SmallIcon-Modus ist identisch, außer dass es sich um kleine Symbole angezeigt. Die Listenmodus werden kleine Symbole angezeigt, aber es ist immer in einer einzelnen Spalte. Die Details-Modus zeigt die Elemente in mehreren Spalten. Weitere Informationen finden Sie unter [Vorgehensweise: Hinzufügen von Spalten, die Windows Forms-ListView-Steuerelement](how-to-add-columns-to-the-windows-forms-listview-control.md). Der Ansichtsmodus richtet sich nach der <xref:System.Windows.Forms.ListView.View%2A> Eigenschaft. Alle Ansichtsmodi können Images aus einer Bildliste anzuzeigen. Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in der Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md).  
  
 Die folgende Tabelle enthält einige der <xref:System.Windows.Forms.ListView> Member und die Ansichten, die sie in gültig sind.  
  
|ListView-Element|Ansicht|  
|---------------------|----------|  
|<xref:System.Windows.Forms.ListView.Alignment%2A> -Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoArrange%2A> -Eigenschaft|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.AutoResizeColumn%2A>-Methode|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.Columns%2A> -Eigenschaft|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.DrawSubItem> -Ereignis|<xref:System.Windows.Forms.View.Details>|  
|<xref:System.Windows.Forms.ListView.FindItemWithText%2A>-Methode|<xref:System.Windows.Forms.View.Details>, <xref:System.Windows.Forms.View.List>oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.FindNearestItem%2A>-Methode|<xref:System.Windows.Forms.View.SmallIcon> oder <xref:System.Windows.Forms.View.LargeIcon>|  
|<xref:System.Windows.Forms.ListView.GetItemAt%2A>-Methode|<xref:System.Windows.Forms.View.Details> oder <xref:System.Windows.Forms.View.Tile>|  
|<xref:System.Windows.Forms.ListView.Groups%2A> -Eigenschaft|Alle Ansichten, mit Ausnahme <xref:System.Windows.Forms.View.List>|  
|<xref:System.Windows.Forms.ListView.HeaderStyle%2A> -Eigenschaft|<xref:System.Windows.Forms.View.Details>.|  
|<xref:System.Windows.Forms.ListView.InsertionMark%2A> -Eigenschaft|<xref:System.Windows.Forms.View.LargeIcon>, <xref:System.Windows.Forms.View.SmallIcon>oder <xref:System.Windows.Forms.View.Tile>|  
  
 Die wichtigste Eigenschaft von der <xref:System.Windows.Forms.ListView> Steuerelement <xref:System.Windows.Forms.ListView.Items%2A>, die vom Steuerelement angezeigten Elemente enthält. Die <xref:System.Windows.Forms.ListView.SelectedItems%2A> Eigenschaft enthält eine Auflistung der derzeit im Steuerelement ausgewählten Elemente. Der Benutzer kann mehrere Elemente auswählen, z. B. um Drag & drop mehrere Elemente gleichzeitig zu einem anderen Steuerelement, wenn die <xref:System.Windows.Forms.ListView.MultiSelect%2A> -Eigenschaftensatz auf `true`. Die <xref:System.Windows.Forms.ListView> Steuerelement können Sie die Kontrollkästchen neben den Elementen angezeigt, wenn die <xref:System.Windows.Forms.ListView.CheckBoxes%2A> -Eigenschaftensatz auf `true`.  
  
 Die <xref:System.Windows.Forms.ListView.Activation%2A> Eigenschaft bestimmt, welche Art von Aktion des Benutzers ausführen muss, um ein Element in der Liste aktivieren: die Optionen sind <xref:System.Windows.Forms.ItemActivation.Standard>, <xref:System.Windows.Forms.ItemActivation.OneClick>, und <xref:System.Windows.Forms.ItemActivation.TwoClick>. <xref:System.Windows.Forms.ItemActivation.OneClick> -Aktivierung erfordert ein Klick auf das Element zu aktivieren. <xref:System.Windows.Forms.ItemActivation.TwoClick> Aktivierung muss der Benutzer doppelklicken, um das Element zu aktivieren. die Farbe des Elementtextes ändert sich ein einzigen Klick. <xref:System.Windows.Forms.ItemActivation.Standard> Aktivierung muss der Benutzer doppelklicken, um ein Element zu aktivieren, aber das Element ändert sich nicht auf die Darstellung.  
  
 Die <xref:System.Windows.Forms.ListView> Steuerelement unterstützt auch die visuellen Stile und andere verfügbare Features auf der Windows XP-Plattform, einschließlich der Gruppierung, Ansicht "Nebeneinander" und Einfügen von Markierungen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ListView>
- [ListView-Steuerelement](listview-control-windows-forms.md)
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen mit dem ListView-Steuerelement in Windows Forms](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Spalten zu dem ListView-Steuerelement in Windows Forms](how-to-add-columns-to-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Symbolen für das ListView-Steuerelement in Windows Forms](how-to-display-icons-for-the-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen von Unterelementen in Spalten mit dem ListView-Steuerelement in Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)
- [Vorgehensweise: Wählen Sie ein Element in dem ListView-Steuerelement in Windows Forms](how-to-select-an-item-in-the-windows-forms-listview-control.md)
- [Vorgehensweise: Gruppieren von Elementen in ein ListView-Steuerelement in Windows Forms](how-to-group-items-in-a-windows-forms-listview-control.md)
- [Vorgehensweise: Anzeigen einer Einfügemarke in ein ListView-Steuerelement in Windows Forms](how-to-display-an-insertion-mark-in-a-windows-forms-listview-control.md)
- [Vorgehensweise: Hinzufügen von Suchfunktionen zu einem ListView-Steuerelement](how-to-add-search-capabilities-to-a-listview-control.md)
- [Vorgehensweise: Hinzufügen von benutzerdefinierten Daten zu einem TreeView- oder ListView-Steuerelement (Windows Forms)](add-custom-information-to-a-treeview-or-listview-control-wf.md)
- [Vorgehensweise: Erstellen einer Multipane-Benutzeroberfläche mit Windows Forms](how-to-create-a-multipane-user-interface-with-windows-forms.md)
