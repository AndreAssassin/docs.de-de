---
title: 'Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- serial ports, retrieving strings
- strings [Visual Basic], retrieving from serial ports
- My.Resources object
ms.assetid: 8371ce2c-e1c7-476b-a86d-9afc2614b6b7
ms.openlocfilehash: 6c832cd9ef5df904850261f4de2d769bfc28c3cb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296718"
---
# <a name="how-to-receive-strings-from-serial-ports-in-visual-basic"></a><span data-ttu-id="b5977-102">Vorgehensweise: Empfangen von Zeichenfolgen von seriellen Anschlüssen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="b5977-102">How to: Receive Strings From Serial Ports in Visual Basic</span></span>
<span data-ttu-id="b5977-103">Dieses Thema beschreibt, wie `My.Computer.Ports` zum Empfangen von Zeichenfolgen von seriellen Ports des Computers in Visual Basic verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b5977-103">This topic describes how to use `My.Computer.Ports` to receive strings from the computer's serial ports in Visual Basic.</span></span>  
  
### <a name="to-receive-strings-from-the-serial-port"></a><span data-ttu-id="b5977-104">So werden Zeichenfolgen von seriellen Anschlüssen empfangen</span><span class="sxs-lookup"><span data-stu-id="b5977-104">To receive strings from the serial port</span></span>  
  
1. <span data-ttu-id="b5977-105">Initialisieren Sie die zurückgegebene Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="b5977-105">Initialize the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#38)]  
  
2. <span data-ttu-id="b5977-106">Bestimmen Sie, welcher serielle Anschluss die Zeichenfolgen bereitstellen soll.</span><span class="sxs-lookup"><span data-stu-id="b5977-106">Determine which serial port should provide the strings.</span></span> <span data-ttu-id="b5977-107">In diesem Beispiel wird vorausgesetzt, dass es `COM1` ist.</span><span class="sxs-lookup"><span data-stu-id="b5977-107">This example assumes it is `COM1`.</span></span>  
  
3. <span data-ttu-id="b5977-108">Verwenden Sie die `My.Computer.Ports.OpenSerialPort`-Methode, um einen Verweis auf den Port abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5977-108">Use the `My.Computer.Ports.OpenSerialPort` method to obtain a reference to the port.</span></span> <span data-ttu-id="b5977-109">Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span><span class="sxs-lookup"><span data-stu-id="b5977-109">For more information, see <xref:Microsoft.VisualBasic.Devices.Ports.OpenSerialPort%2A>.</span></span>  
  
     <span data-ttu-id="b5977-110">Der `Try...Catch...Finally`-Block ermöglicht es der Anwendung, den seriellen Port auch dann zu schließen, wenn eine Ausnahme generiert wird.</span><span class="sxs-lookup"><span data-stu-id="b5977-110">The `Try...Catch...Finally` block allows the application to close the serial port even if it generates an exception.</span></span> <span data-ttu-id="b5977-111">Sämtlicher Code, der den seriellen Anschluss ändert, sollte in diesem Block angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5977-111">All code that manipulates the serial port should appear within this block.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#39)]  
  
4. <span data-ttu-id="b5977-112">Erstellen Sie eine `Do`-Schleife für das Lesen von Textzeilen, bis keine weiteren Zeilen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="b5977-112">Create a `Do` loop for reading lines of text until no more lines are available.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#40)]  
  
5. <span data-ttu-id="b5977-113">Verwenden Sie die <xref:System.IO.Ports.SerialPort.ReadLine>-Methode, um die nächste verfügbare Textzeile aus dem seriellen Anschluss auszulesen.</span><span class="sxs-lookup"><span data-stu-id="b5977-113">Use the <xref:System.IO.Ports.SerialPort.ReadLine> method to read the next available line of text from the serial port.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#41)]  
  
6. <span data-ttu-id="b5977-114">Verwenden Sie eine `If`-Anweisung, um zu ermitteln, ob die <xref:System.IO.Ports.SerialPort.ReadLine>-Methode `Nothing` zurückgibt (was bedeutet, dass kein weiterer Text mehr verfügbar ist).</span><span class="sxs-lookup"><span data-stu-id="b5977-114">Use an `If` statement to determine if the <xref:System.IO.Ports.SerialPort.ReadLine> method returns `Nothing` (which means no more text is available).</span></span> <span data-ttu-id="b5977-115">Wenn sie `Nothing` zurückgibt, beenden Sie die `Do`-Schleife.</span><span class="sxs-lookup"><span data-stu-id="b5977-115">If it does return `Nothing`, exit the `Do` loop.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#42)]  
  
