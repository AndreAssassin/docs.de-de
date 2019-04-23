---
title: 'Vorgehensweise: Bestimmen, welche Zusatztaste gedrückt wurde'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 571af49cdf82b876cfb72a7c7636874c8d155fb7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213935"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a>Vorgehensweise: Bestimmen, welche Zusatztaste gedrückt wurde
Wenn Sie eine Anwendung, die die Tastaturanschläge des Benutzers akzeptiert erstellen, können Sie auch Zusatztasten wie die Tasten UMSCHALT, ALT und STRG überwachen möchten. Wenn eine Taste in Kombination mit anderen Schlüsseln oder Mausklicks gedrückt wird, kann Ihre Anwendung entsprechend reagieren. Z. B. wenn die Buchstaben S gedrückt wird, einfach dadurch möglicherweise ein "s" auf dem Bildschirm angezeigt werden, aber wenn die Tasten STRG + S gedrückt werden, kann das aktuelle Dokument gespeichert werden. Verarbeitet die <xref:System.Windows.Forms.Control.KeyDown> -Ereignis, das <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> Eigenschaft der <xref:System.Windows.Forms.KeyEventArgs> empfangen vom Ereignis-Handler legt die Modifizierertasten gedrückt sind. Sie können auch die <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> Eigenschaft <xref:System.Windows.Forms.KeyEventArgs> gibt das Zeichen, die auch alle Zusatztasten, die mit einem bitweisen OR kombiniert gedrückt wurde. Aber wenn Sie behandeln die <xref:System.Windows.Forms.Control.KeyPress> Ereignis oder ein Mausereignis der Ereignishandler empfängt diese Informationen nicht. In diesem Fall müssen Sie verwenden die <xref:System.Windows.Forms.Control.ModifierKeys%2A> Eigenschaft der <xref:System.Windows.Forms.Control> Klasse. In beiden Fällen müssen Sie ein bitweises AND des entsprechenden ausführen <xref:System.Windows.Forms.Keys> Wert und der Wert, die Sie testen. Die <xref:System.Windows.Forms.Keys> Enumeration bietet Variationen der einzelnen Schlüssel Modifizierer, daher es wichtig ist, dass Sie den bitweisen ausführen und mit dem richtigen Wert. Beispielsweise wird durch die UMSCHALTTASTE gedrückt dargestellt <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> und <xref:System.Windows.Forms.Keys.LShiftKey> UMSCHALT zu testen, wie Sie Modifizierertaste wird der korrekte Wert <xref:System.Windows.Forms.Keys.Shift>. Auf ähnliche Weise, STRG und ALT als Modifizierer Sie testen sollten verwenden die <xref:System.Windows.Forms.Keys.Control> und <xref:System.Windows.Forms.Keys.Alt> Werte.  
  
> [!NOTE]
>  Visual Basic-Programmierer können auch Zugriff auf wichtige Informationen über die <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> Eigenschaft  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a>Um zu bestimmen, welche Zusatztaste gedrückt wurde  
  
-   Verwenden Sie den bitweisen `AND` -Operator mit der <xref:System.Windows.Forms.Control.ModifierKeys%2A> -Eigenschaft und den Wert der <xref:System.Windows.Forms.Keys> Enumeration, um zu bestimmen, ob eine bestimmte Modifizierertaste gedrückt wird. Im folgenden Codebeispiel wird veranschaulicht, um festzustellen, ob die UMSCHALT-Taste, innerhalb gedrückt wird einer <xref:System.Windows.Forms.Control.KeyPress> -Ereignishandler.  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [Tastatureingaben in einer Windows Forms-Anwendung](keyboard-input-in-a-windows-forms-application.md)
- [Vorgehensweise: Bestimmen Sie, dass wenn CapsLock ist in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
