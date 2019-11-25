---
title: Grundlagen zu Windows Forms-Anwendungen
ms.date: 07/20/2015
helpviewer_keywords:
- Windows applications
- Windows Forms, Visual Basic
ms.assetid: 0b919d30-7fd6-42db-85c8-543d15312441
ms.openlocfilehash: 1aa1edf0130e388c6cc87662d83591f41a8e2325
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349163"
---
# <a name="windows-forms-application-basics-visual-basic"></a>Grundlagen zu Windows Forms-Anwendungen (Visual Basic)

An important part of Visual Basic is the ability to create Windows Forms applications that run locally on users' computers. You can use Visual Studio to create the application and user interface using Windows Forms. A Windows Forms application is built on classes from the <xref:System.Windows.Forms> namespace.

## <a name="designing-windows-forms-applications"></a>Designing Windows Forms Applications

You can create Windows Forms and Windows service applications with Visual Studio. Weitere Informationen finden Sie unter den folgenden Themen:

- [Getting Started with Windows Forms](../../../framework/winforms/getting-started-with-windows-forms.md). Provides information on how to create and program Windows Forms.

- [Windows Forms Controls](../../../framework/winforms/controls/index.md). Collection of topics detailing the use of Windows Forms controls.

- [Windows Service Applications](../../../framework/windows-services/index.md). Lists topics that explain how to create Windows services.

## <a name="building-rich-interactive-user-interfaces"></a>Erstellen von interaktiven Benutzeroberflächen mit anspruchsvollen Grafiken

Windows Forms is the smart-client component of the .NET Framework, a set of managed libraries that enable common application tasks such as reading and writing to the file system. Using a development environment like Visual Studio, you can create Windows Forms applications that display information, request input from users, and communicate with remote computers over a network.

In Windows Forms, a form is a visual surface on which you display information to the user. You commonly build Windows Forms applications by placing controls on forms and developing responses to user actions, such as mouse clicks or key presses. Ein *Steuerelement* ist ein diskretes Benutzeroberflächenelement (UI-Element), das Daten anzeigt oder Dateneingaben akzeptiert.

### <a name="events"></a>Ereignisse

When a user does something to your form or one of its controls, it generates an event. Die Anwendung reagiert auf diese Ereignisse und verarbeitet sie zum Zeitpunkt ihres Auftretens. Weitere Informationen finden Sie unter [Erstellen von Ereignishandlern in Windows Forms](../../../framework/winforms/creating-event-handlers-in-windows-forms.md).

### <a name="controls"></a>Steuerelemente

Windows Forms contains a variety of controls that you can place on forms: controls that display text boxes, buttons, drop-down boxes, radio buttons, and even Web pages. Eine Liste aller Steuerelemente, die in einem Formular verwendet werden können, finden Sie unter [Steuerelemente für Windows Forms](../../../framework/winforms/controls/controls-to-use-on-windows-forms.md). Windows Forms unterstützt über die <xref:System.Windows.Forms.UserControl>-Klasse auch das Erstellen benutzerdefinierter Steuerelemente, wenn ein vorhandenes Steuerelement für Ihre Anforderungen nicht geeignet ist.

Windows Forms verfügt über komplexe Steuerelemente für die Benutzeroberfläche, mit denen Funktionen aus Anwendungen wie Microsoft Office emuliert werden können. Using the <xref:System.Windows.Forms.ToolStrip> and <xref:System.Windows.Forms.MenuStrip> control, you can create toolbars and menus that contain text and images, display submenus, and host other controls such as text boxes and combo boxes.

With the Visual Studio drag-and-drop forms designer, you can easily create Windows Forms applications: just select the controls with your cursor and place them where you want on the form. The designer provides tools such as grid lines and "snap lines" to take the hassle out of aligning controls. And whether you use Visual Studio or compile at the command line, you can use the <xref:System.Windows.Forms.FlowLayoutPanel>, <xref:System.Windows.Forms.TableLayoutPanel> and <xref:System.Windows.Forms.SplitContainer> controls to create advanced form layouts with minimal time and effort.

### <a name="custom-ui-elements"></a>Custom UI Elements

Finally, if you must create your own custom UI elements, the <xref:System.Drawing> namespace contains all of the classes you need to render lines, circles, and other shapes directly on a form.

For step-by-step information about using these features, see the following Help topics.

|Beschreibung|Siehe|
|--------|---------|
|Create a new Windows Forms application with Visual Studio|[Tutorial 1: Create a picture viewer](/visualstudio/ide/tutorial-1-create-a-picture-viewer)|
|Use controls on forms|[Vorgehensweise: Hinzufügen von Steuerelementen zu Windows Forms](../../../framework/winforms/controls/how-to-add-controls-to-windows-forms.md)|
|Create graphics with <xref:System.Drawing>|[Erste Schritte mit Grafikprogrammierung](../../../framework/winforms/advanced/getting-started-with-graphics-programming.md)|
|Create custom controls|[Gewusst wie: Erben von der UserControl-Klasse](../../../framework/winforms/controls/how-to-inherit-from-the-usercontrol-class.md)|

## <a name="displaying-and-manipulating-data"></a>Anzeigen und Bearbeiten von Daten

Viele Anwendungen müssen Daten aus einer Datenbank, einer XML-Datei, einem XML-Webdienst oder einer anderen Datenquelle anzeigen. Windows Forms provides a flexible control called the <xref:System.Windows.Forms.DataGridView> control for rendering such tabular data in a traditional row and column format, so that every piece of data occupies its own cell. Using <xref:System.Windows.Forms.DataGridView> you can customize the appearance of individual cells, lock arbitrary rows and columns in place, and display complex controls inside cells, among other features.

