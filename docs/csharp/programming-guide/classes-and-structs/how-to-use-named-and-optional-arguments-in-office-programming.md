---
title: 'Vorgehensweise: Verwenden von benannten und optionalen Argumenten bei der Office-Programmierung – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- named and optional arguments [C#], Office programming
- optional arguments [C#], Office programming
- named arguments [C#], Office programming
ms.assetid: 65b8a222-bcd8-454c-845f-84adff5a356f
ms.openlocfilehash: 3ecea9d55ef61d2158da0dabeca22a58460b3bea
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59313969"
---
# <a name="how-to-use-named-and-optional-arguments-in-office-programming-c-programming-guide"></a><span data-ttu-id="945f1-102">Vorgehensweise: Verwenden von benannten und optionalen Argumenten bei der Office-Programmierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="945f1-102">How to: Use Named and Optional Arguments in Office Programming (C# Programming Guide)</span></span>
<span data-ttu-id="945f1-103">Benannte und optionale Argumente, die in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)] eingeführt wurden, optimieren die Zweckmäßigkeit, die Flexibilität und die Lesbarkeit in der C#-Programmierung.</span><span class="sxs-lookup"><span data-stu-id="945f1-103">Named arguments and optional arguments, introduced in [!INCLUDE[csharp_dev10_long](~/includes/csharp-dev10-long-md.md)], enhance convenience, flexibility, and readability in C# programming.</span></span> <span data-ttu-id="945f1-104">Diese Funktionen erleichtern zusätzlich den Zugriff auf COM-Schnittstellen wie etwa die Automatisierungs-APIs in Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="945f1-104">In addition, these features greatly facilitate access to COM interfaces such as the Microsoft Office automation APIs.</span></span>  
  
 <span data-ttu-id="945f1-105">In folgendem Beispiel hat die Methode [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) sechzehn Parameter, die Eigenschaften einer Tabelle repräsentieren, wie z.B. die Zeilen- und Spaltenanzahl, das Format, die Rahmen, Schriftarten und Farben.</span><span class="sxs-lookup"><span data-stu-id="945f1-105">In the following example, method [ConvertToTable](<xref:Microsoft.Office.Interop.Word.Range.ConvertToTable%2A>) has sixteen parameters that represent characteristics of a table, such as number of columns and rows, formatting, borders, fonts, and colors.</span></span> <span data-ttu-id="945f1-106">Alle sechzehn Parameter sind optional, weil Sie oftmals keine bestimmten Werte für sie festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="945f1-106">All sixteen parameters are optional, because most of the time you do not want to specify particular values for all of them.</span></span> <span data-ttu-id="945f1-107">Ohne benannte und optionale Argumente muss aber trotzdem ein Wert oder Platzhalterwert für jeden Parameter angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="945f1-107">However, without named and optional arguments, a value or a placeholder value has to be provided for each parameter.</span></span> <span data-ttu-id="945f1-108">Mit benannten und optionalen Argumenten geben Sie nur für die Parameter Werte an, die für Ihr Projekt erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="945f1-108">With named and optional arguments, you specify values only for the parameters that are required for your project.</span></span>  
  
 <span data-ttu-id="945f1-109">Microsoft Office Word muss auf Ihrem Computer installiert sein, damit Sie diesen Vorgang abschließen können.</span><span class="sxs-lookup"><span data-stu-id="945f1-109">You must have Microsoft Office Word installed on your computer to complete these procedures.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-new-console-application"></a><span data-ttu-id="945f1-110">So erstellen Sie eine Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="945f1-110">To create a new console application</span></span>  
  
1. <span data-ttu-id="945f1-111">Starten Sie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="945f1-111">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="945f1-112">Zeigen Sie im Menü **Datei** auf **Neu**, und klicken Sie dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="945f1-112">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3. <span data-ttu-id="945f1-113">Erweitern Sie im Bereich **Templates Categories** (Vorlagenkategorien) den Eintrag **Visual C#**, und klicken Sie dann auf **Windows**.</span><span class="sxs-lookup"><span data-stu-id="945f1-113">In the **Templates Categories** pane, expand **Visual C#**, and then click **Windows**.</span></span>  
  
4. <span data-ttu-id="945f1-114">Sehen Sie am oberen Rand des Bereichs **Vorlagen nach**, um sicherzustellen, dass **.NET Framework 4** im Feld **Zielframework** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="945f1-114">Look in the top of the **Templates** pane to make sure that **.NET Framework 4** appears in the **Target Framework** box.</span></span>  
  
5. <span data-ttu-id="945f1-115">Klicken Sie im Bereich **Vorlagen** auf **Konsolenanwendung**.</span><span class="sxs-lookup"><span data-stu-id="945f1-115">In the **Templates** pane, click **Console Application**.</span></span>  
  
