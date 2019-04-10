---
title: 'Vorgehensweise: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip [Windows Forms], displaying option buttons
- displaying option buttons [Windows Forms], MenuStrip [Windows Forms]
- option buttons [Windows Forms], displaying in MenuStrip
ms.assetid: 8b596af2-9ff8-4f7b-93d7-cba830e167f4
ms.openlocfilehash: 61feda3f49c9a9e03a606c0284629f809d6876b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115530"
---
# <a name="how-to-display-option-buttons-in-a-menustrip-windows-forms"></a><span data-ttu-id="f9b29-102">Vorgehensweise: Anzeigen von Optionsfeldern in einem MenuStrip (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="f9b29-102">How to: Display Option Buttons in a MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="f9b29-103">Optionsfelder, auch bekannt als die Optionsfelder, ähneln der Kontrollkästchen, mit dem Unterschied, dass Benutzer nur jeweils eine auswählen können.</span><span class="sxs-lookup"><span data-stu-id="f9b29-103">Option buttons, also known as radio buttons, are similar to check boxes except that users can select only one at a time.</span></span> <span data-ttu-id="f9b29-104">Zwar wird standardmäßig die <xref:System.Windows.Forms.ToolStripMenuItem> -Klasse keinen Optionsfeld-aus-Verhalten, das die Klasse bietet ein Kontrollkästchen-Verhalten, das Sie anpassen können, um das Implementieren des Verhaltens von Optionsfeldern für Menüelemente in einem <xref:System.Windows.Forms.MenuStrip> Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f9b29-104">Although by default the <xref:System.Windows.Forms.ToolStripMenuItem> class does not provide option-button behavior, the class does provide check-box behavior that you can customize to implement option-button behavior for menu items in a <xref:System.Windows.Forms.MenuStrip> control.</span></span>  
  
 <span data-ttu-id="f9b29-105">Wenn die <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> -Eigenschaft eines Menüelements ist `true`, Benutzer können auf das Element, um die ein-und ein Häkchen klicken.</span><span class="sxs-lookup"><span data-stu-id="f9b29-105">When the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property of a menu item is `true`, users can click the item to toggle the display of a check mark.</span></span> <span data-ttu-id="f9b29-106">Die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Eigenschaft gibt den aktuellen Zustand des Elements an.</span><span class="sxs-lookup"><span data-stu-id="f9b29-106">The <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property indicates the current state of the item.</span></span> <span data-ttu-id="f9b29-107">Um grundlegende Optionsfeld-Verhalten zu implementieren, müssen Sie sicherstellen, dass wenn ein Element ausgewählt ist, Sie legen die <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> -Eigenschaft für das zuvor ausgewählte Element `false`.</span><span class="sxs-lookup"><span data-stu-id="f9b29-107">To implement basic option-button behavior, you must ensure that when an item is selected, you set the <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> property for the previously selected item to `false`.</span></span>  
  
 <span data-ttu-id="f9b29-108">Die folgenden Verfahren wird beschrieben, wie dies implementiert und weitere Funktionen in einer Klasse, erbt die <xref:System.Windows.Forms.ToolStripMenuItem> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f9b29-108">The following procedures describe how to implement this and additional functionality in a class that inherits the <xref:System.Windows.Forms.ToolStripMenuItem> class.</span></span> <span data-ttu-id="f9b29-109">Die `ToolStripRadioButtonMenuItem` Klasse überschreibt z. B. <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> und <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> das Verhalten der Funktionsauswahl und Darstellung von Optionsfeldern angeben.</span><span class="sxs-lookup"><span data-stu-id="f9b29-109">The `ToolStripRadioButtonMenuItem` class overrides members such as <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> and <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> to provide the selection behavior and appearance of option buttons.</span></span> <span data-ttu-id="f9b29-110">Darüber hinaus diese Klasse überschreibt die <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft, sodass Sie in einem Untermenü Optionen sind deaktiviert, es sei denn, das übergeordnete Element ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f9b29-110">Additionally, this class overrides the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that options on a submenu are disabled unless the parent item is selected.</span></span>  
  
### <a name="to-implement-option-button-selection-behavior"></a><span data-ttu-id="f9b29-111">Zum Implementieren des Verhaltens von Optionsfeld-Auswahl</span><span class="sxs-lookup"><span data-stu-id="f9b29-111">To implement option-button selection behavior</span></span>  
  
