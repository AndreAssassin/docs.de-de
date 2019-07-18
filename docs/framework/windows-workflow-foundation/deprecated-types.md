---
title: Veraltete Typen in Windows Workflow Foundation
ms.date: 03/30/2017
ms.assetid: 4aebe928-a964-4c1c-abf7-0dbbd3604b13
ms.openlocfilehash: c8325e60d708b53e1701a980355d5d2bf20e8a4b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64644967"
---
# <a name="deprecated-types-in-windows-workflow-foundation"></a>Veraltete Typen in Windows Workflow Foundation
In .NET 4 hat das Workflowteam eine neue Workflow-Engine im <xref:System.Activities>-Namespace eingeführt. Mit der Version von .NET 4.5 Beta markieren wir die meisten Typen in den "WF3" <xref:System.Workflow.Activities>, <xref:System.Workflow.ComponentModel>, und <xref:System.Workflow.Runtime> Namespaces als veraltet.  
  
## <a name="obsolete-namespaces-and-tools"></a>Veraltete Namespaces und Tools  
 Die folgenden Assemblys enthalten mindestens einen öffentlichen Typ, der veraltet sein wird:  
  
- System.Workflow.Activities.dll  
  
- System.Workflow.ComponentModel.dll  
  
- System.Workflow.Runtime.dll  
  
- System.WorkflowServices.dll  
  
- Microsoft.Workflow.DebugController.dll  
  
- Microsoft.Workflow.Compiler.exe  
  
- Wfc.exe  
  
 Daher werden bei Kunden, die veraltete WF3-APIs verwenden, Erstellungswarnungen mit einer Meldung angezeigt, die der folgenden ähnelt:  
  
 **Warnung: BC40000 X ist veraltet: WF 3-Typen sind veraltet. Verwenden Sie stattdessen wf4.** In einem zukünftigen Release werden die Typen aus .NET Framework entfernt, doch der genaue Zeitpunkt hierfür steht noch nicht fest (nicht in 4.5). Dieser Schritt ermöglicht es uns, unseren Kunden unsere Pläne mitzuteilen und ihnen ausreichend Zeit zu geben, zum neuen WF4-Modell zu wechseln. Zur Unterstützung dieser in WF 3-Typen werden natürlich weiterhin die [Microsoft Support Lifecycle-Richtlinie](https://aka.ms/MicrosoftSupportLifecycle). Vorhandene WF3-Anwendungen, die ohne Probleme auf .NET 4.5 ausgeführt wird, und Visual Studio 2012 unterstützt neue und vorhandene WF3-basierte Lösungen.  
  
 Regelbezogene Typen im <xref:System.Workflow.Activities.Rules>-Namespace, für die es in WF 4.5 keinen Ersatz gibt, wurden nicht als veraltet markiert.  
  
 Kunden, die ihre Anwendungen zu wf4 migrieren möchten, findet in der Hilfe der [Workflow 4 Migrationsanleitung](migration-guidance.md).
