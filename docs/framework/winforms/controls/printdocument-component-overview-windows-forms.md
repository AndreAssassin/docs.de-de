---
title: Übersicht über die PrintDocument-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 96bca5d96722098f76059c58c32b3fea0ff78cd2
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211729"
---
# <a name="printdocument-component-overview-windows-forms"></a><span data-ttu-id="e0344-102">Übersicht über die PrintDocument-Komponente (Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e0344-102">PrintDocument Component Overview (Windows Forms)</span></span>

<span data-ttu-id="e0344-103">Die Komponente [PrintDocument](printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können.</span><span class="sxs-lookup"><span data-stu-id="e0344-103">The Windows Forms [PrintDocument](printdocument-component-windows-forms.md) component is used to set the properties that describe what to print and the ability to print the document within Windows-based applications.</span></span> <span data-ttu-id="e0344-104">Sie kann zusammen mit der Komponente [PrintDialog](printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.</span><span class="sxs-lookup"><span data-stu-id="e0344-104">It can be used in conjunction with the [PrintDialog](printdialog-component-windows-forms.md) component to be in control of all aspects of document printing.</span></span>

## <a name="working-with-the-printdocument-component"></a><span data-ttu-id="e0344-105">Arbeiten mit der PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="e0344-105">Working with the PrintDocument Component</span></span>

<span data-ttu-id="e0344-106">Zwei der wichtigsten Szenarios, bei denen die <xref:System.Drawing.Printing.PrintDocument> Komponente sind:</span><span class="sxs-lookup"><span data-stu-id="e0344-106">Two of the main scenarios that involve the <xref:System.Drawing.Printing.PrintDocument> component are:</span></span>

- <span data-ttu-id="e0344-107">Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei.</span><span class="sxs-lookup"><span data-stu-id="e0344-107">Simple print jobs, such as printing an individual text file.</span></span> <span data-ttu-id="e0344-108">In diesem Fall fügen Sie der <xref:System.Drawing.Printing.PrintDocument> Komponente zu einem Windows-Formular hinzufügen anschließend Programmierlogik, die eine Datei im ausgibt der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler.</span><span class="sxs-lookup"><span data-stu-id="e0344-108">In such a case you would add the <xref:System.Drawing.Printing.PrintDocument> component to a Windows Form, then add programming logic that prints a file in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler.</span></span> <span data-ttu-id="e0344-109">Die Programmierlogik muss mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken.</span><span class="sxs-lookup"><span data-stu-id="e0344-109">The programming logic should culminate with the <xref:System.Drawing.Printing.PrintDocument.Print%2A> method to print the document.</span></span> <span data-ttu-id="e0344-110">Diese Methode sendet eine <xref:System.Drawing.Graphics> in enthaltene Objekt das <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse, an den Drucker.</span><span class="sxs-lookup"><span data-stu-id="e0344-110">This method sends a <xref:System.Drawing.Graphics> object, contained in the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class, to the printer.</span></span> <span data-ttu-id="e0344-111">Ein Beispiel für die zeigt, wie Sie ein Textdokument mit Drucken der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e0344-111">For an example that shows how to print a text document using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print a Multi-Page Text File in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).</span></span>

- <span data-ttu-id="e0344-112">Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="e0344-112">More complex print jobs, such as a situation where you will want to reuse printing logic you have written.</span></span> <span data-ttu-id="e0344-113">In diesem Fall würden Sie eine neue Komponente von Ableiten der <xref:System.Drawing.Printing.PrintDocument> Komponente und außer Kraft setzen (finden Sie unter [überschreibt](~/docs/visual-basic/language-reference/modifiers/overrides.md) für Visual Basic oder [überschreiben](~/docs/csharp/language-reference/keywords/override.md) für C#) die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.</span><span class="sxs-lookup"><span data-stu-id="e0344-113">In such a case you would derive a new component from the <xref:System.Drawing.Printing.PrintDocument> component and override (see [Overrides](~/docs/visual-basic/language-reference/modifiers/overrides.md) for Visual Basic or [override](~/docs/csharp/language-reference/keywords/override.md) for C#) the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>

<span data-ttu-id="e0344-114">Wenn es auf ein Formular hinzugefügt wird die <xref:System.Drawing.Printing.PrintDocument> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer in Visual Studio angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0344-114">When it is added to a form, the <xref:System.Drawing.Printing.PrintDocument> component appears in the tray at the bottom of the Windows Forms Designer in Visual Studio.</span></span>

## <a name="see-also"></a><span data-ttu-id="e0344-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0344-115">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="e0344-116">Druckunterstützung in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e0344-116">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="e0344-117">PrintDocument-Komponente</span><span class="sxs-lookup"><span data-stu-id="e0344-117">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
