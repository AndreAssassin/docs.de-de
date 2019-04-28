---
title: 'Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)'
ms.date: 03/30/2017
helpviewer_keywords:
- TextBox control [Windows Forms], read-only
- read-only text boxes
- text boxes [Windows Forms], read-only
ms.assetid: 60baa9ab-fa57-44ad-bb7c-61b05aa64296
ms.openlocfilehash: 72dc188993474ad4b39f0cfa74cadffdb99ff46f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61746832"
---
# <a name="how-to-create-a-read-only-text-box-windows-forms"></a><span data-ttu-id="db7a5-102">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="db7a5-102">How to: Create a Read-Only Text Box (Windows Forms)</span></span>
<span data-ttu-id="db7a5-103">Sie können ein bearbeitbares Windows Forms-Text-Feld in ein schreibgeschütztes Steuerelement umwandeln.</span><span class="sxs-lookup"><span data-stu-id="db7a5-103">You can transform an editable Windows Forms text box into a read-only control.</span></span> <span data-ttu-id="db7a5-104">Beispielsweise kann im Textfeld einen Wert angezeigt, der in der Regel bearbeitet wird, aber möglicherweise nicht aktuell, aufgrund des Zustands der Anwendung.</span><span class="sxs-lookup"><span data-stu-id="db7a5-104">For example, the text box may display a value that is usually edited but may not be currently, due to the state of the application.</span></span>  
  
### <a name="to-create-a-read-only-text-box"></a><span data-ttu-id="db7a5-105">Erstellen ein schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="db7a5-105">To create a read-only text box</span></span>  
  
1. <span data-ttu-id="db7a5-106">Legen Sie die <xref:System.Windows.Forms.TextBox> des Steuerelements <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft `true`.</span><span class="sxs-lookup"><span data-stu-id="db7a5-106">Set the <xref:System.Windows.Forms.TextBox> control's <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property to `true`.</span></span> <span data-ttu-id="db7a5-107">Die Eigenschaft auf festgelegt `true`, Benutzer können weiterhin scrollen und Hervorheben von Text in einem Textfeld ohne Änderungen.</span><span class="sxs-lookup"><span data-stu-id="db7a5-107">With the property set to `true`, users can still scroll and highlight text in a text box without allowing changes.</span></span> <span data-ttu-id="db7a5-108">Ein **Kopie** Befehl funktioniert in einem Textfeld, aber **Ausschneiden** und **einfügen** Befehle sind nicht.</span><span class="sxs-lookup"><span data-stu-id="db7a5-108">A **Copy** command is functional in a text box, but **Cut** and **Paste** commands are not.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="db7a5-109">Die <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> Eigenschaft wirkt sich nur auf eine Benutzerinteraktion bei der Ausführung.</span><span class="sxs-lookup"><span data-stu-id="db7a5-109">The <xref:System.Windows.Forms.TextBoxBase.ReadOnly%2A> property only affects user interaction at run time.</span></span> <span data-ttu-id="db7a5-110">Sie können weiterhin textfeldinhalte programmgesteuert ändern zur Laufzeit durch Ändern der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft des Textfelds.</span><span class="sxs-lookup"><span data-stu-id="db7a5-110">You can still change text box contents programmatically at run time by changing the <xref:System.Windows.Forms.TextBox.Text%2A> property of the text box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7a5-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db7a5-111">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="db7a5-112">Übersicht über das TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="db7a5-112">TextBox Control Overview</span></span>](textbox-control-overview-windows-forms.md)
- [<span data-ttu-id="db7a5-113">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db7a5-113">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="db7a5-114">Vorgehensweise: Erstellen Sie ein Kennwort-Textfeld mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db7a5-114">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db7a5-115">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="db7a5-115">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="db7a5-116">Vorgehensweise: Wählen Sie Text im TextBox-Steuerelement von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="db7a5-116">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db7a5-117">Vorgehensweise: Zeigen Sie mehrerer Zeilen in der TextBox-Steuerelement in Windows Forms an</span><span class="sxs-lookup"><span data-stu-id="db7a5-117">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="db7a5-118">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="db7a5-118">TextBox Control</span></span>](textbox-control-windows-forms.md)
