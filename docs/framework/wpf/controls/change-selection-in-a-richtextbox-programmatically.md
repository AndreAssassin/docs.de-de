---
title: Programmgesteuertes Ändern der Auswahl in einem RichTextBox-Element
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: b8acfe7cde1fe5dae96cd6324f75c5b146be9ec9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62001714"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a>Programmgesteuertes Ändern der Auswahl in einem RichTextBox-Element
Dieses Beispiel zeigt, wie Sie programmgesteuert ändern Sie die aktuelle Auswahl in einem <xref:System.Windows.Controls.RichTextBox>. Diese Auswahl ist identisch, als ob der Benutzer den Inhalt mithilfe der Benutzeroberfläche ausgewählt haben.  
  
## <a name="example"></a>Beispiel  
 Die folgenden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Code beschreibt ein benanntes <xref:System.Windows.Controls.RichTextBox> -Steuerelement mit einfachem Inhalt.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code wählt programmgesteuert beliebigen Text, klickt der Benutzer innerhalb der <xref:System.Windows.Controls.RichTextBox>.  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über RichTextBox](richtextbox-overview.md)
- [Übersicht über TextBox](textbox-overview.md)
