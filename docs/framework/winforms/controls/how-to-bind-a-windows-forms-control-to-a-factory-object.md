---
title: 'Vorgehensweise: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: 2de892d94afdfcdc580d20f90fb60ebabf4a9b37
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61761415"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="eebed-102">Vorgehensweise: Binden eines Windows Forms-Steuerelements an ein Factoryobjekt</span><span class="sxs-lookup"><span data-stu-id="eebed-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="eebed-103">Beim Erstellen von Steuerelementen, die mit Daten interagieren, ist es manchmal erforderlich, ein Steuerelement an ein Objekt oder eine Methode zu binden, das bzw. die andere Objekte generiert.</span><span class="sxs-lookup"><span data-stu-id="eebed-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="eebed-104">Diese Art von Objekt oder Methode wird als Factory bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="eebed-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="eebed-105">Die Datenquelle kann beispielsweise der Rückgabewert aus einem Methodenaufruf anstelle eines Objekts im Arbeitsspeicher oder eines Typs sein.</span><span class="sxs-lookup"><span data-stu-id="eebed-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="eebed-106">Sie können ein Steuerelement an diese Art von Datenquelle binden, solange die Quelle eine Auflistung zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eebed-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="eebed-107">Sie können ein Steuerelement problemlos an ein Factoryobjekt binden, indem Sie das <xref:System.Windows.Forms.BindingSource>-Steuerelement verwenden.</span><span class="sxs-lookup"><span data-stu-id="eebed-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eebed-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eebed-108">Example</span></span>  
 <span data-ttu-id="eebed-109">Das folgende Beispiel zeigt, wie ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mithilfe eines <xref:System.Windows.Forms.BindingSource>-Steuerelements an eine Factorymethode gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="eebed-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="eebed-110">Die Factorymethode lautet `GetOrdersByCustomerId` und gibt alle Befehle für einen bestimmten Kunden in der Northwind-Datenbank zurück.</span><span class="sxs-lookup"><span data-stu-id="eebed-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="eebed-111">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="eebed-111">Compiling the Code</span></span>  
 <span data-ttu-id="eebed-112">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eebed-112">This example requires:</span></span>  
  
- <span data-ttu-id="eebed-113">Verweise auf die Assemblys "System", "System.Data", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="eebed-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="eebed-114">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="eebed-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="eebed-115">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="eebed-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eebed-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eebed-116">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="eebed-117">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="eebed-117">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="eebed-118">Vorgehensweise: Binden eines Windows Forms-Steuerelements an einen Typ</span><span class="sxs-lookup"><span data-stu-id="eebed-118">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
