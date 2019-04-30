---
title: 'Vorgehensweise: Treffertest mithilfe eines Win32-Hostcontainers'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], using Win32 host containers
- visual objects [WPF], hit tests on
- Win32 host containers [WPF], hit tests using
ms.assetid: 9491f7f3-d8ba-4573-a888-2f064d1349dc
ms.openlocfilehash: ac5cae5bcd94dc8bf80ff95b8971914e1fa5ba2c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62025105"
---
# <a name="how-to-hit-test-using-a-win32-host-container"></a>Vorgehensweise: Treffertest mithilfe eines Win32-Hostcontainers
Sie können visuelle Objekte in erstellen eine [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster durch Bereitstellen eines Hosts Hostcontainer für visuelle Objekte. Verarbeiten Sie die Meldungen, die an die Meldungsfilterschleife des Hostcontainers übergeben werden, um für die visuellen Objekte im Container die Ereignisbehandlung bereitzustellen. Finden Sie unter [Lernprogramm: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md) für Weitere Informationen zum Hosten von visuellen Objekten in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code zeigt, wie Sie Mausereignishandler für Einrichten einer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, das als Hostcontainer für visuelle Objekte verwendet wird.  
  
 [!code-csharp[VisualsHitTesting#103](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyWindow.cs#103)]
 [!code-vb[VisualsHitTesting#103](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyWindow.vb#103)]  
  
 Das folgende Beispiel zeigt, wie Sie einen Treffertest als Reaktion auf abgefangene Mausereignisse einrichten.  
  
 [!code-csharp[VisualsHitTesting#104](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsHitTesting/CSharp/MyCircle.cs#104)]
 [!code-vb[VisualsHitTesting#104](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsHitTesting/VisualBasic/MyCircle.vb#104)]  
  
 Die <xref:System.Windows.Interop.HwndSource> -Objekt [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Inhalt in einem [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)] Fenster. Der Wert des der <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft der <xref:System.Windows.Interop.HwndSource> -Objekt stellt den obersten Knoten in der Hierarchie der visuellen Struktur dar.  
  
 Das vollständige Beispiel für Treffertests Objekte mithilfe eines Win32-Hostcontainers, finden Sie unter [Treffertests mit Win32-Interoperabilität](https://go.microsoft.com/fwlink/?LinkID=159995).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Treffertests in der visuellen Ebene](hit-testing-in-the-visual-layer.md)
- [Tutorial: Hosten von visuellen Objekten in einer Win32-Anwendung](tutorial-hosting-visual-objects-in-a-win32-application.md)
