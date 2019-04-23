---
title: 'Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- Direct3D9 [WPF interoperability], hosting Direct3D9 content
- WPF [WPF], hosting Direct3D9 content
ms.assetid: 60983736-0ab5-42cc-8b16-e9fbde261a43
ms.openlocfilehash: 07cfa5bed6e5af131a60a303f0702f18413043e8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59320228"
---
# <a name="walkthrough-hosting-direct3d9-content-in-wpf"></a>Exemplarische Vorgehensweise: Hosten von Direct3D9-Inhalt in WPF
Diese exemplarische Vorgehensweise veranschaulicht das Hosten von Direct3D9-Inhalt in einer Windows Presentation Foundation (WPF)-Anwendung.  
  
 Im Verlauf dieser exemplarischen Vorgehensweise führen Sie die folgenden Aufgaben aus:  
  
-   Erstellen Sie ein WPF-Projekt zum Hosten von Direct3D9-Inhalt.  
  
-   Importieren des Direct3D9-Inhalts.  
  
-   Zeigt den Direct3D9-Inhalt mithilfe der <xref:System.Windows.Interop.D3DImage> Klasse.  
  
 Wenn Sie fertig sind, wissen Sie, wie zum Hosten von Direct3D9-Inhalt in einer WPF-Anwendung.  
  
## <a name="prerequisites"></a>Vorraussetzungen  
 Zum Durchführen dieser exemplarischen Vorgehensweise benötigen Sie die folgenden Komponenten:  
  
-   Visual Studio.  
  
-   DirectX SDK 9 oder höher.  
  
-   Eine DLL, die von Direct3D9-Inhalt in einem WPF-kompatiblen Format enthält. Weitere Informationen finden Sie unter [zwischen WPF und Direct3D9](wpf-and-direct3d9-interoperation.md) und [Exemplarische Vorgehensweise: Erstellen von Direct3D9-Inhalten zum Hosten in WPF](walkthrough-creating-direct3d9-content-for-hosting-in-wpf.md).  
  
## <a name="creating-the-wpf-project"></a>Erstellen des WPF-Projekts  
 Der erste Schritt ist die Erstellung des Projekts für die WPF-Anwendung.  
  
#### <a name="to-create-the-wpf-project"></a>So erstellen Sie das WPF-Projekt  
  
-   Erstellen Sie ein neues WPF-Anwendungsprojekt in Visual c# mit dem Namen `D3DHost`. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Meine erste WPF-Desktopanwendung](../getting-started/walkthrough-my-first-wpf-desktop-application.md).  
  
     Datei "MainWindow.xaml" wird geöffnet, der [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].  
  
## <a name="importing-the-direct3d9-content"></a>Importieren des Direct3D9-Inhalts  
 Importieren Sie den Direct3D9-Inhalt aus einer nicht verwalteten DLL mithilfe der `DllImport` Attribut.  
  
#### <a name="to-import-direct3d9-content"></a>Zum Importieren von Direct3D9-Inhalt  
  
1. Öffnen Sie "MainWindow.Xaml.cs" im Code-Editor.  
  
2. Ersetzen Sie den automatisch generierten Code durch den folgenden Code ein.  
  
     [!code-csharp[System.Windows.Interop.D3DImage#1](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml.cs#1)]  
  
## <a name="hosting-the-direct3d9-content"></a>Hosten von Direct3D9-Inhalt  
 Verwenden Sie abschließend die <xref:System.Windows.Interop.D3DImage> -Klasse zum Hosten von Direct3D9-Inhalt.  
  
#### <a name="to-host-the-direct3d9-content"></a>Zum Hosten von Direct3D9-Inhalt  
  
1. Ersetzen Sie in "MainWindow.xaml" die automatisch generierte XAML mit dem folgenden XAML.  
  
     [!code-xaml[System.Windows.Interop.D3DImage#10](~/samples/snippets/csharp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/CS/window1.xaml#10)]  
  
2. Erstellen Sie das Projekt.  
  
3. Kopieren Sie die DLL mit dem Direct3D9-Inhalt in den Ordner "bin" / Debug ist.  
  
4. Drücken Sie F5, um das Projekt auszuführen.  
  
     Der Direct3D9-Inhalt wird innerhalb der WPF-Anwendung.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.D3DImage>
- [Überlegungen zur Leistung für die Interoperabilität zwischen Direct3D9 und WPF](performance-considerations-for-direct3d9-and-wpf-interoperability.md)
