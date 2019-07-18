---
title: Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?
ms.date: 03/30/2017
helpviewer_keywords:
- ListBox control [Windows Forms], adding and removing items
- ListBox control [Windows Forms], vs. ComboBox
- bound controls [Windows Forms], combo boxes
- Windows Forms controls, data binding
- ComboBox control [Windows Forms], compared to ListBox
- combo boxes [Windows Forms], compared to list boxes
- ListBox control [Windows Forms], accessing items
- ListCount property
ms.assetid: 7bcaea58-1cfa-46db-9baf-b75a69d8f9ec
ms.openlocfilehash: 8a2429049acf1a22edde8d132ece17da4e91f1db
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61759829"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a>Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?
Die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> Steuerelemente weisen ähnliche Verhaltensweisen und in einigen Fällen austauschbar. Es gibt jedoch Situationen, wenn eine Aufgabe besser geeignet ist.  
  
 Im Allgemeinen ist ein Kombinationsfeld geeignet, wenn es eine Liste der empfohlenen Optionen, und ein Listenfeld, das ist geeignet, wenn Sie Eingabe, was in der Liste ist beschränken möchten. Ein Kombinationsfeld enthält ein Textfeld, Optionen, die nicht in der Liste im eingegeben werden können. Die Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>. In diesem Fall wird das Steuerelement ein Element auswählen, wenn Sie die ersten Buchstaben eingeben.  
  
 Darüber hinaus sparen Kombinationsfelder Platz auf einem Formular. Da die vollständige Liste nicht angezeigt wird, bis der Benutzer auf den Pfeil klickt, passt ein Kombinationsfeld in einem kleinen Bereich, in denen ein Listenfeld, das nicht passen würde. Eine Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.Simple>: die vollständige Liste angezeigt wird, und das Kombinationsfeld beansprucht mehr Platz als ein Listenfeld, das der Fall.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement](add-and-remove-items-from-a-wf-combobox.md)
- [Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [Windows Forms-Steuerelemente zum Auflisten von Optionen](windows-forms-controls-used-to-list-options.md)
