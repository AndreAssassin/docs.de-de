---
title: 'Vorgehensweise: Suchen nach Unterverzeichnissen mit einem bestimmten Muster in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- pattern matching
- folders, finding
ms.assetid: c9265fd1-7483-4150-8b7f-ff642caa939d
ms.openlocfilehash: 705fa6e40d0e6d18826966e3f10cfd31d9e7a6ff
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58823401"
---
# <a name="how-to-find-subdirectories-with-a-specific-pattern-in-visual-basic"></a><span data-ttu-id="6d361-102">Vorgehensweise: Suchen nach Unterverzeichnissen mit einem bestimmten Muster in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d361-102">How to: Find Subdirectories with a Specific Pattern in Visual Basic</span></span>
<span data-ttu-id="6d361-103">Die <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>-Methode gibt eine schreibgeschützte Auflistung von Zeichenfolgen zurück, die die Pfadnamen für die Unterverzeichnisse in einem Verzeichnis darstellen.</span><span class="sxs-lookup"><span data-stu-id="6d361-103">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A> method returns a read-only collection of strings representing the path names for the subdirectories in a directory.</span></span> <span data-ttu-id="6d361-104">Sie können den `wildCards` -Parameter verwenden, um ein bestimmtes Muster anzugeben.</span><span class="sxs-lookup"><span data-stu-id="6d361-104">You can use the `wildCards` parameter to specify a specific pattern.</span></span> <span data-ttu-id="6d361-105">Wenn Sie den Inhalt der Unterverzeichnisse in Ihre Suche mit einbeziehen möchten, legen Sie den `searchType`-Parameter auf `SearchOption.SearchAllSubDirectories` fest.</span><span class="sxs-lookup"><span data-stu-id="6d361-105">If you would like to include the contents of subdirectories in the search, set the `searchType` parameter to `SearchOption.SearchAllSubDirectories`.</span></span>  
  
 <span data-ttu-id="6d361-106">Es wird eine leere Auflistung zurückgegeben, wenn keine Dateien dem angegebenen Muster entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6d361-106">An empty collection is returned if no directories matching the specified pattern are found.</span></span>  
  
### <a name="to-find-subdirectories-with-a-specific-pattern"></a><span data-ttu-id="6d361-107">Suchen nach Unterverzeichnissen mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="6d361-107">To find subdirectories with a specific pattern</span></span>  
  
-   <span data-ttu-id="6d361-108">Verwenden Sie die `GetDirectories`-Methode, die den Namen und Pfad des zu durchsuchenden Verzeichnisses bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="6d361-108">Use the `GetDirectories` method, supplying the name and path of the directory you want to search.</span></span> <span data-ttu-id="6d361-109">Im folgenden Beispiel werden alle Verzeichnisse in der Verzeichnisstruktur zurückgegeben, in deren Namen sich das Wort „Logs“ befindet. Außerdem werden Sie in `ListBox1` eingefügt.</span><span class="sxs-lookup"><span data-stu-id="6d361-109">The following example returns all the directories in the directory structure that contain the word "Logs" in their name, and adds them to `ListBox1`.</span></span>  
  
     [!code-vb[VbVbcnFileAccess#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnFileAccess/VB/Class1.vb#1)]  
  
## <a name="robust-programming"></a><span data-ttu-id="6d361-110">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="6d361-110">Robust Programming</span></span>  
 <span data-ttu-id="6d361-111">Die folgenden Bedingungen können einen Ausnahmefehler verursachen:</span><span class="sxs-lookup"><span data-stu-id="6d361-111">The following conditions may cause an exception:</span></span>  
  
-   <span data-ttu-id="6d361-112">Der Pfad ist aus einem der folgenden Gründe ungültig: Er ist eine Zeichenfolge der Länge 0, er enthält nur Leerzeichen, er enthält ungültige Zeichen, oder er ist ein Gerätepfad (beginnt mit \\\\.\\) (<xref:System.ArgumentException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-112">The path is not valid for one of the following reasons: it is a zero-length string, it contains only white space, it contains invalid characters, or it is a device path (starts with \\\\.\\) (<xref:System.ArgumentException>).</span></span>  
  
-   <span data-ttu-id="6d361-113">Der Pfad ist ungültig, da er `Nothing` ist (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-113">The path is not valid because it is `Nothing` (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="6d361-114">Mindestens eins der angegebenen Platzhalterzeichen ist `Nothing`, eine leere Zeichenfolge oder enthält nur Leerzeichen (<xref:System.ArgumentNullException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-114">One or more of the specified wildcard characters is `Nothing`, an empty string, or contains only spaces (<xref:System.ArgumentNullException>).</span></span>  
  
-   <span data-ttu-id="6d361-115">`directory` ist nicht vorhanden (<xref:System.IO.DirectoryNotFoundException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-115">`directory` does not exist (<xref:System.IO.DirectoryNotFoundException>).</span></span>  
  
-   <span data-ttu-id="6d361-116">`directory` verweist auf eine vorhandene Datei (<xref:System.IO.IOException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-116">`directory` points to an existing file (<xref:System.IO.IOException>).</span></span>  
  
-   <span data-ttu-id="6d361-117">Der Pfad überschreitet die im System definierte maximale Länge (<xref:System.IO.PathTooLongException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-117">The path exceeds the system-defined maximum length (<xref:System.IO.PathTooLongException>).</span></span>  
  
-   <span data-ttu-id="6d361-118">Der Pfad eines Datei- oder Ordnernamens enthält einen Doppelpunkt (:) oder weist ein ungültiges Format auf (<xref:System.NotSupportedException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-118">A file or folder name in the path contains a colon (:) or is in an invalid format (<xref:System.NotSupportedException>).</span></span>  
  
-   <span data-ttu-id="6d361-119">Dem Benutzer fehlen die erforderlichen Berechtigungen zum Anzeigen des Pfades (<xref:System.Security.SecurityException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-119">The user lacks necessary permissions to view the path (<xref:System.Security.SecurityException>).</span></span>  
  
-   <span data-ttu-id="6d361-120">Der Benutzer verfügt nicht über die erforderlichen Berechtigungen (<xref:System.UnauthorizedAccessException>).</span><span class="sxs-lookup"><span data-stu-id="6d361-120">The user lacks necessary permissions (<xref:System.UnauthorizedAccessException>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d361-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6d361-121">See also</span></span>

- <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetDirectories%2A>
- [<span data-ttu-id="6d361-122">Vorgehensweise: Suchen nach Dateien mit einem bestimmten Muster</span><span class="sxs-lookup"><span data-stu-id="6d361-122">How to: Find Files with a Specific Pattern</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-find-files-with-a-specific-pattern.md)
