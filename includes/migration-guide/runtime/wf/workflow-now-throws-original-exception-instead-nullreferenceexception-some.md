---
ms.openlocfilehash: 6e5e90a4cfb862b3bfd74ac5a3715e97a736f598
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802509"
---
### <a name="workflow-now-throws-original-exception-instead-of-nullreferenceexception-in-some-cases"></a><span data-ttu-id="40208-101">Der Workflow löst jetzt anstelle einer NullReferenceException teilweise eine ursprüngliche Ausnahme aus</span><span class="sxs-lookup"><span data-stu-id="40208-101">Workflow now throws original exception instead of NullReferenceException in some cases</span></span>

|   |   |
|---|---|
|<span data-ttu-id="40208-102">Details</span><span class="sxs-lookup"><span data-stu-id="40208-102">Details</span></span>|<span data-ttu-id="40208-103">In .NET Framework 4.6.2 und früheren Versionen löst die System.Activities-Workflowruntime eine <code>null</code> aus, wenn die Execute-Methode einer Workflowaktivität eine Ausnahme mit einem <xref:System.Exception.Message>-Wert für die <xref:System.NullReferenceException?displayProperty=name>-Eigenschaft auslöst, wodurch die ursprüngliche Ausnahme maskiert wird. In .NET Framework 4.7 wird die zuvor maskierte Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="40208-103">In the .NET Framework 4.6.2 and earlier versions, when the Execute method of a workflow activity throws an exception with a <code>null</code> value for the <xref:System.Exception.Message> property, the System.Activities Workflow runtime throws a <xref:System.NullReferenceException?displayProperty=name>, masking the original exception.In the .NET Framework 4.7, the previously masked exception is thrown.</span></span>|
|<span data-ttu-id="40208-104">Vorschlag</span><span class="sxs-lookup"><span data-stu-id="40208-104">Suggestion</span></span>|<span data-ttu-id="40208-105">Wenn Ihr Code von der Verarbeitung von <xref:System.NullReferenceException?displayProperty=name> abhängig ist, ändern Sie diesen, um die Ausnahmen zu erfassen, die Ihre benutzerdefinierten Aktivitäten auslösen könnten.</span><span class="sxs-lookup"><span data-stu-id="40208-105">If your code relies on handling the <xref:System.NullReferenceException?displayProperty=name>, change it to catch the exceptions that could be thrown from your custom activities.</span></span>|
|<span data-ttu-id="40208-106">Bereich</span><span class="sxs-lookup"><span data-stu-id="40208-106">Scope</span></span>|<span data-ttu-id="40208-107">Gering</span><span class="sxs-lookup"><span data-stu-id="40208-107">Minor</span></span>|
|<span data-ttu-id="40208-108">Version</span><span class="sxs-lookup"><span data-stu-id="40208-108">Version</span></span>|<span data-ttu-id="40208-109">4.7</span><span class="sxs-lookup"><span data-stu-id="40208-109">4.7</span></span>|
|<span data-ttu-id="40208-110">Typ</span><span class="sxs-lookup"><span data-stu-id="40208-110">Type</span></span>|<span data-ttu-id="40208-111">Laufzeit</span><span class="sxs-lookup"><span data-stu-id="40208-111">Runtime</span></span>|
|<span data-ttu-id="40208-112">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="40208-112">Affected APIs</span></span>|<ul><li><xref:System.Activities.CodeActivity.Execute(System.Activities.CodeActivityContext)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.AsyncCodeActivity%601.BeginExecute(System.Activities.AsyncCodeActivityContext,System.AsyncCallback,System.Object)?displayProperty=nameWithType></li><li><xref:System.Activities.WorkflowInvoker.Invoke?displayProperty=nameWithType></li></ul>|

