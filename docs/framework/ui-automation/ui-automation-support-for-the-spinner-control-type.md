---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Spinner-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Spinner control type
- Spinner control type
- control types, Spinner
ms.assetid: 3a29d185-65d8-42e3-bcc3-7f43e96f40c5
ms.openlocfilehash: c32fcffcbe360fc9158725b3eac2558377639abc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69954667"
---
# <a name="ui-automation-support-for-the-spinner-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Spinner-Steuerelementtyp
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „Spinner“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Spinner-Steuerelemente werden dazu verwendet, um aus einem Bereich von Elementen oder Zahlen auszuwählen.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „Spinner“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Spinner-Steuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgende Tabelle wird die Steuerelementansicht und Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur dargestellt, die für Spinner-Steuerelemente gelten, wenn sie die „Range Value“-, „Value“- und „Selection“-Steuerelementmuster unterstützen und beschreiben, was in der jeweiligen Ansicht enthalten sein kann. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
 **„Range Value“- oder „Value“-Steuerelementmuster**  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 oder 1)<br />-Schaltfläche (2)|Spinner|  
  
 **Selection-Steuerelementmuster**  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Spinner<br /><br /> -Edit (0 oder 1)<br />-Schaltfläche (2)<br />-List item (0 oder mehr)|Spinner<br /><br /> -ListItem (0 oder mehr)|  
  
 Um sicherzustellen, dass die beiden Schaltflächen in der Teilstruktur der Steuerelement Ansicht von automatisierten Testtools unter `SmallIncrement` schieden `SmallDecrement` werden können, weisen Sie oder `AutomationId` nach Bedarf zu. Bei einigen Implementierungen ist das zugeordnete Edit-Steuerelement möglicherweise ein Peer des Spinner-Steuerelements.  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften aufgelistet, deren Wert oder Definition für Spinner-Steuerelemente besonders relevant ist. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie unter [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Der durch Klicken aktivierbare Punkt des Spinner-Steuerelements übergibt den Fokus an den Bearbeitungsbereich des Steuerelements.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Das Spinner-Steuerelement ruft seinen Namen in der Regel aus einer statischen Textbezeichnung ab.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Spinner-Steuerelemente verfügen über eine statische Textbezeichnung.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Spinner|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Drehfeld“|Lokalisierte Zeichenfolge für den Steuerelementtyp „Spinner“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das Spinner-Steuerelement muss immer ein Inhaltselement sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Spinner-Steuerelement muss immer ein Steuerelement sein.|  
  
<a name="Required_UI_Automation_Control_Patterns_and_Properties"></a>   
## <a name="required-ui-automation-control-patterns-and-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster und -Eigenschaften  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster aufgelistet, die von allen Spinner-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster/Mustereigenschaft|Unterstützung/Wert|Hinweise|  
|---------------------------------------|--------------------|-----------|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider>|Variabel|Spinner-Steuerelemente mit einer zur Auswahl stehenden Liste von Elementen müssen dieses Muster unterstützen.|  
|<xref:System.Windows.Automation.Provider.ISelectionProvider.CanSelectMultiple%2A>|False|Spinner-Steuerelemente sind immer Einfachauswahlcontainer.|  
|<xref:System.Windows.Automation.Provider.IRangeValueProvider>|Variabel|Spinner-Steuerelemente, die einen numerischen Bereich umfassen, können dieses Muster unterstützen.|  
|<xref:System.Windows.Automation.Provider.IValueProvider>|Variabel|Spinner-Steuerelemente, die einen einzelnen Satz von Optionen oder Zahlen umfassen, können dieses Muster unterstützen.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Spinner-Steuerelementen unterstützt werden müssen. Weitere Informationen zu [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md)-Ereignissen finden Sie unter  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.SelectionPatternIdentifiers.InvalidatedEvent>|Variabel|None|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Required|None|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Required|None|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Required|None|  
|Durch geänderte<xref:System.Windows.Automation.ValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|None|  
|Durch geänderte<xref:System.Windows.Automation.RangeValuePatternIdentifiers.ValueProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|None|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Required|None|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.Spinner>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
