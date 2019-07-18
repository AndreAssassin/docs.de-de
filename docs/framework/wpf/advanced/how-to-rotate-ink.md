---
title: 'Vorgehensweise: Drehen von Freihandeingaben'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], rotating
- rotating ink [WPF]
ms.assetid: fac36cc9-dd01-41ca-9bde-9d33e3790bbe
ms.openlocfilehash: 31f5d0ffb6f0fdcdaef13bc44653f8c7938ac7f3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768458"
---
# <a name="how-to-rotate-ink"></a>Vorgehensweise: Drehen von Freihandeingaben
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird kopiert, der Freihand auf einer <xref:System.Windows.Controls.InkCanvas> auf eine <xref:System.Windows.Controls.Canvas> , enthält ein <xref:System.Windows.Controls.InkPresenter>.  Wenn die Anwendung die Freihandeingaben kopiert, dreht es auch die Freihandeingaben 90 Grad im Uhrzeigersinn.  
  
 [!code-xaml[HowToRotateInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[HowToRotateInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRotateInk/CSharp/Window1.xaml.cs#2)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine benutzerdefinierte <xref:System.Windows.Documents.Adorner> , die die Striche auf dreht ein <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-csharp[AdornerForStrokes#1](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/RotatingAdornerForStrokes.cs#1)]
 [!code-vb[AdornerForStrokes#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/RotatingAdornerForStrokes.vb#1)]  
  
 Im folgende Beispiel wird eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, definiert ein <xref:System.Windows.Controls.InkPresenter> und füllt sie mit Freihandeingaben. Die `Window_Loaded` Ereignishandler fügt den benutzerdefinierten Adorner, der die <xref:System.Windows.Controls.InkPresenter>.  
  
 [!code-xaml[AdornerForStrokes#2](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[AdornerForStrokes#3](~/samples/snippets/csharp/VS_Snippets_Wpf/AdornerForStrokes/CSharp/Window1.xaml.cs#3)]
 [!code-vb[AdornerForStrokes#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AdornerForStrokes/VisualBasic/Window1.xaml.vb#3)]
