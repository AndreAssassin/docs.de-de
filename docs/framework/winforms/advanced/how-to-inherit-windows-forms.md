---
title: 'Vorgehensweise: Erben von Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 0d8799359a12b9bb64331d83df2500bede8c0ff2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314541"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="543ae-102">Vorgehensweise: Erben von Windows Forms</span><span class="sxs-lookup"><span data-stu-id="543ae-102">How to: Inherit Windows Forms</span></span>
<span data-ttu-id="543ae-103">Das Erstellen neuer Windows Forms durch Vererbung der Eigenschaften der Basisformulare ist eine praktische Möglichkeit zum Duplizieren Ihrer Bemühungen, ohne ein Formular jedes Mal von Grund auf neu erstellen zu müssen, wenn Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="543ae-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>  
  
 <span data-ttu-id="543ae-104">Weitere Informationen zum erben von Formularen zur Entwurfszeit mit der **Vererbungsauswahl** und das Dialogfeld zur visuellen Unterscheidung zwischen den Sicherheitsebenen der vererbten Steuerelemente, finden Sie unter [Vorgehensweise: Erben von Formularen mithilfe des Dialogfelds Auswahl](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="543ae-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>  
  
 <span data-ttu-id="543ae-105">**Hinweis** Damit die Formularvererbung vom Dialogfeld unterstützt wird, muss die Datei oder der Namespace mit dem jeweiligen Formular in eine ausführbare Datei oder DLL integriert werden.</span><span class="sxs-lookup"><span data-stu-id="543ae-105">**Note** In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="543ae-106">Wählen Sie zum Erstellen des Projekts aus dem Menü **Erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="543ae-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="543ae-107">Darüber hinaus muss der Klasse, die das Formular erbt, auch ein Verweis auf den Namespace hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="543ae-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span> <span data-ttu-id="543ae-108">Je nach den aktiven Einstellungen oder der Version unterscheiden sich die Dialogfelder und Menübefehle auf Ihrem Bildschirm möglicherweise von den in der Hilfe beschriebenen.</span><span class="sxs-lookup"><span data-stu-id="543ae-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="543ae-109">Klicken Sie im Menü **Extras** auf **Einstellungen importieren und exportieren** , um die Einstellungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="543ae-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="543ae-110">Weitere Informationen finden Sie unter [Personalisieren von Visual Studio-IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="543ae-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-inherit-a-form-programmatically"></a><span data-ttu-id="543ae-111">So erfolgt die Vererbung eines Formulars programmgesteuert</span><span class="sxs-lookup"><span data-stu-id="543ae-111">To inherit a form programmatically</span></span>  
  
1. <span data-ttu-id="543ae-112">Fügen Sie in der Klasse einen Verweis zu dem Namespace hinzu, der das Formular enthält, das vererbt werden soll.</span><span class="sxs-lookup"><span data-stu-id="543ae-112">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>  
  
2. <span data-ttu-id="543ae-113">Fügen Sie in der Klassendefinition einen Verweis auf das Formular hinzu, das vererbt werden soll.</span><span class="sxs-lookup"><span data-stu-id="543ae-113">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="543ae-114">Der Verweis sollte den Namespace enthalten, in dem sich das Formular befindet, gefolgt von einem Punkt und dem Namen des eigentlichen Formulars.</span><span class="sxs-lookup"><span data-stu-id="543ae-114">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>  
  
    ```vb  
    Public Class Form2  
        Inherits Namespace1.Form1  
    ```  
  
    ```csharp  
    public class Form2 : Namespace1.Form1  
    ```  
  
 <span data-ttu-id="543ae-115">Denken Sie beim Erben von Formularen daran, dass Probleme mit Ereignishandlern auftreten können, die zwei Mal aufgerufen werden, da jedes Ereignis sowohl von der Basisklasse als auch von der geerbten Klasse behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="543ae-115">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="543ae-116">Weitere Informationen dazu, wie Sie dieses Problem vermeiden können, finden Sie unter [Problembehandlung für geerbte Ereignishandler in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span><span class="sxs-lookup"><span data-stu-id="543ae-116">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="543ae-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="543ae-117">See also</span></span>

- [<span data-ttu-id="543ae-118">Inherits-Anweisung</span><span class="sxs-lookup"><span data-stu-id="543ae-118">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="543ae-119">Imports-Anweisung (.NET-Namespace und -Typ)</span><span class="sxs-lookup"><span data-stu-id="543ae-119">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="543ae-120">using</span><span class="sxs-lookup"><span data-stu-id="543ae-120">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="543ae-121">Auswirkungen beim Ändern der Darstellung von Basisformularen</span><span class="sxs-lookup"><span data-stu-id="543ae-121">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="543ae-122">Visuelle Vererbung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="543ae-122">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
