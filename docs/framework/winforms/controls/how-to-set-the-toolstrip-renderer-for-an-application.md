---
title: 'Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Renderer property [Windows Forms]
- ToolStripProfessionalRenderer class [Windows Forms]
- ToolStrip control [Windows Forms]
- MenuStrip control [Windows Forms]
- toolbars [Windows Forms], customizing
ms.assetid: 46acef3e-9844-4ae8-9a2e-3006fe99cadf
ms.openlocfilehash: 22f9276a3fa7fcecf6b4667f5aaba489c6ed296e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64630578"
---
# <a name="how-to-set-the-toolstrip-renderer-for-an-application"></a>Vorgehensweise: Festlegen des ToolStrip-Renderers für eine Anwendung
Sie können die Darstellung von <xref:System.Windows.Forms.ToolStrip>-Steuerelementen einzeln oder für alle <xref:System.Windows.Forms.ToolStrip>-Steuerelemente in Ihrer Anwendung anpassen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie ein benutzerdefinierter Renderer selektiv auf ein <xref:System.Windows.Forms.ToolStrip>-Steuerelement und ein <xref:System.Windows.Forms.MenuStrip>-Steuerelement angewendet wird.  
  
 Um dieses Codebeispiel zu verwenden, kompilieren Sie die Anwendung, führen Sie diese aus, und wählen Sie dann den Bereich des benutzerdefinierten Renderings im <xref:System.Windows.Forms.ComboBox>-Steuerelement aus. Klicken Sie auf **Übernehmen**, um den Renderer festzulegen.  
  
 Um benutzerdefinierte Rendering von Menüelementen zu sehen, wählen die <xref:System.Windows.Forms.MenuStrip> option die <xref:System.Windows.Forms.ComboBox> steuern, klicken Sie auf **übernehmen**, und öffnen Sie dann die **Datei** Menüelement.  
  
 [!code-csharp[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#1)]
 [!code-vb[System.Windows.Forms.ToolStrip.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#1)]  
[!code-csharp[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/CS/Program.cs#70)]
[!code-vb[System.Windows.Forms.ToolStrip.Misc#70](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ToolStrip.Misc/VB/Program.vb#70)]  
  
 Legen Sie die <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType>-Eigenschaft fest, damit ein benutzerdefinierter Renderer auf alle <xref:System.Windows.Forms.ToolStrip>-Steuerelemente in Ihrer Anwendung angewendet wird.  
  
 Legen Sie die <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType>-Eigenschaft fest, damit ein benutzerdefinierter Renderer auf ein einzelnes <xref:System.Windows.Forms.ToolStrip>-Steuerelement angewendet wird.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System.Design", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.ToolStripManager>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- [ToolStrip-Steuerelement](toolstrip-control-windows-forms.md)
