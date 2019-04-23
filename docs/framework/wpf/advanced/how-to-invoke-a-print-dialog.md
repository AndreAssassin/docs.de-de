---
title: 'Vorgehensweise: Aufrufen eines Druckdialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 2ced508eb83e2955fdcd1ad87fb6415e2052446f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206043"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="5e298-102">Vorgehensweise: Aufrufen eines Druckdialogfelds</span><span class="sxs-lookup"><span data-stu-id="5e298-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="5e298-103">Um die Funktion zum Drucken von aus der Anwendung zu ermöglichen, Sie können einfach erstellen und öffnen Sie eine <xref:System.Windows.Controls.PrintDialog> Objekt.</span><span class="sxs-lookup"><span data-stu-id="5e298-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e298-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e298-104">Example</span></span>  
 <span data-ttu-id="5e298-105">Das <xref:System.Windows.Controls.PrintDialog>-Steuerelement stellt einen einheitlichen Einstiegspunkt für [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], Konfiguration und [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)]-Auftragsübermittlung bereit.</span><span class="sxs-lookup"><span data-stu-id="5e298-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="5e298-106">Das Steuerelement ist benutzerfreundlich und kann instanziiert werden, indem [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup oder Code.</span><span class="sxs-lookup"><span data-stu-id="5e298-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="5e298-107">Im folgende Beispiel wird veranschaulicht, wie zu instanziieren und öffnen Sie das Steuerelement in Code und daraus zu drucken.</span><span class="sxs-lookup"><span data-stu-id="5e298-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="5e298-108">Es wird gezeigt, wie stellen Sie sicher, dass das Dialogfeld die Benutzer die Möglichkeit, einen bestimmten Bereich von Seiten festlegen erhält.</span><span class="sxs-lookup"><span data-stu-id="5e298-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="5e298-109">Im Beispielcode wird davon ausgegangen, dass eine FixedDocumentSequence.xps-Datei im Stammverzeichnis von Laufwerk C: vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="5e298-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="5e298-110">Sobald das Dialogfeld geöffnet ist, werden Benutzer auf dem Computer installierten Drucker auswählen können.</span><span class="sxs-lookup"><span data-stu-id="5e298-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="5e298-111">Haben sie auch die Option der Auswahl der [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) erstellen eine [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] Datei drucken.</span><span class="sxs-lookup"><span data-stu-id="5e298-111">They will also have the option of selecting the [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5e298-112">Die <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Kontrolle über [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], die in diesem Thema erläutert wird darf nicht mit verwechselt werden die <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> -Komponente von Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="5e298-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="5e298-113">Genau genommen können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> -Methode ohne jemals Öffnen des Dialogfelds.</span><span class="sxs-lookup"><span data-stu-id="5e298-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="5e298-114">In dieser Hinsicht kann das Steuerelement als eine Druckkomponente verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5e298-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="5e298-115">Aber zur Verbesserung der Leistung, es wäre besser, verwenden Sie entweder die <xref:System.Printing.PrintQueue.AddJob%2A> Methode oder eine der zahlreichen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter>.</span><span class="sxs-lookup"><span data-stu-id="5e298-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="5e298-116">Weitere Informationen hierzu finden Sie unter [Programmgesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md) und.</span><span class="sxs-lookup"><span data-stu-id="5e298-116">For more about this, see [Programmatically Print XPS Files](how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e298-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e298-117">See also</span></span>

- <xref:System.Windows.Controls.PrintDialog>
- [<span data-ttu-id="5e298-118">Dokumente in WPF</span><span class="sxs-lookup"><span data-stu-id="5e298-118">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="5e298-119">Übersicht über das Drucken</span><span class="sxs-lookup"><span data-stu-id="5e298-119">Printing Overview</span></span>](printing-overview.md)
- [<span data-ttu-id="5e298-120">Microsoft XPS-Dokument-Generator</span><span class="sxs-lookup"><span data-stu-id="5e298-120">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
