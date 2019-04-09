---
title: Übersicht über das TextBox-Steuerelement (Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- TextBox
helpviewer_keywords:
- TextBox control [Windows Forms], about TextBox controls
- text boxes [Windows Forms], adding
ms.assetid: d1a9c7f5-fa53-480a-a75c-158f8649ea2f
ms.openlocfilehash: a91b67df1071c79707bb20a68efb4d5e6f083ae0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162136"
---
# <a name="textbox-control-overview-windows-forms"></a><span data-ttu-id="f5f52-102">Übersicht über das TextBox-Steuerelement (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f5f52-102">TextBox Control Overview (Windows Forms)</span></span>
<span data-ttu-id="f5f52-103">Windows Forms-Textfelder werden Eingaben von den Benutzer erhalten oder zum Anzeigen von Text verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5f52-103">Windows Forms text boxes are used to get input from the user or to display text.</span></span> <span data-ttu-id="f5f52-104">Die <xref:System.Windows.Forms.TextBox> Steuerelement wird im Allgemeinen für bearbeitbaren Text verwendet, obwohl sie auch schreibgeschützt festgelegt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5f52-104">The <xref:System.Windows.Forms.TextBox> control is generally used for editable text, although it can also be made read-only.</span></span> <span data-ttu-id="f5f52-105">Textfelder können mehrere Zeilen angezeigt, Umbrechen von Text auf die Größe des Steuerelements und fügen die einfache Formatierung.</span><span class="sxs-lookup"><span data-stu-id="f5f52-105">Text boxes can display multiple lines, wrap text to the size of the control, and add basic formatting.</span></span> <span data-ttu-id="f5f52-106">Die <xref:System.Windows.Forms.TextBox> -Steuerelement stellt einen einzelnen Formatstil für Text angezeigt oder in das Steuerelement eingegeben.</span><span class="sxs-lookup"><span data-stu-id="f5f52-106">The <xref:System.Windows.Forms.TextBox> control provides a single format style for text displayed or entered into the control.</span></span> <span data-ttu-id="f5f52-107">Um mehrere Arten von formatiertem Text anzuzeigen, verwenden die <xref:System.Windows.Forms.RichTextBox> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f5f52-107">To display multiple types of formatted text, use the <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="f5f52-108">Weitere Informationen finden Sie unter [Übersicht über das RichTextBox-Steuerelement](richtextbox-control-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="f5f52-108">For more information, see [RichTextBox Control Overview](richtextbox-control-overview-windows-forms.md).</span></span>  
  
## <a name="working-with-the-textbox-control"></a><span data-ttu-id="f5f52-109">Arbeiten mit dem TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f5f52-109">Working with the TextBox Control</span></span>  
 <span data-ttu-id="f5f52-110">Vom Steuerelement angezeigte Text ist Bestandteil der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f5f52-110">The text displayed by the control is contained in the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span> <span data-ttu-id="f5f52-111">Standardmäßig können Sie bis zu 2048 Zeichen in einem Textfeld eingeben.</span><span class="sxs-lookup"><span data-stu-id="f5f52-111">By default, you can enter up to 2048 characters in a text box.</span></span> <span data-ttu-id="f5f52-112">Setzen Sie die <xref:System.Windows.Forms.TextBox.Multiline%2A> Eigenschaft `true`, können Sie bis zu 32 KB Text eingeben.</span><span class="sxs-lookup"><span data-stu-id="f5f52-112">If you set the <xref:System.Windows.Forms.TextBox.Multiline%2A> property to `true`, you can enter up to 32 KB of text.</span></span> <span data-ttu-id="f5f52-113">Die <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft kann zur Entwurfszeit im Fenster Eigenschaften zur Laufzeit im Code oder durch die Benutzereingabe zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f5f52-113">The <xref:System.Windows.Forms.TextBox.Text%2A> property can be set at design time with the Properties Window, at run time in code, or by user input at run time.</span></span> <span data-ttu-id="f5f52-114">Den aktuellen Inhalt eines Textfelds können zur Laufzeit abgerufen werden, durch Lesen der <xref:System.Windows.Forms.TextBox.Text%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="f5f52-114">The current contents of a text box can be retrieved at run time by reading the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="f5f52-115">Das folgende Codebeispiel legt Text im Steuerelement zur Laufzeit fest.</span><span class="sxs-lookup"><span data-stu-id="f5f52-115">The following code example sets text in the control at run time.</span></span> <span data-ttu-id="f5f52-116">Die `InitializeMyControl` -Prozedur wird nicht automatisch ausgeführt; muss aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f5f52-116">The `InitializeMyControl` procedure will not execute automatically; it must be called.</span></span>  
  
```vb  
Private Sub InitializeMyControl()  
   ' Put some text into the control first.  
   TextBox1.Text = "This is a TextBox control."  
End Sub  
```  
  
```csharp  
private void InitializeMyControl() {  
   // Put some text into the control first.  
   textBox1.Text = "This is a TextBox control.";  
}  
```  
  
```cpp  
private:  
   void InitializeMyControl()  
   {  
      // Put some text into the control first.  
      textBox1->Text = "This is a TextBox control.";  
   }  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5f52-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5f52-117">See also</span></span>

- <xref:System.Windows.Forms.TextBox>
- [<span data-ttu-id="f5f52-118">Vorgehensweise: Steuern der Einfügemarke in einem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5f52-118">How to: Control the Insertion Point in a Windows Forms TextBox Control</span></span>](how-to-control-the-insertion-point-in-a-windows-forms-textbox-control.md)
- [<span data-ttu-id="f5f52-119">Vorgehensweise: Erstellen eines Kennwort-Textfelds mit dem TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5f52-119">How to: Create a Password Text Box with the Windows Forms TextBox Control</span></span>](how-to-create-a-password-text-box-with-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f5f52-120">Vorgehensweise: Erstellen eines schreibgeschützten Textfelds</span><span class="sxs-lookup"><span data-stu-id="f5f52-120">How to: Create a Read-Only Text Box</span></span>](how-to-create-a-read-only-text-box-windows-forms.md)
- [<span data-ttu-id="f5f52-121">Vorgehensweise: Setzen von Anführungszeichen in Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f5f52-121">How to: Put Quotation Marks in a String</span></span>](how-to-put-quotation-marks-in-a-string-windows-forms.md)
- [<span data-ttu-id="f5f52-122">Vorgehensweise: Programmgesteuertes Auswählen von Text im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5f52-122">How to: Select Text in the Windows Forms TextBox Control</span></span>](how-to-select-text-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f5f52-123">Vorgehensweise: Anzeigen mehrerer Zeilen im TextBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5f52-123">How to: View Multiple Lines in the Windows Forms TextBox Control</span></span>](how-to-view-multiple-lines-in-the-windows-forms-textbox-control.md)
- [<span data-ttu-id="f5f52-124">TextBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f5f52-124">TextBox Control</span></span>](textbox-control-windows-forms.md)
