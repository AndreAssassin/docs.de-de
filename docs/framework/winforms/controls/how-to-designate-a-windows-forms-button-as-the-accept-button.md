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
ms.openlocfilehash: 8e608bb2cb4635ef1d29fd7a0aff3ac95fcd9af5
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59309822"
---
# <a name="how-to-designate-a-windows-forms-button-as-the-accept-button"></a><span data-ttu-id="b7dc2-102">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Annehmen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b7dc2-102">How to: Designate a Windows Forms Button as the Accept Button</span></span>
<span data-ttu-id="b7dc2-103">Auf jedem Windows-Formular, Sie können festlegen, eine <xref:System.Windows.Forms.Button> Steuerelement "Annehmen"-Schaltfläche, auch bekannt als die Standardschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="b7dc2-103">On any Windows Form, you can designate a <xref:System.Windows.Forms.Button> control to be the accept button, also known as the default button.</span></span> <span data-ttu-id="b7dc2-104">Wenn der Benutzer die EINGABETASTE drückt, wird die Schaltfläche "Standard" geklickt haben, unabhängig davon, welche anderen Formular auf das Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="b7dc2-104">Whenever the user presses the ENTER key, the default button is clicked regardless of which other control on the form has the focus.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b7dc2-105">Die Ausnahmen von dieser sind, wenn das Steuerelement mit Fokus auf eine andere Schaltfläche ist – in diesem Fall wird die Schaltfläche mit den Fokus geklickt werden, oder ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das fängt die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="b7dc2-105">The exceptions to this are when the control with focus is another button — in that case, the button with the focus will be clicked — or a multiline text box, or a custom control that traps the ENTER key.</span></span>  
  
### <a name="to-designate-the-accept-button"></a><span data-ttu-id="b7dc2-106">Festlegen von "Annehmen"-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b7dc2-106">To designate the accept button</span></span>  
  
1. <span data-ttu-id="b7dc2-107">Festlegen des Formulars <xref:System.Windows.Forms.Form.AcceptButton%2A> -Eigenschaft auf die entsprechende <xref:System.Windows.Forms.Button> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="b7dc2-107">Set the form's <xref:System.Windows.Forms.Form.AcceptButton%2A> property to the appropriate <xref:System.Windows.Forms.Button> control.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b7dc2-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7dc2-108">See also</span></span>

- <xref:System.Windows.Forms.Form.AcceptButton%2A>
- [<span data-ttu-id="b7dc2-109">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b7dc2-109">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="b7dc2-110">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7dc2-110">Ways to Select a Windows Forms Button Control</span></span>](ways-to-select-a-windows-forms-button-control.md)
- [<span data-ttu-id="b7dc2-111">Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="b7dc2-111">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="b7dc2-112">Vorgehensweise: Definieren einer Windows Forms-Schaltfläche als „Abbrechen“-Schaltfläche</span><span class="sxs-lookup"><span data-stu-id="b7dc2-112">How to: Designate a Windows Forms Button as the Cancel Button</span></span>](how-to-designate-a-windows-forms-button-as-the-cancel-button.md)
- [<span data-ttu-id="b7dc2-113">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="b7dc2-113">Button Control</span></span>](button-control-windows-forms.md)
