---
title: Übersicht über die Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, overview
- user interface, see UI
- accessibility, UI automation
ms.assetid: 65847654-9994-4a9e-b36d-2dd5d998770b
ms.openlocfilehash: 6f938302967e1b519105769717d326e5042a7bce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179924"
---
# <a name="ui-automation-overview"></a>Übersicht über die Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Aktuelle Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden Sie auf der Seite zur [Windows-Automatisierungs-API: UI-Automatisierung](/windows/win32/winauto/entry-uiauto-win32).  
  
 [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]ist das neue Barrierefreiheitsframework für Microsoft Windows, [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)]das auf allen Betriebssystemen verfügbar ist, die unterstützen.  
  
 Die[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] stellt programmgesteuerten Zugriff auf die meisten [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] auf dem Desktop zur Verfügung, sodass Hilfstechnologieprodukte, z. B. die Bildschirmsprachausgabe, Informationen über die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] für die Endbenutzer bereitstellen und die [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] mit anderen Verfahren als Standardeingaben ändern können. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht außerdem die Interaktion von automatisierten Testskripts mit der [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)].  
  
> [!NOTE]
> [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht keine Kommunikation zwischen Prozessen, die von anderen Benutzern durch den Befehl **Ausführen als** gestartet werden.  
  
 Benutzeroberflächenautomatisierungs-Clientanwendungen können mit der Gewissheit geschrieben werden, dass sie mit verschiedenen Frameworks funktionieren. Der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kern maskiert alle Unterschiede in den Frameworks, die den verschiedenen Komponenten von [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]zugrunde liegen. Beispielsweise werden `Content` die Eigenschaft [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] einer `Caption` Schaltfläche, die Eigenschaft einer Win32-Schaltfläche und die `ALT` Eigenschaft eines HTML-Bildes einer einzelnen Eigenschaft zugeordnet, <xref:System.Windows.Automation.AutomationElement.AutomationElementInformation.Name%2A>, in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ansicht.  
  
DIE Benutzeroberflächenautomatisierung bietet vollständige Funktionen auf unterstützten Windows-Betriebssystemen, auf denen .NET Framework ausgeführt wird (siehe [.NET Framework-Systemanforderungen](../get-started/system-requirements.md) oder Versionen von .NET Core ab .NET Core 3.0).  
  
 BENUTZERoberflächenautomatisierungsanbieter bieten über einen integrierten Überbrückungsdienst Unterstützung für Microsoft Active Accessibility-Clientanwendungen.  
  
<a name="Providers_and_Clients"></a>
## <a name="providers-and-clients"></a>Anbieter und Clients  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] verfügt über vier Hauptkomponenten, wie in der folgenden Tabelle aufgeführt.  
  
|Komponente|Beschreibung|  
|---------------|-----------------|  
|Anbieter-API (UIAutomationProvider.dll und UIAutomationTypes.dll)|Eine Reihe von Schnittstellendefinitionen, die von Benutzeroberflächenautomatisierungs-Anbietern implementiert werden, sowie Objekte, die Informationen über [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente bereitstellen und auf Programmeingaben reagieren.|  
|Client-API (UIAutomationClient.dll und UIAutomationTypes.dll)|Eine Reihe von Typen für verwalteten Code, der es Benutzeroberflächenautomatisierungs-Clientanwendungen ermöglicht, Informationen über [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] abzurufen und Eingaben an Steuerelemente zu senden.|  
|UiAutomationCore.dll|Der zugrunde liegende Code (gelegentlich als [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Code bezeichnet), der die Kommunikation zwischen Anbietern und Clients verwaltet.|  
|UIAutomationClientsideProviders.dll|Ein Satz von Benutzeroberflächenautomatisierungs-Anbietern für Standard-Legacysteuerelemente. ([!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] Steuerelemente haben [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]systemeigene Unterstützung für .) Diese Unterstützung ist automatisch für Clientanwendungen verfügbar.|  
  
 Aus Sicht des Softwareentwicklers gibt es zwei Möglichkeiten zum Verwenden von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]: entweder kann eine Unterstützung für benutzerdefinierte Steuerelemente mithilfe der Anbieter-API erstellt werden oder Anwendungen, die den [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Kern verwenden, um mit [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elementen mithilfe der Client-API zu kommunizieren. Abhängig von Ihren Schwerpunkten sollten Sie auf verschiedene Teile der Dokumentation zugreifen. In den folgenden Abschnitten können Sie mehr über die Konzepte erfahren und sich praktisches Wissen aneignen.  
  
|`Section`|Inhalt|Zielgruppe|  
|-------------|--------------------|--------------|  
|[Grundlagen der Benutzeroberflächenautomatisierung](index.md) (dieser Abschnitt)|Allgemeine Übersichten über die Konzepte.|Alle.|  
|[Benutzeroberflächenautomatisierungs-Anbieter für verwalteten Code](ui-automation-providers-for-managed-code.md)|Übersichten und Hilfethemen zum Verwenden der Anbieter-API.|Entwickler von Steuerelementen.|  
|[Benutzeroberflächenautomatisierungs-Clients für verwalteten Code](ui-automation-clients-for-managed-code.md)|Übersichten und Hilfethemen zum Verwenden der Client-API.|Entwickler von Clientanwendungen.|  
|[Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns.md)|Informationen zum Implementieren von Steuerelementmustern durch Anbieter und den Funktionalitäten, die Clients zur Verfügung stehen.|Alle.|  
|[Textmuster zur Benutzeroberflächenautomatisierung](ui-automation-text-pattern.md)|Informationen zum Implementieren des Text-Steuerelementmusters durch Anbieter und den Funktionalitäten, die Clients zur Verfügung stehen.|Alle.|  
|[Steuerelementtypen der Benutzeroberflächenautomatisierung](ui-automation-control-types.md)|Informationen über die Eigenschaften und Steuerelementmuster, die von verschiedenen Steuerelementtypen unterstützt werden.|Alle.|  
  
 In der folgenden Tabelle werden [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Namespaces, die DLLs, die sie enthalten, und die sie verwendende Zielgruppe, aufgelistet.  
  
|Namespace|DLLs, auf die verwiesen wird|Zielgruppe|  
|---------------|---------------------|--------------|  
|<xref:System.Windows.Automation>|UIAutomationClientUIAutomationTypes|Benutzeroberflächenautomatisierungs-Cliententwickler: wird zum Suchen nach <xref:System.Windows.Automation.AutomationElement> -Objekten, zum Registrieren von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignissen und zum Arbeiten mit [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmustern verwendet.|  
|<xref:System.Windows.Automation.Provider>|UIAutomationProviderUIAutomationTypes|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für andere Frameworks als [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
|<xref:System.Windows.Automation.Text>|UIAutomationClientUIAutomationTypes|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für Frameworks, die über [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]hinausgehen. Dieser wird zum Implementieren von TextPattern-Steuerelementmustern verwendet.|  
|<xref:System.Windows.Automation.Peers>|PresentationFramework|Entwickler von Benutzeroberflächenautomatisierungs-Anbietern für [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].|  
  
<a name="UI_Automation_Model"></a>
## <a name="ui-automation-model"></a>Benutzeroberflächenautomatisierungs-Modell  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] macht [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente für Clientanwendungen vollständig als <xref:System.Windows.Automation.AutomationElement>verfügbar. Elemente sind in einer Baumstruktur, mit dem Desktop als Stammelement, enthalten. Clients können die „Rohdatenansicht“ der Struktur als „Steuerelementansicht“ oder „Inhaltsansicht“ filtern. Anwendungen können auch benutzerdefinierte Ansichten erstellen.  
  
 <xref:System.Windows.Automation.AutomationElement> -Objekte machen allgemeine Eigenschaften der von ihnen dargestellten [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] -Elemente verfügbar. Eine dieser Eigenschaften ist der „Steuerelementtyp“, der die grundlegende Darstellung und Funktionalität als einzelne Entität definiert, z. B. als Schaltfläche oder Kontrollkästchen.  
  
 Darüber hinaus machen Elemente Steuerelementmuster verfügbar, die ihren Steuerelementtypen entsprechende Eigenschaften bereitstellen. Steuerelementmuster machen gleichzeitig Methoden verfügbar, die es Clients ermöglichen, weitere Informationen über das Element zu erlangen und Eingaben bereitzustellen.  
  
> [!NOTE]
> Es gibt keine 1:1-Entsprechung zwischen Steuerelementtypen und Steuerelementmustern. Ein Steuerelementmuster kann von mehreren Steuerelementtypen unterstützt werden, und ein Steuerelement kann mehrere Steuerelementmuster unterstützen, von denen jedes einen anderen Aspekt des Verhaltens verfügbar macht. Ein Kombinationsfeld hat beispielsweise mindestens zwei Steuerelementmuster: eines mit der Fähigkeit zum Erweitern und Reduzieren und ein anderes, das den Auswahlmechanismus darstellt. Weitere Informationen finden Sie unter [UI Automation Control Types](ui-automation-control-types.md).  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] gibt durch Ereignisse Informationen an Clientanwendungen weiter. Im Gegensatz [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] zu WinEvents basieren Ereignisse nicht auf einem Broadcast-Mechanismus. [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Clients melden sich für bestimmte Ereignisbenachrichtigungen an und können anfordern, dass spezifische [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften und Steuerelementmuster-Informationen an den Ereignishandler übergeben werden. Außerdem enthält ein [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis einen Verweis auf das Element, das es ausgelöst hat. Anbieter können die Leistung verbessern, indem sie Ereignisse selektiv abhängig davon auslösen, ob Clients zuhören.  
  
## <a name="see-also"></a>Weitere Informationen

- [UI Automation Tree Overview](ui-automation-tree-overview.md)
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](ui-automation-properties-overview.md)
- [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](ui-automation-events-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Sicherheit](ui-automation-security-overview.md)
