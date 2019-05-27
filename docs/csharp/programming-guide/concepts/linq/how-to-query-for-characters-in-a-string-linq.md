---
title: 'Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: 727a1be7-dbec-4ab8-b414-bc2d56feb6ff
ms.openlocfilehash: b31dfb4c9fb7f7efc439a1703f13aafca3053e6a
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65584443"
---
# <a name="how-to-query-for-characters-in-a-string-linq-c"></a><span data-ttu-id="1ed2b-102">Vorgehensweise: Abfragen von Zeichen in einer Zeichenfolge (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed2b-102">How to: Query for Characters in a String (LINQ) (C#)</span></span>
<span data-ttu-id="1ed2b-103">Da die <xref:System.String>-Klasse die generische <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle implementiert, kann jede Zeichenfolge als Folge von Zeichen abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-103">Because the <xref:System.String> class implements the generic <xref:System.Collections.Generic.IEnumerable%601> interface, any string can be queried as a sequence of characters.</span></span> <span data-ttu-id="1ed2b-104">Dies ist allerdings kein üblicher Einsatz von LINQ.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-104">However, this is not a common use of LINQ.</span></span> <span data-ttu-id="1ed2b-105">Verwenden Sie für komplex Musterabgleichvorgänge die <xref:System.Text.RegularExpressions.Regex>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-105">For complex pattern matching operations, use the <xref:System.Text.RegularExpressions.Regex> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1ed2b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1ed2b-106">Example</span></span>  
 <span data-ttu-id="1ed2b-107">In folgendem Beispiel wird eine Zeichenfolge abgefragt, um die Zahl von enthaltenen numerischen Ziffern zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-107">The following example queries a string to determine the number of numeric digits it contains.</span></span> <span data-ttu-id="1ed2b-108">Beachten Sie, dass die Abfrage „wieder verwendet“ wird, nachdem sie zum ersten Mal ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-108">Note that the query is "reused" after it is executed the first time.</span></span> <span data-ttu-id="1ed2b-109">Dies ist möglich, da die Abfrage selbst keine Ergebnisse speichert.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-109">This is possible because the query itself does not store any actual results.</span></span>  
  
```csharp  
class QueryAString  
{  
    static void Main()  
    {  
        string aString = "ABCDE99F-J74-12-89A";  
  
        // Select only those characters that are numbers  
        IEnumerable<char> stringQuery =  
          from ch in aString  
          where Char.IsDigit(ch)  
          select ch;  
  
        // Execute the query  
        foreach (char c in stringQuery)  
            Console.Write(c + " ");  
  
        // Call the Count method on the existing query.  
        int count = stringQuery.Count();  
        Console.WriteLine("Count = {0}", count);  
  
        // Select all characters before the first '-'  
        IEnumerable<char> stringQuery2 = aString.TakeWhile(c => c != '-');  
  
        // Execute the second query  
        foreach (char c in stringQuery2)  
            Console.Write(c);  
  
        Console.WriteLine(System.Environment.NewLine + "Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
  Output: 9 9 7 4 1 2 8 9  
  Count = 8  
  ABCDE99F  
*/  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ed2b-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="1ed2b-110">Compiling the Code</span></span>  
 <span data-ttu-id="1ed2b-111">Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.</span><span class="sxs-lookup"><span data-stu-id="1ed2b-111">Create a C# console application project, with `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ed2b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ed2b-112">See also</span></span>

- [<span data-ttu-id="1ed2b-113">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed2b-113">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)
- [<span data-ttu-id="1ed2b-114">Vorgehensweise: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (C#)</span><span class="sxs-lookup"><span data-stu-id="1ed2b-114">How to: Combine LINQ Queries with Regular Expressions (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