Mit intelligenten Windows Forms-Clients kann problemlos eine Netzwerkverbindung zu Datenquellen hergestellt werden. The <xref:System.Windows.Forms.BindingSource> component, new with Windows Forms in Visual Studio 2005 and the .NET Framework 2.0, represents a connection to a data source, and exposes methods for binding data to controls, navigating to the previous and next records, editing records, and saving changes back to the original source. Das <xref:System.Windows.Forms.BindingNavigator>-Steuerelement stellt über die <xref:System.Windows.Forms.BindingSource>-Komponente eine einfache Schnittstelle zum Navigieren zwischen Datensätzen bereit.

### <a name="data-bound-controls"></a>Data-Bound Controls

You can create data-bound controls easily using the Data Sources window, which displays data sources such as databases, Web services, and objects in your project. Zum Erstellen datengebundener Steuerelemente können Sie Elemente aus diesem Fenster auf Formulare im Projekt ziehen. Darüber hinaus können Sie auch bestehende Steuerelemente an Daten binden, indem Sie Objekte aus dem Datenquellenfenster auf bestehende Steuerelemente ziehen.

### <a name="settings"></a>Einstellungen

Another type of data binding you can manage in Windows Forms is settings. Most smart-client applications must retain some information about their run-time state, such as the last-known size of forms, and retain user-preference data, such as default locations for saved files. The application-settings feature addresses these requirements by providing an easy way to store both types of settings on the client computer. Once defined using either Visual Studio or a code editor, these settings are persisted as XML and automatically read back into memory at run time.

For step-by-step information about using these features, see the following Help topics.

|Beschreibung|Siehe|
|--------|---------|
|Use the <xref:System.Windows.Forms.BindingSource> component|[Vorgehensweise: Binden von Windows Forms-Steuerelementen an die BindingSource-Komponente mithilfe des Designers](../../../framework/winforms/controls/bind-wf-controls-with-the-bindingsource.md)|
|Work with ADO.NET data sources|[Vorgehensweise: Sortieren und Filtern von ADO.NET-Daten mit der BindingSource-Komponente in Windows Forms](../../../framework/winforms/controls/sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)|
|Use the Data Sources window|[Exemplarische Vorgehensweise: Anzeigen von Daten in einem Windows Form](/visualstudio/data-tools/accessing-data-in-visual-studio)|

## <a name="deploying-applications-to-client-computers"></a>Bereitstellen von Anwendungen auf Clientcomputern

Once you have written your application, you must send it to your users so that they can install and run it on their own client computers. Using the ClickOnce technology, you can deploy your applications from within Visual Studio by using just a few clicks and provide users with a URL pointing to your application on the Web. ClickOnce manages all of the elements and dependencies in your application and ensures that the application is properly installed on the client computer.

ClickOnce applications can be configured to run only when the user is connected to the network, or to run both online and offline. When you specify that an application should support offline operation, ClickOnce adds a link to your application in the user's **Start** menu, so that the user can open it without using the URL.

Wenn Sie die Anwendung aktualisieren, veröffentlichen Sie auf dem Webserver ein neues Bereitstellungsmanifest und eine neue Kopie der Anwendung. ClickOnce detects that there is an update available and upgrades the user's installation; no custom programming is required to update old assemblies.

For a full introduction to ClickOnce, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment). For step-by-step information about using these features, see the following Help topics:

|Beschreibung|Siehe|
|--------|---------|
|Deploy an application with ClickOnce|[Gewusst wie: Veröffentlichen einer ClickOnce-Anwendung mit dem Webpublishing-Assistenten](/visualstudio/deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard)<br /><br /> [Exemplarische Vorgehensweise: Manuelles Bereitstellen einer ClickOnce-Anwendung](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application)|
|Update a ClickOnce deployment|[Gewusst wie: Verwalten von Aktualisierungen für eine ClickOnce-Anwendung](/visualstudio/deployment/how-to-manage-updates-for-a-clickonce-application)|
|Manage security with ClickOnce|[Gewusst wie: Aktivieren von ClickOnce-Sicherheitseinstellungen](/visualstudio/deployment/how-to-enable-clickonce-security-settings)|

## <a name="other-controls-and-features"></a>Andere Steuerelemente und Funktionen

In Windows Forms stehen viele weitere Features bereit, mit denen häufige Aufgaben schnell und einfach ausgeführt werden können, beispielsweise zum Erstellen von Dialogfeldern, Drucken, Hinzufügen von Hilfe und Dokumentation sowie zum Lokalisieren von Anwendungen in mehrere Sprachen. In addition, Windows Forms relies on the robust security system of the .NET Framework, enabling you to release more secure applications to your customers.

For step-by-step information about using these features, see the following Help topics:

|Beschreibung|Siehe|
|--------|---------|
|Print the contents of a form|[Vorgehensweise: Drucken von Grafiken in Windows Forms](../../../framework/winforms/advanced/how-to-print-graphics-in-windows-forms.md)<br /><br /> [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md)|
|Weitere Informationen zur Windows Forms-Sicherheit|[Übersicht über die Sicherheit in Windows Forms](../../../framework/winforms/security-in-windows-forms-overview.md)|

## <a name="see-also"></a>Siehe auch

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- [Übersicht über Windows Forms](../../../framework/winforms/windows-forms-overview.md)
- [My.Forms-Objekt](../../../visual-basic/language-reference/objects/my-forms-object.md)
