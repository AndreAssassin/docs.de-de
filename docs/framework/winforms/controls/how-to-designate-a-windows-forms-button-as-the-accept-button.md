---
title: 'Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- buttons [Windows Forms], default on Windows Forms
- Accept button on Windows Forms
- Button control [Windows Forms], designating as default
- Windows Forms controls, default button on form
ms.assetid: 22cc9da6-b913-4e04-9554-dee443ac5c3a
ms.openlocfilehash: 5b21ee7da7a666a391be3bc5be57855eaa7ec8b5
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967368"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="5f888-102">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5f888-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="5f888-103">In jedem Windows-Formular können Sie ein <xref:System.Windows.Forms.Button> Steuerelement als Accept-Schaltfläche festlegen, das auch als Standard Schaltfläche bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="5f888-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="5f888-104">Wenn der Benutzer die EINGABETASTE drückt, wird die Standard Schaltfläche unabhängig davon, welches andere Steuerelement im Formular den Fokus besitzt, angeklickt.</span><span class="sxs-lookup"><span data-stu-id="5f888-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="5f888-105">Dies gilt auch, wenn das Steuerelement mit dem Fokus eine andere Schaltfläche ist – in diesem Fall wird auf die Schaltfläche mit dem Fokus geklickt – oder ein mehrzeilige Textfeld oder ein benutzerdefiniertes Steuerelement, das die EINGABETASTE fängt.</span><span class="sxs-lookup"><span data-stu-id="5f888-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="5f888-106">So bestimmen Sie die Accept-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="5f888-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="5f888-107">Legen Sie die- <xref:System.Windows.Forms.Form.AcceptButton%2A> Eigenschaft des Formulars auf <xref:System.Windows.Forms.Button> das entsprechende Steuerelement fest.</span><span class="sxs-lookup"><span data-stu-id="5f888-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
    ```vb  
    Private Sub SetDefault(ByVal myDefaultBtn As Button)  
      Me.AcceptButton = myDefaultBtn   
    End Sub  
    ```  
  
    ```csharp  
    private void SetDefault(Button myDefaultBtn)  
    {  
       this.AcceptButton = myDefaultBtn;  
    }  
    ```  
  
    ```cpp  
    private:  
       void SetDefault(Button ^ myDefaultBtn)  
       {  
          this->AcceptButton = myDefaultBtn;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5f888-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f888-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="5f888-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5f888-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="5f888-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5f888-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="5f888-111">Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks</span><span class="sxs-lookup"><span data-stu-id="5f888-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="5f888-112">Vorgehensweise: Festlegen einer Windows Forms Schaltfläche als Schaltfläche "Abbrechen"</span><span class="sxs-lookup"><span data-stu-id="5f888-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="5f888-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="5f888-113">Button Control</span></span>](button-control-windows-forms.md)
