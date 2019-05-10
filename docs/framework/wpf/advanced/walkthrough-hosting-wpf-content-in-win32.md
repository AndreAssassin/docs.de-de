---
title: 'Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32'
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- hosting WPF content in Win32 window [WPF]
ms.assetid: 38ce284a-4303-46dd-b699-c9365b22a7dc
ms.openlocfilehash: 01ac0e2cafc704b64634f1fb36145387b49c34a0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64650789"
---
# <a name="walkthrough-hosting-wpf-content-in-win32"></a>Exemplarische Vorgehensweise: Hosten von WPF-Inhalt in Win32
[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] stellt eine umfangreiche Umgebung zum Erstellen von Anwendungen bereit. Wenn Sie allerdings bereits erheblichen Aufwand für [!INCLUDE[TLA#tla_win32](../../../../includes/tlasharptla-win32-md.md)]-Code betrieben haben, kann es effektiver sein, zumindest einen Teil dieses Codes in Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Anwendung wieder zu verwenden, anstatt ihn vollständig neu zu schreiben. [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] bietet ein einfaches Verfahren zum Hosten von [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster.  
  
 In diesem Tutorial wird beschrieben, wie eine beispielanwendung schreiben [Hosten von WPF-Inhalt in einem Win32-Fenster](https://go.microsoft.com/fwlink/?LinkID=160004), die von Hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster. Dieses Beispiel kann auf das Hosten beliebiger [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fenster erweitert werden.  Da verwalteter und nicht verwalteter Code kombiniert werden muss, wird die Anwendung in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] geschrieben.  

<a name="requirements"></a>   
## <a name="requirements"></a>Anforderungen  
 In diesem Lernprogramm wird vorausgesetzt, dass Sie mit den Grundlagen der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung und der [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Programmierung vertraut sind. Für eine grundlegende Einführung in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Programmierung finden Sie [Einstieg](../getting-started/index.md). Eine Einführung in die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] , Sie-Programmierung zahlreichen Büchern zu diesem Thema, insbesondere *Programming Windows* von Charles Petzold.  
  
 Da das Beispiel, das in diesem Lernprogramm begleitet in implementiert ist [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], in diesem Tutorial wird davon ausgegangen, Vertrautheit mit der Verwendung von [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)] Programm die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] [!INCLUDE[TLA2#tla_api](../../../../includes/tla2sharptla-api-md.md)] sowie einen Überblick über die Programmierung von verwaltetem Code. Grundkenntnisse in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] sind hilfreich, aber keine Voraussetzung.  
  
> [!NOTE]
>  Dieses Lernprogramm enthält eine Reihe von Codebeispielen aus dem genannten Beispiel. Aus Gründen der besseren Lesbarkeit wird jedoch nicht der gesamte Beispielcode aufgeführt. Den vollständigen Beispielcode finden Sie unter [Hosten von WPF-Inhalt in einem Win32-Fenster](https://go.microsoft.com/fwlink/?LinkID=160004).  
  
<a name="basic_procedure"></a>   
## <a name="the-basic-procedure"></a>Das grundlegende Verfahren  
 Dieser Abschnitt enthält das grundlegende Verfahren, die Sie, um verwenden Hosts [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster. In den weiteren Abschnitten werden die einzelnen Schritte näher erläutert.  
  
 Entscheidend für das Hosten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] von Inhalt an einen [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster ist die <xref:System.Windows.Interop.HwndSource> Klasse. Diese Klasse umschließt die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, sodass er integriert werden soll Ihre [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] als untergeordnetes Fenster. Bei folgender Vorgehensweise werden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] und [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in einer einzigen Anwendung zusammengefasst.  
  
1. Implementieren Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhalt als verwaltete Klasse.  
  
2. Implementieren Sie eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendung mit [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]. Wenn Sie mit einer vorhandenen Anwendung und nicht verwaltetem [!INCLUDE[TLA#tla_cpp](../../../../includes/tlasharptla-cpp-md.md)]-Code beginnen, können Sie diese in der Regel verwalteten Code aufrufen lassen, indem Sie das `/clr`-Compilerflag in die Projekteinstellungen aufnehmen.  
  
3. Legen Sie das Threadingmodell auf Singlethread-Apartment (STA) fest.  
  
4. Behandeln der [WM_CREATE](/windows/desktop/winmsg/wm-create)Benachrichtigung in Ihrer Fensterprozedur, und führen Sie folgende Schritte:  
  
    1. Erstellen Sie ein neues <xref:System.Windows.Interop.HwndSource>-Objekt, und verwenden Sie das übergeordnete Fenster als `parent`-Parameter.  
  
    2. Erstellen Sie eine Instanz der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse.  
  
    3. Weisen Sie einen Verweis auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhaltsobjekt zu den <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft der <xref:System.Windows.Interop.HwndSource>.  
  
    4. Rufen Sie HWND für den Inhalt ab. Die <xref:System.Windows.Interop.HwndSource.Handle%2A>-Eigenschaft des <xref:System.Windows.Interop.HwndSource>-Objekts enthält das Fensterhandle (HWND). Um ein HWND zu erhalten, das Sie im nicht verwalteten Teil der Anwendung verwenden können, wandeln Sie `Handle.ToPointer()` in ein HWND um.  
  
5. Implementieren Sie eine verwaltete Klasse, die ein statisches Feld mit einem Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt enthält. Diese Klasse ermöglicht Ihnen, einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code abzurufen.  
  
6. Weisen Sie dem statischen Feld den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu.  
  
7. Empfangen von Benachrichtigungen vom die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -inhaltsobjektereignisse einen Handler an eine oder mehrere der Inhalt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Ereignisse.  
  
8. Kommunizieren Sie mithilfe des im statischen Feld gespeicherten Verweises mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt, um Eigenschaften festzulegen usw.  
  
> [!NOTE]
>  Sie können auch [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] zum Implementieren Ihrer [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Sie müssen ihn allerdings separat als eine [!INCLUDE[TLA#tla_dll](../../../../includes/tlasharptla-dll-md.md)] kompilieren und auf diese [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] aus Ihrer [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendung heraus verweisen. Die übrigen Schritte ähneln dem oben beschriebenen Verfahren. 

<a name="implementing_the_application"></a>
## <a name="implementing-the-host-application"></a>Implementieren der Hostanwendung
 In diesem Abschnitt wird beschrieben, wie Sie Host [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhalt in einer grundlegenden [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Anwendung. Der Inhalt selbst wird in [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)] als verwaltete Klasse implementiert. Größtenteils handelt es sich um eine einfache [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Programmierung. Die wichtigsten Aspekte der Content-Implementierung finden Sie im [Implementieren des WPF-Inhalts](#implementing_the_wpf_page).

<a name="autoNestedSectionsOUTLINE1"></a>
- [Die grundlegende Anwendung](#the_basic_application)

- [Hosten des WPF-Inhalts](#hosting_the_wpf_page)

- [Verweisen auf den WPF-Inhalt](#holding_a_reference)

- [Kommunizieren mit dem WPF-Inhalt](#communicating_with_the_page)

<a name="the_basic_application"></a>
### <a name="the-basic-application"></a>Die grundlegende Anwendung
 Der Ausgangspunkt für die hostanwendung bestand darin, eine Visual Studio 2005-Vorlage zu erstellen.

1. Öffnen Sie Visual Studio 2005, und wählen Sie **neues Projekt** aus der **Datei** Menü.

2. Wählen Sie **Win32** aus der Liste der [!INCLUDE[TLA2#tla_visualcpp](../../../../includes/tla2sharptla-visualcpp-md.md)] Projekttypen. Wenn Ihre Standardsprache nicht [!INCLUDE[TLA2#tla_cpp](../../../../includes/tla2sharptla-cpp-md.md)], finden Sie diese Projekttypen unter **andere Sprachen**.

3. Wählen Sie eine **Win32-Projekt** -Vorlage aus, weisen Sie einen Namen für das Projekt, und klicken Sie auf **OK** zum Starten der **Win32-Anwendungsassistenten**.

4. Akzeptieren Sie die Standardeinstellungen des Assistenten, und klicken Sie auf **Fertig stellen** auf das Projekt zu starten.

 Mit der Vorlage wird eine grundlegende [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendung erstellt, die Folgendes enthält:

- Einen Einstiegspunkt für die Anwendung.

- Ein Fenster mit einer zugeordneten Fensterprozedur (WndProc).

- Ein Menü mit **Datei** und **Hilfe** Überschriften. Die **Datei** Menü enthält eine **beenden** Element, das die Anwendung geschlossen wird. Die **Hilfe** Menü enthält eine **zu** Element, ein einfaches Dialogfeld gestartet wird.

 Bevor Sie beginnen das Schreiben von Code zum Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, müssen Sie zwei Änderungen an der grundlegenden Vorlage vornehmen.

 Die erste besteht darin, das Projekt als verwalteten Code zu kompilieren. Standardmäßig wird das Projekt als nicht verwalteter Code kompiliert. Da aber [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] in verwaltetem Code implementiert wird, muss das Projekt entsprechend kompiliert werden.

1. Mit der rechten Maustaste in des Namens des Projekts **Projektmappen-Explorer** , und wählen Sie **Eigenschaften** aus dem Kontextmenü zum Starten der **Eigenschaftenseiten** Dialogfeld.

2. Wählen Sie **Konfigurationseigenschaften** aus der Strukturansicht im linken Bereich.

3. Wählen Sie **Common Language Runtime** aus unterstützen, die die **Projektstandards** Liste im rechten Bereich.

4. Wählen Sie **Common Language Runtime-Unterstützung (/ Clr)** aus dem Dropdown-Listenfeld.

> [!NOTE]
>  Das Compilerflag ermöglicht Ihnen, in der Anwendung verwalteten Code zu verwenden. Der nicht verwaltete Code wird jedoch wie zuvor kompiliert.

 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] verwendet das Threadingmodell Singlethread-Apartment (STA). Damit Sie einwandfrei funktionieren mit der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhaltscode, Sie müssen das Threadingmodell der Anwendung auf STA festlegen, indem Sie ein Attribut auf den Einstiegspunkt anwenden.

 [!code-cpp[Win32HostingWPFPage#WinMain](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#winmain)]

<a name="hosting_the_wpf_page"></a>
### <a name="hosting-the-wpf-content"></a>Hosten des WPF-Inhalts
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ist eine einfache Anwendung Eintrag. Sie besteht aus mehreren <xref:System.Windows.Controls.TextBox>-Steuerelementen zum Erfassen von Benutzername, Adresse usw. Es gibt auch zwei <xref:System.Windows.Controls.Button> Steuerelemente **OK** und **Abbrechen**. Wenn der Benutzer klickt **OK**, der Schaltfläche <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignishandler erfasst die Daten aus der <xref:System.Windows.Controls.TextBox> steuert, weist sie entsprechenden Eigenschaften und löst ein benutzerdefiniertes Ereignis `OnButtonClicked`. Wenn der Benutzer klickt **Abbrechen**, löst der Handler einfach `OnButtonClicked`. Das Ereignisargumentobjekt für `OnButtonClicked` enthält ein boolesches Feld, das angibt, auf welche Schaltfläche geklickt wurde.

 Der Code zum Hosten der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt wird in einem Handler für implementiert die [WM_CREATE](/windows/desktop/winmsg/wm-create) Benachrichtigung auf das Hostfenster.

 [!code-cpp[Win32HostingWPFPage#WMCreate](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcreate)]

 Die `GetHwnd` -Methode übernimmt Größen-und Positionsinformationen sowie das übergeordnete Fensterhandle und gibt das Fensterhandle des gehosteten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt.

> [!NOTE]
>  Sie können keine `#using`-Direktive für den `System::Windows::Interop`-Namespace verwenden. Dies würde zu einem Namenskonflikt zwischen der <xref:System.Windows.Interop.MSG>-Struktur in diesem Namespace und der in winuser.h deklarierten MSG-Struktur führen. Verwenden Sie stattdessen vollqualifizierte Namen, um auf den Inhalt dieses Namespace zuzugreifen.

 [!code-cpp[Win32HostingWPFPage#GetHwnd](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#gethwnd)]

 Sie können keine hosten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt direkt im Anwendungsfenster. Stattdessen müssen Sie zuerst ein <xref:System.Windows.Interop.HwndSource>-Objekt erstellen, um den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt zu umschließen. Dieses Objekt stellt im Wesentlichen ein Fenster, das zum Hosten dient eine [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Sie hosten die <xref:System.Windows.Interop.HwndSource> Objekt im übergeordneten Fenster, indem es als untergeordnetes Element erstellen eine [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] Fenster, das Teil Ihrer Anwendung ist. Die <xref:System.Windows.Interop.HwndSource>-Konstruktorparameter enthalten größtenteils dieselben Informationen, die Sie beim Erstellen eines untergeordneten [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Fensters an CreateWindow übergeben würden. 

 Als Nächstes erstellen Sie eine Instanz von der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Content-Objekt. In diesem Fall wird der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt unter Verwendung von `WPFPage` als separate Klasse, nämlich [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)], implementiert. Sie können den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt auch mit [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] implementieren. Hierzu Sie müssen allerdings ein separates Projekt einrichten, und erstellen die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte als ein [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)]. Sie können dem Projekt einen Verweis auf diese [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)] hinzufügen und ihn zum Erstellen einer Instanz des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts verwenden.

 Sie anzeigen, die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte in Ihrer untergeordneten Fenster einen Verweis auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalte an die <xref:System.Windows.Interop.HwndSource.RootVisual%2A> Eigenschaft der <xref:System.Windows.Interop.HwndSource>.

 Durch die nächste Codezeile wird ein Ereignishandler (`WPFButtonClicked`) an das [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Ereignis des `OnButtonClicked`-Inhalts angefügt. Dieser Handler wird aufgerufen, wenn der Benutzer klickt auf die **OK** oder **Abbrechen** Schaltfläche. Finden Sie unter [kommunizieren mit dem WPF-Inhalt](#communicating_with_the_page) für Weitere Informationen zu diesem Ereignishandler.

 Durch die letzte angezeigte Codezeile wird das Fensterhandle (HWND) zurückgegeben, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist. Sie können dieses Handle vom [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Code zum Senden von Meldungen an das gehostete Fenster verwenden, auch wenn das in diesem Beispiel nicht gezeigt wird. Das <xref:System.Windows.Interop.HwndSource>-Objekt löst jedes Mal ein Ereignis aus, wenn es eine Meldung empfängt. Rufen Sie zum Verarbeiten der Meldungen die <xref:System.Windows.Interop.HwndSource.AddHook%2A>-Methode auf, um einen Meldungshandler anzufügen und anschließend die Meldungen in diesem Handler zu verarbeiten.

<a name="holding_a_reference"></a>
### <a name="holding-a-reference-to-the-wpf-content"></a>Verweisen auf den WPF-Inhalt
 Bei vielen Anwendungen möchten Sie zu einem späteren Zeitpunkt mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt kommunizieren. Angenommen, Sie möchten die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften ändern oder vom <xref:System.Windows.Interop.HwndSource>-Objekt andere [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalte hosten lassen. Dazu benötigen Sie einen Verweis auf das <xref:System.Windows.Interop.HwndSource>-Objekt oder den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Das <xref:System.Windows.Interop.HwndSource>-Objekt und der zugehörige [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt bleiben im Arbeitsspeicher, bis Sie das Fensterhandle zerstören. Die Variable, die Sie dem <xref:System.Windows.Interop.HwndSource>-Objekt zuweisen, verlässt jedoch den Gültigkeitsbereich, sobald die Steuerung von der Fensterprozedur zurückgegeben wird. Eine übliche Methode, dieses Problem bei [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Anwendungen zu umgehen, besteht in der Verwendung einer statischen oder globalen Variablen. Leider können Sie diesen Variablentypen kein verwaltetes Objekt zuweisen. Sie können das Fensterhandle, das dem <xref:System.Windows.Interop.HwndSource>-Objekt zugeordnet ist, einer globalen oder statischen Variablen zuweisen. Dadurch erhalten Sie aber noch keinen Zugriff auf das Objekt.

 Die einfachste Lösung für dieses Problem besteht darin, eine verwaltete Klasse zu implementieren, die eine Reihe von statischen Feldern mit Verweisen auf alle verwalteten Objekte enthält, auf die Sie zugreifen müssen. Im Beispiel wird die `WPFPageHost`-Klasse für einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt verwendet. Außerdem soll sie die Anfangswerte einiger Eigenschaften enthalten, die später vom Benutzer geändert werden können. Dies wird im Header definiert.

 [!code-cpp[Win32HostingWPFPage#WPFPageHost](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.h#wpfpagehost)]

 Der letzte Teil der `GetHwnd`-Funktion weist diesen Feldern Werte zur späteren Verwendung zu, während `myPage` im Gültigkeitsbereich verbleibt.

<a name="communicating_with_the_page"></a>
### <a name="communicating-with-the-wpf-content"></a>Kommunizieren mit dem WPF-Inhalt
 Es gibt zwei Arten der Kommunikation mit dem [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt. Die Anwendung empfängt Informationen aus der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, wenn der Benutzer klickt auf die **OK** oder **Abbrechen** Schaltflächen. Die Anwendung verfügt auch über eine [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], die es dem Benutzer ermöglicht, zahlreiche [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften zu ändern, z. B. Hintergrundfarbe oder Standardschriftgröße.

 Wie oben erwähnt, löst der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt ein `OnButtonClicked`-Ereignis aus, wenn der Benutzer auf eine der beiden Schaltflächen klickt. Die Anwendung fügt einen Handler an dieses Ereignis an, um die entsprechenden Benachrichtigungen zu empfangen. Wenn die **OK** Schaltfläche geklickt wurde, ruft der Handler ab, die Benutzerinformationen aus der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, und zeigt ihn in eine Reihe von statischen Steuerelementen.

 [!code-cpp[Win32HostingWPFPage#WPFButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wpfbuttonclicked)]

 Der Handler empfängt ein benutzerdefiniertes Ereignisargumentobjekt vom [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt: `MyPageEventArgs`. Des Objekts `IsOK` -Eigenschaftensatz auf `true` Wenn die **OK** Schaltfläche geklickt wurde, und `false` Wenn die **Abbrechen** Schaltfläche geklickt wurde.

 Wenn die **OK** Schaltfläche geklickt wurde, der Handler Ruft einen Verweis auf die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt aus der Container-Klasse. Anschließend ruft er die Benutzerinformationen ab, die in den zugeordneten [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltseigenschaften enthalten sind. Dabei werden die statischen Steuerelemente zum Anzeigen der Informationen im übergeordneten Fenster verwendet. Da die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsdaten in Form einer verwalteten Zeichenfolge vorliegen, müssen Sie gemarshallt werden, damit sie von einem [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]-Steuerelement verwendet werden können. Wenn die **Abbrechen** Schaltfläche geklickt wurde, löscht der Handler die Daten aus den statischen Steuerelementen.

 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] der Anwendung stellt eine Reihe von Optionsfeldern bereit, mit denen der Benutzer die Hintergrundfarbe des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts und verschiedene Schriftarteigenschaften ändern kann. Das folgende Beispiel ist ein Auszug aus der Fensterprozedur der Anwendung (WndProc) und deren Meldungsbehandlung, die zahlreiche Eigenschaften für verschiedene Meldungen festlegt, darunter die Hintergrundfarbe. Die anderen sind ähnlich und werden nicht angezeigt. Sehen Sie sich das vollständige Beispiel an, um ausführliche Informationen, auch zum Kontext, zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WMCommandToBG](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/Win32HostingWPFPage.cpp#wmcommandtobg)]

 Wenn Sie die Hintergrundfarbe festlegen möchten, rufen Sie einen Verweis auf den [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt (`hostedPage`) von `WPFPageHost` ab, und legen Sie die Eigenschaft für die Hintergrundfarbe auf die entsprechende Farbe fest. Im Beispiel werden drei Farboptionen verwendet: die ursprüngliche Farbe, hellgrün oder helle Lachsfarbe. Die ursprüngliche Hintergrundfarbe wird als statisches Feld in der `WPFPageHost`-Klasse gespeichert. Um die anderen beiden festzulegen, erstellen Sie ein neues <xref:System.Windows.Media.SolidColorBrush>-Objekt und übergeben dem Konstruktor einen statischen Farbwert aus dem <xref:System.Windows.Media.Colors>-Objekt.

<a name="implementing_the_wpf_page"></a>
## <a name="implementing-the-wpf-page"></a>Implementieren der WPF-Seite
 Sie hosten können, und Verwenden der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt ohne Kenntnisse in der tatsächlichen Implementierung. Wenn die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt in einem separaten gepackt [!INCLUDE[TLA2#tla_dll](../../../../includes/tla2sharptla-dll-md.md)], es könnte erstellt wurden in einem [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Sprache. Es folgt eine kurze exemplarische Vorgehensweise zur [!INCLUDE[TLA#tla_cppcli](../../../../includes/tlasharptla-cppcli-md.md)]-Implementierung, die in diesem Beispiel verwendet wird. Dieser Abschnitt enthält folgende Unterabschnitte:

<a name="autoNestedSectionsOUTLINE2"></a>
- [Layout](#page_layout)

- [Zurückgeben der Daten an das Hostfenster](#returning_data_to_window)

- [Festlegen der WPF-Eigenschaften](#set_page_properties)

<a name="page_layout"></a>
### <a name="layout"></a>Layout
 Die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] Elemente in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhalt bestehen aus fünf <xref:System.Windows.Controls.TextBox> steuert, zugeordnete <xref:System.Windows.Controls.Label> Steuerelemente: Name, Adresse, City, State und Zip. Es gibt auch zwei <xref:System.Windows.Controls.Button> Steuerelemente **OK** und **Abbrechen**

 Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalt wird in der `WPFPage`-Klasse implementiert. Das Layout wird mit einem <xref:System.Windows.Controls.Grid>-Layoutelement behandelt. Die Klasse erbt von <xref:System.Windows.Controls.Grid>, wodurch sie zum Stammelement des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhalts wird.

 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Konstruktor-Inhalts übernimmt die erforderliche Breite und Höhe und Größe der <xref:System.Windows.Controls.Grid> entsprechend. Es definiert dann das grundlegende Layout durch Erstellen eines Satzes von <xref:System.Windows.Controls.ColumnDefinition> und <xref:System.Windows.Controls.RowDefinition> Objekte und Hinzufügen der <xref:System.Windows.Controls.Grid> Objekt Basis <xref:System.Windows.Controls.Grid.ColumnDefinitions%2A> und <xref:System.Windows.Controls.Grid.RowDefinitions%2A> Auflistungen bzw. Dadurch wird ein Raster von fünf Zeilen und sieben Spalten definiert. Die Abmessungen werden durch den Inhalt der Zellen bestimmt.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorToGridDef](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortogriddef)]

 Anschließend fügt der Konstruktor die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-Elemente zu <xref:System.Windows.Controls.Grid> hinzu. Das erste Element ist der Titeltext. Dabei handelt es sich um ein <xref:System.Windows.Controls.Label>-Steuerelement, das in der ersten Zeile des Rasters zentriert ist.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorTitle](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectortitle)]

 Die nächste Zeile enthält das <xref:System.Windows.Controls.Label>-Steuerelement für den Namen und das zugehörige <xref:System.Windows.Controls.TextBox>-Steuerelement. Da für jedes aus Beschriftung und Textfeld bestehende Paar derselbe Code verwendet wird, wird er in einem Paar privater Methoden platziert und für alle fünf Paare aus Beschriftung/Textfeld verwendet. Durch die Methoden wird das entsprechende Steuerelement erstellt, und es werden die statischen Methoden <xref:System.Windows.Controls.Grid> und <xref:System.Windows.Controls.Grid.SetColumn%2A> der <xref:System.Windows.Controls.Grid.SetRow%2A>-Klasse aufgerufen, um die Steuerelemente in der entsprechenden Zelle zu platzieren. Nachdem das Steuerelement erstellt wurde, wird im Beispiel die <xref:System.Windows.Controls.UIElementCollection.Add%2A>-Methode für die <xref:System.Windows.Controls.Panel.Children%2A>-Eigenschaft von <xref:System.Windows.Controls.Grid> aufgerufen, um das Steuerelement zum Raster hinzuzufügen. Der Code zum Hinzufügen der übrigen Beschriftung/Textfeld-Paare ist ähnlich. Sehen Sie sich den Beispielcode an, um ausführliche Informationen zu erhalten.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorName](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorname)]

 Die Implementierung der beiden Methoden wird wie folgt durchgeführt:

 [!code-cpp[Win32HostingWPFPage#WPFPageCreateHelpers](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagecreatehelpers)]

 Im Beispiel schließlich wird die **OK** und **Abbrechen** Schaltflächen und fügt einen Ereignishandler an ihre <xref:System.Windows.Controls.Primitives.ButtonBase.Click> Ereignisse.

 [!code-cpp[Win32HostingWPFPage#WPFPageCtorButtonsEvents](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagectorbuttonsevents)]

<a name="returning_data_to_window"></a>
### <a name="returning-the-data-to-the-host-window"></a>Zurückgeben der Daten an das Hostfenster
 Das <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignis wird durch Klicken auf eine der Schaltflächen ausgelöst. Das Hostfenster könnte einfach Handler an diese Ereignisse anfügen und die Daten direkt aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen abrufen. In diesem Beispiel wird ein weniger direkter Ansatz verwendet. Verarbeitet die <xref:System.Windows.Controls.Primitives.ButtonBase.Click> innerhalb der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt, und klicken Sie dann löst ein benutzerdefiniertes Ereignis `OnButtonClicked`, benachrichtigt der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Inhalt. Dadurch wird die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhalt die Gültigkeit einiger Parameter überprüfen, bevor der Host benachrichtigt wird. Der Handler fragt den Text aus den <xref:System.Windows.Controls.TextBox>-Steuerelementen ab und weist ihn öffentlichen Eigenschaften zu, aus denen der Host die Informationen abrufen kann.

 Die Ereignisdeklaration in WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageEventDecl](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpageeventdecl)]

 Der <xref:System.Windows.Controls.Primitives.ButtonBase.Click>-Ereignishandler in WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageButtonClicked](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagebuttonclicked)]

<a name="set_page_properties"></a>
### <a name="setting-the-wpf-properties"></a>Festlegen der WPF-Eigenschaften
 Die [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] -Host ermöglicht es den Benutzer, mehrere ändern [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] -Inhaltseigenschaften. In [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] müssen lediglich Eigenschaften geändert werden. Die Implementierung in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]-Inhaltsklasse ist etwas komplizierter, da es keine einzelne globale Eigenschaft gibt, mit der die Schriftarten für alle Steuerelemente gesteuert werden. Stattdessen wird die entsprechende Eigenschaft für die einzelnen Steuerelemente in den set-Accessoren der Eigenschaften geändert. Das folgende Beispiel zeigt den Code für die `DefaultFontFamily` Eigenschaft. Durch Festlegen der Eigenschaft wird eine private Methode aufgerufen, mit der die <xref:System.Windows.Controls.Control.FontFamily%2A>-Eigenschaften für die verschiedenen Steuerelemente festgelegt werden.

 Aus WPFPage.h:

 [!code-cpp[Win32HostingWPFPage#WPFPageFontFamilyProperty](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.h#wpfpagefontfamilyproperty)]

 Aus WPFPage.cpp:

 [!code-cpp[Win32HostingWPFPage#WPFPageSetFontFamily](~/samples/snippets/cpp/VS_Snippets_Wpf/Win32HostingWPFPage/CPP/WPFPage.cpp#wpfpagesetfontfamily)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Interop.HwndSource>
- [Interaktion zwischen WPF und Win32](wpf-and-win32-interoperation.md)
