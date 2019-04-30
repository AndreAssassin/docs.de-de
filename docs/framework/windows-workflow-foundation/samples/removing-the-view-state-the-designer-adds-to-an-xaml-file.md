---
title: Entfernen der Designer ansichtzustands in einer XAML-Datei – WF
ms.date: 03/30/2017
ms.assetid: a801ce22-8699-483c-a392-7bb3834aae4f
ms.openlocfilehash: 71a2aadeefd53b391f4589ed9dc32d9cd6e3183a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004938"
---
# <a name="removing-the-view-state-the-designer-adds-to-an-xaml-file"></a><span data-ttu-id="c66f3-102">Entfernen des dem Designer hinzugefügt, dass ein XAML-Datei</span><span class="sxs-lookup"><span data-stu-id="c66f3-102">Removing the view state the designer adds to an XAML file</span></span>

<span data-ttu-id="c66f3-103">Dieses Beispiel veranschaulicht, wie eine Klasse erstellt wird, die von <xref:System.Xaml.XamlWriter> abgeleitet wird, und entfernt den Ansichtszustand aus einer XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="c66f3-103">This sample demonstrates how to create a class that derives from <xref:System.Xaml.XamlWriter> and removes view state from a XAML file.</span></span> [!INCLUDE[wfd1](../../../../includes/wfd1-md.md)] <span data-ttu-id="c66f3-104">schreibt Informationen in das XAML-Dokument, das als Ansichtszustand bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="c66f3-104">writes information into the XAML document, which is known as view state.</span></span> <span data-ttu-id="c66f3-105">Der Ansichtszustand bezieht sich auf die Informationen, die während der Entwurfszeit erforderlich sind, z. B. die Layoutpositionierung, jedoch nicht zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="c66f3-105">View state refers to the information that is required at design time, such as layout positioning, that is not required at runtime.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="c66f3-106">fügt diese Informationen in das XAML-Dokument ein, während es bearbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="c66f3-106">inserts this information into the XAML document as it is edited.</span></span> [!INCLUDE[wfd2](../../../../includes/wfd2-md.md)] <span data-ttu-id="c66f3-107">schreibt den Ansichtszustand in der XAML-Datei mit dem `mc:Ignorable`-Attribut. Daher werden diese Informationen nicht geladen, wenn die Laufzeit die XAML-Datei lädt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-107">writes the view state into the XAML file with the `mc:Ignorable` attribute, so this information is not loaded when the runtime loads the XAML file.</span></span> <span data-ttu-id="c66f3-108">In diesem Beispiel wird veranschaulicht, wie eine Klasse erstellt wird, mit der diese Ansichtszustandsinformationen bei der Verarbeitung von XAML-Knoten entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="c66f3-108">This sample demonstrates how to create a class that removes that view state information while processing XAML nodes.</span></span>

## <a name="discussion"></a><span data-ttu-id="c66f3-109">Diskussion</span><span class="sxs-lookup"><span data-stu-id="c66f3-109">Discussion</span></span>

<span data-ttu-id="c66f3-110">In diesem Beispiel wird veranschaulicht, wie ein benutzerdefinierter Writer erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c66f3-110">This sample demonstrates how to create a custom writer.</span></span>

<span data-ttu-id="c66f3-111">Zum Erstellen eines benutzerdefinierten XAML-Writers müssen Sie eine Klasse erstellen, die von <xref:System.Xaml.XamlWriter> erbt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-111">To build a custom XAML writer, create a class that inherits from <xref:System.Xaml.XamlWriter>.</span></span> <span data-ttu-id="c66f3-112">Wie XAML-Writer häufig geschachtelt werden, ist es üblich, zu verfolgen einen "inneren" XAML-Writer.</span><span class="sxs-lookup"><span data-stu-id="c66f3-112">As XAML writers are often nested, it is typical to keep track of an "inner" XAML writer.</span></span> <span data-ttu-id="c66f3-113">Diese "inneren" Writer können als Verweis auf den verbleibenden Stapel XAML-Writer, sodass Sie über mehrere Einstiegspunkte verfügen und die Verarbeitung der restlichen Stapels delegieren betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="c66f3-113">These "inner’ writers can be thought of as the reference to the remaining stack of XAML writers, allowing you to have multiple entry points to do work and then delegate processing to the remainder of the stack.</span></span>

