---
title: 'Vorgehensweise: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- fonts [Windows Forms], showing list
- FontDialog component [Windows Forms]
- fonts [Windows Forms], attributes
- Font property [Windows Forms], setting with FontDialog component
- Font dialog box [Windows Forms], displaying
- fonts [Windows Forms], selecting
ms.assetid: 35692c1b-0937-4b7a-9207-1ae6bdc244a0
ms.openlocfilehash: fba9caecc71c5cb77c811fc112616647c79689c6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59220187"
---
# <a name="how-to-show-a-font-list-with-the-fontdialog-component"></a><span data-ttu-id="11256-102">Vorgehensweise: Anzeigen einer Schriftartenliste mit der FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="11256-102">How to: Show a Font List with the FontDialog Component</span></span>
<span data-ttu-id="11256-103">Die [FontDialog](fontdialog-component-windows-forms.md) -Komponente können Benutzer wählen Sie eine Schriftart sowie deren Anzeige ändern, z. B. Größe und Gewicht.</span><span class="sxs-lookup"><span data-stu-id="11256-103">The [FontDialog](fontdialog-component-windows-forms.md) component allows users to select a font, as well as change its display aspects, such as its weight and size.</span></span>  
  
 <span data-ttu-id="11256-104">Im Dialogfeld ausgewählte Schriftart wird zurückgegeben, der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11256-104">The font selected in the dialog box is returned in the <xref:System.Windows.Forms.FontDialog.Font%2A> property.</span></span> <span data-ttu-id="11256-105">Daher ist die Nutzung der vom Benutzer ausgewählten Schriftart so einfach wie das Lesen einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="11256-105">Thus, taking advantage of the font selected by the user is as easy as reading a property.</span></span>  
  
### <a name="to-select-font-properties-using-the-fontdialog-component"></a><span data-ttu-id="11256-106">Schriftarteigenschaften, die mit der FontDialog-Komponente auswählen</span><span class="sxs-lookup"><span data-stu-id="11256-106">To select font properties using the FontDialog Component</span></span>  
  
1.  <span data-ttu-id="11256-107">Anzeigen des Dialogfelds mit der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="11256-107">Display the dialog box using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
2.  <span data-ttu-id="11256-108">Verwenden der <xref:System.Windows.Forms.DialogResult> Eigenschaft, um zu bestimmen, wie Sie das Dialogfeld geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="11256-108">Use the <xref:System.Windows.Forms.DialogResult> property to determine how the dialog box was closed.</span></span>  
  
3.  <span data-ttu-id="11256-109">Verwenden der <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft, um die gewünschte Schriftart fest.</span><span class="sxs-lookup"><span data-stu-id="11256-109">Use the <xref:System.Windows.Forms.FontDialog.Font%2A> property to set the desired font.</span></span>  
  
     <span data-ttu-id="11256-110">Im folgenden Beispiel wird die <xref:System.Windows.Forms.Button> des Steuerelements <xref:System.Windows.Forms.Control.Click> -Ereignishandler öffnet eine <xref:System.Windows.Forms.FontDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="11256-110">In the example below, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens a <xref:System.Windows.Forms.FontDialog> component.</span></span> <span data-ttu-id="11256-111">Wenn eine Schriftart ausgewählt und der Benutzer klickt **OK**, <xref:System.Windows.Forms.FontDialog.Font%2A> Eigenschaft eine <xref:System.Windows.Forms.TextBox> Steuerelement, das auf dem Formular für die ausgewählte Schriftart festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="11256-111">When a font is chosen and the user clicks **OK**, the <xref:System.Windows.Forms.FontDialog.Font%2A> property of a <xref:System.Windows.Forms.TextBox> control that is on the form is set to the chosen font.</span></span> <span data-ttu-id="11256-112">Im Beispiel wird vorausgesetzt, das Formular enthält ein <xref:System.Windows.Forms.Button> -Steuerelement, ein <xref:System.Windows.Forms.TextBox> -Steuerelement, und ein <xref:System.Windows.Forms.FontDialog> Komponente.</span><span class="sxs-lookup"><span data-stu-id="11256-112">The example assumes your form has a <xref:System.Windows.Forms.Button> control, a  <xref:System.Windows.Forms.TextBox> control, and a <xref:System.Windows.Forms.FontDialog> component.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       If FontDialog1.ShowDialog() = DialogResult.OK Then  
          TextBox1.Font = FontDialog1.Font  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       if(fontDialog1.ShowDialog() == DialogResult.OK)  
       {  
          textBox1.Font = fontDialog1.Font;  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          if(fontDialog1->ShowDialog() == DialogResult::OK)  
          {  
             textBox1->Font = fontDialog1->Font;  
          }  
       }  
    ```  
  
     <span data-ttu-id="11256-113">(Visual C#- und [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="11256-113">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="11256-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11256-114">See also</span></span>

- <xref:System.Windows.Forms.FontDialog>
- [<span data-ttu-id="11256-115">FontDialog-Komponente</span><span class="sxs-lookup"><span data-stu-id="11256-115">FontDialog Component</span></span>](fontdialog-component-windows-forms.md)
