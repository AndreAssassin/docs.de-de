---
title: 'Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: c4cdce49-b1c8-4420-b12a-9ff7e6671368
ms.openlocfilehash: 52b961c5a016754964285221e252965ff89efd26
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485239"
---
# <a name="how-to-query-an-assemblys-metadata-with-reflection-linq-c"></a>Vorgehensweise: Abfragen der Metadaten einer Assembly mit Reflektion (LINQ) (C#)

Die Reflektions-APIs der .NET Framework-Klassenbibliothek können verwendet werden, um die Metadaten in einer .NET-Assembly zu untersuchen und Auflistungen von Typen, Typmembern, Parametern usw., die sich in der Assembly befinden, zu erstellen. Da diese Auflistungen die generische `IEnumerable`-Schnittstelle unterstützen, können sie mithilfe von LINQ abgefragt werden.  
  
Das folgende Beispiel zeigt, wie LINQ mit Reflektion verwendet werden kann, um bestimmte Metadaten über Methoden abzurufen, die einem angegebenen Suchkriterium entsprechen. In diesem Fall findet die Abfrage die Namen aller Methoden in der Assembly, die aufzählbare Typen zurückgeben wie z.B. Arrays.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
using System.Reflection;  
using System.IO;  
namespace LINQReflection  
{  
    class ReflectionHowTO  
    {  
        static void Main(string[] args)  
        {  
            Assembly assembly = Assembly.Load("System.Core, Version=3.5.0.0, Culture=neutral, PublicKeyToken= b77a5c561934e089");  
            var pubTypesQuery = from type in assembly.GetTypes()  
                        where type.IsPublic  
                            from method in type.GetMethods()  
                            where method.ReturnType.IsArray == true   
                                || ( method.ReturnType.GetInterface(  
                                    typeof(System.Collections.Generic.IEnumerable<>).FullName ) != null  
                                && method.ReturnType.FullName != "System.String" )  
                            group method.ToString() by type.ToString();  
  
            foreach (var groupOfMethods in pubTypesQuery)  
            {  
                Console.WriteLine("Type: {0}", groupOfMethods.Key);  
                foreach (var method in groupOfMethods)  
                {  
                    Console.WriteLine("  {0}", method);  
                }  
            }  
  
            Console.WriteLine("Press any key to exit");  
            Console.ReadKey();  
        }  
    }    
}  
```  
  
 Im Beispiel wird die <xref:System.Reflection.Assembly.GetTypes%2A>-Methode verwendet, um ein Array von Typen in der angegebenen Assembly zurückzugeben. Der [where](../../../../csharp/language-reference/keywords/where-clause.md)-Filter wird angewendet, sodass nur öffentliche Typen zurückgegeben werden. Für jeden öffentlichen Typ wird mit dem <xref:System.Reflection.MethodInfo>-Array eine Unterabfrage generiert, die vom <xref:System.Type.GetMethods%2A>-Aufruf zurückgegeben wird. Diese Ergebnisse werden gefiltert, damit nur die Methoden zurückgegeben werden, deren Rückgabetyp ein Array oder ein Typ ist, der <xref:System.Collections.Generic.IEnumerable%601> implementiert. Abschließend werden die Ergebnisse mithilfe des Typnamens als Schlüssel gruppiert.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.  
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)
