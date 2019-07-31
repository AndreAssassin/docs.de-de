---
title: Serialisieren von Workflows und Aktivitäten in und aus XAML
ms.date: 03/30/2017
ms.assetid: 37685b32-24e3-4d72-88d8-45d5fcc49ec2
ms.openlocfilehash: c18afa7232adabc4f1c4e17fde993064b9189e39
ms.sourcegitcommit: 3eeea78f52ca771087a6736c23f74600cc662658
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2019
ms.locfileid: "68671893"
---
# <a name="serialize-workflows-and-activities-to-and-from-xaml"></a><span data-ttu-id="650e9-102">Serialisieren von Workflows und Aktivitäten in und aus XAML</span><span class="sxs-lookup"><span data-stu-id="650e9-102">Serialize Workflows and Activities to and from XAML</span></span>

<span data-ttu-id="650e9-103">Zusätzlich zur Kompilierung in Typen, die in Assemblys enthalten sind, können Workflowdefinitionen in XAML serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-103">In addition to being compiled into types that are contained in assemblies, workflow definitions can also be serialized to XAML.</span></span> <span data-ttu-id="650e9-104">Diese serialisierten Definitionen können zur Bearbeitung oder Überprüfung erneut geladen werden, zur Kompilierung in ein Buildsystem übergeben werden oder geladen und aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-104">These serialized definitions can be reloaded for editing or inspection, passed to a build system for compilation, or loaded and invoked.</span></span> <span data-ttu-id="650e9-105">Dieses Thema bietet einen Überblick über das Serialisieren von Workflowdefinitionen und das Arbeiten mit XAML-Workflowdefinitionen.</span><span class="sxs-lookup"><span data-stu-id="650e9-105">This topic provides an overview of serializing workflow definitions and working with XAML workflow definitions.</span></span>

## <a name="work-with-xaml-workflow-definitions"></a><span data-ttu-id="650e9-106">Arbeiten mit XAML-Workflow Definitionen</span><span class="sxs-lookup"><span data-stu-id="650e9-106">Work with XAML Workflow definitions</span></span>

<span data-ttu-id="650e9-107">Zum Erstellen einer Workflowdefinition zur Serialisierung wird die <xref:System.Activities.ActivityBuilder>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="650e9-107">To create a workflow definition for serialization, the <xref:System.Activities.ActivityBuilder> class is used.</span></span> <span data-ttu-id="650e9-108">Die Erstellung einer <xref:System.Activities.ActivityBuilder>-Klasse funktioniert ähnlich wie die Erstellung einer <xref:System.Activities.DynamicActivity>.</span><span class="sxs-lookup"><span data-stu-id="650e9-108">Creating an <xref:System.Activities.ActivityBuilder> is very similar to creating a <xref:System.Activities.DynamicActivity>.</span></span> <span data-ttu-id="650e9-109">Alle gewünschte Argumente werden angegeben, und die Aktivitäten, aus denen das Verhalten besteht, werden konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="650e9-109">Any desired arguments are specified, and the activities that constitute the behavior are configured.</span></span> <span data-ttu-id="650e9-110">Im folgenden Beispiel wird eine `Add`-Aktivität erstellt, die zwei Eingabeargumente verwendet, diese zusammenfügt und das Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="650e9-110">In the following example, an `Add` activity is created that takes two input arguments, adds them together, and returns the result.</span></span> <span data-ttu-id="650e9-111">Da diese Aktivität ein Ergebnis zurückgibt, wird die generische <xref:System.Activities.ActivityBuilder%601>-Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="650e9-111">Because this activity returns a result, the generic <xref:System.Activities.ActivityBuilder%601> class is used.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#41](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#41)]

