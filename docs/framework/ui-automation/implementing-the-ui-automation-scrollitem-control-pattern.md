---
title: Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
helpviewer_keywords:
- control patterns, Scroll Item
- UI Automation, Scroll Item control pattern
- Scroll Item control pattern
ms.assetid: 903bab5c-80c1-44d7-bdc2-0a418893b987
ms.openlocfilehash: e8f9373c840b00c8089f01a562f768f27f2cd945
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71043304"
---
# <a name="implementing-the-ui-automation-scrollitem-control-pattern"></a>Implementieren des ScrollItem-Steuerelementmusters der Benutzeroberflächenautomatisierung
> [!NOTE]
> Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]finden [Sie unter Windows Automation-API: Automatisierung](https://go.microsoft.com/fwlink/?LinkID=156746)der Benutzeroberfläche.  
  
 Dieses Thema enthält Richtlinien und Konventionen für das Implementieren des <xref:System.Windows.Automation.Provider.IScrollItemProvider>, einschließlich Informationen über Eigenschaften, Methoden und Ereignissen. Links zu zusätzlichen Referenzen sind am Ende dieses Themas aufgelistet.  
  
 Das <xref:System.Windows.Automation.ScrollItemPattern>-Steuerelementmuster wird verwendet, um einzelne untergeordnete Steuerelemente von Containern zu unterstützen, in denen <xref:System.Windows.Automation.Provider.IScrollProvider> implementiert ist. Dieses Steuerelementmuster dient als Kommunikationskanal zwischen einem untergeordneten Steuerelement und dessen Container, um sicherzustellen, dass der Container den aktuell sichtbaren Inhalt (oder die Region) innerhalb des Viewports ändern kann, um das untergeordnete Steuerelement anzuzeigen. Beispiele für Steuerelemente, die dieses Steuerelementmuster implementieren, finden Sie unter [Control Pattern Mapping for UI Automation Clients](control-pattern-mapping-for-ui-automation-clients.md).  
  
<a name="Implementation_Guidelines_and_Conventions"></a>   
## <a name="implementation-guidelines-and-conventions"></a>Implementierungsrichtlinien und -konventionen  
 Beachten Sie beim Implementieren des ScrollItem-Steuerelementmusters die folgenden Richtlinien und Konventionen:  
  
- In einem Window- oder Canvas-Steuerelement enthaltene Elemente müssen die IScrollItemProvider-Schnittstelle nicht implementieren. Stattdessen können sie jedoch einen gültigen Speicherort für die <xref:System.Windows.Automation.AutomationElementIdentifiers.BoundingRectangleProperty> verfügbar machen. Dadurch kann eine Benutzeroberflächenautomatisierungs-Clientanwendung die <xref:System.Windows.Automation.ScrollPattern>-Steuerelementmustermethoden im Container verwenden, um das untergeordnete Element anzuzeigen.  
  
<a name="Required_Members_for_IScrollItemProvider"></a>   
## <a name="required-members-for-iscrollitemprovider"></a>Erforderliche Member für IScrollItemProvider  
 Die folgende Methode ist zum Implementieren der IScrollProvider-Schnittstelle erforderlich.  
  
|Erforderliche Member|Memberart|Hinweise|  
|----------------------|-----------------|-----------|  
|<xref:System.Windows.Automation.Provider.IScrollItemProvider.ScrollIntoView%2A>|-Methode|None|  
  
 Diesem Steuerelementmuster sind keine Eigenschaften oder Ereignisse zugeordnet.  
  
<a name="Exceptions"></a>   
## <a name="exceptions"></a>Ausnahmen  
 Anbieter müssen die folgenden Ausnahmen auslösen.  
  
|Ausnahmetyp|Bedingung|  
|--------------------|---------------|  
|<xref:System.InvalidOperationException>|Wenn ein Element nicht in die Ansicht gescrollt werden kann:<br /><br /> -   <xref:System.Windows.Automation.ScrollItemPattern.ScrollIntoView%2A>|  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Steuerelementmuster für Benutzeroberflächenautomatisierung](ui-automation-control-patterns-overview.md)
- [Unterstützung von Steuerelementmustern in einem Benutzeroberflächenautomatisierungs-Anbieter](support-control-patterns-in-a-ui-automation-provider.md)
- [Steuerelementmuster für Benutzeroberflächenautomatisierung für Clients](ui-automation-control-patterns-for-clients.md)
- [Übersicht über die Benutzeroberflächenautomatisierungs-Struktur](ui-automation-tree-overview.md)
- [Verwenden der Zwischenspeicherung in der Benutzeroberflächenautomatisierung](use-caching-in-ui-automation.md)
