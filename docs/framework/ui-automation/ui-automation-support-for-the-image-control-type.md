---
title: Benutzeroberflächenautomatisierungs-Unterstützung für den Bild-Steuerelementtyp
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Image control type
- control types, Image
- Image control type
ms.assetid: 4e0eeefb-e09b-46d2-b83b-0a7e35543ab8
ms.openlocfilehash: d6c772137472b6a9e0c287def6fac9fe545414ee
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196293"
---
# <a name="ui-automation-support-for-the-image-control-type"></a>Benutzeroberflächenautomatisierungs-Unterstützung für den Bild-Steuerelementtyp
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 Dieses Thema enthält Informationen zur [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Unterstützung für den Steuerelementtyp „Image“. In [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]umfasst ein Steuerelementtyp eine Reihe von Bedingungen, die ein Steuerelement erfüllen muss, damit die <xref:System.Windows.Automation.AutomationElement.ControlTypeProperty> -Eigenschaft verwendet werden kann. Die Bedingungen schließen bestimmte Richtlinien für [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaftswerte und Steuerelementmuster ein.  
  
 Als Symbole, Informationsgrafiken und Diagramme verwendete Image-Steuerelemente unterstützen den Steuerelementtyp „Image“. Als Hintergrund- oder Wasserzeichenbilder verwendete Steuerelemente unterstützen den Steuerelementtyp „Image“ nicht.  
  
 In den folgenden Abschnitten werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur, -Eigenschaften, -Steuerelementmuster und -Ereignisse definiert, die für den Steuerelementtyp „Image“ erforderlich sind. Die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Anforderungen gelten für alle Image-Steuerelemente, egal ob [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], [!INCLUDE[TLA#tla_win32](../../../includes/tlasharptla-win32-md.md)]oder [!INCLUDE[TLA#tla_winforms](../../../includes/tlasharptla-winforms-md.md)].  
  
<a name="Required_UI_Automation_Tree_Structure"></a>   
## <a name="required-ui-automation-tree-structure"></a>Erforderliche Benutzeroberflächenautomatisierungs-Struktur  
 In der folgenden Tabelle werden die Steuerelementansicht und die Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur für Image-Steuerelemente sowie die möglichen Inhalte der Ansichten beschrieben. Weitere Informationen über die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur finden Sie unter [UI Automation Tree Overview](../../../docs/framework/ui-automation/ui-automation-tree-overview.md).  
  
|Steuerelementansicht|Inhaltsansicht|  
|------------------|------------------|  
|Bild|Bild (abhängig davon, ob das Bild Informationen enthält (basierend auf dem Wert der `IsContentElement` -Eigenschaft))|  
  
<a name="Required_UI_Automation_Properties"></a>   
## <a name="required-ui-automation-properties"></a>Erforderliche Benutzeroberflächenautomatisierungs-Eigenschaften  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaften aufgelistet, deren Wert oder Definition für den Image-Steuerelementtyp besonders relevant ist. Weitere Informationen zu Eigenschaften [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -finden Sie unter [UI Automation Properties for Clients](../../../docs/framework/ui-automation/ui-automation-properties-for-clients.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Eigenschaft|Wert|Hinweise|  
|------------------------------------------------------------------------------------|-----------|-----------|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationIdProperty>|Siehe Hinweise.|Der Wert dieser Eigenschaft muss für alle Steuerelemente in einer Anwendung eindeutig sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty>|Siehe Hinweise.|Das äußere Rechteck, das das gesamte Steuerelement enthält.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ClickablePointProperty>|Siehe Hinweise.|Der durch Klicken aktivierbare Punkt des Image-Steuerelements muss ein Punkt innerhalb des umschließenden Rechtecks des Image-Steuerelements sein.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsKeyboardFocusableProperty>|Siehe Hinweise.|Wenn das Steuerelement den Tastaturfokus erhalten kann, muss es diese Eigenschaft unterstützen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty>|Siehe Hinweise.|Die Name-Eigenschaft muss für alle Image-Steuerelemente verfügbar gemacht werden, die Informationen enthalten. Der programmgesteuerte Zugriff auf diese Informationen erfordert, dass eine aus Text bestehende Entsprechung zur Grafik bereitgestellt wird. Wenn das Image-Steuerelement rein dekorativen Zwecken dient, muss es nur in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur angezeigt werden und benötigt daher keinen Namen. Benutzeroberflächenframeworks müssen eine ALT- oder alternative Texteigenschaft für Bilder unterstützen, die innerhalb des Frameworks festgelegt werden kann. Diese Eigenschaft wird dann der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] Name-Eigenschaft zugeordnet.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LabeledByProperty>|Siehe Hinweise.|Wenn eine statische Textbezeichnung vorhanden ist, muss diese Eigenschaft einen Verweis auf das entsprechende Steuerelement verfügbar machen.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ControlTypeProperty>|Bild|Dieser Wert ist für alle Benutzeroberflächenframeworks gleich.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.LocalizedControlTypeProperty>|„Bild“|Lokalisierte Zeichenfolge für den Steuerelementtyp „Image“.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsContentElementProperty>|Siehe Hinweise.|Das Image-Steuerelement muss in der Inhaltsansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur enthalten sein, wenn es bedeutsame Informationen enthält, die für den Endbenutzer noch nicht verfügbar gemacht wurden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.IsControlElementProperty>|True|Das Image-Steuerelement ist in der Steuerelementansicht der [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Struktur immer enthalten.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.HelpTextProperty>|Siehe Hinweise.|Die HelpText-Eigenschaft macht eine lokalisierte Zeichenfolge verfügbar, die die tatsächliche visuelle Darstellung des Steuerelements (z. B. ein rotes Quadrat mit einem weißen „X“) oder andere dem Bild zugeordnete QuickInfo-Informationen beschreibt.<br /><br /> Diese Eigenschaft muss unterstützt werden, wenn eine lange Beschreibung erforderlich ist, um weitere Informationen zum Image-Steuerelement zu vermitteln. Beispielsweise eine komplizierte Grafik oder ein Diagramm. Diese Eigenschaft wird dem „LongDesc“-HTML-Tag und dem „Desc“-SVG-Tag (Scalable Vector Graphics) zugeordnet. Mit Image-Steuerelementen arbeitende Entwickler müssen eine Eigenschaft unterstützen, um das Festlegen der visuellen Beschreibung für das Steuerelement zu gestatten. Diese Eigenschaft muss der „VisualDescription“-Eigenschaft der Benutzeroberflächenautomatisierung zugeordnet werden.|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.ItemStatusProperty>|Siehe Hinweise.|Wenn das Image-Steuerelement Statusinformationen zu einem bestimmten Element auf dem Bildschirm darstellt, sollte das Steuerelement in diesem Element enthalten sein. Wenn das Bild in einem Element enthalten ist, muss das Element die Status-Eigenschaft unterstützen und entsprechende Benachrichtigungen auslösen, wenn sich der Status ändert.<br /><br /> Wenn ein Bild ein eigenständiges Steuerelement ist und den Status übermittelt, muss diese Eigenschaft unterstützt werden.|  
  
<a name="Required_UI_Automation_Control_Patterns"></a>   
## <a name="required-ui-automation-control-patterns"></a>Erforderliche Benutzeroberflächenautomatisierungs-Steuerelementmuster  
 In der folgenden Tabelle werden die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Steuerelementmuster aufgelistet, die von allen Image-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Steuerelementmustern finden Sie unter [UI Automation Control Patterns Overview](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md).  
  
|Steuerelementmuster|Unterstützung|Hinweise|  
|---------------------|-------------|-----------|  
|<xref:System.Windows.Automation.Provider.IGridItemProvider>|Variabel|Das Image-Steuerelement unterstützt das GridItem-Muster, wenn sich das Steuerelement innerhalb eines Rastercontainers befindet.|  
|<xref:System.Windows.Automation.Provider.ITableItemProvider>|Variabel|Das Image-Steuerelement unterstützt das TableItem-Muster, wenn sich das Steuerelement innerhalb eines Containers befindet, der Header-Steuerelemente aufweist.|  
|<xref:System.Windows.Automation.Provider.IInvokeProvider>|Nie|Wenn das Image-Steuerelement ein durch Klicken aktivierbares Bild enthält, sollte das Steuerelement einen Steuerelementtyp unterstützen, der das Invoke-Muster unterstützt, z. B. den Steuerelementtyp „Button“.|  
|<xref:System.Windows.Automation.Provider.ISelectionItemProvider>|Nie|Image-Steuerelemente sollten das SelectionItem-Muster nicht unterstützen.|  
  
<a name="Required_UI_Automation_Events"></a>   
## <a name="required-ui-automation-events"></a>Erforderliche Benutzeroberflächenautomatisierungs-Ereignisse  
 Die folgende Tabelle enthält die [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignisse, die von allen Image-Steuerelementen unterstützt werden müssen. Weitere Informationen zu Ereignissen finden Sie unter [UI Automation Events Overview](../../../docs/framework/ui-automation/ui-automation-events-overview.md).  
  
|[!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)] -Ereignis|Unterstützung|Hinweise|  
|---------------------------------------------------------------------------------|-------------|-----------|  
|<xref:System.Windows.Automation.InvokePatternIdentifiers.InvokedEvent>|Nie|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementAddedToSelectionEvent>|Nie|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementRemovedFromSelectionEvent>|Nie|Keiner|  
|<xref:System.Windows.Automation.SelectionItemPatternIdentifiers.ElementSelectedEvent>|Nie|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsOffscreenProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.IsEnabledProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|Durch geänderte<xref:System.Windows.Automation.AutomationElementIdentifiers.NameProperty> -Eigenschaft ausgelöstes Ereignis.|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.AutomationFocusChangedEvent>|Erforderlich|Keiner|  
|<xref:System.Windows.Automation.AutomationElementIdentifiers.StructureChangedEvent>|Erforderlich|Keiner|  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Automation.ControlType.Image>
- [Übersicht über Steuerelementtypen für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-types-overview.md)
- [Übersicht über die Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-overview.md)
