---
title: Anpassen des Workflowentwurfsvorgangs
ms.date: 03/30/2017
helpviewer_keywords:
- extending [WF], Workflow Designer
ms.assetid: 98135077-0f5d-4d16-9337-01094e843537
ms.openlocfilehash: 926edb4478551affa03619f44ee886d5eb591e4d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65637265"
---
# <a name="customizing-the-workflow-design-experience"></a>Anpassen des Workflowentwurfsvorgangs

Die Szenarien zum Entwerfen von benutzerdefinierten Aktivitäten und zum erneuten Hosten von [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] wurden in [!INCLUDE[netfx40_short](../../../includes/netfx40-short-md.md)] deutlich vereinfacht. Die Entwicklung und Bereitstellung sind jetzt einfacher sowie flexibler. Die wichtigste Änderung ist, dass das neue Aktivitätsdesigner-Programmiermodell von Windows Presentation Foundation (WPF) erstellt wird. Dies ermöglicht Ihnen, Aktivitätsdesigner deklarativ zu definieren und den [!INCLUDE[wfd2](../../../includes/wfd2-md.md)] in anderen Anwendungen vergleichsweise einfach erneut zu hosten. Beim erneuten Hosten kann ein benutzerdefinierter Ausdrucks-Editor entwickelt werden, um IntelliSense oder eine vereinfachte Ausdrucksdomäne zu unterstützen. Die Integration mit Windows Communication Foundation (WCF) ist mit der Verwendung von Workflowdiensten nahtloser geworden. Benutzerdefinierte Aktivitätsdesigner und die Modellelementstruktur können verwendet werden, um die Entwurfszeiterfahrung in neu gehosteten Workflowdesignern zu verbessern.

## <a name="in-this-section"></a>In diesem Abschnitt

 [Verwenden benutzerdefinierter Aktivitätsdesigner und Vorlagen](using-custom-activity-designers-and-templates.md)

 Beschreibt die Erstellung eines neuen benutzerdefinierten Aktivitätsdesigners und von Vorlagen.

 [Erneutes Hosten des Workflow-Designers](rehosting-the-workflow-designer.md)

 Beschreibt das erneute hosten die [!INCLUDE[wfd1](../../../includes/wfd1-md.md)] außerhalb von Visual Studio und wie Validierungsfehler angezeigt.

 [Verwenden eines benutzerdefinierten Ausdrucks-Editors](using-a-custom-expression-editor.md)

 Beschreibt, wie einen benutzerdefinierter Ausdrucks-Editor für die Verwendung von workflowdesignern, die außerhalb von Visual Studio 2010 zu implementieren.

## <a name="reference"></a>Referenz

<xref:System.Activities.Presentation.ActivityDesigner>

## <a name="see-also"></a>Siehe auch

- [Erweitern der Windows Workflow Foundation](extend.md)
- [Designer](./samples/designer.md)
- [Benutzerdefinierte Aktivitätsdesigner](./samples/custom-activity-designers.md)
- [Erneutes Hosten von Designern](./samples/designer-rehosting.md)
