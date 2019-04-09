---
title: Methoden zur Auswahl eines Button-Steuerelements in Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Button control [Windows Forms], selecting
ms.assetid: fe2fc058-5118-4f70-b264-6147d64a7a8d
ms.openlocfilehash: f2881646a05d257044c6461f822a4c35a225f8c8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223289"
---
# <a name="ways-to-select-a-windows-forms-button-control"></a><span data-ttu-id="dfa58-102">Methoden zur Auswahl eines Button-Steuerelements in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfa58-102">Ways to Select a Windows Forms Button Control</span></span>
<span data-ttu-id="dfa58-103">Eine Windows Forms-Schaltfläche kann auf folgende Weise ausgewählt werden:</span><span class="sxs-lookup"><span data-stu-id="dfa58-103">A Windows Forms button can be selected in the following ways:</span></span>  
  
-   <span data-ttu-id="dfa58-104">Verwenden Sie eine Maus, um auf die Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="dfa58-104">Use a mouse to click the button.</span></span>  
  
-   <span data-ttu-id="dfa58-105">Rufen Sie der Schaltfläche " <xref:System.Windows.Forms.Control.Click> Ereignis im Code.</span><span class="sxs-lookup"><span data-stu-id="dfa58-105">Invoke the button's <xref:System.Windows.Forms.Control.Click> event in code.</span></span>  
  
-   <span data-ttu-id="dfa58-106">Den Fokus auf die Schaltfläche mit den durch Drücken der TAB-Taste, und wählen Sie dann die Schaltfläche mit den durch Drücken der LEERTASTE oder EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="dfa58-106">Move the focus to the button by pressing the TAB key, and then choose the button by pressing the SPACEBAR or ENTER.</span></span>  
  
-   <span data-ttu-id="dfa58-107">Drücken Sie die Zugriffsschlüssel (ALT + unterstrichener Buchstabe) für die Schaltfläche aus.</span><span class="sxs-lookup"><span data-stu-id="dfa58-107">Press the access key (ALT + the underlined letter) for the button.</span></span> <span data-ttu-id="dfa58-108">Weitere Informationen zu Zugriffsschlüsseln finden Sie unter [Vorgehensweise: Erstellen von Zugriffstasten für Windows-Steuerelemente Forms](how-to-create-access-keys-for-windows-forms-controls.md).</span><span class="sxs-lookup"><span data-stu-id="dfa58-108">For more information about access keys, see [How to: Create Access Keys for Windows Forms Controls](how-to-create-access-keys-for-windows-forms-controls.md).</span></span>  
  
-   <span data-ttu-id="dfa58-109">Wenn die Schaltfläche des Formulars die Schaltfläche "accept" ist, Drücken der EINGABETASTE auswählt, die Schaltfläche, auch wenn ein anderes Steuerelement den Fokus besitzt, außer wenn das andere Steuerelement ist eine weitere Schaltfläche, ein mehrzeiliges Textfeld oder ein benutzerdefiniertes Steuerelement, das fängt die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="dfa58-109">If the button is the "accept" button of the form, pressing ENTER chooses the button, even if another control has the focus — except if that other control is another button, a multi-line text box, or a custom control that traps the enter key.</span></span>  
  
-   <span data-ttu-id="dfa58-110">Ist die Schaltfläche mit der auf die Schaltfläche "Abbrechen" des Formulars, wählt das Drücken der ESC-Taste die Schaltfläche, selbst wenn ein anderes Steuerelement den Fokus besitzt.</span><span class="sxs-lookup"><span data-stu-id="dfa58-110">If the button is the "cancel" button of the form, pressing ESC chooses the button, even if another control has the focus.</span></span>  
  
-   <span data-ttu-id="dfa58-111">Rufen Sie die <xref:System.Windows.Forms.Button.PerformClick%2A> Methode, um programmgesteuert auf die Schaltfläche klicken.</span><span class="sxs-lookup"><span data-stu-id="dfa58-111">Call the <xref:System.Windows.Forms.Button.PerformClick%2A> method to select the button programmatically.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa58-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dfa58-112">See also</span></span>

- [<span data-ttu-id="dfa58-113">Übersicht über das Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dfa58-113">Button Control Overview</span></span>](button-control-overview-windows-forms.md)
- [<span data-ttu-id="dfa58-114">Vorgehensweise: Reagieren auf das Anklicken von Schaltflächen in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dfa58-114">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
- [<span data-ttu-id="dfa58-115">Button-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="dfa58-115">Button Control</span></span>](button-control-windows-forms.md)
