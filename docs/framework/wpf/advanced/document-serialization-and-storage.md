---
title: Serialisierung und Speicherung von Dokumenten
ms.date: 03/30/2017
helpviewer_keywords:
- 'serialization of documents [WPF], , '
- documents [WPF], storage
- documents [WPF], serialization
ms.assetid: 4839cd87-e206-4571-803f-0200098ad37b
ms.openlocfilehash: 519d3aa218fca734a9159503b4107bdbcfc31652
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215949"
---
# <a name="document-serialization-and-storage"></a>Serialisierung und Speicherung von Dokumenten
Microsoft .NET Framework stellt eine leistungsfähige Umgebung zum Erstellen und anzeigen qualitativ hochwertiger Dokumente.  Erweiterte Funktionen, die Unterstützung von sowohl fixierten Dokumenten als auch Flussdokumenten sowie erweiterte Anzeigesteuerelemente, kombiniert mit leistungsstarken 2D- und 3D-Grafikfunktionen führen .NET Framework-Anwendungen, um eine neue Ebene der Qualität und benutzerfreundlichkeit.  Eine speicherinterne Darstellung eines Dokuments flexibel zu verwalten, ist ein wichtiges Feature von .NET Framework und effizient zu speichern und Laden von Dokumenten aus einem Datenspeicher ist nahezu jede Anwendung erforderlich.  Der Prozess der Konvertierung eines Dokuments aus einer speicherinternen Darstellung in einen externen Datenspeicher wird als Serialisierung bezeichnet.  Der umgekehrte Vorgang des Lesens eines Datenspeichers und Neuerstellens der ursprünglichen Instanz im Speicher wird Deserialisierung genannt.  

<a name="AboutSerialization"></a>   
## <a name="about-document-serialization"></a>Informationen zur Dokumentserialisierung  
 Im Idealfall ist der Prozess der Serialisierung und Deserialisierung eines Dokuments aus dem Speicher und wieder zurück für die Anwendung transparent.  Die Anwendung ruft die Write-Methode des Serialisierungsprogramms auf, um das Dokument zu speichern. Die Read-Methode des Deserialisierungsprogramms greift dagegen auf den Datenspeicher zu und erstellt die ursprüngliche Instanz im Speicher neu.  Das jeweilige Format, in dem die Daten gespeichert werden, ist für die Anwendung normalerweise nicht relevant, solange der Serialisierungs- und Deserialisierungsprozess das Dokument wieder in seiner ursprünglichen Form erstellt.  
  
 Oft bieten Anwendungen mehrere Serialisierungsoptionen, die dem Benutzer die Speicherung von Dokumenten auf ein anderes Medium oder in ein anderes Format ermöglichen.  So kann eine Anwendung z.B. „Speichern unter“-Optionen anbieten, um ein Dokument in eine Datenträgerdatei, Datenbank oder einen Webdienst zu speichern.  Entsprechend können verschiedene Serialisierungsprogramme das Dokument in verschiedenen Formaten speichern, wie etwa HTML, RTF, XML, XPS oder das Format eines Drittanbieters.  Für die Anwendung wird eine Schnittstelle definiert, die die Details des Speichermediums innerhalb der Implementierung jedes einzelnen Serialisierungsprogramms isoliert.  Zusätzlich zu den Vorteilen der Kapselung von Speicherdetails, .NET Framework <xref:System.Windows.Documents.Serialization> [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)] einige weitere wichtigen Funktionen bereitzustellen.  
  
### <a name="features-of-net-framework-30-document-serializers"></a>Funktionen der Dokumentserialisierungsprogramme von .NET Framework 3.0  
  
-   Durch direkten Zugriff auf Dokumentobjekte der höheren Ebene (logische Struktur und visuelle Elemente) wird eine effiziente Speicherung von aufgeteiltem Inhalt, 2D-/3D-Elementen, Bildern, Medien, Hyperlinks, Anmerkungen und anderen Supportinhalten aktiviert.  
  
-   Synchrone und asynchrone Vorgänge  
  
-   Unterstützung für Plug-In-Serialisierungsprogramme mit erweiterten Funktionen:  
  
    -   Systemweiter Zugriff für die Verwendung von allen .NET Framework-Anwendungen.  
  
    -   Einfache Erkennbarkeit von Anwendungs-Plug-Ins  
  
    -   Einfache Bereitstellung, Installation und Update von benutzerdefinierten Drittanbieter-Plug-Ins  
  
    -   Unterstützung von Benutzeroberflächen für benutzerdefinierte Laufzeiteinstellungen und -optionen  
  
