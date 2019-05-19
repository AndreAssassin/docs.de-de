---
title: 'Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers'
ms.date: 03/30/2017
helpviewer_keywords:
- ImageList component [Windows Forms], adding images
- ImageList component [Windows Forms], removing images
- images [Windows Forms], adding to ImageList component
ms.assetid: 5699b244-e37c-4d20-bc35-7441e55c1e3a
ms.openlocfilehash: 346d7107c9c17c5df06fa0e47f7a35355344f590
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880733"
---
# <a name="how-to-add-or-remove-imagelist-images-with-the-designer"></a><span data-ttu-id="bfd75-102">Vorgehensweise: Hinzufügen oder Entfernen von ImageList-Bildern mithilfe des Designers</span><span class="sxs-lookup"><span data-stu-id="bfd75-102">How to: Add or Remove ImageList Images with the Designer</span></span>
<span data-ttu-id="bfd75-103">Sie können Bilder zum Hinzufügen einer <xref:System.Windows.Forms.ImageList> Komponente mehrere Möglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="bfd75-103">You can add images to an <xref:System.Windows.Forms.ImageList> component several different ways.</span></span> <span data-ttu-id="bfd75-104">Sie können Bilder sehr schnell hinzufügen, indem Sie mithilfe des Smarttags zugeordnet der <xref:System.Windows.Forms.ImageList>, oder wenn Sie mehrere weitere Eigenschaften für Festlegen der <xref:System.Windows.Forms.ImageList>, Umständen ist es praktischer, Hinzufügen von Bildern mit dem Fenster "Eigenschaften".</span><span class="sxs-lookup"><span data-stu-id="bfd75-104">You can add images very quickly by using the smart tag associated with the <xref:System.Windows.Forms.ImageList>, or if you are setting several other properties on the <xref:System.Windows.Forms.ImageList>, you may find it more convenient to add images with the Properties window.</span></span> <span data-ttu-id="bfd75-105">Sie können auch Bilder hinzufügen, indem Sie Code.</span><span class="sxs-lookup"><span data-stu-id="bfd75-105">You can also add images by using code.</span></span> <span data-ttu-id="bfd75-106">Weitere Informationen zur Vorgehensweise beim Hinzufügen von Bildern mithilfe von Code finden Sie unter [Vorgehensweise: Hinzufügen oder Entfernen von Bildern mit der Windows Forms ImageList-Komponente](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="bfd75-106">For more information about how to add images with code, see [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span> <span data-ttu-id="bfd75-107">Füllen Sie in der Regel die <xref:System.Windows.Forms.ImageList> Komponente mit Bildern, bevor Sie mit einem Steuerelement verknüpft ist, aber dies ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bfd75-107">Typically you populate the <xref:System.Windows.Forms.ImageList> component with images before it is associated with a control, but this is not required.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bfd75-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="bfd75-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bfd75-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="bfd75-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bfd75-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="bfd75-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-images-by-using-the-properties-window"></a><span data-ttu-id="bfd75-111">Zum Hinzufügen oder Entfernen von Bildern mithilfe des Eigenschaften-Fensters</span><span class="sxs-lookup"><span data-stu-id="bfd75-111">To add or remove images by using the Properties window</span></span>  
  
1. <span data-ttu-id="bfd75-112">Wählen Sie die <xref:System.Windows.Forms.ImageList> -Komponente, oder fügen Sie eine auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bfd75-112">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2.  <span data-ttu-id="bfd75-113">Klicken Sie im Fenster Eigenschaften auf die Schaltfläche mit den Auslassungspunkten (![die Auslassungszeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben dem <xref:System.Windows.Forms.ImageList.Images%2A> Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="bfd75-113">In the Properties window, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) next to the <xref:System.Windows.Forms.ImageList.Images%2A> property.</span></span>  
  
3. <span data-ttu-id="bfd75-114">In der **Image-Auflistungs-Editor**, klicken Sie auf **hinzufügen** oder **entfernen** zum Hinzufügen oder Entfernen von Bildern aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="bfd75-114">In the **Image Collection Editor**, click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
### <a name="to-add-or-remove-images-using-the-smart-tag"></a><span data-ttu-id="bfd75-115">Hinzufügen oder Entfernen von Bildern mithilfe des Smarttags</span><span class="sxs-lookup"><span data-stu-id="bfd75-115">To add or remove images using the smart tag</span></span>  
  
1. <span data-ttu-id="bfd75-116">Wählen Sie die <xref:System.Windows.Forms.ImageList> -Komponente, oder fügen Sie eine auf das Formular.</span><span class="sxs-lookup"><span data-stu-id="bfd75-116">Select the <xref:System.Windows.Forms.ImageList> component, or add one to the form.</span></span>  
  
2. <span data-ttu-id="bfd75-117">Klicken Sie auf die Smarttag-Glyphe (![Smarttag-Glyphe](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span><span class="sxs-lookup"><span data-stu-id="bfd75-117">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph"))</span></span>  
  
3. <span data-ttu-id="bfd75-118">In der **ImageList-Aufgaben** wählen Sie im Dialogfeld **Bilder auswählen**.</span><span class="sxs-lookup"><span data-stu-id="bfd75-118">In the **ImageList Tasks** dialog box, select **Choose Images**.</span></span>  
  
4. <span data-ttu-id="bfd75-119">In der **Editor Kolekce Images** klicken Sie auf **hinzufügen** oder **entfernen** zum Hinzufügen oder Entfernen von Bildern aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="bfd75-119">In the **Images Collection Editor** click **Add** or **Remove** to add or remove images from the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfd75-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bfd75-120">See also</span></span>

- [<span data-ttu-id="bfd75-121">Bilder, Bitmaps und Metadateien</span><span class="sxs-lookup"><span data-stu-id="bfd75-121">Images, Bitmaps, and Metafiles</span></span>](../advanced/images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="bfd75-122">Exemplarische Vorgehensweise: Ausführen von häufigen Aufgaben mit Smarttags Tags auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="bfd75-122">Walkthrough: Performing Common Tasks Using Smart Tags on Windows Forms Controls</span></span>](performing-common-tasks-using-smart-tags-on-wf-controls.md)
- [<span data-ttu-id="bfd75-123">ImageList-Komponente</span><span class="sxs-lookup"><span data-stu-id="bfd75-123">ImageList Component</span></span>](imagelist-component-windows-forms.md)