<span data-ttu-id="c66f3-114">In diesem Beispiel gibt es einige relevante Elemente.</span><span class="sxs-lookup"><span data-stu-id="c66f3-114">In this sample, there are a few items of interest.</span></span> <span data-ttu-id="c66f3-115">Eines ist die Überprüfung, ob das geschriebene Element aus einem Designernamespace stammt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-115">One is the check to see whether the item being written is from a designer namespace.</span></span> <span data-ttu-id="c66f3-116">Beachten Sie, dass dies die Verwendung anderer Typen des Designernamespace in einem Workflow nicht mehr ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c66f3-116">Note that this also strips out the use of other types from the designer namespace in a workflow.</span></span>

```csharp
static Boolean IsDesignerAttachedProperty(XamlMember xamlMember)
{
    return xamlMember.IsAttachable &&
        xamlMember.PreferredXamlNamespace.Equals(c_sapNamespaceURI, StringComparison.OrdinalIgnoreCase);
}

const String c_sapNamespaceURI = "http://schemas.microsoft.com/netfx/2009/xaml/activities/presentation";

// The next item of interest is the constructor, where the utilization of the inner XAML writer is seen.
public ViewStateCleaningWriter(XamlWriter innerWriter)
{
    this.InnerWriter = innerWriter;
    this.MemberStack = new Stack<XamlMember>();
}

XamlWriter InnerWriter {get; set; }
Stack<XamlMember> MemberStack {get; set; }
```

<span data-ttu-id="c66f3-117">Hierdurch wird auch ein Stapel von XAML-Membern erstellt, die beim Durchlaufen des Knotenstreams verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c66f3-117">This also creates a stack of XAML members that are used while traversing the node stream.</span></span> <span data-ttu-id="c66f3-118">Die verbleibende Arbeit dieses Beispiels ist zum größten Teil in der `WriteStartMember`-Methode enthalten.</span><span class="sxs-lookup"><span data-stu-id="c66f3-118">The remaining work of this sample is largely contained in the `WriteStartMember` method.</span></span>

```csharp
public override void WriteStartMember(XamlMember xamlMember)
{
    MemberStack.Push(xamlMember);

    if (IsDesignerAttachedProperty(xamlMember))
    {
        m_attachedPropertyDepth++;
    }

    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteStartMember(xamlMember);
}
```

<span data-ttu-id="c66f3-119">Nachfolgende Methoden können überprüfen, ob sie immer noch in einem Ansichtszustandscontainer enthalten sind. Wenn dies der Fall ist, können sie zurückkehren und den Knoten nicht im Writerstapel weiter übergeben.</span><span class="sxs-lookup"><span data-stu-id="c66f3-119">Subsequent methods then check to see whether they are still contained in a view state container, and if so, return, and do not pass the node down the writer stack.</span></span>

```csharp
public override void WriteValue(Object value)
{
    if (m_attachedPropertyDepth > 0)
    {
        return;
    }

    InnerWriter.WriteValue(value);
}
```

<span data-ttu-id="c66f3-120">Um einen benutzerdefinierten XAML-Writer verwenden zu können, müssen Sie ihn in einem Stapel XAML-Writer verketten.</span><span class="sxs-lookup"><span data-stu-id="c66f3-120">To use a custom XAML writer, you must chain it together in a stack of XAML writers.</span></span> <span data-ttu-id="c66f3-121">Der folgende Code zeigt diese Verwendung.</span><span class="sxs-lookup"><span data-stu-id="c66f3-121">The following code shows how this can be used.</span></span>

```csharp
XmlWriterSettings writerSettings = new XmlWriterSettings {  Indent = true };
XmlWriter xmlWriter = XmlWriter.Create(File.OpenWrite(args[1]), writerSettings);
XamlXmlWriter xamlWriter = new XamlXmlWriter(xmlWriter, new XamlSchemaContext());
XamlServices.Save(new ViewStateCleaningWriter(ActivityXamlServices.CreateBuilderWriter(xamlWriter)), ab);
```

## <a name="to-use-this-sample"></a><span data-ttu-id="c66f3-122">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="c66f3-122">To use this sample</span></span>

