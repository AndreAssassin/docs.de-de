---
title: Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Clipboard, storing data to (My.Computer.Clipboard)
- Clipboard, reading from (My.Computer.Clipboard)
- Clipboard
- My.Computer.Clipboard object, tasks
- data [Visual Basic], Clipboard
- reading data, from Clipboard
ms.assetid: f690119a-4378-4f7d-b20e-d9377ef49496
ms.openlocfilehash: 19d0fcafb76c40a00939de59968dfaf2e6bd683c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816880"
---
# <a name="storing-data-to-and-reading-from-the-clipboard-visual-basic"></a><span data-ttu-id="f7ab9-102">Speichern von Daten in der Zwischenablage und Lesen von Daten aus der Zwischenablage (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f7ab9-102">Storing data to and reading from the Clipboard (Visual Basic)</span></span>
<span data-ttu-id="f7ab9-103">Die Zwischenablage kann zum Speichern von Daten, z.B. Texten und Bildern, verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-103">The Clipboard can be used to store data, such as text and images.</span></span> <span data-ttu-id="f7ab9-104">Da die Zwischenablage von allen aktiven Prozessen genutzt wird, kann sie zur Übertragung von Daten zwischen den Prozessen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-104">Because the Clipboard is shared by all active processes, it can be used to transfer data between them.</span></span> <span data-ttu-id="f7ab9-105">Mit dem Objekt `My.Computer.Clipboard` können Sie einfach auf die Zwischenablage zugreifen, aus ihr lesen sowie in sie schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-105">The `My.Computer.Clipboard` object allows you to easily access the Clipboard and to read from and write to it.</span></span>  
  