1.  <span data-ttu-id="f9b29-112">Initialisieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Eigenschaft `true` Elementauswahl zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f9b29-112">Initialize the <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> property to `true` to enable item selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#110](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#110)]
     [!code-vb[ToolStripRadioButtonMenuItem#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#110)]  
  
2.  <span data-ttu-id="f9b29-113">Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> Methode, um die Auswahl der zuvor ausgewählten Elements zu löschen, wenn ein neues Element ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="f9b29-113">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A> method to clear the selection of the previously selected item when a new item is selected.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#120](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#120)]
     [!code-vb[ToolStripRadioButtonMenuItem#120](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#120)]  
  
3.  <span data-ttu-id="f9b29-114">Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> Methode, um sicherzustellen, dass beim Klicken auf ein Element, das bereits ausgewählt wurde, wird nicht die Auswahl gelöscht.</span><span class="sxs-lookup"><span data-stu-id="f9b29-114">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnClick%2A> method to ensure that clicking an item that has already been selected will not clear the selection.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#130](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#130)]
     [!code-vb[ToolStripRadioButtonMenuItem#130](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#130)]  
  
### <a name="to-modify-the-appearance-of-the-option-button-items"></a><span data-ttu-id="f9b29-115">Zum Ändern der Darstellung der Optionsfeld-Elemente</span><span class="sxs-lookup"><span data-stu-id="f9b29-115">To modify the appearance of the option-button items</span></span>  
  
1.  <span data-ttu-id="f9b29-116">Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> Methode, um das Standard-Häkchen ein Optionsfeld mit mit Ersetzen der <xref:System.Windows.Forms.RadioButtonRenderer> Klasse.</span><span class="sxs-lookup"><span data-stu-id="f9b29-116">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method to replace the default check-mark with an option button by using the <xref:System.Windows.Forms.RadioButtonRenderer> class.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#140](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#140)]
     [!code-vb[ToolStripRadioButtonMenuItem#140](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#140)]  
  
2.  <span data-ttu-id="f9b29-117">Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, und <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> Methoden zum Nachverfolgen des Status der Maus, und stellen sicher, dass die <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> zeichnet den Status richtig Optionsfeld-Methode.</span><span class="sxs-lookup"><span data-stu-id="f9b29-117">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseEnter%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseLeave%2A>, <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseDown%2A>, and <xref:System.Windows.Forms.ToolStripMenuItem.OnMouseUp%2A> methods to track the state of the mouse and ensure that the <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A> method paints the correct option-button state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#150](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#150)]
     [!code-vb[ToolStripRadioButtonMenuItem#150](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#150)]  
  
### <a name="to-disable-options-on-a-submenu-when-the-parent-item-is-not-selected"></a><span data-ttu-id="f9b29-118">So deaktivieren Sie Optionen in einem Untermenü, wenn das übergeordnete Element nicht ausgewählt ist</span><span class="sxs-lookup"><span data-stu-id="f9b29-118">To disable options on a submenu when the parent item is not selected</span></span>  
  
1.  <span data-ttu-id="f9b29-119">Außer Kraft setzen der <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> Eigenschaft so, dass das Element deaktiviert wird, wenn es sich um ein übergeordnetes Element mit sowohl hat eine <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> Wert `true` und ein <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> Wert `false`.</span><span class="sxs-lookup"><span data-stu-id="f9b29-119">Override the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property so that the item is disabled when it has a parent item with both a <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A> value of `true` and a <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A> value of `false`.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#160](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#160)]
     [!code-vb[ToolStripRadioButtonMenuItem#160](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#160)]  
  
2.  <span data-ttu-id="f9b29-120">Überschreiben der <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> Methode zum Abonnieren der <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> Ereignis des übergeordneten Elements.</span><span class="sxs-lookup"><span data-stu-id="f9b29-120">Override the <xref:System.Windows.Forms.ToolStripMenuItem.OnOwnerChanged%2A> method to subscribe to the <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event of the parent item.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#170](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#170)]
     [!code-vb[ToolStripRadioButtonMenuItem#170](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#170)]  
  
3.  <span data-ttu-id="f9b29-121">Im Handler für den übergeordneten Elements <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> -Ereignis, das Element, um die Anzeige zu aktualisieren, mit dem neuen aktivierten Zustand ungültig.</span><span class="sxs-lookup"><span data-stu-id="f9b29-121">In the handler for the parent-item <xref:System.Windows.Forms.ToolStripMenuItem.CheckedChanged> event, invalidate the item to update the display with the new enabled state.</span></span>  
  
     [!code-csharp[ToolStripRadioButtonMenuItem#180](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#180)]
     [!code-vb[ToolStripRadioButtonMenuItem#180](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#180)]  
  
## <a name="example"></a><span data-ttu-id="f9b29-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f9b29-122">Example</span></span>  
 <span data-ttu-id="f9b29-123">Das folgende Codebeispiel stellt die vollständige `ToolStripRadioButtonMenuItem` -Klasse, und ein <xref:System.Windows.Forms.Form> Klasse und `Program` Klasse zur Veranschaulichung des Verhaltens von Optionsfeldern.</span><span class="sxs-lookup"><span data-stu-id="f9b29-123">The following code example provides the complete `ToolStripRadioButtonMenuItem` class, and a <xref:System.Windows.Forms.Form> class and `Program` class to demonstrate the option-button behavior.</span></span>  
  
 [!code-csharp[ToolStripRadioButtonMenuItem#000](~/samples/snippets/csharp/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/cs/ToolStripRadioButtonMenuItem.cs#000)]
 [!code-vb[ToolStripRadioButtonMenuItem#000](~/samples/snippets/visualbasic/VS_Snippets_Winforms/ToolStripRadioButtonMenuItem/vb/ToolStripRadioButtonMenuItem.vb#000)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f9b29-124">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f9b29-124">Compiling the Code</span></span>  
 <span data-ttu-id="f9b29-125">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f9b29-125">This example requires:</span></span>  
  
-   <span data-ttu-id="f9b29-126">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="f9b29-126">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9b29-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9b29-127">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- <xref:System.Windows.Forms.ToolStripMenuItem.CheckOnClick%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Checked%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnCheckedChanged%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.OnPaint%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RadioButtonRenderer>
- [<span data-ttu-id="f9b29-128">MenuStrip-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f9b29-128">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
- [<span data-ttu-id="f9b29-129">Vorgehensweise: Implementieren eines benutzerdefinierten ToolStripRenderer</span><span class="sxs-lookup"><span data-stu-id="f9b29-129">How to: Implement a Custom ToolStripRenderer</span></span>](how-to-implement-a-custom-toolstriprenderer.md)