<span data-ttu-id="650e9-112">Die einzelnen <xref:System.Activities.DynamicActivityProperty>-Instanzen stellen die Eingabeargumente für den Workflow dar, und das <xref:System.Activities.ActivityBuilder.Implementation%2A>-Element enthält die Aktivitäten, aus denen die Logik des Workflows besteht.</span><span class="sxs-lookup"><span data-stu-id="650e9-112">Each of the <xref:System.Activities.DynamicActivityProperty> instances represents one of the input arguments to the workflow, and the <xref:System.Activities.ActivityBuilder.Implementation%2A> contains the activities that make up the logic of the workflow.</span></span> <span data-ttu-id="650e9-113">Beachten Sie, dass die Ausdrücke mit R-Wert in diesem Beispiel Visual Basic-Ausdrücke sind.</span><span class="sxs-lookup"><span data-stu-id="650e9-113">Note that the r-value expressions in this example are Visual Basic expressions.</span></span> <span data-ttu-id="650e9-114">Lambda-Ausdrücke sind nicht in XAML serialisierbar, es sei denn, <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="650e9-114">Lambda expressions are not serializable to XAML unless <xref:System.Activities.Expressions.ExpressionServices.Convert%2A> is used.</span></span> <span data-ttu-id="650e9-115">Wenn die serialisierten Workflows im Workflow-Designer geöffnet oder bearbeitet werden sollen, sollten Visual Basic Ausdrücke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-115">If the serialized workflows are intended to be opened or edited in the workflow designer, then Visual Basic expressions should be used.</span></span> <span data-ttu-id="650e9-116">Weitere Informationen finden Sie unter [Erstellen von Workflows, Aktivitäten und Ausdrücken mit imperativem Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span><span class="sxs-lookup"><span data-stu-id="650e9-116">For more information, see [Authoring Workflows, Activities, and Expressions Using Imperative Code](authoring-workflows-activities-and-expressions-using-imperative-code.md).</span></span>

<span data-ttu-id="650e9-117">Um die von der <xref:System.Activities.ActivityBuilder>-Instanz dargestellte Workflowdefinition in XAML zu serialisieren, verwenden Sie <xref:System.Activities.XamlIntegration.ActivityXamlServices>, um <xref:System.Xaml.XamlWriter> zu erstellen, und anschließend <xref:System.Xaml.XamlServices>, um die Workflowdefinition mithilfe von <xref:System.Xaml.XamlWriter> zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="650e9-117">To serialize the workflow definition represented by the <xref:System.Activities.ActivityBuilder> instance to XAML, use <xref:System.Activities.XamlIntegration.ActivityXamlServices> to create a <xref:System.Xaml.XamlWriter>, and then use <xref:System.Xaml.XamlServices> to serialize the workflow definition by using the <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="650e9-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices>verfügt über Methoden zum <xref:System.Activities.ActivityBuilder> Zuordnen von-Instanzen zu und aus XAML und zum Laden von XAML <xref:System.Activities.DynamicActivity> -Workflows und zum Zurückgeben einer, die aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="650e9-118"><xref:System.Activities.XamlIntegration.ActivityXamlServices> has methods to map <xref:System.Activities.ActivityBuilder> instances to and from XAML and to load XAML workflows and return a <xref:System.Activities.DynamicActivity> that can be invoked.</span></span> <span data-ttu-id="650e9-119">Im folgenden Beispiel wird die <xref:System.Activities.ActivityBuilder> -Instanz aus dem vorherigen Beispiel in eine Zeichenfolge serialisiert und in einer Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="650e9-119">In the following example, the <xref:System.Activities.ActivityBuilder> instance from the previous example is serialized to a string and saved to a file.</span></span>

```csharp
// Serialize the workflow to XAML and store it in a string.
StringBuilder sb = new StringBuilder();
StringWriter tw = new StringWriter(sb);
XamlWriter xw = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(tw, new XamlSchemaContext()));
XamlServices.Save(xw, ab);
string serializedAB = sb.ToString();

// Display the XAML to the console.
Console.WriteLine(serializedAB);

// Serialize the workflow to XAML and save it to a file.
StreamWriter sw = File.CreateText(@"C:\Workflows\add.xaml");
XamlWriter xw2 = ActivityXamlServices.CreateBuilderWriter(new XamlXmlWriter(sw, new XamlSchemaContext()));
XamlServices.Save(xw2, ab);
sw.Close();
```

