---
title: Aktivitäten zur Ablaufsteuerung in WF
ms.date: 03/30/2017
ms.assetid: 6892885b-f7c5-4aea-8f5e-28863fb4ae75
ms.openlocfilehash: bcbb12210af2d0172977dca6f81355031baa043a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945911"
---
# <a name="control-flow-activities-in-wf"></a>Aktivitäten zur Ablaufsteuerung in WF
[!INCLUDE[netfx_current_long](../../../includes/netfx-current-long-md.md)] stellt mehrere Aktivitäten zum Steuern des Ausführungsflusses innerhalb eines Workflows bereit. Einige dieser Aktivitäten (wie z. B. `Switch` und `If`) implementieren flusssteuerungsstrukturen ähnlich denen in programmierumgebungen wie z.B. Visual C#, während andere (z. B. `Pick`) neue Programmierungsstrukturen modellieren.  
  
 Beachten Sie, dass Aktivitäten wie die Aktivitäten `Parallel` und `ParallelForEach` mehrere untergeordnete Aktivitäten für eine gleichzeitige Ausführung planen, bei einem Workflow jedoch nur ein einzelner Thread verwendet wird. Jede untergeordnete Aktivität in diesen Aktivitäten wird sequenziell ausgeführt, und nachfolgende Aktivitäten werden erst ausgeführt, wenn vorherige Aktivitäten beendet werden oder sich im Leerlauf befindet. Deshalb sind diese Aktivitäten sehr hilfreich bei Anwendungen, in denen sich die Ausführung mehrerer potenziell blockierender Aktivitäten überschneidet. Wenn keine der untergeordneten Aktivitäten in diesen Aktivitäten in den Leerlauf wechselt, wird eine `Parallel`-Aktivität auf dieselbe Weise wie eine `Sequence`-Aktivität ausgeführt, und eine `ParallelForEach`-Aktivität wird genau wie eine `ForEach`-Aktivität ausgeführt. Wenn jedoch asynchrone Aktivitäten (z. B. Aktivitäten, die von <xref:System.Activities.AsyncCodeActivity> abgeleitet werden) oder Messagingaktivitäten verwendet werden, geht die Steuerung auf den nächsten Branch über, während die untergeordnete Aktivität darauf wartet, dass ihre Nachricht empfangen oder ihre asynchrone Arbeit abgeschlossen wird.  
  
## <a name="flow-control-activities"></a>Flusssteuerungsaktivitäten  
  
|Aktivität|Beschreibung|  
|--------------|-----------------|  
|<xref:System.Activities.Statements.DoWhile>|Führt die enthaltenen Aktivitäten ein Mal aus und setzt dies fort, solange für eine Bedingung `true` festgelegt ist.|  
|<xref:System.Activities.Statements.ForEach%601>|Führt eine eingebettete Anweisung für jedes Element in einer Auflistung nacheinander aus. <xref:System.Activities.Statements.ForEach%601> ist dem Schlüsselwort `foreach` ähnlich, wird jedoch eher als Aktivität implementiert, nicht als Sprachanweisung.|  
|<xref:System.Activities.Statements.If>|Führt enthaltene Aktivitäten aus, wenn eine Bedingung auf `true` festgelegt ist, und kann Aktivitäten ausführen, die in der <xref:System.Activities.Statements.If.Else%2A>-Eigenschaft enthalten sind, wenn die Bedingung auf `false` festgelegt ist.|  
|<xref:System.Activities.Statements.Parallel>|Führt enthaltene Aktivitäten parallel aus.|  
|<xref:System.Activities.Statements.ParallelForEach%601>|Führt eine eingebettete Anweisung für jedes Element in einer Auflistung gleichzeitig aus.|  
|<xref:System.Activities.Statements.Pick>|Stellt ereignisbasierte Flusssteuerungsmodellierung bereit.|  
|<xref:System.Activities.Statements.PickBranch>|Stellt einen potenziellen Ausführungspfad innerhalb einer <xref:System.Activities.Statements.Pick>-Aktivität dar.|  
|<xref:System.Activities.Statements.Sequence>|Führt enthaltene Aktivitäten nacheinander aus.|  
|<xref:System.Activities.Statements.Switch%601>|Wählt aus einer Reihe von Aktivitäten eine Aktivität zur Ausführung aus, basierend auf dem Wert eines angegebenen Ausdrucks.|  
|<xref:System.Activities.Statements.While>|Führt enthaltene Aktivitäten aus, solange eine Bedingung auf `true` festgelegt ist.|