1. <span data-ttu-id="c66f3-123">Öffnen Sie mit Visual Studio 2010 die ViewStateCleaningWriter.sln-Projektmappendatei.</span><span class="sxs-lookup"><span data-stu-id="c66f3-123">Using Visual Studio 2010, open the ViewStateCleaningWriter.sln solution file.</span></span>

2. <span data-ttu-id="c66f3-124">Öffnen Sie eine Eingabeaufforderung, und navigieren Sie zu dem Verzeichnis, in dem ViewStageCleaningWriter.exe erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c66f3-124">Open a command prompt and navigate to the directory where the ViewStageCleaningWriter.exe is built.</span></span>

3. <span data-ttu-id="c66f3-125">Führen Sie ViewStateCleaningWriter.exe für die Datei Workflow1.xaml aus.</span><span class="sxs-lookup"><span data-stu-id="c66f3-125">Run ViewStateCleaningWriter.exe on the Workflow1.xaml file.</span></span>

   <span data-ttu-id="c66f3-126">Die Syntax für die ausführbare Datei ist im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-126">The syntax for the executable is shown in the following example.</span></span>

   ```console
   ViewStateCleaningWriter.exe [input file] [output file]
   ```

   <span data-ttu-id="c66f3-127">Hierdurch erfolgt die Ausgabe einer XAML-Datei, die \[Ausgabedatei], der alle Ansichtszustandsinformationen entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="c66f3-127">This outputs a XAML file to \[outfile], which has all its view state information removed.</span></span>

> [!NOTE]
> <span data-ttu-id="c66f3-128">Für einen <xref:System.Activities.Statements.Sequence>-Workflow wird eine Reihe von Virtualisierungshinweisen entfernt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-128">For a <xref:System.Activities.Statements.Sequence> workflow, a number of virtualization hints are removed.</span></span> <span data-ttu-id="c66f3-129">Dies veranlasst den Designer, das Layout beim nächsten Laden neu zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="c66f3-129">This causes the designer to recalculate layout the next time it is loaded.</span></span> <span data-ttu-id="c66f3-130">Wenn Sie dieses Beispiel für ein <xref:System.Activities.Statements.Flowchart> verwenden, werden alle Positionierungs- und Zeilenroutinginformationen entfernt. Bei nachfolgendem Laden in den Designer werden alle Aktivitäten auf der linken Seite des Bildschirms gestapelt.</span><span class="sxs-lookup"><span data-stu-id="c66f3-130">When you use this sample for a <xref:System.Activities.Statements.Flowchart>, all positioning and line routing information are removed and on subsequent loading into the designer, all activities are stacked on the left side of the screen.</span></span>

## <a name="to-create-a-sample-xaml-file-for-use-with-this-sample"></a><span data-ttu-id="c66f3-131">So erstellen Sie eine Beispiel-XAML-Datei zur Verwendung mit diesem Beispiel</span><span class="sxs-lookup"><span data-stu-id="c66f3-131">To create a sample XAML file for use with this sample</span></span>

1. <span data-ttu-id="c66f3-132">Öffnen Sie Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="c66f3-132">Open Visual Studio 2010.</span></span>

2. <span data-ttu-id="c66f3-133">So erstellen Sie eine neue Workflowkonsolenanwendung.</span><span class="sxs-lookup"><span data-stu-id="c66f3-133">Create a new Workflow Console Application.</span></span>

3. <span data-ttu-id="c66f3-134">Legen Sie einige Aktivitäten in der Entwurfsfläche ab.</span><span class="sxs-lookup"><span data-stu-id="c66f3-134">Drag and drop a few activities onto the canvas</span></span>

4. <span data-ttu-id="c66f3-135">Speichern Sie die Workflow-XAML-Datei.</span><span class="sxs-lookup"><span data-stu-id="c66f3-135">Save the workflow XAML file.</span></span>

5. <span data-ttu-id="c66f3-136">Überprüfen Sie die XAML-Datei auf die Eigenschaften, die dem Ansichtszustand zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="c66f3-136">Inspect the XAML file to see the view state attached properties.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c66f3-137">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c66f3-137">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c66f3-138">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c66f3-138">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="c66f3-139">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="c66f3-139">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c66f3-140">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c66f3-140">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\ViewStateCleaningWriter`