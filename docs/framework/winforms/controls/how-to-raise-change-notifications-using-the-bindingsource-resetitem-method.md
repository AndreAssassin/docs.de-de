---
title: 'Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der ResetItem-Methode einer BindingSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: 68073f245e1a2eb18a277d7011ca0183dabb3724
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61913145"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a>Vorgehensweise: Auslösen von Änderungsbenachrichtigungen mithilfe der ResetItem-Methode einer BindingSource
Einige Datenquellen für Ihre Steuerelemente lösen keine Änderungsbenachrichtigungen aus, wenn Elemente geändert, hinzugefügt oder gelöscht werden Mit der <xref:System.Windows.Forms.BindingSource>-Komponente können Sie Bindungen zu solchen Datenquellen herstellen und Änderungsbenachrichtigungen in Ihrem Code auslösen.  
  
## <a name="example"></a>Beispiel  
 Anhand dieses Formular wird gezeigt, wie Sie mit einer <xref:System.Windows.Forms.BindingSource>-Komponente eine Liste an ein <xref:System.Windows.Forms.DataGridView>-Steuerelement binden können. Diese Liste löst keine Änderungsbenachrichtigungen aus, weshalb die <xref:System.Windows.Forms.BindingSource.ResetItem%2A>-Methode für die <xref:System.Windows.Forms.BindingSource> aufgerufen wird, wenn ein Element in der Liste ändert wurde. sein.  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
- Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".  
  
 Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md). Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [BindingSource-Komponente](bindingsource-component.md)
- [Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ](how-to-bind-a-windows-forms-control-to-a-type.md)
