---
title: Implementieren des Value-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Value
- UI Automation, Value control pattern
- Value control pattern
ms.assetid: b0fcdd87-3add-4345-bca9-e891205e02ba
ms.openlocfilehash: 55290e8f14f81c50239097905e5407dbcf547c4c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968224"
---
# <a name="implementing-the-ui-automation-value-control-pattern"></a>Implementieren des Value-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IValueProvider>, einschließlich Informationen zu Ereignissen und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.ValuePattern> -Steuerelementmuster wird verwendet, um Steuerelemente zu unterstützen, die einen systeminternen Wert haben, der keinen Bereich umfasst und als Zeichenfolge dargestellt werden kann. Diese Zeichenfolge kann je nach Steuerelement und dessen Einstellungen bearbeitet werden. Beispiele für Steuerelemente, die dieses Muster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](../../../docs/framework/ui-automation/control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Value-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Steuerelemente wie <xref:System.Windows.Automation.ControlType.ListItem> und <xref:System.Windows.Automation.ControlType.TreeItem> müssen, unabhängig vom aktuellen Bearbeitungsmodus des Steuerelements, <xref:System.Windows.Automation.ValuePattern> unterstützen, wenn der Wert irgendeines der Elemente bearbeitet werden kann. Das übergeordnete Steuerelement muss außerdem <xref:System.Windows.Automation.ValuePattern> unterstützen, wenn die untergeordneten Elemente bearbeitbar sind.  
  
 ![Bearbeitbares Listenelement.](../../../docs/framework/ui-automation/media/uia-valuepattern-editable-listitem.PNG "UIA_ValuePattern_Editable_ListItem")  
Beispiel eines bearbeitbaren Listenelements  
  
- Einzeilige Bearbeitungssteuerelemente unterstützen programmgesteuerten Zugriff auf ihren Inhalt, indem <xref:System.Windows.Automation.Provider.IValueProvider>für sie implementiert wird. Für mehrzeilige Bearbeitungssteuerelemente wird <xref:System.Windows.Automation.Provider.IValueProvider>jedoch nicht implementiert. Stattdessen wird Zugriff auf ihre Inhalte geboten, indem <xref:System.Windows.Automation.Provider.ITextProvider>für sie implementiert wird.  
  
- Um den Textinhalt eines mehrzeiligen Bearbeitungssteuerelements abzurufen, muss <xref:System.Windows.Automation.Provider.ITextProvider>für das Steuerelement implementiert sein. <xref:System.Windows.Automation.Provider.ITextProvider> bietet aber nicht die Möglichkeit, den Wert eines Steuerelements festzulegen.  
  
- Mit<xref:System.Windows.Automation.Provider.IValueProvider> ist es nicht möglich, Formatierungsinformationen oder Teilzeichenfolgen abzurufen. Implementieren Sie <xref:System.Windows.Automation.Provider.ITextProvider> in diesen Fällen.  
  
- <xref:System.Windows.Automation.Provider.IValueProvider> muss für Steuerelemente wie z. B. das **Farbauswahl** -Auswahlsteuerelement von [!INCLUDE[TLA#tla_word](../../../includes/tlasharptla-word-md.md)] (unten dargestellt) implementiert werden. Hierdurch werden Zeichenfolgenzuordnungen zwischen einem Farbwert (beispielsweise „Gelb“) und der entsprechenden internen [!INCLUDE[TLA#tla_rgb](../../../includes/tlasharptla-rgb-md.md)] -Struktur unterstützt.  
  
 ![Farbauswahl mit gelber Hervorhebung.](../../../docs/framework/ui-automation/media/uia-valuepattern-colorpicker.png "UIA_ValuePattern_ColorPicker")  
Beispiel für eine Zuordnung zwischen Farbmustern und Zeichenfolgen  
  
- Für ein Steuerelement sollte dessen <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty> auf `true` und dessen <xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty> auf `false` festgelegt sein, bevor ein Aufruf von <xref:System.Windows.Automation.Provider.IValueProvider.SetValue%2A>zugelassen wird.  
  
<a name="Required_Members_for_the_IValueProvider_Interface"></a>   
## <a name="required-members-for-ivalueprovider"></a>Erforderliche Member für IValueProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IValueProvider>erforderlich.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.ValuePattern.IsReadOnlyProperty>|Eigenschaft|None|  
|<xref:System.Windows.Automation.ValuePattern.ValueProperty>|Eigenschaft|None|  
|<xref:System.Windows.Automation.ValuePattern.SetValue%2A>|Methode|None|  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> : Wenn Gebiets Schema spezifische Informationen in einem falschen Format an ein Steuerelement übermittelt werden, z. b. ein falsch formatiertes Datum.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> : Wenn ein neuer Wert nicht von einer Zeichenfolge in ein Format konvertiert werden kann, das vom Steuerelement erkannt wird.|  
|<xref:System.Windows.Automation.ElementNotEnabledException>|<xref:System.Windows.Automation.ValuePattern.SetValue%2A><br /><br /> : Beim Versuch, ein nicht aktiviertes Steuerelement zu bearbeiten.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](../../../docs/framework/ui-automation/support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](../../../docs/framework/ui-automation/ui-automation-control-patterns-for-clients.md)
- [Beispiel für ValuePattern Insert Text](https://github.com/Microsoft/WPF-Samples/tree/master/Accessibility/InsertText)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](../../../docs/framework/ui-automation/ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](../../../docs/framework/ui-automation/use-caching-in-ui-automation.md)