6. <span data-ttu-id="945f1-116">Geben Sie einen Namen für das Projekt im Feld **Name** ein.</span><span class="sxs-lookup"><span data-stu-id="945f1-116">Type a name for your project in the **Name** field.</span></span>  
  
7. <span data-ttu-id="945f1-117">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="945f1-117">Click **OK**.</span></span>  
  
     <span data-ttu-id="945f1-118">Das neue Projekt wird im **Projektmappen-Explorer** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="945f1-118">The new project appears in **Solution Explorer**.</span></span>  
  
### <a name="to-add-a-reference"></a><span data-ttu-id="945f1-119">So fügen Sie einen Verweis hinzu</span><span class="sxs-lookup"><span data-stu-id="945f1-119">To add a reference</span></span>  
  
1. <span data-ttu-id="945f1-120">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann auf **Verweis hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="945f1-120">In **Solution Explorer**, right-click your project's name and then click **Add Reference**.</span></span> <span data-ttu-id="945f1-121">Das Dialogfeld **Verweis hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="945f1-121">The **Add Reference** dialog box appears.</span></span>  
  
2. <span data-ttu-id="945f1-122">Wählen Sie auf der Seite **.NET** **Microsoft.Office.Interop.Word** in der Liste **Komponentenname** aus.</span><span class="sxs-lookup"><span data-stu-id="945f1-122">On the **.NET** page, select **Microsoft.Office.Interop.Word** in the **Component Name** list.</span></span>  
  
3. <span data-ttu-id="945f1-123">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="945f1-123">Click **OK**.</span></span>  
  
### <a name="to-add-necessary-using-directives"></a><span data-ttu-id="945f1-124">So fügen Sie erforderliche using-Anweisungen hinzu</span><span class="sxs-lookup"><span data-stu-id="945f1-124">To add necessary using directives</span></span>  
  
1. <span data-ttu-id="945f1-125">Klicken Sie im **Projektmappen-Explorer** mit der rechten Maustaste auf die Datei **Program.cs** und dann auf **Code anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="945f1-125">In **Solution Explorer**, right-click the **Program.cs** file and then click **View Code**.</span></span>  
  
2. <span data-ttu-id="945f1-126">Fügen Sie am Anfang der Codedatei die folgenden `using`-Direktiven hinzu.</span><span class="sxs-lookup"><span data-stu-id="945f1-126">Add the following `using` directives to the top of the code file.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#4)]  
  
### <a name="to-display-text-in-a-word-document"></a><span data-ttu-id="945f1-127">So zeigen Sie Text in einem Word-Dokument an</span><span class="sxs-lookup"><span data-stu-id="945f1-127">To display text in a Word document</span></span>  
  
1. <span data-ttu-id="945f1-128">Fügen Sie in der Klasse `Program` in Program.cs die folgende Methode hinzu, um eine Word-Anwendung und ein Word-Dokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945f1-128">In the `Program` class in Program.cs, add the following method to create a Word application and a Word document.</span></span> <span data-ttu-id="945f1-129">Die Methode [Hinzufügen](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) verfügt über vier optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="945f1-129">The [Add](<xref:Microsoft.Office.Interop.Word.Documents.Add%2A>) method has four optional parameters.</span></span> <span data-ttu-id="945f1-130">In diesem Beispiel werden ihre Standardwerte verwendet.</span><span class="sxs-lookup"><span data-stu-id="945f1-130">This example uses their default values.</span></span> <span data-ttu-id="945f1-131">Deshalb sind in der aufrufenden Anweisung keine Argumente erforderlich.</span><span class="sxs-lookup"><span data-stu-id="945f1-131">Therefore, no arguments are necessary in the calling statement.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#6)]  
  
2. <span data-ttu-id="945f1-132">Fügen Sie den folgenden Code am Ende der Methode hinzu, um zu definieren, wo der Text im Dokument angezeigt werden und um welchen Text es sich dabei handeln soll.</span><span class="sxs-lookup"><span data-stu-id="945f1-132">Add the following code at the end of the method to define where to display text in the document, and what text to display.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#7)]  
  
### <a name="to-run-the-application"></a><span data-ttu-id="945f1-133">So führen Sie die Anwendung aus</span><span class="sxs-lookup"><span data-stu-id="945f1-133">To run the application</span></span>  
  
1. <span data-ttu-id="945f1-134">Fügen Sie die folgende Anweisung in Main hinzu.</span><span class="sxs-lookup"><span data-stu-id="945f1-134">Add the following statement to Main.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#8)]  
  
2. <span data-ttu-id="945f1-135">Drücken Sie STRG+F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="945f1-135">Press CTRL+F5 to run the project.</span></span> <span data-ttu-id="945f1-136">Ein Word-Dokument mit dem angegebenen Text wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="945f1-136">A Word document appears that contains the specified text.</span></span>  
  
