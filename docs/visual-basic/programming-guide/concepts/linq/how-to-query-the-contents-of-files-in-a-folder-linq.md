---
title: 'Vorgehensweise: Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: edacbcd3-f3e4-4429-a8be-28a58dc0dd70
ms.openlocfilehash: 8af6653c3cffe846082606de81d4bbefedaa30e9
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592124"
---
# <a name="how-to-query-the-contents-of-files-in-a-folder-linq-visual-basic"></a><span data-ttu-id="f6b72-102">Vorgehensweise: Abfragen des Inhalts von Dateien in einem Ordner (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6b72-102">How to: Query the Contents of Files in a Folder (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="f6b72-103">Dieses Beispiel zeigt, wie Sie die Abfrage über alle Dateien in einer angegebenen Verzeichnisstruktur durchführen, jede Datei öffnen, und ihre Inhalte überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f6b72-103">This example shows how to query over all the files in a specified directory tree, open each file, and inspect its contents.</span></span> <span data-ttu-id="f6b72-104">Diese Technik kann zum Erstellen von Indizes oder umgekehrten Indizes des Inhalts einer Verzeichnisstruktur verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f6b72-104">This type of technique could be used to create indexes or reverse indexes of the contents of a directory tree.</span></span> <span data-ttu-id="f6b72-105">In diesem Beispiel wird eine einfache Zeichenfolgensuche ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="f6b72-105">A simple string search is performed in this example.</span></span> <span data-ttu-id="f6b72-106">Komplexere Formen des Mustervergleichs können jedoch mit einem regulären Ausdruck ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6b72-106">However, more complex types of pattern matching can be performed with a regular expression.</span></span> <span data-ttu-id="f6b72-107">Weitere Informationen finden Sie unter [Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="f6b72-107">For more information, see [How to: Combine LINQ Queries with Regular Expressions (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6b72-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6b72-108">Example</span></span>  
  
```vb  
Module Module1  
    'QueryContents  
    Public Sub Main()  
  
        ' Modify this path as necessary.  
        Dim startFolder = "c:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        Dim searchTerm = "Visual Studio"  
  
        ' Search the contents of each file.  
        ' A regular expression created with the RegEx class  
        ' could be used instead of the Contains method.  
        Dim queryMatchingFiles = From file In fileList _  
                                 Where file.Extension = ".htm" _  
                                 Let fileText = GetFileText(file.FullName) _  
                                 Where fileText.Contains(searchTerm) _  
                                 Select file.FullName  
  
        Console.WriteLine("The term " & searchTerm & " was found in:")  
  
        ' Execute the query.  
        For Each filename In queryMatchingFiles  
            Console.WriteLine(filename)  
        Next  
  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
  
    End Sub  
  
    ' Read the contents of the file. This is done in a separate  
    ' function in order to handle potential file system errors.  
    Function GetFileText(ByVal name As String) As String  
  
        ' If the file has been deleted, the right thing  
        ' to do in this case is return an empty string.  
        Dim fileContents = String.Empty  
  
        ' If the file has been deleted since we took   
        ' the snapshot, ignore it and return the empty string.  
        If System.IO.File.Exists(name) Then  
            fileContents = System.IO.File.ReadAllText(name)  
        End If  
  
        Return fileContents  
  
    End Function  
End Module  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f6b72-109">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="f6b72-109">Compiling the Code</span></span>  
<span data-ttu-id="f6b72-110">Erstellen Sie ein Konsolenanwendungsprojekt für VB.NET, mit einem `Imports` -Anweisung für den Namespace "System.Linq".</span><span class="sxs-lookup"><span data-stu-id="f6b72-110">Create a VB.NET console application project, with an `Imports` statement for the System.Linq namespace.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f6b72-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6b72-111">See also</span></span>

- [<span data-ttu-id="f6b72-112">LINQ to Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f6b72-112">LINQ to Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [<span data-ttu-id="f6b72-113">LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="f6b72-113">LINQ and File Directories (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
