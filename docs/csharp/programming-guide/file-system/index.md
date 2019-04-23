---
title: Das Dateisystem und die Registrierung – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- file system [C#]
- registry [C#]
- files [C#]
ms.assetid: 0f2511cf-2b02-4b41-b001-b1754677c38f
ms.openlocfilehash: 64c852e6fcc034cb56651ffc2d22fa5323bbb54f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61680063"
---
# <a name="file-system-and-the-registry-c-programming-guide"></a><span data-ttu-id="ece12-102">Das Dateisystem und die Registrierung (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ece12-102">File System and the Registry (C# Programming Guide)</span></span>
<span data-ttu-id="ece12-103">Die folgenden Themen zeigen die Verwendung von C# und dem .NET Framework zum Ausführen verschiedener grundlegender Vorgänge in Dateien, Ordnern und der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="ece12-103">The following topics show how to use C# and the .NET Framework to perform various basic operations on files, folders, and the Registry.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ece12-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ece12-104">In This Section</span></span>  
  
|<span data-ttu-id="ece12-105">**Titel**</span><span class="sxs-lookup"><span data-stu-id="ece12-105">**Title**</span></span>|<span data-ttu-id="ece12-106">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ece12-106">**Description**</span></span>|  
|---------------|---------------------|  
|[<span data-ttu-id="ece12-107">Vorgehensweise: Durchlaufen eines Verzeichnisbaums</span><span class="sxs-lookup"><span data-stu-id="ece12-107">How to: Iterate Through a Directory Tree</span></span>](../../../csharp/programming-guide/file-system/how-to-iterate-through-a-directory-tree.md)|<span data-ttu-id="ece12-108">Zeigt, wie eine Verzeichnisstruktur manuell durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="ece12-108">Shows how to manually iterate through a directory tree.</span></span>|  
|[<span data-ttu-id="ece12-109">Vorgehensweise: Abrufen von Informationen über Dateien, Ordner und Laufwerke</span><span class="sxs-lookup"><span data-stu-id="ece12-109">How to: Get Information About Files, Folders, and Drives</span></span>](../../../csharp/programming-guide/file-system/how-to-get-information-about-files-folders-and-drives.md)|<span data-ttu-id="ece12-110">Zeigt, wie Sie Informationen zu Dateien, Ordnern und Laufwerken abrufen, beispielsweise die Uhrzeit der Erstellung und die Größe.</span><span class="sxs-lookup"><span data-stu-id="ece12-110">Shows how to retrieve information such as creation times and size, about files, folders and drives.</span></span>|  
|[<span data-ttu-id="ece12-111">Vorgehensweise: Erstellen einer Datei oder eines Ordners</span><span class="sxs-lookup"><span data-stu-id="ece12-111">How to: Create a File or Folder</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-file-or-folder.md)|<span data-ttu-id="ece12-112">Zeigt, wie Sie eine neue Datei oder einen neuen Ordner erstellen.</span><span class="sxs-lookup"><span data-stu-id="ece12-112">Shows how to create a new file or folder.</span></span>|  
|[<span data-ttu-id="ece12-113">Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ece12-113">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)|<span data-ttu-id="ece12-114">Zeigt, wie Sie Dateien und Ordner kopieren, löschen und verschieben.</span><span class="sxs-lookup"><span data-stu-id="ece12-114">Shows how to copy, delete and move files and folders.</span></span>|  
|[<span data-ttu-id="ece12-115">Vorgehensweise: Bereitstellen eines Statusdialogfelds für Dateioperationen</span><span class="sxs-lookup"><span data-stu-id="ece12-115">How to: Provide a Progress Dialog Box for File Operations</span></span>](../../../csharp/programming-guide/file-system/how-to-provide-a-progress-dialog-box-for-file-operations.md)|<span data-ttu-id="ece12-116">Zeigt, wie Sie ein standardmäßiges Windows-Fortschrittsdialogfeld für bestimmte Dateivorgänge anzeigen.</span><span class="sxs-lookup"><span data-stu-id="ece12-116">Shows how to display a standard Windows progress dialog for certain file operations.</span></span>|  
|[<span data-ttu-id="ece12-117">Vorgehensweise: Schreiben in eine Textdatei</span><span class="sxs-lookup"><span data-stu-id="ece12-117">How to: Write to a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-write-to-a-text-file.md)|<span data-ttu-id="ece12-118">Zeigt, wie Sie in eine Textdatei schreiben.</span><span class="sxs-lookup"><span data-stu-id="ece12-118">Shows how to write to a text file.</span></span>|  
|[<span data-ttu-id="ece12-119">Vorgehensweise: Lesen aus einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="ece12-119">How to: Read From a Text File</span></span>](../../../csharp/programming-guide/file-system/how-to-read-from-a-text-file.md)|<span data-ttu-id="ece12-120">Zeigt, wie Sie aus einer Textdatei lesen.</span><span class="sxs-lookup"><span data-stu-id="ece12-120">Shows how to read from a text file.</span></span>|  
|[<span data-ttu-id="ece12-121">Vorgehensweise: Zeilenweises Lesen einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="ece12-121">How to: Read a Text File One Line at a Time</span></span>](../../../csharp/programming-guide/file-system/how-to-read-a-text-file-one-line-at-a-time.md)|<span data-ttu-id="ece12-122">Zeigt, wie Sie Text zeilenweise aus einer Datei abrufen.</span><span class="sxs-lookup"><span data-stu-id="ece12-122">Shows how to retrieve text from a file one line at a time.</span></span>|  
|[<span data-ttu-id="ece12-123">Vorgehensweise: Erstellen eines Schlüssels in der Registrierung</span><span class="sxs-lookup"><span data-stu-id="ece12-123">How to: Create a Key In the Registry</span></span>](../../../csharp/programming-guide/file-system/how-to-create-a-key-in-the-registry.md)|<span data-ttu-id="ece12-124">Zeigt, wie Sie einen Schlüssel in die Systemregistrierung schreiben.</span><span class="sxs-lookup"><span data-stu-id="ece12-124">Shows how to write a key to the system registry.</span></span>|  
  
## <a name="related-sections"></a><span data-ttu-id="ece12-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="ece12-125">Related Sections</span></span>  
 [<span data-ttu-id="ece12-126">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="ece12-126">File and Stream I/O</span></span>](../../../standard/io/index.md)  
  
 [<span data-ttu-id="ece12-127">Vorgehensweise: Kopieren, Löschen und Verschieben von Dateien und Ordnern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ece12-127">How to: Copy, Delete, and Move Files and Folders (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/how-to-copy-delete-and-move-files-and-folders.md)  
  
 [<span data-ttu-id="ece12-128">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ece12-128">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
  
 [<span data-ttu-id="ece12-129">Dateien, Ordner und Laufwerke</span><span class="sxs-lookup"><span data-stu-id="ece12-129">Files, Folders and Drives</span></span>](../../../csharp/programming-guide/file-system/index.md)  
  
 <xref:System.IO?displayProperty=nameWithType>