7. <span data-ttu-id="b5977-116">Fügen Sie einen `Else`-Block zur `If`-Anweisung hinzu, um den Fall so zu behandeln, als würde die Zeichenfolge tatsächlich gelesen.</span><span class="sxs-lookup"><span data-stu-id="b5977-116">Add an `Else` block to the `If` statement to handle the case if the string is actually read.</span></span> <span data-ttu-id="b5977-117">Der Block fügt die Zeichenfolge vom seriellen Anschluss an die Rückgabezeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="b5977-117">The block appends the string from the serial port to the return string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#43)]  
  
8. <span data-ttu-id="b5977-118">Gibt die Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="b5977-118">Return the string.</span></span>  
  
     [!code-vb[VbVbalrMyComputer#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#44)]  
  
## <a name="example"></a><span data-ttu-id="b5977-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b5977-119">Example</span></span>  
 [!code-vb[VbVbalrMyComputer#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyComputer/VB/Class2.vb#37)]  
  
 <span data-ttu-id="b5977-120">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b5977-120">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="b5977-121">In der Codeausschnittauswahl ist er unter **Konnektivität und Netzwerk** zu finden.</span><span class="sxs-lookup"><span data-stu-id="b5977-121">In the code snippet picker, it is located in **Connectivity and Networking**.</span></span> <span data-ttu-id="b5977-122">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="b5977-122">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="b5977-123">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b5977-123">Compiling the Code</span></span>  
 <span data-ttu-id="b5977-124">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5977-124">This example assumes the computer is using `COM1`.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="b5977-125">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="b5977-125">Robust Programming</span></span>  
 <span data-ttu-id="b5977-126">In diesem Beispiel wird davon ausgegangen, dass der Computer `COM1` verwendet.</span><span class="sxs-lookup"><span data-stu-id="b5977-126">This example assumes the computer is using `COM1`.</span></span> <span data-ttu-id="b5977-127">Der Code sollte dem Benutzer erlauben, den gewünschten seriellen Anschluss aus einer Liste der verfügbaren Anschlüsse auszuwählen, um mehr Flexibilität zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="b5977-127">For more flexibility, the code should allow the user to select the desired serial port from a list of available ports.</span></span> <span data-ttu-id="b5977-128">Weitere Informationen finden Sie unter [Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span><span class="sxs-lookup"><span data-stu-id="b5977-128">For more information, see [How to: Show Available Serial Ports](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md).</span></span>  
  
 <span data-ttu-id="b5977-129">Dieses Beispiel verwendet einen `Try...Catch...Finally`-Block, um sicherzustellen, dass die Anwendung den Anschluss schließt, und um Zeitüberschreitungen zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="b5977-129">This example uses a `Try...Catch...Finally` block to make sure that the application closes the port and to catch any timeout exceptions.</span></span> <span data-ttu-id="b5977-130">Weitere Informationen finden Sie unter [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b5977-130">For more information, see [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5977-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b5977-131">See also</span></span>

- <xref:Microsoft.VisualBasic.Devices.Ports>
- <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>
- [<span data-ttu-id="b5977-132">Vorgehensweise: Wählen mit Modems an seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="b5977-132">How to: Dial Modems Attached to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-dial-modems-attached-to-serial-ports.md)
- [<span data-ttu-id="b5977-133">Vorgehensweise: Senden von Zeichenfolgen an serielle Anschlüsse</span><span class="sxs-lookup"><span data-stu-id="b5977-133">How to: Send Strings to Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-send-strings-to-serial-ports.md)
- [<span data-ttu-id="b5977-134">Vorgehensweise: Anzeigen von verfügbaren seriellen Anschlüssen</span><span class="sxs-lookup"><span data-stu-id="b5977-134">How to: Show Available Serial Ports</span></span>](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-show-available-serial-ports.md)
