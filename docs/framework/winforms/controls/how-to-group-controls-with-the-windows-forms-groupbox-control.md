---
title: 'Vorgehensweise: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows Forms'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], grouping
- GroupBox control [Windows Forms], grouping controls
- Windows Forms controls, grouping
ms.assetid: 0bda316d-bd2a-43aa-ac73-342453303169
ms.openlocfilehash: d2bad0020d18cd262bc2fe3489a00209308bd7b9
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335874"
---
# <a name="how-to-group-controls-with-the-windows-forms-groupbox-control"></a><span data-ttu-id="54fc3-102">Vorgehensweise: Gruppieren von Steuerelementen mit dem GroupBox-Steuerelement in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="54fc3-102">How to: Group Controls with the Windows Forms GroupBox Control</span></span>
<span data-ttu-id="54fc3-103">Windows Forms <xref:System.Windows.Forms.GroupBox> Steuerelemente werden verwendet, um die Gruppierung anderer Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="54fc3-103">Windows Forms <xref:System.Windows.Forms.GroupBox> controls are used to group other controls.</span></span> <span data-ttu-id="54fc3-104">Es gibt drei Gründe zum Gruppieren von Steuerelementen:</span><span class="sxs-lookup"><span data-stu-id="54fc3-104">There are three reasons to group controls:</span></span>  
  
-   <span data-ttu-id="54fc3-105">Um eine visuelle Gruppierung von verwandten Form-Elemente für eine übersichtliche Benutzeroberfläche zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54fc3-105">To create a visual grouping of related form elements for a clear user interface.</span></span>  
  
-   <span data-ttu-id="54fc3-106">Um programmgesteuerte Gruppierung (von Optionsfeldern an, z. B.) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54fc3-106">To create programmatic grouping (of radio buttons, for example).</span></span>  
  
-   <span data-ttu-id="54fc3-107">Für das Verschieben von der Steuerelements zur Entwurfszeit als eine Einheit.</span><span class="sxs-lookup"><span data-stu-id="54fc3-107">For moving the controls as a unit at design time.</span></span>  
  
### <a name="to-create-a-group-of-controls"></a><span data-ttu-id="54fc3-108">Um eine Gruppe von Steuerelementen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="54fc3-108">To create a group of controls</span></span>  
  
1. <span data-ttu-id="54fc3-109">Zeichnen einer <xref:System.Windows.Forms.GroupBox> Steuerelement in einem Formular.</span><span class="sxs-lookup"><span data-stu-id="54fc3-109">Draw a <xref:System.Windows.Forms.GroupBox> control on a form.</span></span>  
  
2. <span data-ttu-id="54fc3-110">Fügen Sie weitere Steuerelemente, dem Gruppenfeld, jede Gruppe im Feld zu zeichnen.</span><span class="sxs-lookup"><span data-stu-id="54fc3-110">Add other controls to the group box, drawing each inside the group box.</span></span>  
  
     <span data-ttu-id="54fc3-111">Wenn Sie vorhandene Steuerelemente verfügen, die Sie in einem Gruppenfeld einschließen möchten, können Sie wählen Sie alle Steuerelemente, verschieben Sie sie in die Zwischenablage, wählen Sie die <xref:System.Windows.Forms.GroupBox> steuern, und fügen Sie sie in das Gruppenfeld.</span><span class="sxs-lookup"><span data-stu-id="54fc3-111">If you have existing controls that you want to enclose in a group box, you can select all the controls, cut them to the Clipboard, select the <xref:System.Windows.Forms.GroupBox> control, and then paste them into the group box.</span></span> <span data-ttu-id="54fc3-112">Sie können auch in das Gruppenfeld ziehen.</span><span class="sxs-lookup"><span data-stu-id="54fc3-112">You can also drag them into the group box.</span></span>  
  
3. <span data-ttu-id="54fc3-113">Legen Sie die <xref:System.Windows.Forms.GroupBox.Text%2A> Eigenschaft des Gruppenfelds eine geeignete Beschriftung.</span><span class="sxs-lookup"><span data-stu-id="54fc3-113">Set the <xref:System.Windows.Forms.GroupBox.Text%2A> property of the group box to an appropriate caption.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54fc3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="54fc3-114">See also</span></span>

- <xref:System.Windows.Forms.GroupBox>
- [<span data-ttu-id="54fc3-115">GroupBox-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="54fc3-115">GroupBox Control</span></span>](groupbox-control-windows-forms.md)