## <a name="reading-from-the-clipboard"></a><span data-ttu-id="f7ab9-106">Lesen aus der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="f7ab9-106">Reading from the Clipboard</span></span>  
 <span data-ttu-id="f7ab9-107">Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A>-Methode, um den Text in der Zwischenablage auszulesen.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-107">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetText%2A> method to read the text in the Clipboard.</span></span> <span data-ttu-id="f7ab9-108">Der folgende Code liest den Text aus und zeigt ihn in einem Nachrichtenfeld an.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-108">The following code reads the text and displays it in a message box.</span></span> <span data-ttu-id="f7ab9-109">Es muss Text in der Zwischenablage gespeichert sein, damit das Beispiel richtig ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-109">There must be text stored on the Clipboard for the example to run correctly.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#4)]  
  
 <span data-ttu-id="f7ab9-110">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-110">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="f7ab9-111">Er befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-111">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.</span></span> <span data-ttu-id="f7ab9-112">Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="f7ab9-112">For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="f7ab9-113">Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A>-Methode zum Abrufen eines Bilds aus der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-113">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetImage%2A> method to retrieve an image from the Clipboard.</span></span> <span data-ttu-id="f7ab9-114">In diesem Beispiel wird überprüft, ob ein Bild in der Zwischenablage ist, bevor es abgerufen und `PictureBox1` zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-114">This example checks to see if there is an image on the Clipboard before retrieving it and assigning it to `PictureBox1`.</span></span>  
  
 [!code-vb[VbResourceTasks#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#16)]  
  
 <span data-ttu-id="f7ab9-115">Dieses Codebeispiel ist auch als IntelliSense-Codeausschnitt verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-115">This code example is also available as an IntelliSense code snippet.</span></span> <span data-ttu-id="f7ab9-116">Es befindet sich in der Codeausschnittauswahl unter **Windows Forms-Anwendungen > Zwischenablage**. Weitere Informationen finden Sie unter [Codeausschnitte](/visualstudio/ide/code-snippets).</span><span class="sxs-lookup"><span data-stu-id="f7ab9-116">In the code snippet picker, it is located in **Windows Forms Applications > Clipboard**.For more information, see [Code Snippets](/visualstudio/ide/code-snippets).</span></span>  
  
 <span data-ttu-id="f7ab9-117">Elemente, die in die Zwischenablage gelegt wurden, bleiben dort, auch nachdem die Anwendung heruntergefahren wurde.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-117">Items placed on the Clipboard will persist even after the application is shut down.</span></span>  
  
## <a name="determining-the-type-of-file-stored-in-the-clipboard"></a><span data-ttu-id="f7ab9-118">Bestimmen des Dateityps, der in der Zwischenablage gespeichert ist</span><span class="sxs-lookup"><span data-stu-id="f7ab9-118">Determining the type of file stored in the Clipboard</span></span>  
 <span data-ttu-id="f7ab9-119">Daten in der Zwischenablage können eine Anzahl von verschiedenen Formen annehmen, z.B. eine Audiodatei oder ein Bild.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-119">Data on the Clipboard may take a number of different forms, such as text, an audio file, or an image.</span></span> <span data-ttu-id="f7ab9-120">Um zu ermitteln, welche Art von Datei sich in der Zwischenablage befindet, können Sie Methoden wie z.B. <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A> und <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A> verwenden.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-120">In order to determine what sort of file is on the Clipboard, you can use methods such as <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsAudio%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsFileDropList%2A>, <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsImage%2A>, and <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsText%2A>.</span></span> <span data-ttu-id="f7ab9-121">Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A>-Methode kann verwendet werden, wenn Sie ein benutzerdefiniertes Format überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-121">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.ContainsData%2A> method can be used if you have a custom format that you want to check.</span></span>  
  
 <span data-ttu-id="f7ab9-122">Verwenden Sie die `ContainsImage`-Funktion, um zu bestimmen, ob die Daten in der Zwischenablage ein Bild sind.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-122">Use the `ContainsImage` function to determine whether the data contained on the Clipboard is an image.</span></span> <span data-ttu-id="f7ab9-123">Der folgende Code überprüft, ob die Daten ein Bild sind und erstattet dementsprechend Bericht.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-123">The following code checks to see whether the data is an image and reports accordingly.</span></span>  
  
 [!code-vb[VbResourceTasks#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#13)]  
  
## <a name="clearing-the-clipboard"></a><span data-ttu-id="f7ab9-124">Löschen der Zwischenablage</span><span class="sxs-lookup"><span data-stu-id="f7ab9-124">Clearing the Clipboard</span></span>  
 <span data-ttu-id="f7ab9-125">Die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A>-Methode löscht den Inhalt der Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-125">The <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.Clear%2A> method clears the Clipboard.</span></span> <span data-ttu-id="f7ab9-126">Da die Zwischenablage von anderen Prozessen gleichzeitig verwendet wird, kann sich das Löschen auf diese Prozesse auswirken.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-126">Because the Clipboard is shared by other processes, clearing it may have an impact on those processes.</span></span>  
  
 <span data-ttu-id="f7ab9-127">Im folgenden Code wird die Verwendung der `Clear`-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-127">The following code shows how to use the `Clear` method.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#3)]  
  
## <a name="writing-to-the-clipboard"></a><span data-ttu-id="f7ab9-128">In die Zwischenablage schreiben</span><span class="sxs-lookup"><span data-stu-id="f7ab9-128">Writing to the Clipboard</span></span>  
 <span data-ttu-id="f7ab9-129">Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A>-Methode, um Text in die Zwischenablage zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-129">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetText%2A> method to write text to the Clipboard.</span></span> <span data-ttu-id="f7ab9-130">Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-130">The following code writes the string "This is a test string" to the Clipboard.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#1)]  
  
 <span data-ttu-id="f7ab9-131">Die `SetText`-Methode kann einen Formatparameter akzeptieren, der einen Typ von <xref:System.Windows.Forms.TextDataFormat> enthält.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-131">The `SetText` method can accept a format parameter that contains a type of <xref:System.Windows.Forms.TextDataFormat>.</span></span> <span data-ttu-id="f7ab9-132">Der folgende Code schreibt die Zeichenfolge „Das ist eine Testzeichenfolge“ als RTF-Text in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-132">The following code writes the string "This is a test string" to the Clipboard as RTF text.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#2)]  
  
 <span data-ttu-id="f7ab9-133">Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A>-Methode, um Daten in die Zwischenablage zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-133">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetData%2A> method to write data to the Clipboard.</span></span> <span data-ttu-id="f7ab9-134">In diesem Beispiel wird das `DataObject` `dataChunk` im benutzerdefiniertem Format `specialFormat` in die Zwischenablage geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-134">This example writes the `DataObject` `dataChunk` to the Clipboard in the custom format `specialFormat`.</span></span>  
  
 [!code-vb[VbVbcnMyClipboard#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMyClipboard/VB/Class1.vb#7)]  
  
 <span data-ttu-id="f7ab9-135">Verwenden Sie die <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A>-Methode, um Audiodaten in die Zwischenablage zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-135">Use the <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetAudio%2A> method to write audio data to the Clipboard.</span></span> <span data-ttu-id="f7ab9-136">In diesem Beispiel wird das Bytearray `musicReader` erstellt, die Datei `cool.wav` darin gelesen und anschließend in die Zwischenablage geschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-136">This example creates the byte array `musicReader`, reads the file `cool.wav` into it, and then writes it to the Clipboard.</span></span>  
  
 [!code-vb[VbResourceTasks#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#5)]  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7ab9-137">Da auf die Zwischenablage von anderen Benutzern zugegriffen werden kann, verwenden Sie sie nicht, um sensible Informationen wie Passwörter oder vertrauliche Daten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f7ab9-137">Because the Clipboard can be accessed by other users, do not use it to store sensitive information, such as passwords or confidential data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7ab9-138">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f7ab9-138">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.GetAudioStream%2A>
- <xref:Microsoft.VisualBasic.MyServices.ClipboardProxy.SetDataObject%2A>
- [<span data-ttu-id="f7ab9-139">Vorgehensweise: Lesen von Objektdaten aus einer XML-Datei</span><span class="sxs-lookup"><span data-stu-id="f7ab9-139">How to: Read Object Data from an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-read-object-data-from-an-xml-file.md)
- [<span data-ttu-id="f7ab9-140">Vorgehensweise: Schreiben von Objektdaten in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="f7ab9-140">How to: Write Object Data to an XML File</span></span>](../../../programming-guide/concepts/serialization/how-to-write-object-data-to-an-xml-file.md)
