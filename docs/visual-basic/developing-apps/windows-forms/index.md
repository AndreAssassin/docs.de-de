---
title: Grundlagen zu Windows Forms-Anwendungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 6ab898c93086e477bf4384b4d6c725fbdc8fe761
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879148"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)
Ein wichtiger Bestandteil von Visual Basic ist die Fähigkeit zum Erstellen von Windows Forms-Anwendungen, die lokal auf Benutzercomputern ausgeführt werden. Sie können Visual Studio verwenden, um die mithilfe von Windows Forms-Anwendung und die Benutzeroberfläche zu erstellen. Eine Windows Forms-Anwendung baut auf Klassen aus der <xref:System.Windows.Forms> Namespace.  
  
## <a name="designing-windows-forms-applications"></a>Entwerfen von Windows Forms-Anwendungen  
 Sie können Windows Forms und Windows-dienstanwendungen mit Visual Studio erstellen. Weitere Informationen finden Sie unter den folgenden Themen:  
  
- [Erste Schritte mit Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Enthält Informationen zum Erstellen und Programmieren von Windows Forms.  
   
- [Windows Forms-Steuerelementen](../../../framework/winforms/controls/index.md). Sammlung von Themen, die Verwendung von Windows Forms-Steuerelementen.  
  
- [Windows-Dienstanwendungen](../../../framework/windows-services/index.md). Enthält Themen, die erläutern, wie Sie Windows-Dienste zu erstellen.  
  
## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken  
 Windows Forms ist die Smart Client-Komponente von .NET Framework, ein Satz verwalteter Bibliotheken, die generelle Anwendungsaufgaben wie Lesen und Schreiben in das Dateisystem zu ermöglichen. Verwenden einer Entwicklungsumgebung wie Visual Studio, können Sie erstellen Windows Forms-Anwendungen, die Informationen anzeigen, Eingaben von Benutzern anfordern, und die Kommunikation mit Remotecomputern über ein Netzwerk.  
  
 In Windows Forms ist ein Formular eine visuelle Oberfläche, die auf der Sie die Informationen für den Benutzer anzuzeigen. Im Allgemeinen erstellen Sie Windows Forms-Anwendungen von Steuerelementen auf Formularen platzieren und Reaktionen auf Benutzeraktionen wie Mausklicks oder Tastatureingaben entwickeln. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.  
  
### <a name="events"></a>Ereignisse  
 Wenn ein Benutzer im Formular oder einem seiner Steuerelemente ausführt, wird ein Ereignis generiert. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).  
  
### <a name="controls"></a>Steuerelemente  
 Windows Forms enthält eine Vielzahl von Kontrollen, die Sie in Formularen platzieren können: Steuerelemente, Textfelder, Schaltflächen, Dropdownfeldern, Optionsfeldern und sogar Webseiten anzeigen. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.  
  
 Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Mithilfe der <xref:System.Windows.Forms.ToolStrip> und <xref:System.Windows.Forms.MenuStrip> -Steuerelement, können Sie Symbolleisten und Menüs, die Text und Bilder enthalten, Untermenüs oder weitere Steuerelemente wie Textfelder und Kombinationsfelder erstellen.  
  
 Mit der Visual Studio Drag & Drop Forms-Designer können Sie problemlos Windows Forms-Anwendungen erstellen: Wählen Sie die Steuerelemente mit den Cursor einfach, und platzieren, in dem auf dem Formular werden sollen. Der Designer bietet Tools wie Rasterlinien und "Ausrichtungslinien" Steuerelemente ausgerichtet werden. Und, ob Sie Visual Studio oder über die Befehlszeile kompilieren, können Sie die <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> und <xref:System.Windows.Forms.SplitContainer> Steuerelemente zum Erstellen erweiterter Formularlayouts mit minimalem Aufwand.  
  
