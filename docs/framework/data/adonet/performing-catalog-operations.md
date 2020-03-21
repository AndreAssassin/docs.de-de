---
title: Ausführen von Katalogoperationen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e60f542f-6271-495b-a9e4-48553481c2a3
ms.openlocfilehash: bedeb4e9c510a3feeedc038e9c4cef6c4721e345
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149244"
---
# <a name="performing-catalog-operations"></a><span data-ttu-id="aa08a-102">Ausführen von Katalogoperationen</span><span class="sxs-lookup"><span data-stu-id="aa08a-102">Performing Catalog Operations</span></span>
<span data-ttu-id="aa08a-103">Um einen Befehl zum Ändern einer Datenbank oder eines Katalogs auszuführen, z. B. die CREATE TABLE- oder CREATE PROCEDURE-Anweisung, erstellen Sie ein **Command-Objekt** mit den entsprechenden SQL-Anweisungen und einem **Connection-Objekt.**</span><span class="sxs-lookup"><span data-stu-id="aa08a-103">To execute a command to modify a database or catalog, such as the CREATE TABLE or CREATE PROCEDURE statement, create a **Command** object using the appropriate SQL statements and a **Connection** object.</span></span> <span data-ttu-id="aa08a-104">Führen Sie den Befehl mit der **ExecuteNonQuery-Methode** des **Command-Objekts** aus.</span><span class="sxs-lookup"><span data-stu-id="aa08a-104">Execute the command with the **ExecuteNonQuery** method of the **Command** object.</span></span>  
  
 <span data-ttu-id="aa08a-105">Im folgenden Codebeispiel wird eine gespeicherte Prozedur in einer Microsoft SQL Server-Datenbank erstellt.</span><span class="sxs-lookup"><span data-stu-id="aa08a-105">The following code example creates a stored procedure in a Microsoft SQL Server database.</span></span>  
  
```vb  
' Assumes connection is a valid SqlConnection.  
Dim queryString As String = "CREATE PROCEDURE InsertCategory " & _  
    "@CategoryName nchar(15), " & _  
    "@Identity int OUT " & _  
    "AS " & _  
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " & _  
    "SET @Identity = @@Identity " & _  
    "RETURN @@ROWCOUNT"  
  
Dim command As SqlCommand = New SqlCommand(queryString, connection)  
command.ExecuteNonQuery()  
```  
  
```csharp  
// Assumes connection is a valid SqlConnection.  
string queryString = "CREATE PROCEDURE InsertCategory  " +
    "@CategoryName nchar(15), " +  
    "@Identity int OUT " +  
    "AS " +
    "INSERT INTO Categories (CategoryName) VALUES(@CategoryName) " +
    "SET @Identity = @@Identity " +  
    "RETURN @@ROWCOUNT";  
  
SqlCommand command = new SqlCommand(queryString, connection);  
command.ExecuteNonQuery();  
```  
  
## <a name="see-also"></a><span data-ttu-id="aa08a-106">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa08a-106">See also</span></span>

- [<span data-ttu-id="aa08a-107">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="aa08a-107">Using Commands to Modify Data</span></span>](using-commands-to-modify-data.md)
- [<span data-ttu-id="aa08a-108">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="aa08a-108">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="aa08a-109">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="aa08a-109">ADO.NET Overview</span></span>](ado-net-overview.md)
