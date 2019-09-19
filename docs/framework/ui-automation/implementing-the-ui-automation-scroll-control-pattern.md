---
title: Implementieren des Scroll-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- UI Automation, Scroll control pattern
- control patterns, Scroll
- Scroll control pattern
ms.assetid: 73d64242-6cbb-424c-92dd-dc69530b7899
ms.openlocfilehash: b8193ed8c7b5fab934d83eb31f5b562136a290ec
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043314"
---
# <a name="implementing-the-ui-automation-scroll-control-pattern"></a>Implementieren des Scroll-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren von <xref:System.Windows.Automation.Provider.IScrollProvider>, einschließlich Informationen über Ereignisse und Eigenschaften. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.ScrollPattern> -Steuerelementmuster dient zur Unterstützung eines Steuerelements, das als bildlauffähiger Container für eine Auflistung von untergeordneten Objekten fungiert. Es ist nicht erforderlich, dass das Steuerelement Bildlaufleisten verwendet, um die Bildlauffunktionen zu unterstützen, obwohl dies häufig der Fall ist.  
  
 ![Scroll-Steuerelement ohne Scrollleisten.](./media/uia-scrollpattern-without-scrollbars.PNG "UIA_ScrollPattern_Without_Scrollbars")  
Beispiel für ein Bildlaufsteuerelement, das keine Bildlaufleisten verwendet  
  
 Beispiele für Steuerelemente, die dieses Steuerelement implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des Scroll-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- Die untergeordneten Elemente dieses Steuerelements müssen <xref:System.Windows.Automation.Provider.IScrollItemProvider>implementieren.  
  
- Die Bildlaufleisten eines Containersteuerelements bieten keine Unterstützung für das <xref:System.Windows.Automation.ScrollPattern> -Steuerelementmuster. Sie müssen stattdessen die <xref:System.Windows.Automation.RangeValuePattern> -Steuerelementmuster unterstützen.  
  
- Wenn das Scrollen in Prozentwerten gemessen wird, müssen alle Werte oder Beträge, die sich auf die Einteilung der Bildlaufleiste beziehen, auf einen Bereich von 0 bis 100 normalisiert werden.  
  
- <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> und <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> sind unabhängig von der <xref:System.Windows.Automation.AutomationElement.IsEnabledProperty>.  
  
- Wenn <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontallyScrollableProperty> = `false` ist, dann muss <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalViewSizeProperty> auf 100 % und <xref:System.Windows.Automation.ScrollPatternIdentifiers.HorizontalScrollPercentProperty> auf <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. Wenn <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticallyScrollableProperty> = `false` ist, dann muss <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalViewSizeProperty> ebenso auf 100 % und <xref:System.Windows.Automation.ScrollPatternIdentifiers.VerticalScrollPercentProperty> auf <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>. Dadurch kann ein Benutzeroberflächenautomatisierungs-Client diese Eigenschaftswerte innerhalb der <xref:System.Windows.Automation.ScrollPattern.SetScrollPercent%2A> -Methode verwenden, während zugleich eine [Racebedingung](https://support.microsoft.com/default.aspx?scid=kb;en-us;317723) vermieden wird, wenn eine Richtung aktiviert wird, die für den Client für einen Bildlauf nicht von Interesse ist.  
  
- <xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A> ist gebietsschemaspezifisch. Bei der Einstellung „HorizontalScrollPercent = 100,0“ muss die Bildlaufposition des Steuerelements auf das Äquivalent seiner äußersten rechten Position für Sprachen wie Englisch festgelegt werden, die von links nach rechts gelesen werden. Für Sprachen wie Arabisch, die von rechts nach links gelesen werden, muss die Bildlaufposition bei der Einstellung „HorizontalScrollPercent = 100,0“ auf der äußerste linke Position festgelegt werden.  
  
<a name="Required_Members_for_IScrollProvider"></a>   
## <a name="required-members-for-iscrollprovider"></a>Erforderliche Member für IScrollProvider  
 Die folgenden Eigenschaften und Methoden sind für das Implementieren von <xref:System.Windows.Automation.Provider.IScrollProvider>erforderlich.  
  
|Erforderliche Member|Memberart|Hinweise|  
|---------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalScrollPercent%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalScrollPercent%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontalViewSize%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticalViewSize%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.HorizontallyScrollable%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.VerticallyScrollable%2A>|Eigenschaft|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A>|Methode|None|  
|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A>|Methode|None|  
  
 Diesem Steuerelementmuster sind keine Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> löst diese Ausnahme aus, wenn ein Steuerelement <xref:System.Windows.Automation.ScrollAmount.SmallIncrement> -Werte ausschließlich für horizontale oder vertikale Bildläufe unterstützt, aber ein <xref:System.Windows.Automation.ScrollAmount.LargeIncrement> -Wert übergeben wird.|  
|<xref:System.ArgumentException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> löst diese Ausnahme aus, wenn ein Wert, der nicht in einen Double-Wert konvertiert werden kann, übergeben wird.|  
|<xref:System.ArgumentOutOfRangeException>|<xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> löst diese Ausnahme aus, wenn ein Wert größer 100 oder kleiner 0 übergeben wird (außer bei -1, was <xref:System.Windows.Automation.ScrollPatternIdentifiers.NoScroll>entspricht).|  
|<xref:System.InvalidOperationException>|Sowohl <xref:System.Windows.Automation.Provider.IScrollProvider.Scroll%2A> als auch <xref:System.Windows.Automation.Provider.IScrollProvider.SetScrollPercent%2A> lösen diese Ausnahme aus, wenn versucht wird, in eine nicht unterstützte Richtung zu scrollen.|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
