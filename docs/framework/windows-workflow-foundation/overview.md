---
title: Übersicht über Windows-Workflow
ms.date: 03/30/2017
ms.assetid: fc44adbe-1412-49ae-81af-0298be44aae6
ms.openlocfilehash: 57c394805d4aa07f8a137af259619bb1e65c43de
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217600"
---
# <a name="windows-workflow-overview"></a>Übersicht über Windows-Workflow
Ein Workflow ist eine Reihe von elementaren Einheiten mit dem Namen *Aktivitäten* , die als Modell, das einen realen Vorgang beschreibt gespeichert sind. Mit Workflows können die Reihenfolge der Ausführung sowie abhängige Beziehungen zwischen kurz- und langfristiger Arbeit beschrieben werden. Diese Arbeit durchläuft das Modell vom Anfang bis zum Ende, und Aktivitäten werden unter Umständen von Personen oder Systemfunktionen ausgeführt.  
  
## <a name="workflow-run-time-engine"></a>Workflowruntime-Engine  
 Jede ausgeführte Workflowinstanz wird von einer prozessinternen Runtime-Engine erstellt und verwaltet, mit dem der Hostprozess durch eines der folgenden Objekte interagiert:  
  
-   Ein <xref:System.Activities.WorkflowInvoker>-Objekt, der den Workflow wie eine Methode aufruft.  
  
-   Ein <xref:System.Activities.WorkflowApplication>-Objekt für die explizite Kontrolle über die Ausführung einer einzelnen Workflowinstanz.  
  
-   Ein <xref:System.ServiceModel.WorkflowServiceHost>-Objekt für meldungsbasierte Interaktionen in Szenarien mit mehreren Instanzen.  
  
 Jede dieser Klassen umschließt die Kernaktivitätslaufzeit, die als <xref:System.Activities.ActivityInstance> dargestellt wird und für die Aktivitätsausführung zuständig ist. Es kann mehrere <xref:System.Activities.ActivityInstance>-Objekte innerhalb einer Anwendungsdomäne geben, die gleichzeitig ausgeführt werden.  
  
 Jede der vorausgehenden drei Hostinteraktionsobjekte wird aus einer Aktivitätsstruktur erstellt, die als Workflowprogramm bezeichnet wird. Mithilfe dieser Typen oder einen benutzerdefinierten Host, der umschließt <xref:System.Activities.ActivityInstance>, Workflows ausgeführt werden können, in einem beliebigen Windows-Prozess einschließlich konsolenanwendungen, formularbasierten Anwendungen, Windows-Diensten, [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] Web Sites und Windows Communication Foundation ( WCF)-Dienste.  
  
 ![Workflowkomponenten im Hostprozess](./media/44c79d1d-178b-4487-87ed-3e33015a3842.gif "44c79d1d-178b-4487-87ed-3e33015a3842")  
Workflowkomponenten im Hostprozess  
  
## <a name="interaction-between-workflow-components"></a>Interaktion zwischen Workflowkomponenten  
 Im folgenden Diagramm wird dargestellt, wie Workflowkomponenten miteinander interagieren.  
  
 ![Diagramm, das zeigt, wie Workflowkomponenten interagieren.](./media/overview/workflow-component-interatction.gif)  
  
 Im vorangehenden Diagramm wird die <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode der <xref:System.Activities.WorkflowInvoker>-Klasse verwendet, um mehrere Instanzen eines Workflows aufzurufen. <xref:System.Activities.WorkflowInvoker> für einfache Workflows verwendet wird, die keine Verwaltung vom Host benötigen. Workflows, die Verwaltung durch den Host benötigen (z. B. <xref:System.Activities.Bookmark> Wiederaufnahme) muss ausgeführt werden, mithilfe von <xref:System.Activities.WorkflowApplication.Run%2A> stattdessen. Es ist nicht erforderlich, auf den Abschluss einer Workflowinstanz zu warten, bevor ein weiterer Workflow aufgerufen wird. Die Runtime-Engine unterstützt die Ausführung mehrerer Workflowinstanzen gleichzeitig.  Die aufgerufenen Workflows sind:  
  
-   Eine <xref:System.Activities.Statements.Sequence>-Aktivität, die eine untergeordnete <xref:System.Activities.Statements.WriteLine>-Aktivität enthält. <xref:System.Activities.Variable> der übergeordneten Aktivität wird an <xref:System.Activities.InArgument> der untergeordneten Aktivität gebunden. Weitere Informationen zu Variablen, Argumenten und Bindung finden Sie unter [Variablen und Argumente](variables-and-arguments.md).  
  
-   Eine benutzerdefinierte Aktivität mit dem Namen `ReadLine`. Ein <xref:System.Activities.OutArgument> der `ReadLine`-Aktivität wird an die aufrufende <xref:System.Activities.WorkflowInvoker.Invoke%2A>-Methode zurückgegeben.  
  
-   Eine benutzerdefinierte Aktivität, die von der abstrakten <xref:System.Activities.CodeActivity>-Klasse abgeleitet wird. <xref:System.Activities.CodeActivity> kann auf Laufzeitfunktionen (z. B. Nachverfolgung und Eigenschaften) mit dem <xref:System.Activities.CodeActivityContext> zugreifen, der als Parameter über die <xref:System.Activities.CodeActivity.Execute%2A>-Methode verfügbar ist. Weitere Informationen über diese Laufzeitfunktionen finden Sie unter [nachverfolgung und Ablaufverfolgung für Workflows](workflow-tracking-and-tracing.md) und [Eigenschaften der Workflowausführung](workflow-execution-properties.md).  
  
## <a name="see-also"></a>Siehe auch

- [BizTalk Server 2006 oder WF? Auswählen des richtigen Workflowtools für Ihr Projekt](https://go.microsoft.com/fwlink/?LinkId=154901)