### <a name="to-change-the-text-to-a-table"></a><span data-ttu-id="945f1-137">So ändern Sie Text in eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="945f1-137">To change the text to a table</span></span>  
  
1. <span data-ttu-id="945f1-138">Verwenden Sie die `ConvertToTable`-Methode, um den Text in eine Tabelle einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="945f1-138">Use the `ConvertToTable` method to enclose the text in a table.</span></span> <span data-ttu-id="945f1-139">Die Methode verfügt über sechzehn optionale Parameter.</span><span class="sxs-lookup"><span data-stu-id="945f1-139">The method has sixteen optional parameters.</span></span> <span data-ttu-id="945f1-140">IntelliSense schließt optionale Parameter in Klammern ein, wie in folgender Abbildung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="945f1-140">IntelliSense encloses optional parameters in brackets, as shown in the following illustration.</span></span>  
  
     ![Liste der Parameter für die ConvertToTable-Methode](./media/how-to-use-named-and-optional-arguments-in-office-programming/convert-table-parameters.png)  
  
     <span data-ttu-id="945f1-142">Benannte und optionale Argumente ermöglichen es Ihnen, nur Werte für die Parameter anzugeben, die Sie auch ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="945f1-142">Named and optional arguments enable you to specify values for only the parameters that you want to change.</span></span> <span data-ttu-id="945f1-143">Fügen Sie den folgenden Code am Ende der `DisplayInWord`-Methode hinzu, um eine einfache Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="945f1-143">Add the following code to the end of method `DisplayInWord` to create a simple table.</span></span> <span data-ttu-id="945f1-144">Das Argument gibt an, dass die Kommas in der Textzeichenfolge in `range` die Zelle der Tabelle trennen.</span><span class="sxs-lookup"><span data-stu-id="945f1-144">The argument specifies that the commas in the text string in `range` separate the cells of the table.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#9)]  
  
     <span data-ttu-id="945f1-145">In früheren Versionen von C# erfordert der Aufruf an `ConvertToTable` ein Verweisargument für jeden Parameter, wie in folgendem Codebeispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="945f1-145">In earlier versions of C#, the call to `ConvertToTable` requires a reference argument for each parameter, as shown in the following code.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#14)]  
  
2. <span data-ttu-id="945f1-146">Drücken Sie STRG+F5, um das Projekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="945f1-146">Press CTRL+F5 to run the project.</span></span>  
  
### <a name="to-experiment-with-other-parameters"></a><span data-ttu-id="945f1-147">So können Sie sich auch an anderen Parametern versuchen</span><span class="sxs-lookup"><span data-stu-id="945f1-147">To experiment with other parameters</span></span>  
  
1. <span data-ttu-id="945f1-148">Um die Tabelle so zu ändern, dass sie nur noch eine Spalte und drei Zeilen hat, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann STRG+F5 ein.</span><span class="sxs-lookup"><span data-stu-id="945f1-148">To change the table so that it has one column and three rows, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#10)]  
  
2. <span data-ttu-id="945f1-149">Um ein vordefiniertes Format für eine Tabelle anzugeben, ersetzen Sie die letzte Zeile in `DisplayInWord` durch folgende Anweisung, und geben Sie dann STRG+F5 ein.</span><span class="sxs-lookup"><span data-stu-id="945f1-149">To specify a predefined format for the table, replace the last line in `DisplayInWord` with the following statement and then type CTRL+F5.</span></span> <span data-ttu-id="945f1-150">Das Format kann jede der [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>)-Konstanten sein.</span><span class="sxs-lookup"><span data-stu-id="945f1-150">The format can be any of the [WdTableFormat](<xref:Microsoft.Office.Interop.Word.WdTableFormat>) constants.</span></span>  
  
     [!code-csharp[csProgGuideNamedAndOptional#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#11)]  
  
## <a name="example"></a><span data-ttu-id="945f1-151">Beispiel</span><span class="sxs-lookup"><span data-stu-id="945f1-151">Example</span></span>  
 <span data-ttu-id="945f1-152">Der folgende Code enthält das vollständige Beispiel.</span><span class="sxs-lookup"><span data-stu-id="945f1-152">The following code includes the full example.</span></span>  
  
 [!code-csharp[csProgGuideNamedAndOptional#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csprogguidenamedandoptional/cs/wordprogram.cs#12)]  
  
## <a name="see-also"></a><span data-ttu-id="945f1-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="945f1-153">See also</span></span>

- [<span data-ttu-id="945f1-154">Benannte und optionale Argumente</span><span class="sxs-lookup"><span data-stu-id="945f1-154">Named and Optional Arguments</span></span>](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)