<span data-ttu-id="650e9-120">Im folgenden Beispiel wird der serialisierte Workflow dargestellt.</span><span class="sxs-lookup"><span data-stu-id="650e9-120">The following example represents the serialized workflow.</span></span>

```xaml
<Activity
  x:TypeArguments="x:Int32"
  x:Class="Add"
  xmlns="http://schemas.microsoft.com/netfx/2009/xaml/activities"
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml">
  <x:Members>
    <x:Property Name="Operand1" Type="InArgument(x:Int32)" />
    <x:Property Name="Operand2" Type="InArgument(x:Int32)" />
  </x:Members>
  <Sequence>
    <WriteLine Text="[Operand1.ToString() + " + " + Operand2.ToString()]" />
    <Assign x:TypeArguments="x:Int32" Value="[Operand1 + Operand2]">
      <Assign.To>
        <OutArgument x:TypeArguments="x:Int32">
          <ArgumentReference x:TypeArguments="x:Int32" ArgumentName="Result" />
          </OutArgument>
      </Assign.To>
    </Assign>
  </Sequence>
</Activity>
```

<span data-ttu-id="650e9-121">Um einen serialisierten Workflow zu laden, verwenden <xref:System.Activities.XamlIntegration.ActivityXamlServices> Sie die <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> -Methode.</span><span class="sxs-lookup"><span data-stu-id="650e9-121">To load a serialized workflow, use the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A> method.</span></span> <span data-ttu-id="650e9-122">Diese verwendet die serialisierte Workflowdefinition und gibt eine <xref:System.Activities.DynamicActivity> zurück, die die Workflowdefinition darstellt.</span><span class="sxs-lookup"><span data-stu-id="650e9-122">This takes the serialized workflow definition and returns a <xref:System.Activities.DynamicActivity> that represents the workflow definition.</span></span> <span data-ttu-id="650e9-123">Beachten Sie, dass die XAML-Daten erst deserialisiert werden, wenn <xref:System.Activities.Activity.CacheMetadata%2A> während des Validierungsprozesses für den Text der <xref:System.Activities.DynamicActivity> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="650e9-123">Note that the XAML is not deserialized until <xref:System.Activities.Activity.CacheMetadata%2A> is called on the body of the <xref:System.Activities.DynamicActivity> during the validation process.</span></span> <span data-ttu-id="650e9-124">Wenn die Validierung nicht explizit aufgerufen wird, wird Sie ausgeführt, wenn der Workflow aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="650e9-124">If validation is not explicitly called, then it is performed when the workflow is invoked.</span></span> <span data-ttu-id="650e9-125">Wenn die XAML-Workflowdefinition ungültig ist, wird eine <xref:System.ArgumentException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="650e9-125">If the XAML workflow definition is invalid, then an <xref:System.ArgumentException> exception is thrown.</span></span> <span data-ttu-id="650e9-126">Alle von <xref:System.Activities.Activity.CacheMetadata%2A> ausgelösten Ausnahmen werden im Aufruf von <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> nicht verarbeitet und müssen vom Aufrufer behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-126">Any exceptions thrown from <xref:System.Activities.Activity.CacheMetadata%2A> escape from the call to <xref:System.Activities.Validation.ActivityValidationServices.Validate%2A> and must be handled by the caller.</span></span> <span data-ttu-id="650e9-127">Im folgenden Beispiel wird der serialisierte Workflow aus dem vorherigen Beispiel geladen und von <xref:System.Activities.WorkflowInvoker> aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="650e9-127">In the following example, the serialized workflow from the previous example is loaded and invoked by using <xref:System.Activities.WorkflowInvoker>.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#43](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#43)]

<span data-ttu-id="650e9-128">Wenn dieser Workflow aufgerufen wird, wird die folgende Ausgabe in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="650e9-128">When this workflow is invoked, the following output is displayed to the console.</span></span>

<span data-ttu-id="650e9-129">**25 + 15**</span><span class="sxs-lookup"><span data-stu-id="650e9-129">**25 + 15**</span></span>\
<span data-ttu-id="650e9-130">**40**</span><span class="sxs-lookup"><span data-stu-id="650e9-130">**40**</span></span>

