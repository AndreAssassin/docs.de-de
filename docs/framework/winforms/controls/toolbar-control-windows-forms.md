---
title: ToolBar-Steuerelement (Windows Forms)
ms.date: 03/30/2017
helpviewer_keywords:
- toolbars [Windows Forms]
- ToolBar control [Windows Forms]
ms.assetid: 6b40e9ce-6a7a-4784-bfc9-7f1d36b7462e
ms.openlocfilehash: 3f0a1b6a7f83753ccae1a129528ed320a2613122
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62009546"
---
# <a name="toolbar-control-windows-forms"></a>ToolBar-Steuerelement (Windows Forms)
> [!NOTE]
>  Obwohl das <xref:System.Windows.Forms.ToolStrip>-Steuerelement das `ToolBar`-Steuerelement ersetzt und funktionell erweitert, wird das `ToolBar`-Steuerelement sowohl aus Gründen der Abwärtskompatibilität als auch, falls gewünscht, für die zukünftige Verwendung beibehalten.  
  
 Das `ToolBar`-Steuerelement von Windows Forms wird in Formularen als eine Steuerleiste verwendet, auf der eine Zeile aus Dropdownmenüs und Bitmapschaltflächen angezeigt wird, die Befehle aktivieren. Daher ist ein Klicken auf eine Symbolleistenschaltfläche mit dem Auswählen eines Menübefehls identisch. Die Schaltflächen können so konfiguriert werden, dass sie so angezeigt werden und sich so verhalten wie Schaltflächen, Dropdownmenüs oder Trennzeichen. In der Regel enthält eine Symbolleiste Schaltflächen und Menüs, die Elementen in der Menüstruktur einer Anwendung entsprechen. Dadurch wird schneller Zugriff auf die am häufigsten verwendeten Funktionen und Befehle einer Anwendung ermöglicht.  
  
> [!NOTE]
>  Die <xref:System.Windows.Forms.ToolBarButton.DropDownMenu%2A>-Eigenschaft des `ToolBar`-Steuerelements übernimmt eine Instanz der <xref:System.Windows.Forms.ContextMenu>-Klasse als Verweis. Wenn Sie diese Art von Schaltfläche auf einer Symbolleiste in Ihrer Anwendung implementieren, sollten Sie sorgfältig auf den Verweis achten, den Sie übergeben, denn die Eigenschaft akzeptiert jedes Objekt, das von der <xref:System.Windows.Forms.Menu>-Klasse erbt.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Übersicht über das ToolBar-Steuerelement](toolbar-control-overview-windows-forms.md)  
 Stellt die allgemeinen Konzepte des `ToolBar`-Steuerelements vor, mit dem Sie benutzerdefinierte Symbolleisten entwerfen können, mit denen Benutzer arbeiten können.  
  
 [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement](how-to-add-buttons-to-a-toolbar-control.md)  
 Beschreibt, wie ein `ToolBar`-Steuerelement hinzugefügt wird.  
  
 [Vorgehensweise: Definieren eines Symbols für eine Symbolleisten-Schaltfläche](how-to-define-an-icon-for-a-toolbar-button.md)  
 Beschreibt, wie Symbole auf den Schaltflächen eines `ToolBar`-Steuerelements angezeigt werden.  
  
 [Vorgehensweise: Trigger Menüereignissen für Symbolleistenschaltflächen](how-to-trigger-menu-events-for-toolbar-buttons.md)  
 Bietet Anweisungen zum Schreiben von Code, in dem interpretiert wird, auf welche Schaltfläche ein Benutzer in einem `ToolBar`-Steuerelement geklickt hat.  
  
 Weitere Informationen hierzu finden Sie auch unter [Gewusst wie: Definieren eines Symbols für eine Symbolleisten-Schaltfläche mithilfe des Designers](how-to-define-an-icon-for-a-toolbar-button-using-the-designer.md), [Vorgehensweise: Hinzufügen von Schaltflächen zu einem ToolBar-Steuerelement, das mithilfe des Designers](how-to-add-buttons-to-a-toolbar-control-using-the-designer.md).  
  
## <a name="reference"></a>Referenz  
 <xref:System.Windows.Forms.ToolBar>-Klasse  
 Enthält Referenzinformationen zur Klasse und zu ihren Membern.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Windows Forms-Steuerelemente](controls-to-use-on-windows-forms.md)  
 Enthält eine vollständige Liste der Windows Forms-Steuerelemente mit Links zu Informationen zur jeweiligen Verwendung.  
  
 [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)  
 Beschreibt Symbolleisten, die Menüs, Steuerelemente und Benutzersteuerelemente in Windows Forms-Anwendungen enthalten können.
