---
title: 'Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- error handling [Windows Forms], examples
- data binding [Windows Forms], examples
- examples [Windows Forms], error handling
- error handling [Windows Forms], data binding
- data binding [Windows Forms], error handling
- BindingSource component [Windows Forms], handling errors and exceptions
ms.assetid: eddc5bad-9513-47df-ab28-f02d8dff7892
ms.openlocfilehash: 709db2a98074e3322adad8b1275b3c4418c14636
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941270"
---
# <a name="how-to-handle-errors-and-exceptions-that-occur-with-databinding"></a><span data-ttu-id="0f44e-102">Vorgehensweise: Behandeln von Fehlern und Ausnahmen in Zusammenhang mit der Datenbindung</span><span class="sxs-lookup"><span data-stu-id="0f44e-102">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>
<span data-ttu-id="0f44e-103">Häufig treten Ausnahmen und Fehler bei den zugrunde liegenden Geschäftsobjekten auf, wenn Sie diese an Steuerelemente binden.</span><span class="sxs-lookup"><span data-stu-id="0f44e-103">Oftentimes exceptions and errors occur on the underlying business objects when you bind them to controls.</span></span> <span data-ttu-id="0f44e-104">Sie können diese Fehler und Ausnahmen abfangen und dann wiederherstellen oder die Fehlerinformationen an den Benutzer übergeben, indem Sie das <xref:System.Windows.Forms.Binding.BindingComplete>-Ereignis für eine bestimmte <xref:System.Windows.Forms.Binding>-, <xref:System.Windows.Forms.BindingSource>- oder <xref:System.Windows.Forms.CurrencyManager>-Komponente behandeln.</span><span class="sxs-lookup"><span data-stu-id="0f44e-104">You can intercept these errors and exceptions and then either recover or pass the error information to the user by handling the <xref:System.Windows.Forms.Binding.BindingComplete> event for a particular <xref:System.Windows.Forms.Binding>, <xref:System.Windows.Forms.BindingSource>, or <xref:System.Windows.Forms.CurrencyManager> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f44e-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0f44e-105">Example</span></span>  
 <span data-ttu-id="0f44e-106">In diesem Codebeispiel wird das Behandeln von Fehlern und Ausnahmen veranschaulicht, die während der Datenbindung auftreten.</span><span class="sxs-lookup"><span data-stu-id="0f44e-106">This code example demonstrates how to handle errors and exceptions that occur during a data-binding operation.</span></span> <span data-ttu-id="0f44e-107">Es zeigt das Abfangen von Fehlern, indem das <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>-Ereignis der <xref:System.Windows.Forms.Binding>Objekte behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="0f44e-107">It demonstrates how to intercept errors by handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event of the <xref:System.Windows.Forms.Binding> objects.</span></span> <span data-ttu-id="0f44e-108">Um Fehler und Ausnahmen durch die Behandlung dieses Ereignisses abfangen zu können, müssen Sie die Formatierung für die Bindung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f44e-108">In order to intercept errors and exceptions by handling this event, you must enable formatting for the binding.</span></span> <span data-ttu-id="0f44e-109">Sie können die Formatierung beim Erstellen der Bindung oder beim Hinzufügen zur Bindungsauflistung oder beim Festlegen der <xref:System.Windows.Forms.Binding.FormattingEnabled%2A>-Eigenschaft auf `true` aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f44e-109">You can enable formatting when the binding is constructed or added to the binding collection, or by setting the <xref:System.Windows.Forms.Binding.FormattingEnabled%2A> property to `true`.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CPP/form1.cpp#3)]
 [!code-csharp[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/CS/form1.cs#3)]
 [!code-vb[System.Windows.Forms.DataConnectorBindingComplete#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorBindingComplete/VB/form1.vb#3)]  
  
 <span data-ttu-id="0f44e-110">Wenn der Code ausgeführt und eine leere Zeichenfolge für den Namen des Teils oder ein Wert für die Teilenummer eingegeben wird, der kleiner als 100 ist, wird ein Meldungsfeld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f44e-110">When the code is running and an empty string is entered for the part name or a value less than 100 is entered for the part number, a message box appears.</span></span> <span data-ttu-id="0f44e-111">Dies ist ein Ergebnis der Behandlung des <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>-Ereignisses für diese Textfeldbindungen.</span><span class="sxs-lookup"><span data-stu-id="0f44e-111">This is a result of handling the <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType> event for these textbox bindings.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0f44e-112">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="0f44e-112">Compiling the Code</span></span>  
 <span data-ttu-id="0f44e-113">Für dieses Beispiel benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0f44e-113">This example requires:</span></span>  
  
- <span data-ttu-id="0f44e-114">Verweise auf die Assemblys "System", "System.Drawing" und "System.Windows.Forms".</span><span class="sxs-lookup"><span data-stu-id="0f44e-114">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="0f44e-115">Informationen zum Erstellen dieses Beispiels über die Befehlszeile für Visual Basic oder Visual c# finden Sie unter [erstellen über die Befehlszeile](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) oder [Befehlszeile mit csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="0f44e-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="0f44e-116">Sie können auch in diesem Beispiel in Visual Studio erstellen, indem Sie den Code in ein neues Projekt einfügen.</span><span class="sxs-lookup"><span data-stu-id="0f44e-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f44e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f44e-117">See also</span></span>

- <xref:System.Windows.Forms.Binding.BindingComplete?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource.BindingComplete?displayProperty=nameWithType>
- [<span data-ttu-id="0f44e-118">BindingSource-Komponente</span><span class="sxs-lookup"><span data-stu-id="0f44e-118">BindingSource Component</span></span>](bindingsource-component.md)