### <a name="custom-ui-elements"></a>Benutzerdefinierte UI-Elemente  
 Schließlich, wenn Sie eigene benutzerdefinierte UI-Elemente erstellen, müssen die <xref:System.Drawing> -Namespace enthält alle Klassen Sie Linien, Kreise und andere Formen direkt auf einem Formular zu rendern müssen.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Erstellen einer neuen Windows Forms-Anwendung mit Visual Studio|[Tutorial 1: Erstellen eines Bildanzeigeprogramms](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|  
|Verwenden von Steuerelementen auf Formularen|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|   
|Erstellen von Grafiken mit <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|  
|Erstellen benutzerdefinierter Steuerelemente|[Vorgehensweise: Erben von der UserControl-Klasse](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|  
  
## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten  
 Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Windows Forms bietet ein flexibles Steuerelement namens der <xref:System.Windows.Forms.DataGridView> für das rendering solcher tabularischer Daten in einem herkömmlichen Zeilen- und Format, sodass jedes Datenelement seine eigene Zelle belegt. Mithilfe von <xref:System.Windows.Forms.DataGridView> können Sie die Darstellung einzelner Zellen anpassen, beliebiger Zeilen und Spalten in Ihrer Position sperren und komplexe Steuerelemente in Zellen, neben weiteren Features anzeigen.  
  
 Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. Die <xref:System.Windows.Forms.BindingSource> Komponente, Neues in Windows Forms in Visual Studio 2005 und die [!INCLUDE[dnprdnlong](~/includes/dnprdnlong-md.md)], stellt eine Verbindung mit einer Datenquelle dar und stellt Methoden zum Binden von Daten an Steuerelemente, Navigieren zum vorherigen oder nächsten Datensatz, Bearbeiten von Datensätzen und speichern Änderungen an der ursprünglichen Quelle. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.  
  
### <a name="data-bound-controls"></a>Datengebundene Steuerelemente  
 Sie können angeben, Erstellen von datengebundenen Steuerelementen, die problemlos mit dem Fenster Datenquellen, das Datenquellen wie Datenbanken, Webdienste und Objekte in Ihrem Projekt anzeigt. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.  
  
### <a name="settings"></a>Einstellungen  
 Ein weiterer Typ von Datenbindung, die Sie in Windows Forms verwalten können, sind Einstellungen. Die meisten intelligenten Clientanwendungen müssen bestimmte Informationen über ihren Laufzeitzustand, z. B. die zuletzt bekannte Größe des Formulars, und behalten die benutzereinstellung Daten, wie Standardverzeichnisse für gespeicherte Dateien. Die Anwendungseinstellungen Funktion erfüllt diese Anforderungen durch die Bereitstellung einer einfachen Möglichkeit, beide Arten von Einstellungen auf dem Clientcomputer zu speichern. Nach der Definition mit Visual Studio oder einem Code-Editor, sind diese Einstellungen als XML beibehalten und zur Laufzeit automatisch in den Arbeitsspeicher eingelesen.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen.  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Verwenden der <xref:System.Windows.Forms.BindingSource> Komponente|[Vorgehensweise: Binden von Windows Forms-Steuerelementen mithilfe der BindingSource-Komponente, die mithilfe des Designers](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|  
|Arbeiten Sie mit Datenquellen von ADO.NET|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der Windows Forms-BindingSource-Komponente](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Verwenden Sie das Fenster "Datenquellen"|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|  
  
## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern  
 Nachdem Sie Ihre Anwendung geschrieben haben, müssen Sie diese für Ihre Benutzer senden, damit sie installieren können, und führen Sie es auf dem eigenen Clientcomputer. Mithilfe der [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] -Technologie können Sie Ihre Anwendungen innerhalb von Visual Studio mit nur wenigen Klicks bereitstellen und Benutzern eine URL verweist auf die Anwendung im Web bereitstellen. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] verwaltet alle Elemente und Abhängigkeiten in Ihrer Anwendung und stellt sicher, dass die Anwendung ordnungsgemäß auf dem Clientcomputer installiert ist.  
  
 [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]-Anwendungen können so konfiguriert werden, dass sie nur ausgeführt werden, wenn der Benutzer mit dem Netzwerk verbunden ist, oder dass sie sowohl online als auch offline ausgeführt werden können. Wenn Sie angeben, dass eine Anwendung den Offlinebetrieb unterstützen soll [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] Fügt einen Link zur Anwendung des Benutzers **starten** Menü, damit der Benutzer sie öffnen kann, ohne die URL.  
  
 Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] erkennt, dass es ein Update verfügbar ist und die Installation des Benutzers aktualisiert. Es ist keine benutzerdefinierte Programmierung erforderlich, zum Aktualisieren von alten Assemblys.  
  
 Eine umfassende Einführung in [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] finden Sie unter [ClickOnce-Sicherheit und -Bereitstellung](/visualstudio/deployment/clickonce-security-and-deployment). Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Bereitstellen einer Anwendung mit [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Vorgehensweise: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|  
|Update einer [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)] Bereitstellung|[Vorgehensweise: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|  
|Verwalten der Sicherheit mit [!INCLUDE[ndptecclick](~/includes/ndptecclick-md.md)]|[Vorgehensweise: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|  
  
## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen  
 In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. Darüber hinaus verwendet Windows Forms die stabiles Sicherheitssystem von .NET Framework, sodass Sie sicherere Anwendungen für Ihre Kunden freigeben.  
  
 Ausführliche Informationen zur Verwendung dieser Funktionen finden Sie unter den folgenden Hilfethemen:  
  
|Beschreibung|Siehe|  
|--------|---------|  
|Drucken des Inhalts eines Formulars|[Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|   
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|  
  
## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Übersicht über Windows Forms](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
