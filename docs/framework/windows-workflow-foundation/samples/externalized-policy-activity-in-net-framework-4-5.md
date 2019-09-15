---
title: Externalisierte Richtlinienaktivität in .NET Framework 4.5
ms.date: 03/30/2017
ms.assetid: 92fd6f92-23a1-4adf-b96a-2754ea93ad3e
ms.openlocfilehash: 7d3c9b2bd9da7e3793479c002094504a4a556aa0
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70989568"
---
# <a name="externalized-policy-activity-in-net-framework-45"></a>Externalisierte Richtlinienaktivität in .NET Framework 4.5

Dieses Beispiel veranschaulicht, wie die ExternalizedPolicy4-Aktivität die [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Ausführung vorhandener Windows Workflow Foundation ( <xref:System.Workflow.Activities.Rules.RuleSet> WF 3,5 [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] )-Objekte in Windows Workflow Foundation (WF 4,5) direkt mithilfe der Regel-Engine zulässt. die in WF 3,5 geliefert wird. Mit dieser Aktivität können Sie alle vorhandenen WF 3.5 <xref:System.Workflow.Activities.Rules.RuleSet>-Elemente öffnen und ausführen. Weitere Informationen zur WF 3,5-Regel-Engine, die im Rahmen Windows Workflow Foundation enthalten ist, finden Sie unter [Einführung in das Windows Workflow Foundation Regel-Engine](https://go.microsoft.com/fwlink/?LinkId=166079). Weitere Informationen zum Migrieren von Regeln [!INCLUDE[wf1](../../../../includes/wf1-md.md)] zu [!INCLUDE[netfx_current_short](../../../../includes/netfx-current-short-md.md)]in finden Sie in der Migrations Anleitung im [Leitfaden](../migration-guidance.md)zur Migration.

## <a name="projects-in-this-sample"></a>Projekte in diesem Beispiel

|Projektname|Beschreibung|Hauptdateien|
|-|-|-|
|ExternalizedPolicy4|Enthält die ExternalizedPolicy4-Aktivität und ihren WF 4.5-Designer.|**ExternalizedPolicy4.cs**: Aktivitäts Definition.<br /><br /> **ExternalizedPolicy4Designer. XAML**: Benutzerdefinierter Designer für die ExternalizedPolicy4-Aktivität. Er verwendet den Regeleditor (<xref:System.Workflow.Activities.Rules.Design.RuleSetDialog>) der WF 3.5-Regel-Engine.|
|ImperativeCodeClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalizedPolicy4-Anwendung mit obligatorischem C#-Code konfiguriert und ausführt (kein Designer verwendet).|**ApplyDiscount.rules**: Datei mit [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Regeldefinitionen.<br /><br /> **Order.cs**: Der Typ, der eine Kundenbestellung darstellt. Regeln werden auf Objekte dieses Typs angewendet.<br /><br /> **Program.cs**: Konfiguriert und führt einen Workflow aus, der über eine Policy4-Aktivität verfügt, um in ApplyDiscount. Rules definierte Regeln auf Instanzen von Order-Objekten anzuwenden.<br /><br /> App. config: Die Konfigurationsdatei mit dem Pfad der Regeldatei.|
|DesignerClientSample|Beispielclientanwendung, die einen Workflow mithilfe einer ExternalPolicy4-Anwendung im [!INCLUDE[wf1](../../../../includes/wf1-md.md)]-Designer konfiguriert und ausführt.|**Sequence1. XAML**: Sequenzieller Workflow, der eine Policy4-Aktivität verwendet, um Regel Auswertungen auszuführen.<br /><br /> **Program.cs**: Führt eine Instanz des in "Sequence1.xaml" definierten Workflows aus.|

## <a name="the-externalizedpolicy4-activity"></a>Die ExternalizedPolicy4-Aktivität

Die ExternalizedPolicy4-Aktivität ist eine <xref:System.Activities.NativeActivity>, mit der die Ausführung von <xref:System.Workflow.Activities.Rules.RuleSet>-Objekten in WF 3.5 innerhalb von WF 4.5-Workflows ermöglicht wird. Das folgende Beispiel ist eine vereinfachte Definition des öffentlichen Objektmodells der Aktivität.

```csharp
public class ExternalizedPolicy4Activity<TResult>: CodeActivity
{
    public string RulesFilePath

    public string RuleSetName

    [RequiredArgument]
    public InArgument<T> TargetObject

    [RequiredArgument]
    public OutArgument<T> ResultObject

    public OutArgument<ValidationErrorCollection> ValidationErrors
}
```

|Eigenschaft|Beschreibung|
|-|-|
|RuleSetFilePath|Pfad zur .NET Framework 3.5 <xref:System.Workflow.Activities.Rules.RuleSet> Datei, die beim Ausführen der Aktivität ausgewertet werden soll.|
|RuleSetName|Name des <xref:System.Workflow.Activities.Rules.RuleSet>, der in der RULES-Datei verwendet werden soll.|
|TargetObject|Das Objekt, für das die <xref:System.Workflow.Activities.Rules.Rule>-Objekte im <xref:System.Workflow.Activities.Rules.RuleSet> ausgewertet werden.|
|ResultObject|Das Objekt, das sich nach der Anwendung der Regeln ergibt. (Die Regeln werden zum Beispiel auf das Input-Argument angewendet, und das Ergebnis wird im Result-Argument gespeichert.)|
|ValidationError|Die Liste der Validierungsfehler, die von der WF 3.5-Regel-Engine beim Überprüfen des <xref:System.Workflow.Activities.Rules.RuleSet> für das Zielobjekt vor der Ausführung zurückgegeben wurde.|

## <a name="externalizedpolicy4-activity-designer"></a>ExternalizedPolicy4-Aktivitätsdesigner

Mit dem ExternalizedPolicy4-Designer können Sie eine Aktivität zur Verwendung eines vorhandenen RuleSet konfigurieren, ohne dass Sie Code schreiben müssen. Geben Sie den Pfad an, in dem sich die RULES-Datei befindet, und legen Sie den zu verwendenden <xref:System.Workflow.Activities.Rules.RuleSet>-Namen fest. Sie können außerdem das <xref:System.Workflow.Activities.Rules.RuleSet> ändern. Nach dem Erstellen der Projektmappe befindet sich dies im Abschnitt Microsoft.Samples.Activities.Rules. Mit dem Designer können Sie eine RULES-Datei und ein <xref:System.Workflow.Activities.Rules.RuleSet> auswählen. Wenn auf die Schaltfläche **Regelsatz bearbeiten** geklickt wird, wird WF <xref:System.Workflow.Activities.Rules.Design.RuleSetDialog> 3,5 angezeigt. Dieses Dialogfeld ist der neu gehostete WF 3.5-Regeleditor. Es wird verwendet, um die von der ExternalizedPolicy4-Aktivität ausgeführten Regeln anzuzeigen und zu bearbeiten.

## <a name="policy4-and-externalpolicy4"></a>Policy4 und ExternalPolicy4

Mit der Policy-Aktivität können Sie eine .NET Framework 3,5-RuleSet in einem WF 4,5-Workflow erstellen und ausführen. Das <xref:System.Workflow.Activities.Rules.RuleSet> wird inline in der XAML-Definition der Policy4-Aktivität serialisiert. Im ExternalizedPolicy4-Beispiel wird gezeigt, wie ein vorhandenes externes <xref:System.Workflow.Activities.Rules.RuleSet> (enthalten in einer RULES-Datei) verwendet wird.

## <a name="use-this-sample"></a>Verwenden Sie dieses Beispiel

Zum Ausführen dieses Beispiels ist keine spezielle Einrichtung erforderlich. Öffnen Sie die Projekt Mappe in Visual Studio, und drücken Sie dann **F5** , um die Anwendung auszuführen.

Dieses Beispiel enthält zwei Client Anwendungen: ImperativeCodeClientSample und DesignerClientSample. Der ImperativeCodeClientSample-Client zeigt, wie die ExternalizedPolicy4-Aktivität mit obligatorischem C#-Code konfiguriert und ausgeführt wird. Das DesignerClientSample zeigt, wie die ExternalizedPolicy4-Aktivität mithilfe des Designers konfiguriert und ausgeführt wird.

### <a name="run-the-imperativecodeclientsample-application"></a>Ausführen der ImperativeCodeClientSample-Anwendung

1. Öffnen Sie die Projektmappendatei *Policy4sample. sln* mithilfe von Visual Studio.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **ImperativeCodeClientSample** , und wählen Sie dann **als Startprojekt festlegen**aus.

3. Drücken Sie **STRG**+**F5**, um das Projekt auszuführen.

### <a name="run-the-designerclientsample-application"></a>Ausführen der Anwendung DesignerClientSample

1. Öffnen Sie die Projektmappendatei *Policy4sample. sln* mithilfe von Visual Studio.

2. Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt **DesignerClientSample** , und wählen Sie dann **als Startprojekt festlegen**aus.

3. Drücken Sie **STRG**+**UMSCHALT**+**B** , um das Projekt zu kompilieren.

4. Drücken Sie **STRG**+**F5** , um das Projekt auszuführen.

> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ) und Beispiele herunterzuladen.
>
> Dieses Beispiel befindet sich im folgenden Verzeichnis:
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Rules-ExternalizedPolicy4`
