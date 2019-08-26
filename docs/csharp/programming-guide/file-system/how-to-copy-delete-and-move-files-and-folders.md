---
title: 'Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- I/O [C#]
ms.assetid: 62e52cd7-9597-4e4a-acf9-1315f5cdbf05
ms.openlocfilehash: dd32798062dbfc9a10acd27ce51d8d5dd3b164f6
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69590087"
---
# <a name="how-to-copy-delete-and-move-files-and-folders-c-programming-guide"></a><span data-ttu-id="b2a52-102">Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b2a52-102">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>
<span data-ttu-id="b2a52-103">Die folgenden Beispiele veranschaulichen, wie Dateien und Ordner mithilfe der Klassen <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType> und <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> aus dem Namespace <xref:System.IO?displayProperty=nameWithType> synchron kopiert, verschoben und gelöscht werden können.</span><span class="sxs-lookup"><span data-stu-id="b2a52-103">The following examples show how to copy, move, and delete files and folders in a synchronous manner by using the <xref:System.IO.File?displayProperty=nameWithType>, <xref:System.IO.Directory?displayProperty=nameWithType>, <xref:System.IO.FileInfo?displayProperty=nameWithType>, and <xref:System.IO.DirectoryInfo?displayProperty=nameWithType> classes from the <xref:System.IO?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="b2a52-104">Diese Beispiele stellen keine Statusanzeige oder irgendeine andere Benutzeroberfläche bereit.</span><span class="sxs-lookup"><span data-stu-id="b2a52-104">These examples do not provide a progress bar or any other user interface.</span></span> <span data-ttu-id="b2a52-105">Informationen zum Bereitstellen eines standardmäßigen Statusdialogfelds finden Sie unter [Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateivorgänge](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span><span class="sxs-lookup"><span data-stu-id="b2a52-105">If you want to provide a standard progress dialog box, see [How to: Provide a Progress Dialog Box for File Operations](how-to-provide-a-progress-dialog-box-for-file-operations.md).</span></span>  
  
 <span data-ttu-id="b2a52-106">Verwenden Sie <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> zum Bereitstellen von Ereignissen, mit denen Sie bei Vorgängen auf mehreren Dateien den Status berechnen können.</span><span class="sxs-lookup"><span data-stu-id="b2a52-106">Use <xref:System.IO.FileSystemWatcher?displayProperty=nameWithType> to provide events that will enable you to calculate the progress when operating on multiple files.</span></span> <span data-ttu-id="b2a52-107">Eine weitere Möglichkeit ist die Verwendung eines Plattformaufrufs, um die relevanten dateibezogenen Methoden in der Windows-Shell aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="b2a52-107">Another approach is to use platform invoke to call the relevant file-related methods in the Windows Shell.</span></span> <span data-ttu-id="b2a52-108">Weitere Informationen dazu, wie Sie diese Dateivorgänge asynchron ausführen, finden Sie unter [Asynchrone Datei-E/A](../../../standard/io/asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="b2a52-108">For information about how to perform these file operations asynchronously, see [Asynchronous File I/O](../../../standard/io/asynchronous-file-i-o.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b2a52-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2a52-109">Example</span></span>  
 <span data-ttu-id="b2a52-110">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse kopieren.</span><span class="sxs-lookup"><span data-stu-id="b2a52-110">The following example shows how to copy files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#7)]  
  
## <a name="example"></a><span data-ttu-id="b2a52-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2a52-111">Example</span></span>  
 <span data-ttu-id="b2a52-112">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse verschieben.</span><span class="sxs-lookup"><span data-stu-id="b2a52-112">The following example shows how to move files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#8)]  
  
## <a name="example"></a><span data-ttu-id="b2a52-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2a52-113">Example</span></span>  
 <span data-ttu-id="b2a52-114">Im folgenden Beispiel wird gezeigt, wie Sie Dateien und Verzeichnisse löschen.</span><span class="sxs-lookup"><span data-stu-id="b2a52-114">The following example shows how to delete files and directories.</span></span>  
  
 [!code-csharp[csFilesandFolders#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="b2a52-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2a52-115">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="b2a52-116">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b2a52-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="b2a52-117">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b2a52-117">File System and the Registry (C# Programming Guide)</span></span>](index.md)
- [<span data-ttu-id="b2a52-118">Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen</span><span class="sxs-lookup"><span data-stu-id="b2a52-118">How to: Provide a Progress Dialog Box for File Operations</span></span>](how-to-provide-a-progress-dialog-box-for-file-operations.md)
- [<span data-ttu-id="b2a52-119">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="b2a52-119">File and Stream I/O</span></span>](../../../standard/io/index.md)
- [<span data-ttu-id="b2a52-120">Allgemeine E/A-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="b2a52-120">Common I/O Tasks</span></span>](../../../standard/io/common-i-o-tasks.md)
