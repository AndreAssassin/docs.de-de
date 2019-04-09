---
title: Benutzerdefinierte zusammengesetzte Designer – Workflowelementpräsentation
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 70055c4b-1173-47a3-be80-b5bce6f59e9a
ms.openlocfilehash: f4db3325081a820a37a8791849d2ad9697d15151
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118104"
---
# <a name="custom-composite-designers---workflow-items-presenter"></a><span data-ttu-id="9a95e-102">Benutzerdefinierte zusammengesetzte Designer – Workflowelementpräsentation</span><span class="sxs-lookup"><span data-stu-id="9a95e-102">Custom Composite Designers - Workflow Items Presenter</span></span>
<span data-ttu-id="9a95e-103"><xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> ist ein Haupttyp im WF-Designer-Programmiermodell, der die Bearbeitung einer Auflistung enthaltener Elemente zulässt.</span><span class="sxs-lookup"><span data-stu-id="9a95e-103">The <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType> is a key type in the WF designer programming model that allows for the editing of a collection of contained elements.</span></span> <span data-ttu-id="9a95e-104">In dem Beispiel wird veranschaulicht, wie ein Aktivitätsdesigner erstellt wird, der eine solche bearbeitbare Auflistung aufweist.</span><span class="sxs-lookup"><span data-stu-id="9a95e-104">This sample shows how to build an activity designer that surfaces such an editable collection.</span></span>

 <span data-ttu-id="9a95e-105">Dieses Beispiel veranschaulicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a95e-105">This sample demonstrates:</span></span>

-   <span data-ttu-id="9a95e-106">Erstellen eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a95e-106">Creating a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span>

-   <span data-ttu-id="9a95e-107">Erstellen eines Aktivitätsdesigners mit einer "reduzierten" und "erweiterten" Ansicht an.</span><span class="sxs-lookup"><span data-stu-id="9a95e-107">Creating an activity designer with a "collapsed" and "expanded" view.</span></span>

-   <span data-ttu-id="9a95e-108">Überschreiben eines standardmäßigen Designers in einer neu gehosteten Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9a95e-108">Overriding a default designer in a rehosted application.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="9a95e-109">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="9a95e-109">To set up, build, and run the sample</span></span>

1.  <span data-ttu-id="9a95e-110">Öffnen der **UsingWorkflowItemsPresenter.sln** beispiellösung für c# oder VB in Visual Studio 2010.</span><span class="sxs-lookup"><span data-stu-id="9a95e-110">Open the **UsingWorkflowItemsPresenter.sln** sample solution for C# or for VB in Visual Studio 2010.</span></span>

2.  <span data-ttu-id="9a95e-111">Erstellen Sie die Projektmappe, und führen Sie sie aus.</span><span class="sxs-lookup"><span data-stu-id="9a95e-111">Build and run the solution.</span></span> <span data-ttu-id="9a95e-112">Eine neu gehostete Workflow-Designer-Anwendung sollte geöffnet werden, und Sie können Aktivitäten auf den Zeichenbereich ziehen.</span><span class="sxs-lookup"><span data-stu-id="9a95e-112">A rehosted workflow designer application should open, and you can drag activities onto the canvas.</span></span>

## <a name="sample-highlights"></a><span data-ttu-id="9a95e-113">Das Wichtigste zum Beispiel</span><span class="sxs-lookup"><span data-stu-id="9a95e-113">Sample Highlights</span></span>
 <span data-ttu-id="9a95e-114">Der Code für dieses Beispiel zeigt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="9a95e-114">The code for this sample shows the following:</span></span>

-   <span data-ttu-id="9a95e-115">Die Aktivität einem Designer erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="9a95e-115">The activity a designer is built for:</span></span>  `Parallel`

