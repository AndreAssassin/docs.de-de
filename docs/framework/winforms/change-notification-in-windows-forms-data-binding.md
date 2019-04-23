---
title: Änderungsbenachrichtigung in der Windows Forms-Datenbindung
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, data binding
- Windows Forms, adding change notification for data binding
ms.assetid: b5b10f90-0585-41d9-a377-409835262a92
ms.openlocfilehash: 559cdee1cce84df1c4b838e249d11ba235a0c636
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097576"
---
# <a name="change-notification-in-windows-forms-data-binding"></a>Änderungsbenachrichtigung in der Windows Forms-Datenbindung
Einer der wichtigsten Konzepte von Windows Forms-Datenbindung ist *änderungsbenachrichtigung*. Um sicherzustellen, dass die Datenquelle und gebundenen Steuerelementen stets die neuesten Daten verfügen, müssen Sie die änderungsbenachrichtigung für die Datenbindung hinzufügen. Insbesondere möchten Sie sicherstellen, dass die gebundene Steuerelemente über Änderungen benachrichtigt werden, die mit ihrer Datenquelle vorgenommen wurden, und die Datenquelle auf die gebundenen Eigenschaften eines Steuerelements vorgenommenen Änderungen benachrichtigt.  
  
 Es gibt verschiedene Arten von änderungsbenachrichtigungen, abhängig von der Art der Datenbindung:  
  
-   Einfache Bindung, in dem eine einzelnes Steuerelement-Eigenschaft auf eine einzelne Instanz eines Objekts gebunden ist.  
  
-   Listenbasierte Bindung, z. eine einzelnes Steuerelement-Eigenschaft, die an die Eigenschaft eines Elements in einer Liste oder eine Eigenschaft des Steuerelements gebunden b., die an eine Liste der Objekte gebunden werden.  
  
 Darüber hinaus, wenn Sie Windows Forms-Steuerelemente, die Sie für die Datenbindung verwenden möchten erstellen, Sie müssen Anwenden der *PropertyName*Muster für die Steuerelemente so geändert, dass Änderungen an die gebundene Eigenschaft eines Steuerelements an weitergegeben werden die die Datenquelle.  
  
## <a name="change-notification-for-simple-binding"></a>Änderungsbenachrichtigung für die einfache Bindung  
 Bei der einfachen Bindung müssen Geschäftsobjekte änderungsbenachrichtigung bereitstellt, bei Änderung des Werts einer gebundenen Eigenschaft. Hierzu können Sie verfügbar machen eine *PropertyName*Changed-Ereignis für jede Eigenschaft des Geschäftsobjekt und binden das Geschäftsobjekt, das auf Steuerelemente mit den <xref:System.Windows.Forms.BindingSource> oder die bevorzugte Methode, die in dem das Geschäftsobjekt implementiert die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle und löst eine <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignis aus, wenn der Wert einer Eigenschaft ändert. Weitere Informationen finden Sie unter [Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle](how-to-implement-the-inotifypropertychanged-interface.md). Bei Verwendung von Objekten, implementieren die <xref:System.ComponentModel.INotifyPropertyChanged> -Schnittstelle, Sie müssen keine verwenden die <xref:System.Windows.Forms.BindingSource> auf das Objekt an ein Steuerelement zu binden während mit der <xref:System.Windows.Forms.BindingSource> wird empfohlen.  
  
## <a name="change-notification-for-list-based-binding"></a>Änderungsbenachrichtigung für die listenbasierte Bindung  
 Windows Forms, hängt von einer gebundenen Liste Eigenschaftenänderung angeben (die Eigenschaft ein listenelementwert ändert) und die Liste geändert (ein Element gelöscht oder zur Liste hinzugefügt) Informationen an Steuerelemente gebunden. Aus diesem Grund müssen aufgelistet, die für die Datenbindung verwendet implementieren die <xref:System.ComponentModel.IBindingList>, die beide Arten von änderungsbenachrichtigungen bereitstellt. Die <xref:System.ComponentModel.BindingList%601> ist eine generische Implementierung von <xref:System.ComponentModel.IBindingList> und dient zur Verwendung mit Windows Forms-Datenbindung. Können Sie erstellen eine <xref:System.ComponentModel.BindingList%601> , enthält einen Geschäftstyp für das Objekt, das implementiert <xref:System.ComponentModel.INotifyPropertyChanged> und die Liste konvertiert automatisch die <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> Ereignisse <xref:System.ComponentModel.IBindingList.ListChanged> Ereignisse. Die gebundene Liste ist keiner <xref:System.ComponentModel.IBindingList>, müssen Sie die Liste der Objekte an Windows Forms-Steuerelemente binden, indem die <xref:System.Windows.Forms.BindingSource> Komponente. Die <xref:System.Windows.Forms.BindingSource> Komponente bieten Eigenschaftenliste-Konvertierung vergleichbar mit der <xref:System.ComponentModel.BindingList%601>. Weitere Informationen finden Sie unter [Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der BindingSource und der INotifyPropertyChanged-Schnittstelle](./controls/raise-change-notifications--bindingsource.md).  
  
## <a name="change-notification-for-custom-controls"></a>Änderungsbenachrichtigung für benutzerdefinierte Steuerelemente  
 Zum Schluss auf der Seite des Steuerelements verfügbar machen. ein *PropertyName*Changed-Ereignis für jede Eigenschaft, die an Daten gebunden werden soll. Die Änderungen an der Eigenschaft des Steuerelements werden dann an die gebundene Datenquelle weitergegeben werden. Weitere Informationen finden Sie unter [Vorgehensweise: Anwenden des PropertyNameChanged-Musters](how-to-apply-the-propertynamechanged-pattern.md)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.ComponentModel.INotifyPropertyChanged>
- <xref:System.ComponentModel.BindingList%601>
- [Windows Forms-Datenbindung](windows-forms-data-binding.md)
- [Von Windows Forms unterstützte Datenquellen](data-sources-supported-by-windows-forms.md)
- [Datenbindung und Windows Forms](data-binding-and-windows-forms.md)
