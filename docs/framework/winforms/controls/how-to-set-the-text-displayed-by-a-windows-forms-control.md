---
title: 'Vorgehensweise: Festlegen des durch ein Windows Forms-Steuerelement angezeigten Textes'
ms.date: 08/20/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, captions
- Button control [Windows Forms], button text
- StdFont object and CommandButton caption
- captions [Windows Forms], Windows Forms controls
- Text property [Windows Forms], Windows Forms control
- Button control [Windows Forms], text display
- labels [Windows Forms], adding to CommandButton control
- buttons [Windows Forms], text
- captions [Windows Forms], setting
- text
- examples [Windows Forms], controls
- text [Windows Forms], Windows Forms controls
- controls [Windows Forms], captions
- forms [Windows Forms], captions
ms.assetid: 36b95bff-8780-479d-b86a-f1a0673653aa
ms.openlocfilehash: 887aa5ec9b97770903cd87459d6df5adc3f7ddf0
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666156"
---
# <a name="how-to-set-the-text-displayed-by-a-windows-forms-control"></a><span data-ttu-id="7dd98-102">Vorgehensweise: Festlegen des von einem Windows Forms-Steuerelement angezeigten Texts</span><span class="sxs-lookup"><span data-stu-id="7dd98-102">How to: Set the text displayed by a Windows Forms control</span></span>

<span data-ttu-id="7dd98-103">Windows Forms Steuerelemente zeigen normalerweise Text an, der mit der primären Funktion des Steuer Elements verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="7dd98-103">Windows Forms controls usually display some text that's related to the primary function of the control.</span></span> <span data-ttu-id="7dd98-104">Ein <xref:System.Windows.Forms.Button> Steuerelement zeigt beispielsweise in der Regel eine Beschriftung an, die angibt, welche Aktion ausgeführt wird, wenn auf die Schaltfläche geklickt wird.</span><span class="sxs-lookup"><span data-stu-id="7dd98-104">For example, a <xref:System.Windows.Forms.Button> control usually displays a caption indicating what action will be performed if the button is clicked.</span></span> <span data-ttu-id="7dd98-105">Bei allen Steuerelementen können Sie den Text mithilfe der <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft festlegen oder zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="7dd98-105">For all controls, you can set or return the text by using the <xref:System.Windows.Forms.Control.Text%2A> property.</span></span> <span data-ttu-id="7dd98-106">Sie können die Schriftart ändern, indem Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft verwenden.</span><span class="sxs-lookup"><span data-stu-id="7dd98-106">You can change the font by using the <xref:System.Windows.Forms.Control.Font%2A> property.</span></span>

