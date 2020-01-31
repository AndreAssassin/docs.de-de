---
title: ComboBox und ListBox
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
ms.openlocfilehash: 7087760a393bb58d83d899c1741c745fb28585bb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739925"
---
# <a name="when-to-use-a-windows-forms-combobox-instead-of-a-listbox"></a><span data-ttu-id="9c37c-102">Wann ist ein Kombinationsfeld von Windows Forms dem Listenfeld vorzuziehen?</span><span class="sxs-lookup"><span data-stu-id="9c37c-102">When to Use a Windows Forms ComboBox Instead of a ListBox</span></span>
<span data-ttu-id="9c37c-103">Die <xref:System.Windows.Forms.ComboBox>-und die <xref:System.Windows.Forms.ListBox>-Steuerelemente weisen ein ähnliches Verhalten auf, und in manchen Fällen ist es möglicherweise austauschbar.</span><span class="sxs-lookup"><span data-stu-id="9c37c-103">The <xref:System.Windows.Forms.ComboBox> and the <xref:System.Windows.Forms.ListBox> controls have similar behaviors, and in some cases may be interchangeable.</span></span> <span data-ttu-id="9c37c-104">Es gibt jedoch Zeiten, in denen eine oder die andere für eine Aufgabe besser geeignet ist.</span><span class="sxs-lookup"><span data-stu-id="9c37c-104">There are times, however, when one or the other is more appropriate to a task.</span></span>  
  
 <span data-ttu-id="9c37c-105">Im Allgemeinen ist ein Kombinations Feld geeignet, wenn eine Liste der vorgeschlagenen Optionen vorliegt, und ein Listenfeld ist geeignet, wenn Sie die Eingabe auf die Liste der Listen beschränken möchten.</span><span class="sxs-lookup"><span data-stu-id="9c37c-105">Generally, a combo box is appropriate when there is a list of suggested choices, and a list box is appropriate when you want to limit input to what is on the list.</span></span> <span data-ttu-id="9c37c-106">Ein Kombinations Feld enthält ein Textfeld Feld, sodass die Auswahl nicht in der Liste eingegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="9c37c-106">A combo box contains a text box field, so choices not on the list can be typed in.</span></span> <span data-ttu-id="9c37c-107">Die Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="9c37c-107">The exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.DropDownList>.</span></span> <span data-ttu-id="9c37c-108">In diesem Fall wählt das Steuerelement ein Element aus, wenn Sie seinen ersten Buchstaben eingeben.</span><span class="sxs-lookup"><span data-stu-id="9c37c-108">In that case, the control will select an item if you type its first letter.</span></span>  
  
 <span data-ttu-id="9c37c-109">Außerdem sparen Kombinations Felder Platz auf einem Formular.</span><span class="sxs-lookup"><span data-stu-id="9c37c-109">In addition, combo boxes save space on a form.</span></span> <span data-ttu-id="9c37c-110">Da die vollständige Liste erst angezeigt wird, wenn der Benutzer auf den Pfeil nach unten klickt, kann ein Kombinations Feld problemlos in einen kleinen Bereich passen, in dem ein Listenfeld nicht passt.</span><span class="sxs-lookup"><span data-stu-id="9c37c-110">Because the full list is not displayed until the user clicks the down arrow, a combo box can easily fit in a small space where a list box would not fit.</span></span> <span data-ttu-id="9c37c-111">Eine Ausnahme ist, wenn die <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A>-Eigenschaft auf <xref:System.Windows.Forms.ComboBoxStyle.Simple>festgelegt ist: die vollständige Liste wird angezeigt, und das Kombinations Feld benötigt mehr Platz als ein Listenfeld.</span><span class="sxs-lookup"><span data-stu-id="9c37c-111">An exception is when the <xref:System.Windows.Forms.ComboBox.DropDownStyle%2A> property is set to <xref:System.Windows.Forms.ComboBoxStyle.Simple>: the full list is displayed, and the combo box takes up more room than a list box would.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c37c-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c37c-112">See also</span></span>

- <xref:System.Windows.Forms.ComboBox>
- <xref:System.Windows.Forms.ListBox>
- [<span data-ttu-id="9c37c-113">Gewusst wie: Hinzufügen und Entfernen von Elementen in bzw. aus ComboBox-, ListBox- oder CheckedListBox-Steuerelementen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c37c-113">How to: Add and Remove Items from a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](add-and-remove-items-from-a-wf-combobox.md)
- [<span data-ttu-id="9c37c-114">Gewusst wie: Sortieren des Inhalts eines ComboBox-, ListBox- oder CheckedListBox-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="9c37c-114">How to: Sort the Contents of a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>](sort-the-contents-of-a-wf-combobox-listbox-or-checkedlistbox-control.md)
- [<span data-ttu-id="9c37c-115">Windows Forms-Steuerelemente zum Auflisten von Optionen</span><span class="sxs-lookup"><span data-stu-id="9c37c-115">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
