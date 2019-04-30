---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- control types, Menu Item
- Menu Item control type
- UI Automation, Menu Item control type
ms.assetid: 54bce311-3d23-40b9-ba90-1bdbdaf8fbba
ms.openlocfilehash: 236f4ff5bfd709426975c7a8c1d828eb8b3fe89b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62032291"
---
# <a name="ui-automation-support-for-the-menuitem-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den MenuItem-Steuerelementtyp

> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).

Dieses Thema enthält Informationen zur [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „MenuItem“. Im Thema wird die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Struktur des Steuerelements beschrieben und werden die Eigenschaften sowie Steuerelementmuster angegeben, die für den Steuerelementtyp „MenuItem“ erforderlich sind.

Ein Menüsteuerelement ermöglicht die hierarchische Organisation von Elementen, die Befehlen und Ereignishandlern zugeordnet sind. In einer typischen [!INCLUDE[TLA#tla_win](../../../includes/tlasharptla-win-md.md)] -Anwendung enthält eine Menüleiste verschiedene Menüelemente (etwa **Datei**, **Bearbeiten**und **Fenster**), und nach Klicken auf ein Menüelement wird ein Menü angezeigt. Ein Menü enthält eine Sammlung von Menüelementen (z. B. **Neu**, **Öffnen**und **Schließen**), die erweitert werden können, um weitere Menüelemente anzuzeigen, oder auf die geklickt werden kann, um eine bestimmte Aktion auszuführen. Ein Menüelement kann in einem Menü, auf einer Menüleiste oder auf einer Symbolleiste gehostet werden.

In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „MenuItem“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Listensteuerelemente in [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].

<a name="Required_UI_Automation_Tree_Structure"></a>

## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur

In der folgende Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Menüelement-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).

|Steuerelementansicht|Inhaltsansicht|
|------------------|------------------|
|MenuItem „Hilfe“ (?)<br /><br /> <ul><li>Menü (Untermenü des Menüelements „Hilfe“)<br /><br /> <ul><li>MenuItem „Hilfethemen“</li><li>MenuItem „Info“</li></ul></li></ul>|MenuItem „Hilfe“ (?)<br /><br /> -MenuItem "Hilfethemen"<br />-MenuItem "Info"|

Die Steuerelementansicht des MenuItem-Steuerelements verfügt über die oben gezeigte [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur. Beachten Sie, dass die **Hilfe** Menüelement ist eingeschlossen, um die Struktur in einer typischen Untermenühierarchie von Menü zu besser zu veranschaulichen.

Bei der Inhaltsansicht fehlt das Menü in der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, da es dem Endbenutzer keine relevanten Informationen vermittelt.

<a name="Required_UI_Automation_Properties"></a>

## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften, deren Werte oder Definitionen für MenuItem-Steuerelemente besonders relevant sind. Weitere Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Eigenschaften finden Sie [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).

|Eigenschaft|Wert|Beschreibung|
|--------------|-----------|-----------------|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Unterstützt, wenn es ein umschließendes Rechteck gibt. Wenn nicht auf jeden Punkt innerhalb des umschließenden Rechtecks geklickt werden kann, und Sie spezielle Treffertests ausführen, setzen Sie die Eigenschaft außer Kraft, und stellen Sie dann einen klickbaren Punkt bereit.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Das MenuItem-Steuerelement ist in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten und es wird mit einer Bezeichnung versehen.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|`Null`|Keine Bezeichnung.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|MenuItem|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Menüelement“|Lokalisierte Zeichenfolge für den Steuerelementtyp „MenuItem“.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|True|Das MenuItem-Steuerelement ist in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur nie enthalten.|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das MenuItem-Steuerelement muss in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur immer enthalten sein.|

<a name="Required_UI_Automation_Control_Patterns"></a>

## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster, die von allen MenuItem-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).

|Steuerelementmustereigenschaft|Unterstützung|Hinweise|
|------------------------------|-------------|-----------|
|<xref:System.Windows.Automation.Provider.IExpandCollapseProvider>|Variabel|Wenn das Steuerelement erweitert oder reduziert werden kann, implementieren Sie <xref:System.Windows.Automation.Provider.IExpandCollapseProvider>.|
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Variabel|Wenn das Steuerelement eine einzelne Aktion oder einen Befehl ausführt, implementieren Sie <xref:System.Windows.Automation.Provider.IInvokeProvider>.|
|<xref:System.Windows.Automation.Provider.IToggleProvider>|Variabel|Wenn das Steuerelement eine Option darstellt, die aktiviert oder deaktiviert werden kann, implementieren Sie <xref:System.Windows.Automation.Provider.IToggleProvider>.|
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Variabel|Wenn das Steuerelement für die Auswahl aus einer Liste von Optionen unter Menüelementen verwendet wird, implementieren Sie <xref:System.Windows.Automation.Provider.ISelectionItemProvider>.|

<a name="UI_Automation_Events_for_Menu_Item"></a>

## <a name="ui-automation-events-for-menu-item"></a>Benutzeroberflächenautomatisierungs-Ereignisse für Menüelemente

In der folgenden Tabelle sind die [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] -Ereignisse aufgeführt, die dem MenuItem-Steuerelement zugeordnet sind.

|event|Unterstützung|Erklärung|
|-----------|-------------|-----------------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Muss ausgelöst werden, wenn das Steuerelement Invoke-Steuerelementmuster unterstützt.|
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Muss ausgelöst werden, wenn das Steuerelement Toggle-Steuerelementmuster unterstützt.|
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Muss ausgelöst werden, wenn das Steuerelement „Expand Collapse“-Steuerelementmuster unterstützt.|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Variabel|Keine|

<a name="Required_UI_Automation_Events"></a>

## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse

Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen MenuItem-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).

|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung/Wert|Hinweise|
|---------------------------------------------------------------------------------|--------------------|-----------|
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Variabel|Keiner|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Variabel|Keiner|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Variabel|Keiner|
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Variabel|Keiner|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|
|Durch geänderte<xref:System.Windows.Automation.ExpandCollapsePatternIdentifiers.ExpandCollapseStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|
|Durch geänderte<xref:System.Windows.Automation.TogglePatternIdentifiers.ToggleStateProperty> -Eigenschaft ausgelöstes Ereignis.|Variabel|Keiner|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keine|

<a name="Legacy_Issues"></a>

## <a name="legacy-issues"></a>Legacyprobleme

Toggle-Muster werden nur unterstützt, wenn das [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Menüelement aktiviert ist und programmgesteuert festgelegt werden kann, was zum Unterstützen von Toggle-Mustern erforderlich ist. Da das [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)] -Menüelement nicht offenlegt, ob es aktiviert werden kann, werden Invoke-Muster unterstützt, wenn das Menüelement nicht aktiviert ist. Es wird eine Ausnahme gemacht, um Invoke-Muster immer zu unterstützen. Dies gilt auch für Menüelemente, die ausschließlich Toggle-Muster unterstützen sollten. Der Grund hierfür ist, dass Clients nicht irritiert werden sollen, wenn ein Element, das Invoke-Muster unterstützt hat (wenn das Menüelement nicht aktiviert ist), dieses Muster nicht mehr unterstützt, nachdem das Menüelement aktiviert wurde.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.MenuItem>
- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
