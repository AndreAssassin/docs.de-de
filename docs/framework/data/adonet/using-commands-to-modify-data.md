---
title: Verwenden von Befehlen zum Ändern von Daten
ms.date: 03/30/2017
ms.assetid: f4160389-b9ff-4b74-b655-437c76dcd586
ms.openlocfilehash: f2e3d162bfbdcb79cfecefa4ddc8e6a0dc46ee3c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59102452"
---
# <a name="using-commands-to-modify-data"></a><span data-ttu-id="1f35a-102">Verwenden von Befehlen zum Ändern von Daten</span><span class="sxs-lookup"><span data-stu-id="1f35a-102">Using Commands to Modify Data</span></span>
<span data-ttu-id="1f35a-103">Mit einem .NET Framework-Datenanbieter können gespeicherte Prozeduren oder Datendefinitionssprachen-Anweisungen (z. B. CREATE TABLE und ALTER COLUMN) ausgeführt werden, um eine Schemabearbeitung an einer Datenbank oder einem Katalog vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="1f35a-103">Using a .NET Framework data provider, you can execute stored procedures or data definition language statements (for example, CREATE TABLE and ALTER COLUMN) to perform schema manipulation on a database or catalog.</span></span> <span data-ttu-id="1f35a-104">Mit diesen Befehlen werden keine Zeilen zurückgegeben, wie eine Abfrage, sodass der **Befehl** -Objekt bietet eine **ExecuteNonQuery** für die Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="1f35a-104">These commands do not return rows as a query would, so the **Command** object provides an **ExecuteNonQuery** to process them.</span></span>  
  
 <span data-ttu-id="1f35a-105">Zusätzlich zur Verwendung von **ExecuteNonQuery** Schema ändern, können Sie auch diese Methode, um SQL-Anweisungen verarbeiten, die Daten ändern, aber, die nicht Zeilen zurückgeben, z. B. INSERT, UPDATE und DELETE, verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f35a-105">In addition to using **ExecuteNonQuery** to modify schema, you can also use this method to process SQL statements that modify data but that do not return rows, such as INSERT, UPDATE, and DELETE.</span></span>  
  
 <span data-ttu-id="1f35a-106">Zwar von keine Zeilen zurückgegeben werden die **ExecuteNonQuery** -Methode, die Eingabeparameter, Ausgabeparameter und Rückgabewerte übergeben und zurückgegeben wird, über die **Parameter** Auflistung von der **Befehl**  Objekt.</span><span class="sxs-lookup"><span data-stu-id="1f35a-106">Although rows are not returned by the **ExecuteNonQuery** method, input and output parameters and return values can be passed and returned via the **Parameters** collection of the **Command** object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1f35a-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1f35a-107">In This Section</span></span>  
 [<span data-ttu-id="1f35a-108">Aktualisieren von Daten in einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="1f35a-108">Updating Data in a Data Source</span></span>](../../../../docs/framework/data/adonet/updating-data-in-a-data-source.md)  
 <span data-ttu-id="1f35a-109">Beschreibt das Ausführen von Befehlen oder gespeicherten Prozeduren, mit denen Daten in einer Datenbank geändert werden.</span><span class="sxs-lookup"><span data-stu-id="1f35a-109">Describes how to execute commands or stored procedures that modify data in a database.</span></span>  
  
 [<span data-ttu-id="1f35a-110">Ausführen von Katalogoperationen</span><span class="sxs-lookup"><span data-stu-id="1f35a-110">Performing Catalog Operations</span></span>](../../../../docs/framework/data/adonet/performing-catalog-operations.md)  
 <span data-ttu-id="1f35a-111">Beschreibt das Ausführen von Befehlen, mit denen ein Datenbankschema geändert wird.</span><span class="sxs-lookup"><span data-stu-id="1f35a-111">Describes how to execute commands that modify database schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f35a-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f35a-112">See also</span></span>

- [<span data-ttu-id="1f35a-113">Abrufen und Ändern von Daten in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="1f35a-113">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="1f35a-114">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="1f35a-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="1f35a-115">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="1f35a-115">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
