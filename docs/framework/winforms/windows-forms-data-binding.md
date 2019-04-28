---
title: Datenbindung in Web Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms]
- Windows Forms, data binding
- data [Windows Forms], architecture
- Windows Forms controls, data binding
ms.assetid: c3826d8e-ea25-4ad4-a669-45bfb19192aa
ms.openlocfilehash: ed456807137e8cf7594bc50eb0eebb67b88e6b40
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61800112"
---
# <a name="windows-forms-data-binding"></a><span data-ttu-id="f31b3-102">Datenbindung in Web Forms</span><span class="sxs-lookup"><span data-stu-id="f31b3-102">Windows Forms Data Binding</span></span>
<span data-ttu-id="f31b3-103">Mit der Datenbindung in Windows Forms erhalten Sie die Möglichkeit, Informationen aus einer Datenquelle in Steuerelementen im Formular anzuzeigen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f31b3-103">Data binding in Windows Forms gives you the means to display and make changes to information from a data source in controls on the form.</span></span> <span data-ttu-id="f31b3-104">Sie können sowohl herkömmliche Datenquellen als auch beinahe alle Strukturen binden, die Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="f31b3-104">You can bind to both traditional data sources as well as almost any structure that contains data.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f31b3-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="f31b3-105">In This Section</span></span>  
 [<span data-ttu-id="f31b3-106">Datenbindung und Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f31b3-106">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)  
 <span data-ttu-id="f31b3-107">Bietet eine Übersicht über die Datenbindung in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f31b3-107">Provides an overview of data binding in Windows Forms.</span></span>  
  
 [<span data-ttu-id="f31b3-108">Von Windows Forms unterstützte Datenquellen</span><span class="sxs-lookup"><span data-stu-id="f31b3-108">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)  
 <span data-ttu-id="f31b3-109">Beschreibt die Datenquellen, die in Verbindung mit Windows Forms verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f31b3-109">Describes the data sources that can be used with Windows Forms.</span></span>  
  
 [<span data-ttu-id="f31b3-110">Auf Datenbindung bezogene Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f31b3-110">Interfaces Related to Data Binding</span></span>](interfaces-related-to-data-binding.md)  
 <span data-ttu-id="f31b3-111">Beschreibt einige der Schnittstellen, die für die Windows Forms-Datenbindung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f31b3-111">Describes several of the interfaces used with Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="f31b3-112">Vorgehensweise: Navigieren Sie durch Daten in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f31b3-112">How to: Navigate Data in Windows Forms</span></span>](how-to-navigate-data-in-windows-forms.md)  
 <span data-ttu-id="f31b3-113">Zeigt, wie Sie in den Elementen einer Datenquelle navigieren können.</span><span class="sxs-lookup"><span data-stu-id="f31b3-113">Shows how to navigate through items in a data source.</span></span>  
  
 [<span data-ttu-id="f31b3-114">Änderungsbenachrichtigung in der Windows Forms-Datenbindung</span><span class="sxs-lookup"><span data-stu-id="f31b3-114">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)  
 <span data-ttu-id="f31b3-115">Beschreibt die unterschiedlichen Arten von Änderungsbenachrichtigungen für die Datenbindung in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f31b3-115">Describes different types of change notification for Windows Forms data binding.</span></span>  
  
 [<span data-ttu-id="f31b3-116">Vorgehensweise: Implementieren der INotifyPropertyChanged-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f31b3-116">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)  
 <span data-ttu-id="f31b3-117">Zeigt, wie die <xref:System.ComponentModel.INotifyPropertyChanged>-Schnittstelle implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="f31b3-117">Shows how to implement the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="f31b3-118">Die Schnittstelle übergibt die Eigenschaftenänderungen an einem Geschäftsobjekt an ein gebundenes Steuerelement.</span><span class="sxs-lookup"><span data-stu-id="f31b3-118">The interface  communicates to a bound control the property changes on a business object</span></span>  
  
 [<span data-ttu-id="f31b3-119">Vorgehensweise: Anwenden des PropertyNameChanged-Musters</span><span class="sxs-lookup"><span data-stu-id="f31b3-119">How to: Apply the PropertyNameChanged Pattern</span></span>](how-to-apply-the-propertynamechanged-pattern.md)  
 <span data-ttu-id="f31b3-120">Veranschaulicht das Anwenden der *PropertyName*-Muster auf die Eigenschaften eines Windows Forms-Benutzersteuerelements.</span><span class="sxs-lookup"><span data-stu-id="f31b3-120">Shows how to apply the *PropertyName*Changed pattern to properties of a Windows Forms user control.</span></span>  
  
 [<span data-ttu-id="f31b3-121">Vorgehensweise: Implementieren der ITypedList-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f31b3-121">How to: Implement the ITypedList Interface</span></span>](how-to-implement-the-itypedlist-interface.md)  
 <span data-ttu-id="f31b3-122">Zeigt, wie die Ermittlung des Schemas für eine bindbare Liste durch Implementieren der <xref:System.ComponentModel.ITypedList>-Schnittstelle ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="f31b3-122">Shows how to enable discovery of the schema for a bindable list by implementing the <xref:System.ComponentModel.ITypedList> interface.</span></span>  
  
 [<span data-ttu-id="f31b3-123">Vorgehensweise: Implementieren der IListSource-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f31b3-123">How to: Implement the IListSource Interface</span></span>](how-to-implement-the-ilistsource-interface.md)  
 <span data-ttu-id="f31b3-124">Zeigt, wie die <xref:System.ComponentModel.IListSource>-Schnittstelle implementiert wird, um eine bindbare Klasse zu erstellen, die nicht <xref:System.Collections.IList> implementiert, sondern eine Liste von einem anderen Speicherort bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f31b3-124">Shows how to implement the <xref:System.ComponentModel.IListSource> interface to create a bindable class does not implement <xref:System.Collections.IList>, but provides a list from another location.</span></span>  
  
 [<span data-ttu-id="f31b3-125">Vorgehensweise: Sicherstellen, dass mehrere Steuerelemente, die an die gleiche Datenquelle gebunden sind, synchronisiert bleiben</span><span class="sxs-lookup"><span data-stu-id="f31b3-125">How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized</span></span>](multiple-controls-bound-to-data-source-synchronized.md)  
 <span data-ttu-id="f31b3-126">Zeigt, wie das <xref:System.Windows.Forms.BindingSource.BindingComplete>-Ereignis behandelt wird, um sicherzustellen, dass alle an eine Datenquelle gebundenen Steuerelemente synchronisiert bleiben.</span><span class="sxs-lookup"><span data-stu-id="f31b3-126">Shows how to handle the <xref:System.Windows.Forms.BindingSource.BindingComplete> event to ensure all controls bound to a data source remain synchronized.</span></span>  
  
 [<span data-ttu-id="f31b3-127">Vorgehensweise: Stellen Sie sicher, dass die ausgewählte Zeile in einer untergeordneten Tabelle an der richtigen Position verbleibt</span><span class="sxs-lookup"><span data-stu-id="f31b3-127">How to: Ensure the Selected Row in a Child Table Remains at the Correct Position</span></span>](ensure-the-selected-row-in-a-child-table-correct.md)  
 <span data-ttu-id="f31b3-128">Beschreibt, wie Sie sicherstellen können, dass die ausgewählte Zeile in einer untergeordneten Tabelle nicht geändert wird, wenn an einem Feld in der übergeordneten Tabelle eine Änderung vorgenommen wird.</span><span class="sxs-lookup"><span data-stu-id="f31b3-128">Shows how to ensure the selected row of a child table does not change, when a change is made to a field of the parent table.</span></span>  
  
 <span data-ttu-id="f31b3-129">Siehe auch [im Zusammenhang mit Schnittstellen mit Datenbindung](interfaces-related-to-data-binding.md), [Vorgehensweise: Navigieren durch Daten in Windows Forms](how-to-navigate-data-in-windows-forms.md), und [Vorgehensweise: Erstellen ein einfach gebundenen Steuerelements in einem Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span><span class="sxs-lookup"><span data-stu-id="f31b3-129">Also see [Interfaces Related to Data Binding](interfaces-related-to-data-binding.md), [How to: Navigate Data in Windows Forms](how-to-navigate-data-in-windows-forms.md), and [How to: Create a Simple-Bound Control on a Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f31b3-130">Referenz</span><span class="sxs-lookup"><span data-stu-id="f31b3-130">Reference</span></span>  
 <xref:System.Windows.Forms.Binding?displayProperty=nameWithType>  
 <span data-ttu-id="f31b3-131">Beschreibt die Klasse, die für die Bindung zwischen einer bindbaren Komponente und einer Datenquelle steht.</span><span class="sxs-lookup"><span data-stu-id="f31b3-131">Describes the class that represents the binding between a bindable component and a data source.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource?displayProperty=nameWithType>  
 <span data-ttu-id="f31b3-132">Beschreibt die Klasse, die eine Datenquelle für die Bindung an Steuerelemente kapselt.</span><span class="sxs-lookup"><span data-stu-id="f31b3-132">Describes the class that encapsulates a data source for binding to controls.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="f31b3-133">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="f31b3-133">Related Sections</span></span>  
 [<span data-ttu-id="f31b3-134">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="f31b3-134">BindingSource Component</span></span>](./controls/bindingsource-component.md)  
 <span data-ttu-id="f31b3-135">Enthält eine Liste mit Themen, in denen gezeigt wird, wie die <xref:System.Windows.Forms.BindingSource>-Komponente verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f31b3-135">Contains a list of topics that demonstrate how to use the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="f31b3-136">DataGridView-Steuerelement</span><span class="sxs-lookup"><span data-stu-id="f31b3-136">DataGridView Control</span></span>](./controls/datagridview-control-windows-forms.md)  
 <span data-ttu-id="f31b3-137">Enthält eine Liste mit Themen, in denen gezeigt wird, wie ein bindbares DataGrid-Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f31b3-137">Provides a list of topics that demonstrate how to use a bindable datagrid control.</span></span>  
  
 <span data-ttu-id="f31b3-138">Siehe auch [den Zugriff auf Daten in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="f31b3-138">Also see [Accessing Data in Visual Studio](/visualstudio/data-tools/accessing-data-in-visual-studio).</span></span>