-   <span data-ttu-id="9a95e-116">Die Erstellung eines benutzerdefinierten Aktivitätsdesigners mit einem <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9a95e-116">The creation of a custom activity designer with a <xref:System.Activities.Presentation.WorkflowItemsPresenter?displayProperty=nameWithType>.</span></span> <span data-ttu-id="9a95e-117">Einige wichtige Punkte:</span><span class="sxs-lookup"><span data-stu-id="9a95e-117">A few things to point out:</span></span>

    -   <span data-ttu-id="9a95e-118">Beachten Sie die Verwendung der WPF-Datenbindung, um eine Bindung an `ModelItem.Branches` auszuführen.</span><span class="sxs-lookup"><span data-stu-id="9a95e-118">Note the use of WPF data binding to bind to `ModelItem.Branches`.</span></span> `ModelItem` <span data-ttu-id="9a95e-119">ist die Eigenschaft im `WorkflowElementDesigner` , verweist auf die zugrunde liegende Objekt, das der Designer, in diesem Fall verwendet wird unsere `Parallel`.</span><span class="sxs-lookup"><span data-stu-id="9a95e-119">is the property on `WorkflowElementDesigner` that refers to the underlying object the designer is being used for, in this case, our `Parallel`.</span></span>

    -   <span data-ttu-id="9a95e-120"><xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> kann verwendet werden, um ein visuelle Trennung festzulegen, die zwischen den einzelnen Elementen in der Auflistung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9a95e-120">The <xref:System.Activities.Presentation.WorkflowItemsPresenter.SpacerTemplate?displayProperty=nameWithType> can be used to put a visual to display between the individual items in the collection.</span></span>

    -   <xref:System.Activities.Presentation.WorkflowItemsPresenter.ItemsPanel?displayProperty=nameWithType> <span data-ttu-id="9a95e-121">ist eine Vorlage, die bereitgestellt werden kann, um das Layout der Elemente in der Auflistung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="9a95e-121">is a template that can be provided to determine the layout of the items in the collection.</span></span> <span data-ttu-id="9a95e-122">In diesem Fall wird ein horizontaler Stapelbereich verwendet.</span><span class="sxs-lookup"><span data-stu-id="9a95e-122">In this case, a horizontal stack panel is used.</span></span>

 <span data-ttu-id="9a95e-123">Dies wird im folgenden Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="9a95e-123">This following example code shows this.</span></span>

```xaml
<sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                              Items="{Binding Path=ModelItem.Branches}">
    <sad:WorkflowItemsPresenter.SpacerTemplate>
      <DataTemplate>
        <Ellipse Width="10" Height="10" Fill="Black"/>
      </DataTemplate>
    </sad:WorkflowItemsPresenter.SpacerTemplate>
    <sad:WorkflowItemsPresenter.ItemsPanel>
      <ItemsPanelTemplate>
        <StackPanel Orientation="Horizontal"/>
      </ItemsPanelTemplate>
    </sad:WorkflowItemsPresenter.ItemsPanel>
  </sad:WorkflowItemsPresenter>
```

-   <span data-ttu-id="9a95e-124">Führen Sie eine Zuordnung von `DesignerAttribute` zum `Parallel`-Typ aus, und geben Sie dann die gemeldeten Attribute aus.</span><span class="sxs-lookup"><span data-stu-id="9a95e-124">Perform an association of the `DesignerAttribute` to the `Parallel` type and then output the attributes reported.</span></span>

    -   <span data-ttu-id="9a95e-125">Registrieren Sie zuerst alle standardmäßigen Designer.</span><span class="sxs-lookup"><span data-stu-id="9a95e-125">First, register all of the default designers.</span></span>

 <span data-ttu-id="9a95e-126">Nachfolgend ist das Codebeispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="9a95e-126">The following is the code example.</span></span>

```csharp
// register metadata
(new DesignerMetadata()).Register();
RegisterCustomMetadata();
```

```vb
' register metadata
Dim metadata = New DesignerMetadata()
metadata.Register()
' register custom metadata
RegisterCustomMetadata()
```

    -   <span data-ttu-id="9a95e-127">Überschreiben Sie dann "Parallel" in der `RegisterCustomMetadata`-Methode.</span><span class="sxs-lookup"><span data-stu-id="9a95e-127">Then, override the parallel in `RegisterCustomMetadata` method.</span></span>

 <span data-ttu-id="9a95e-128">Im folgenden Code wird dies in C# und Visual Basic veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="9a95e-128">The following code shows this in C# and Visual Basic.</span></span>