### <a name="xps-print-path"></a>XPS-Druckpfad  
 Microsoft .NET Framework [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] -Druckpfad bietet auch einen erweiterbaren Mechanismus zum Schreiben von Dokumenten durch die Druckausgabe.  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] als beide als Dokumentdateiformat und natives druckerspoolerformat für [!INCLUDE[TLA#tla_winvista](../../../../includes/tlasharptla-winvista-md.md)].  [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] Dokumente direkt gesendet werden können [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)]-kompatiblen Druckern ohne Konvertierung in ein Zwischenformat.  Weitere Informationen zu Optionen und Funktionen der Druckpfadausgabe finden Sie unter [Übersicht über das Drucken](printing-overview.md).  
  
<a name="PluginSerializers"></a>   
## <a name="plug-in-serializers"></a>Plug-In-Serialisierungsprogramme  
 Die <xref:System.Windows.Documents.Serialization> APIs bieten Unterstützung für Plug-In-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme, die separat von der Anwendung installiert sind, zur Laufzeit gebunden und erfolgt mithilfe der <xref:System.Windows.Documents.Serialization.SerializerProvider> Discovery-Mechanismus.  Plug-In-Serialisierungsprogramme bieten mehr Vorteile hinsichtlich einfacher Bereitstellung und systemweiter Verwendung.  Verknüpfte Serialisierungsprogramme können auch für teilweise vertrauenswürdige Umgebungen wie z.B. [!INCLUDE[TLA#tla_xbap#plural](../../../../includes/tlasharptla-xbapsharpplural-md.md)] implementiert werden, in denen nicht auf Plug-In-Serialisierungsprogramme zugegriffen werden kann.  Verknüpfte Serialisierungsprogramme, die auf eine abgeleitete Implementierung von basieren die <xref:System.Windows.Documents.Serialization.SerializerWriter> Klasse, wird kompiliert und direkt mit der Anwendung verknüpft.  Plug-In-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden identische öffentliche Methoden und Ereignisse. Daher können eine oder beide Arten von Serialisierungsprogrammen problemlos in der gleichen Anwendung verwendet werden.  
  
 Plug-In-Serialisierungsprogramme helfen Anwendungsentwicklern durch die Möglichkeit zur Erweiterung bei neuen Speicherentwürfen und Dateiformaten, ohne dass sie bereits bei der Erstellung für jedes mögliche Format programmieren müssen.  Von Plug-In-Serialisierungsprogrammen profitieren auch Drittanbieterentwickler durch eine standardisierte Methode, barrierefrei Plug-Ins für benutzerdefinierte oder geschützte Dateiformate bereitzustellen, zu installieren und zu aktualisieren.  
  
### <a name="using-a-plug-in-serializer"></a>Verwenden eines Plug-In-Serialisierungsprogramms  
 Plug-In-Serialisierungsprogramme sind einfach zu verwenden.  Die <xref:System.Windows.Documents.Serialization.SerializerProvider> -Klasse listet ein <xref:System.Windows.Documents.Serialization.SerializerDescriptor> -Objekt für jedes plug-in auf dem System installiert.  Die <xref:System.Windows.Documents.Serialization.SerializerDescriptor.IsLoadable%2A> -Eigenschaft filtert die installierte Plug-Ins auf Grundlage der aktuellen Konfiguration, und stellt sicher, dass das Serialisierungsprogramm geladen und von der Anwendung verwendet werden kann.  Die <xref:System.Windows.Documents.Serialization.SerializerDescriptor> bietet noch weitere Eigenschaften, z. B. <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DisplayName%2A> und <xref:System.Windows.Documents.Serialization.SerializerDescriptor.DefaultFileExtension%2A>, die die Anwendung verwenden können, um den Benutzer ein Serialisierungsprogramm für ein verfügbares Ausgabeformat aufzufordern.  Ein Standard-Plug-In-Serialisierungsprogramm für [!INCLUDE[TLA2#tla_xps](../../../../includes/tla2sharptla-xps-md.md)] wird bereitgestellt, mit dem .NET Framework, das immer aufgelistet.  Nachdem der Benutzer ein Ausgabeformat ausgewählt. die <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> Methode dient zum Erstellen einer <xref:System.Windows.Documents.Serialization.SerializerWriter> für das jeweilige Format.  Die <xref:System.Windows.Documents.Serialization.SerializerWriter>.<xref:System.Windows.Documents.Serialization.SerializerWriter.Write%2A> Methode kann dann aufgerufen werden, um den Dokumentdatenstrom an den Datenspeicher auszugeben.  
  
 Das folgende Beispiel zeigt eine Anwendung, verwendet der <xref:System.Windows.Documents.Serialization.SerializerProvider> -Methode in der Eigenschaft "PlugInFileFilter".  PlugInFileFilter Listet die installierte Plug-Ins auf und erstellt eine Filterzeichenfolge mit den verfügbaren Dateioptionen für ein <xref:Microsoft.Win32.SaveFileDialog>.  
  
 [!code-csharp[DocumentSerialize#DocSerializeFileFilter](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializefilefilter)]  
  
 Nach der Name der Ausgabedatei vom Benutzer ausgewählt wurde, wird das folgende Beispiel veranschaulicht die Verwendung von der <xref:System.Windows.Documents.Serialization.SerializerProvider.CreateSerializerWriter%2A> Methode, um ein bestimmtes Dokument in einem angegebenen Format zu speichern.  
  
 [!code-csharp[DocumentSerialize#DocSerializePlugIn](~/samples/snippets/csharp/VS_Snippets_Wpf/DocumentSerialize/CSharp/ThumbViewer.cs#docserializeplugin)]  
  
<a name="InstallingPluginSerializers"></a>   
### <a name="installing-plug-in-serializers"></a>Installieren von Plug-In-Serialisierungsprogrammen  
 Die <xref:System.Windows.Documents.Serialization.SerializerProvider> Klasse liefert die Anwendungsschnittstelle der oberen Ebene für Plug-In-Serialisierungsprogramm Auffinden und den Zugriff.  <xref:System.Windows.Documents.Serialization.SerializerProvider> Sucht und stellt der Anwendung eine Liste der Serialisierungsprogramme, die installiert und auf dem System zugänglich sind.  Die Einzelheiten der installierten Serialisierungsprogramme werden durch Registrierungseinstellungen definiert.  Plug-In-Serialisierungsprogramme können der Registrierung hinzugefügt werden, mithilfe der <xref:System.Windows.Documents.Serialization.SerializerProvider.RegisterSerializer%2A> Methode; oder wenn es sich bei .NET Framework noch nicht installiert ist, das Plug-In-Installationsskript kann direkt festgelegt werden, die Registrierung Werte selbst.  Die <xref:System.Windows.Documents.Serialization.SerializerProvider.UnregisterSerializer%2A> Methode kann verwendet werden, um ein zuvor installiertes entfernen-Plug-in, oder die registrierungseinstellungen können auf ähnliche Weise durch ein Deinstallationsskript zurückgesetzt werden.  
  
### <a name="creating-a-plug-in-serializer"></a>Erstellen eines Plug-In-Serialisierungsprogramms  
 Plug-In-Serialisierungsprogramme und verknüpfte Serialisierungsprogramme verwenden dieselben verfügbar gemachten, öffentlichen Methoden und Ereignisse und können daher so entworfen werden, dass sie synchron oder asynchron ausgeführt werden.  Folgen Sie diesen drei grundlegenden Schritten zum Erstellen eines Plug-In-Serialisierungsprogramms:  
  
1.  Implementieren und debuggen Sie das Serialisierungsprogramm zuerst als verknüpftes Serialisierungsprogramm.  Das vorherige Erstellen des Serialisierungsprogramms, das kompiliert und direkt mit der Testanwendung verknüpft wird, ermöglicht vollen Zugriff auf Haltepunkte und weitere für den Test nützliche Debugdienste.  
  
2.  Nachdem das Serialisierungsprogramm vollständig getestet ist, eine <xref:System.Windows.Documents.Serialization.ISerializerFactory> Schnittstelle wird zum Erstellen eines Plug-Ins hinzugefügt.  Die <xref:System.Windows.Documents.Serialization.ISerializerFactory> -Schnittstelle gestattet den Vollzugriff auf alle .NET Framework-Objekte einschließlich die logische Struktur <xref:System.Windows.UIElement> Objekte <xref:System.Windows.Documents.IDocumentPaginatorSource>, und <xref:System.Windows.Media.Visual> Elemente.  Darüber hinaus <xref:System.Windows.Documents.Serialization.ISerializerFactory> bietet dieselben synchronen und asynchronen Methoden und Ereignisse, die verknüpfte Serialisierungsprogramme.  Da die Ausgabe großer Dokumente mehr Zeit in Anspruch nehmen kann, sind asynchrone Vorgänge empfehlenswert, um eine reaktionsfähige Benutzerinteraktion und eine Abbrechen-Option zu gewährleisten, falls ein Problem mit dem Datenspeicher auftreten sollte.  
  
3.  Nach Erstellen des Plug-In-Serialisierungsprogramms wird ein Installationsskript für die Verteilung und Installation (und Deinstallation) des Plug-Ins implementiert (siehe oben unter „[Installieren von Plug-In-Serialisierungsprogrammen](#InstallingPluginSerializers)“).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Documents.Serialization>
- <xref:System.Windows.Xps.XpsDocumentWriter>
- <xref:System.Windows.Xps.Packaging.XpsDocument>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [XML Paper Specification: Übersicht](https://go.microsoft.com/fwlink?LinkID=106246)
