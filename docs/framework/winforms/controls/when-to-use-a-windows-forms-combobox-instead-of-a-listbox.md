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
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="8c44b-102">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="8c44b-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="8c44b-103">Die <xref:System.Windows.Forms.ComboBox> und <xref:System.Windows.Forms.ListBox> Steuerelemente weisen ähnliche Verhaltensweisen und in einigen Fällen austauschbar.</span><span class="sxs-lookup"><span data-stu-id="8c44b-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="8c44b-104">Es gibt jedoch Situationen, wenn eine Aufgabe besser geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="8c44b-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="8c44b-105">Im Allgemeinen ist ein Kombinationsfeld geeignet, wenn es eine Liste der empfohlenen Optionen, und ein Listenfeld, das ist geeignet, wenn Sie Eingabe, was in der Liste ist beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="8c44b-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="8c44b-106">Ein Kombinationsfeld enthält ein Textfeld, Optionen, die nicht in der Liste im eingegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="8c44b-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="8c44b-107">Die Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span><span class="sxs-lookup"><span data-stu-id="8c44b-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="8c44b-108">In diesem Fall wird das Steuerelement ein Element auswählen, wenn Sie die ersten Buchstaben eingeben.</span><span class="sxs-lookup"><span data-stu-id="8c44b-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="8c44b-109">Darüber hinaus sparen Kombinationsfelder Platz auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="8c44b-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="8c44b-110">Da die vollständige Liste nicht angezeigt wird, bis der Benutzer auf den Pfeil klickt, passt ein Kombinationsfeld in einem kleinen Bereich, in denen ein Listenfeld, das nicht passen würde.</span><span class="sxs-lookup"><span data-stu-id="8c44b-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="8c44b-111">Eine Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> -Eigenschaftensatz auf <xref:System.Windows.Forms.ComboBoxStyle.Simple>: die vollständige Liste angezeigt wird, und das Kombinationsfeld beansprucht mehr Platz als ein Listenfeld, das der Fall.</span><span class="sxs-lookup"><span data-stu-id="8c44b-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c44b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8c44b-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="8c44b-113">Vorgehensweise: Hinzufügen und Entfernen von Elementen aus einer Windows Forms, ComboBox-, ListBox- oder CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8c44b-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="8c44b-114">Vorgehensweise: Sortieren des Inhalts einer Windows Forms-ComboBox-, ListBox- oder CheckedListBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="8c44b-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="8c44b-115">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="8c44b-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
