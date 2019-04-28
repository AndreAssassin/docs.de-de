---
title: Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- UI Automation, getting toggle states of check boxes
- check boxes, getting toggle states of
- getting, toggle states of check boxes
ms.assetid: 84fc31a3-175f-4e93-90a0-dd29d89b77ce
ms.openlocfilehash: 42dc9c679f877b0136cac12eae232e4365f79bdf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609996"
---
# <a name="get-the-toggle-state-of-a-check-box-using-ui-automation"></a>Abrufen des Umschaltstatus eines Kontrollkästchens mithilfe von Benutzeroberflächenautomatisierung
> [!NOTE]
>  Diese Dokumentation ist für .NET Framework-Entwickler vorgesehen, die die verwalteten [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)]-Klassen verwenden möchten, die im <xref:System.Windows.Automation>-Namespace definiert sind. Die neuesten Informationen zu [!INCLUDE[TLA2#tla_uiautomation](../../../includes/tla2sharptla-uiautomation-md.md)], finden Sie unter [Windows-Automatisierungs-API: Benutzeroberflächenautomatisierung](https://go.microsoft.com/fwlink/?LinkID=156746).  
  
 In diesem Thema wird gezeigt, wie Sie mit [!INCLUDE[TLA#tla_uiautomation](../../../includes/tlasharptla-uiautomation-md.md)] zum Abrufen des Umschaltstatus eines Steuerelements.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die <xref:System.Windows.Automation.AutomationElement.GetCurrentPattern%2A> -Methode der der <xref:System.Windows.Automation.AutomationElement> Klasse zum Abrufen einer <xref:System.Windows.Automation.TogglePattern> Objekt von einem Steuerelement und Zurückgeben der <xref:System.Windows.Automation.ToggleState> Eigenschaft.  
  
 [!code-csharp[NavigatingWithTreeWalker#1200](../../../samples/snippets/csharp/VS_Snippets_Wpf/NavigatingWithTreeWalker/CSharp/ClientClass.cs#1200)]
 [!code-vb[NavigatingWithTreeWalker#1200](../../../samples/snippets/visualbasic/VS_Snippets_Wpf/NavigatingWithTreeWalker/visualbasic/clientclass.vb#1200)]
