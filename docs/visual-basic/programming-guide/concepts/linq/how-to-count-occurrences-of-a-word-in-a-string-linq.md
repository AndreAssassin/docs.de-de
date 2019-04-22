---
title: 'Vorgehensweise: Anzahl der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: bc367e46-f7cc-45f9-936f-754e661b7bb9
ms.openlocfilehash: b3d34503e87aff1180dca4cb8233d668d35b0255
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58820320"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-visual-basic"></a>Vorgehensweise: Anzahl der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (Visual Basic)
Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage verwenden, um die Vorkommen eines angegebenen Worts in einer Zeichenfolge zu zählen. Beachten Sie, dass zuerst die <xref:System.String.Split%2A>-Methode aufgerufen wird, um ein Array von Worten zu erstellen, damit die Zählung ausgeführt werden kann. Für die <xref:System.String.Split%2A>-Methode werden Leistungskosten berechnet. Wenn der einzige Vorgang in der Zeichenfolge die Zählung der Wörter ist, überlegen Sie sich, ob Sie nicht stattdessen die <xref:System.Text.RegularExpressions.Regex.Matches%2A>- oder <xref:System.String.IndexOf%2A>-Methode verwenden möchten. Wenn jedoch die Leistung kein zentrales Problem ist oder Sie die Sequenz in eine Reihenfolge gebracht haben, um andere Abfragetypen darauf auszuführen, macht es Sinn, auch LINQ zum Zählen der Wörter oder Sätze zu verwenden.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Class CountWords  
  
    Shared Sub Main()  
  
        Dim text As String = "Historically, the world of data and the world of objects" &   
                  " have not been well integrated. Programmers work in C# or Visual Basic" &   
                  " and also in SQL or XQuery. On the one side are concepts such as classes," &   
                  " objects, fields, inheritance, and .NET Framework APIs. On the other side" &   
                  " are tables, columns, rows, nodes, and separate languages for dealing with" &   
                  " them. Data types often require translation between the two worlds; there are" &   
                  " different standard functions. Because the object world has no notion of query, a" &   
                  " query can only be represented as a string without compile-time type checking or" &   
                  " IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" &   
                  " objects in memory is often tedious and error-prone."  
  
        Dim searchTerm As String = "data"  
  
        ' Convert the string into an array of words.  
        Dim dataSource As String() = text.Split(New Char() {" ", ",", ".", ";", ":"},   
                                                 StringSplitOptions.RemoveEmptyEntries)  
  
        ' Create and execute the query. It executes immediately   
        ' because a singleton value is produced.  
        ' Use ToLower to match "data" and "Data"   
        Dim matchQuery = From word In dataSource   
                      Where word.ToLowerInvariant() = searchTerm.ToLowerInvariant()   
                      Select word  
  
        ' Count the matches.  
        Dim count As Integer = matchQuery.Count()  
        Console.WriteLine(count & " occurrence(s) of the search term """ &   
                          searchTerm & """ were found.")  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' 3 occurrence(s) of the search term "data" were found.  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und einer `Imports`-Anweisung für den System.Linq-Namespace.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
