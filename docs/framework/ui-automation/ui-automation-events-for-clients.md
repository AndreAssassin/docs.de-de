---
title: Benutzeroberflächenautomatisierungs-Ereignisse für Clients
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, events for clients
- events, UI Automation clients
ms.assetid: b909e388-3f24-4997-b6d4-bd9c35c2dc27
ms.openlocfilehash: f4ce2d996d5a1a6ecd149118b7499650882a732f
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71042283"
---
# <a name="ui-automation-events-for-clients"></a>Benutzeroberflächenautomatisierungs-Ereignisse für Clients
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 In diesem Thema wird beschrieben, wie [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]-Ereignisse von Benutzeroberflächenautomatisierungs-Clients verwendet werden.  
  
 [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] ermöglicht es Clients, Ereignisse zu abonnieren. Diese Fähigkeit verbessert die Leistung, weil es nicht mehr erforderlich ist, alle [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Elemente im System ständig daraufhin abzufragen, ob sich eine Information, eine Struktur oder ein Zustand geändert hat.  
  
 Die Effizienz wird auch durch die Möglichkeit verbessert, Ereignissen nur innerhalb eines definierten Umfangs zu lauschen. Beispielsweise kann ein Client den Fokusänderungsereignisse aller [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Elemente in der Struktur oder nur einem Element und dessen Nachfolgerelementen lauschen.  
  
> [!NOTE]
> Gehen Sie nicht davon aus, dass alle möglichen Ereignisse von einem [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]-Anbieter ausgelöst werden. Beispielsweise werden nicht bei allen Eigenschaftenänderungen Ereignisse von den Standardproxyanbietern für [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)]- oder [!INCLUDE[TLA2#tla_win32](../../../includes/tla2sharptla-win32-md.md)]-Steuerelemente ausgelöst.  
  
 Eine umfassendere Ansicht von [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Ereignissen finden Sie unter [UI Automation Events Overview](ui-automation-events-overview.md).  
  
<a name="Subscribing_to_Events"></a>   
## <a name="subscribing-to-events"></a>Abonnieren von Ereignissen  
 Clientanwendungen abonnieren Ereignisse einer bestimmten Art, indem sie einen Ereignishandler mit einer der folgenden Methoden registrieren.  
  
|Methode|Ereignistyp|Typ der Ereignisargumente|Delegattyp|  
|------------|----------------|--------------------------|-------------------|  
|<xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A>|Fokusänderung|<xref:System.Windows.Automation.AutomationFocusChangedEventArgs>|<xref:System.Windows.Automation.AutomationFocusChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A>|Eigenschaftenänderung|<xref:System.Windows.Automation.AutomationPropertyChangedEventArgs>|<xref:System.Windows.Automation.AutomationPropertyChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddStructureChangedEventHandler%2A>|Strukturänderung|<xref:System.Windows.Automation.StructureChangedEventArgs>|<xref:System.Windows.Automation.StructureChangedEventHandler>|  
|<xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A>|Alle anderen Ereignisse, die durch ein <xref:System.Windows.Automation.AutomationEvent>-Objekt ermittelt werden|<xref:System.Windows.Automation.AutomationEventArgs> oder <xref:System.Windows.Automation.WindowClosedEventArgs>|<xref:System.Windows.Automation.AutomationEventHandler>|  
  
 Vor dem Aufrufen der Methode müssen Sie eine Delegatmethode erstellen, mit der das Ereignis verarbeitet wird. Wenn Sie dies bevorzugen, können Sie verschiedene Arten von Ereignissen in einer einzelnen Methode verarbeiten und diese Methode in mehreren Aufrufen an eine der Methoden in der Tabelle übergeben. Sie können beispielsweise einen einzelnen <xref:System.Windows.Automation.AutomationEventHandler> einrichten, der verschiedene Ereignisse entsprechend der <xref:System.Windows.Automation.AutomationEventArgs.EventId%2A> unterschiedlich verarbeitet.  
  
> [!NOTE]
> Um Ereignisse für Schließen eines Fensters zu verarbeiten, wandeln Sie den Argumenttyp, der dem Ereignishandler übergeben wird, in <xref:System.Windows.Automation.WindowClosedEventArgs> um. Da das [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)]-Element für das Fenster nicht mehr gültig ist, können Sie Informationen nicht mit dem `sender`-Parameter abrufen. Verwenden Sie stattdessen <xref:System.Windows.Automation.WindowClosedEventArgs.GetRuntimeId%2A>.  
  
> [!CAUTION]
> Wenn Ihre Anwendung möglicherweise Ereignisse aus ihrer eigenen [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] empfängt, sollten Sie nicht den [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)]-Thread verwenden, um Ereignisse zu abonnieren oder Abonnements von Ereignissen zu kündigen. Eine solche Vorgehensweise kann zu unvorhersehbarem Verhalten führen. Weitere Informationen finden Sie unter [UI Automation Threading Issues](ui-automation-threading-issues.md).  
  
 Beim Herunterfahren, oder wenn [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Ereignisse nicht mehr für die Anwendung benötigt werden, sollten ein Benutzeroberflächenautomatisierungs-Client eine der folgenden Methoden aufrufen.  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationEventHandler%2A>|Hebt die Registrierung eines Ereignishandlers auf, der mit <xref:System.Windows.Automation.Automation.AddAutomationEventHandler%2A> registriert wurde.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationFocusChangedEventHandler%2A>|Hebt die Registrierung eines Ereignishandlers auf, der mit <xref:System.Windows.Automation.Automation.AddAutomationFocusChangedEventHandler%2A> registriert wurde.|  
|<xref:System.Windows.Automation.Automation.RemoveAutomationPropertyChangedEventHandler%2A>|Hebt die Registrierung eines Ereignishandlers auf, der mit <xref:System.Windows.Automation.Automation.AddAutomationPropertyChangedEventHandler%2A> registriert wurde.|  
|<xref:System.Windows.Automation.Automation.RemoveAllEventHandlers%2A>|Hebt die Registrierung aller registrierten Ereignishandler auf.|  
  
 Beispielcode finden Sie unter [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](subscribe-to-ui-automation-events.md).  
  
## <a name="see-also"></a>Siehe auch

- [Abonnieren von Benutzeroberflächenautomatisierungs-Ereignissen](subscribe-to-ui-automation-events.md)
- [Übersicht über Benutzeroberflächenautomatisierungs-Ereignisse](ui-automation-events-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Eigenschaften](ui-automation-properties-overview.md)
- [TrackFocus-Beispiel](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/FocusTracker)