> [!NOTE]
> <span data-ttu-id="650e9-131">Weitere Informationen zum Aufrufen von Workflows mit Eingabe-und Ausgabe Argumenten finden [Sie unter Verwenden von WorkflowInvoker und WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) und <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span><span class="sxs-lookup"><span data-stu-id="650e9-131">For more information about invoking workflows with input and output arguments, see [Using WorkflowInvoker and WorkflowApplication](using-workflowinvoker-and-workflowapplication.md) and <xref:System.Activities.WorkflowInvoker.Invoke%2A>.</span></span>

<span data-ttu-id="650e9-132">Wenn der serialisierte Workflow Ausdrücke C# enthält, muss eine <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> -Instanz, <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> deren-Eigenschaft `true` auf festgelegt ist, als Parameter <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>an übergeben werden <xref:System.NotSupportedException> , andernfalls wird eine mit einer ähnlichen Meldung ausgelöst. zu den folgenden Aktionen: **Der Ausdrucks Aktivitätstyp ' csharpvalue ' 1 ' erfordert die Kompilierung, um ausgeführt zu werden.  Stellen Sie sicher, dass der Workflow kompiliert wurde.**</span><span class="sxs-lookup"><span data-stu-id="650e9-132">If the serialized workflow contains C# expressions, then an <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings> instance with its <xref:System.Activities.XamlIntegration.ActivityXamlServicesSettings.CompileExpressions%2A> property set to `true` must be passed as a parameter to <xref:System.Activities.XamlIntegration.ActivityXamlServices.Load%2A?displayProperty=nameWithType>, otherwise a <xref:System.NotSupportedException> will be thrown with a message similar to the following: **Expression Activity type 'CSharpValue\`1' requires compilation in order to run.  Please ensure that the workflow has been compiled.**</span></span>

```csharp
ActivityXamlServicesSettings settings = new ActivityXamlServicesSettings
{
    CompileExpressions = true
};

DynamicActivity<int> wf = ActivityXamlServices.Load(new StringReader(serializedAB), settings) as DynamicActivity<int>;
```

<span data-ttu-id="650e9-133">Weitere Informationen finden [ C# ](csharp-expressions.md)Sie unter Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="650e9-133">For more information, see [C# Expressions](csharp-expressions.md).</span></span>

<span data-ttu-id="650e9-134">Eine serialisierte Workflow Definition kann auch mit der <xref:System.Activities.ActivityBuilder> <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> -Methode in eine-Instanz geladen werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-134">A serialized workflow definition can also be loaded into an <xref:System.Activities.ActivityBuilder> instance by using the <xref:System.Activities.XamlIntegration.ActivityXamlServices> <xref:System.Activities.XamlIntegration.ActivityXamlServices.CreateBuilderReader%2A> method.</span></span> <span data-ttu-id="650e9-135">Nachdem ein serialisierter Workflow in eine <xref:System.Activities.ActivityBuilder> -Instanz geladen wurde, kann er überprüft und geändert werden.</span><span class="sxs-lookup"><span data-stu-id="650e9-135">After a serialized workflow is loaded into an <xref:System.Activities.ActivityBuilder> instance, it can be inspected and modified.</span></span> <span data-ttu-id="650e9-136">Dies ist besonders nützlich für Autoren benutzerdefinierter Workflows, da es eine Methode zum Speichern und zum erneuten Laden von Workflowdefinitionen während des Entwurfsprozesses bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="650e9-136">This is useful for custom workflow designer authors and provides a mechanism for saving and reloading workflow definitions during the design process.</span></span> <span data-ttu-id="650e9-137">Im folgenden Beispiel wird die serialisierte Workflowdefinition aus dem vorherigen Beispiel geladen, und ihre Eigenschaften werden überprüft.</span><span class="sxs-lookup"><span data-stu-id="650e9-137">In the following example, the serialized workflow definition from the previous example is loaded and its properties are inspected.</span></span>

[!code-csharp[CFX_WorkflowApplicationExample#44](~/samples/snippets/csharp/VS_Snippets_CFX/cfx_workflowapplicationexample/cs/program.cs#44)]
