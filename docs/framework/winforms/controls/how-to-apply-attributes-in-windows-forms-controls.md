---
title: 'Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: 273d32927582f4467a92cd3b8f87e699c1f167d7
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922783"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="afa6e-102">Vorgehensweise: Anwenden von Attributen auf Windows Forms-Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="afa6e-102">How to: Apply Attributes in Windows Forms Controls</span></span>
<span data-ttu-id="afa6e-103">Zum Entwickeln von Komponenten und Steuerelementen, die ordnungsgemäß mit der Entwurfs Umgebung interagieren und zur Laufzeit ordnungsgemäß ausgeführt werden, müssen Sie Attribute ordnungsgemäß auf Klassen und Member anwenden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="afa6e-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="afa6e-104">Example</span></span>  
 <span data-ttu-id="afa6e-105">Im folgenden Codebeispiel wird veranschaulicht, wie mehrere Attribute für ein benutzerdefiniertes Steuerelement verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="afa6e-106">Das-Steuerelement veranschaulicht eine einfache Protokollierungsfunktion.</span><span class="sxs-lookup"><span data-stu-id="afa6e-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="afa6e-107">Wenn das Steuerelement an eine Datenquelle gebunden ist, werden die Werte angezeigt, die von der Datenquelle <xref:System.Windows.Forms.DataGridView> in einem-Steuerelement gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="afa6e-108">Wenn ein Wert den von der `Threshold` -Eigenschaft angegebenen Wert überschreitet, wird ein `ThresholdExceeded` -Ereignis ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="afa6e-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="afa6e-109">Protokolliert Werte mit einer `LogEntry` -Klasse. `AttributesDemoControl`</span><span class="sxs-lookup"><span data-stu-id="afa6e-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="afa6e-110">Die `LogEntry` -Klasse ist eine Vorlagen Klasse, d. h., Sie wird für den Typ parametrisiert, den Sie protokolliert.</span><span class="sxs-lookup"><span data-stu-id="afa6e-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="afa6e-111">Wenn `AttributesDemoControl` z. b. Werte vom Typ `float`protokolliert, wird jede `LogEntry` Instanz wie folgt deklariert und verwendet.</span><span class="sxs-lookup"><span data-stu-id="afa6e-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="afa6e-112">Da `LogEntry` durch einen beliebigen Typ parametrisiert wird, muss die Reflektion für den Parametertyp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="afa6e-113">Damit die Schwellenwert Funktion funktioniert, muss der Parametertyp `T` die <xref:System.IComparable> -Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="afa6e-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="afa6e-114">Das Formular, das als `AttributesDemoControl` Host für die Abfrage eines Leistungs Zählers in der Regel</span><span class="sxs-lookup"><span data-stu-id="afa6e-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="afa6e-115">Jeder Wert wird in einem `LogEntry` des entsprechenden Typs verpackt und dem <xref:System.Windows.Forms.BindingSource>Formular hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="afa6e-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="afa6e-116">Der `AttributesDemoControl` empfängt den Wert über seine Datenbindung und zeigt den Wert in einem <xref:System.Windows.Forms.DataGridView> -Steuerelement an.</span><span class="sxs-lookup"><span data-stu-id="afa6e-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="afa6e-117">Das erste Codebeispiel ist die `AttributesDemoControl` -Implementierung.</span><span class="sxs-lookup"><span data-stu-id="afa6e-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="afa6e-118">Im zweiten Codebeispiel wird ein Formular veranschaulicht, das `AttributesDemoControl`verwendet.</span><span class="sxs-lookup"><span data-stu-id="afa6e-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="afa6e-119">Attribute auf Klassenebene</span><span class="sxs-lookup"><span data-stu-id="afa6e-119">Class-level Attributes</span></span>  
 <span data-ttu-id="afa6e-120">Einige Attribute werden auf Klassenebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="afa6e-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="afa6e-121">Das folgende Codebeispiel zeigt die Attribute, die in der Regel auf ein Windows Forms Steuerelement angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="afa6e-122">TypeConverter-Attribut</span><span class="sxs-lookup"><span data-stu-id="afa6e-122">TypeConverter Attribute</span></span>  
 <span data-ttu-id="afa6e-123"><xref:System.ComponentModel.TypeConverterAttribute>ist ein weiteres häufig verwendetes Attribut auf Klassenebene.</span><span class="sxs-lookup"><span data-stu-id="afa6e-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="afa6e-124">Im folgenden Codebeispiel wird die Verwendung für die `LogEntry` -Klasse veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="afa6e-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="afa6e-125">Dieses Beispiel zeigt auch eine Implementierung eines <xref:System.ComponentModel.TypeConverter> für den-Typ mit dem `LogEntryTypeConverter` `LogEntry` Namen.</span><span class="sxs-lookup"><span data-stu-id="afa6e-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="afa6e-126">Attribute auf Element Ebene</span><span class="sxs-lookup"><span data-stu-id="afa6e-126">Member-level Attributes</span></span>  
 <span data-ttu-id="afa6e-127">Einige Attribute werden auf der Element Ebene angewendet.</span><span class="sxs-lookup"><span data-stu-id="afa6e-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="afa6e-128">Die folgenden Codebeispiele zeigen einige Attribute, die häufig auf Eigenschaften von Windows Forms-Steuerelementen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="afa6e-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="afa6e-129">AmbientValue-Attribut</span><span class="sxs-lookup"><span data-stu-id="afa6e-129">AmbientValue Attribute</span></span>  
 <span data-ttu-id="afa6e-130">Das folgende Beispiel veranschaulicht das <xref:System.ComponentModel.AmbientValueAttribute> und zeigt Code, der seine Interaktion mit der Entwurfs Umgebung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="afa6e-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="afa6e-131">Diese Interaktion wird als *Ambiente*bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="afa6e-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="afa6e-132">DataBinding-Attribute</span><span class="sxs-lookup"><span data-stu-id="afa6e-132">Databinding Attributes</span></span>  
 <span data-ttu-id="afa6e-133">In den folgenden Beispielen wird eine Implementierung komplexer Daten Bindungen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="afa6e-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="afa6e-134">Die zuvor gezeigte Klassen <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>Ebene gibt die-Eigenschaft und `DataSource` die `DataMember` -Eigenschaft an, die für die Datenbindung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="afa6e-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="afa6e-135">Der <xref:System.ComponentModel.AttributeProviderAttribute> gibt den Typ an, an `DataSource` den die Eigenschaft gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="afa6e-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="afa6e-136">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="afa6e-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="afa6e-137">Das Formular, das hostet `AttributesDemoControl` , erfordert einen Verweis auf die `AttributesDemoControl` Assembly, um zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="afa6e-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa6e-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="afa6e-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="afa6e-139">Entwickeln benutzerdefinierter Windows Forms-Steuerelemente mit .NET Framework</span><span class="sxs-lookup"><span data-stu-id="afa6e-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="afa6e-140">Attribute in Windows Forms-Steuerelementen</span><span class="sxs-lookup"><span data-stu-id="afa6e-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="afa6e-141">[Vorgehensweise: Serialisieren von Auflistungen von Standard Typen mit dem DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="afa6e-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