<span data-ttu-id="7dd98-107">Sie können den Text auch mit dem- [Designer](#designer)festlegen.</span><span class="sxs-lookup"><span data-stu-id="7dd98-107">You can also set the text by using the [designer](#designer).</span></span>

## <a name="programmatic"></a><span data-ttu-id="7dd98-108">Programmgesteuerten</span><span class="sxs-lookup"><span data-stu-id="7dd98-108">Programmatic</span></span>

1. <span data-ttu-id="7dd98-109">Legen Sie für die <xref:System.Windows.Forms.Control.Text%2A>-Eigenschaft eine Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="7dd98-109">Set the <xref:System.Windows.Forms.Control.Text%2A> property to a string.</span></span>

   <span data-ttu-id="7dd98-110">Zum Erstellen einer unterstrichenen Zugriffstaste enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Zugriffstaste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7dd98-110">To create an underlined access key, includes an ampersand (&) before the letter that will be the access key.</span></span>

2. <span data-ttu-id="7dd98-111">Legen Sie die <xref:System.Windows.Forms.Control.Font%2A>-Eigenschaft auf ein Objekt des Typs <xref:System.Drawing.Font> fest.</span><span class="sxs-lookup"><span data-stu-id="7dd98-111">Set the <xref:System.Windows.Forms.Control.Font%2A> property to an object of type <xref:System.Drawing.Font>.</span></span>

    ```vb
    Button1.Text = "Click here to save changes"
    Button1.Font = New Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point)
    ```

    ```csharp
    button1.Text = "Click here to save changes";
    button1.Font = new Font("Arial", 10, FontStyle.Bold, GraphicsUnit.Point);
    ```

    ```cpp
    button1->Text = "Click here to save changes";
    button1->Font = new System::Drawing::Font("Arial", 10, FontStyle::Bold, GraphicsUnit::Point);
    ```

    > [!NOTE]
    > <span data-ttu-id="7dd98-112">Mit einem Escapezeichen können Sie ein Sonderzeichen in Benutzeroberflächenelementen anzeigen, das diese normalerweise anders interpretieren würde, z. B. Menüelemente.</span><span class="sxs-lookup"><span data-stu-id="7dd98-112">You can use an escape character to display a special character in user-interface elements that would normally interpret them differently, such as menu items.</span></span> <span data-ttu-id="7dd98-113">Mit der folgenden Codezeile wird z. b. der Text des Menü Elements so festgelegt, dass der Text "& jetzt für etwas unterschiedliches Element" lautet:</span><span class="sxs-lookup"><span data-stu-id="7dd98-113">For example, the following line of code sets the menu item's text to read "& Now For Something Completely Different":</span></span>

    ```vb
    MPMenuItem.Text = "&& Now For Something Completely Different"
    ```

    ```csharp
    mpMenuItem.Text = "&& Now For Something Completely Different";
    ```

    ```cpp
    mpMenuItem->Text = "&& Now For Something Completely Different";
    ```

## <a name="designer"></a><span data-ttu-id="7dd98-114">Designer</span><span class="sxs-lookup"><span data-stu-id="7dd98-114">Designer</span></span>

1. <span data-ttu-id="7dd98-115">Legen Sie im **Eigenschaften** Fenster von Visual Studio die **Text** -Eigenschaft des-Steuer Elements auf eine entsprechende Zeichenfolge fest.</span><span class="sxs-lookup"><span data-stu-id="7dd98-115">In the **Properties** window in Visual Studio, set the **Text** property of the control to an appropriate string.</span></span>

   <span data-ttu-id="7dd98-116">Zum Erstellen einer unterstrichenen Tastenkombination enthält ein kaufmännisches und-(&) vor dem Buchstaben, der als Tastenkombination verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7dd98-116">To create an underlined shortcut key, includes an ampersand (&) before the letter that will be the shortcut key.</span></span>

2. <span data-ttu-id="7dd98-117">Wählen Sie im Fenster **Eigenschaften** die Schaltfläche mit den Auslassungs Punkten (![Auslassungs Zeichen (...) im Eigenschaftenfenster von Visual Studio](./media/visual-studio-ellipsis-button.png)) neben der Eigenschaft **Schriftart** aus.</span><span class="sxs-lookup"><span data-stu-id="7dd98-117">In the **Properties** window, select the ellipsis button (![Ellipsis button (...) in the Properties window of Visual Studio](./media/visual-studio-ellipsis-button.png)) next to the **Font** property.</span></span>

   <span data-ttu-id="7dd98-118">Wählen Sie im Dialogfeld Standard Schriftart die Schriftart, den Schrift Schnitt, die Größe, die Effekte (z. b. durchgestrichen oder unterstreichen) und das gewünschte Skript aus.</span><span class="sxs-lookup"><span data-stu-id="7dd98-118">In the standard font dialog box, select the font, font style, size, effects (such as strikeout or underline), and script that you want.</span></span>

## <a name="see-also"></a><span data-ttu-id="7dd98-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dd98-119">See also</span></span>

- <xref:System.Windows.Forms.Control.Text%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7dd98-120">Vorgehensweise: Erstellen von Zugriffs Schlüsseln für Windows Forms Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="7dd98-120">How to: Create Access Keys for Windows Forms Controls</span></span>](how-to-create-access-keys-for-windows-forms-controls.md)
- [<span data-ttu-id="7dd98-121">Vorgehensweise: Antworten auf Windows Forms Schaltflächen Klicks</span><span class="sxs-lookup"><span data-stu-id="7dd98-121">How to: Respond to Windows Forms Button Clicks</span></span>](how-to-respond-to-windows-forms-button-clicks.md)