```csharp
void RegisterCustomMetadata()
{
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes(typeof(Parallel), new DesignerAttribute(typeof(CustomParallelDesigner)));
      MetadataStore.AddAttributeTable(builder.CreateTable());
}
```

```vb
Sub RegisterCustomMetadata()
   Dim builder As New AttributeTableBuilder()
   builder.AddCustomAttributes(GetType(Parallel), New DesignerAttribute(GetType(CustomParallelDesigner)))
   MetadataStore.AddAttributeTable(builder.CreateTable())
End Sub
```

-   <span data-ttu-id="9a95e-129">Beachten Sie schließlich die Verwendung unterschiedlicher Datenvorlagen und Trigger, um die entsprechende Vorlage auf Grundlage der `IsRootDesigner`-Eigenschaft auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="9a95e-129">Finally, note the use of differing data templates and triggers to select the appropriate template based on the `IsRootDesigner` property.</span></span>

 <span data-ttu-id="9a95e-130">Nachfolgend ist das Codebeispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="9a95e-130">The following is the code example.</span></span>

```xaml
<sad:ActivityDesigner x:Class="Microsoft.Samples.CustomParallelDesigner"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:sad="clr-namespace:System.Activities.Design;assembly=System.Activities.Design"
    xmlns:sadv="clr-namespace:System.Activities.Design.View;assembly=System.Activities.Design">
  <sad:ActivityDesigner.Resources>
    <DataTemplate x:Key="Expanded">
      <StackPanel>
        <TextBlock>This is the Expanded View</TextBlock>
        <sad:WorkflowItemsPresenter HintText="Drop Activities Here"
                                    Items="{Binding Path=ModelItem.Branches}">
          <sad:WorkflowItemsPresenter.SpacerTemplate>
            <DataTemplate>
              <Ellipse Width="10" Height="10" Fill="Black"/>
            </DataTemplate>
          </sad:WorkflowItemsPresenter.SpacerTemplate>
          <sad:WorkflowItemsPresenter.ItemsPanel>
            <ItemsPanelTemplate>
              <StackPanel Orientation="Horizontal"/>
            </ItemsPanelTemplate>
          </sad:WorkflowItemsPresenter.ItemsPanel>
        </sad:WorkflowItemsPresenter>
      </StackPanel>
    </DataTemplate>
    <DataTemplate x:Key="Collapsed">
      <TextBlock>This is the Collapsed View</TextBlock>
    </DataTemplate>
    <Style x:Key="ExpandOrCollapsedStyle" TargetType="{x:Type ContentPresenter}">
      <Setter Property="ContentTemplate" Value="{DynamicResource Collapsed}"/>
      <Style.Triggers>
        <DataTrigger Binding="{Binding Path=IsRootDesigner}" Value="true">
          <Setter Property="ContentTemplate" Value="{DynamicResource Expanded}"/>
        </DataTrigger>
      </Style.Triggers>
    </Style>
  </sad: ActivityDesigner.Resources>
  <Grid>
    <ContentPresenter Style="{DynamicResource ExpandOrCollapsedStyle}" Content="{Binding}"/>
  </Grid>
</sad: ActivityDesigner>
```

> [!IMPORTANT]
>  <span data-ttu-id="9a95e-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="9a95e-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="9a95e-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="9a95e-132">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="9a95e-133">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="9a95e-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="9a95e-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="9a95e-134">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\CustomActivities\CustomActivityDesigners\WorkflowItemsPresenter`  
  
## <a name="see-also"></a><span data-ttu-id="9a95e-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9a95e-135">See also</span></span>

- <xref:System.Activities.Presentation.WorkflowItemsPresenter>
- [<span data-ttu-id="9a95e-136">Entwickeln von Anwendungen mit dem Workflow-Designer</span><span class="sxs-lookup"><span data-stu-id="9a95e-136">Developing Applications with the Workflow Designer</span></span>](/visualstudio/workflow-designer/developing-applications-with-the-workflow-designer)
