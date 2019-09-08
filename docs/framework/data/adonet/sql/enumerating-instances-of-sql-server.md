---
title: Aufzählen von SQL Server-Instanzen (ADO.NET)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ddf1c83c-9d40-45e6-b04d-9828c6cbbfdc
ms.openlocfilehash: c464762e82a24aab399a23ecb26420b5dce61f55
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782387"
---
# <a name="enumerating-instances-of-sql-server-adonet"></a><span data-ttu-id="eb9c4-102">Aufzählen von SQL Server-Instanzen (ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-102">Enumerating Instances of SQL Server (ADO.NET)</span></span>
<span data-ttu-id="eb9c4-103">SQL Server ermöglicht es Anwendungen, SQL Server Instanzen im aktuellen Netzwerk zu finden.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-103">SQL Server permits applications to find SQL Server instances within the current network.</span></span> <span data-ttu-id="eb9c4-104">Die hierzu erforderlichen Informationen werden den Entwicklern von Anwendungen durch die <xref:System.Data.Sql.SqlDataSourceEnumerator>-Klasse als <xref:System.Data.DataTable> verfügbar gemacht, die Informationen zu allen sichtbaren Servern enthält.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-104">The <xref:System.Data.Sql.SqlDataSourceEnumerator> class exposes this information to the application developer, providing a <xref:System.Data.DataTable> containing information about all the visible servers.</span></span> <span data-ttu-id="eb9c4-105">Diese zurückgegebene Tabelle enthält eine Liste der im Netzwerk verfügbaren Server Instanzen, die der Liste entspricht, wenn ein Benutzer versucht, eine neue Verbindung zu erstellen, und erweitert die Dropdown Liste, die alle verfügbaren Server in den **Verbindungs Eigenschaften enthält.** (Dialogfeld).</span><span class="sxs-lookup"><span data-stu-id="eb9c4-105">This returned table contains a list of server instances available on the network that matches the list provided when a user attempts to create a new connection, and expands the drop-down list containing all the available servers on the **Connection Properties** dialog box.</span></span> <span data-ttu-id="eb9c4-106">Die Liste der angezeigten Ergebnisse ist nicht immer vollständig.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-106">The results displayed are not always complete.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb9c4-107">Wie bei den meisten Windows-Diensten wird auch hier empfohlen, den SQL-Browserdienst mit minimalen Berechtigungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-107">As with most Windows services, it is best to run the SQL Browser service with the least possible privileges.</span></span> <span data-ttu-id="eb9c4-108">Weitere Informationen zum SQL-Browserdienst und dessen Verwaltung finden Sie in der Onlinedokumentation zu SQL Server.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-108">See SQL Server Books Online for more information on the SQL Browser service, and how to manage its behavior.</span></span>  
  
## <a name="retrieving-an-enumerator-instance"></a><span data-ttu-id="eb9c4-109">Abrufen einer Enumeratorinstanz</span><span class="sxs-lookup"><span data-stu-id="eb9c4-109">Retrieving an Enumerator Instance</span></span>  
 <span data-ttu-id="eb9c4-110">Damit Sie die Tabelle mit den Informationen zu den verfügbaren SQL Server-Instanzen abrufen können, müssen Sie zunächst einen Enumerator abrufen. Hierzu verwenden Sie die freigegebene/statische <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A>-Eigenschaft:</span><span class="sxs-lookup"><span data-stu-id="eb9c4-110">In order to retrieve the table containing information about the available SQL Server instances, you must first retrieve an enumerator, using the shared/static <xref:System.Data.Sql.SqlDataSourceEnumerator.Instance%2A> property:</span></span>  
  
```vb  
Dim instance As System.Data.Sql.SqlDataSourceEnumerator = _  
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
```csharp  
System.Data.Sql.SqlDataSourceEnumerator instance =   
   System.Data.Sql.SqlDataSourceEnumerator.Instance  
```  
  
 <span data-ttu-id="eb9c4-111">Nachdem Sie die statische Instanz abgerufen haben, können Sie die <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A>-Methode aufrufen. Diese gibt eine <xref:System.Data.DataTable> mit den Informationen zu den verfügbaren Servern zurück:</span><span class="sxs-lookup"><span data-stu-id="eb9c4-111">Once you have retrieved the static instance, you can call the <xref:System.Data.Sql.SqlDataSourceEnumerator.GetDataSources%2A> method, which returns a <xref:System.Data.DataTable> containing information about the available servers:</span></span>  
  
```vb  
Dim dataTable As System.Data.DataTable = instance.GetDataSources()  
```  
  
```csharp  
System.Data.DataTable dataTable = instance.GetDataSources();  
```  
  
 <span data-ttu-id="eb9c4-112">Die vom Methodenaufruf zurückgegebene Tabelle enthält die folgenden Spalten, die wiederum jeweils alle `string`-Werte enthalten:</span><span class="sxs-lookup"><span data-stu-id="eb9c4-112">The table returned from the method call contains the following columns, all of which contain `string` values:</span></span>  
  
|<span data-ttu-id="eb9c4-113">Spalte</span><span class="sxs-lookup"><span data-stu-id="eb9c4-113">Column</span></span>|<span data-ttu-id="eb9c4-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="eb9c4-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="eb9c4-115">**Servername**</span><span class="sxs-lookup"><span data-stu-id="eb9c4-115">**ServerName**</span></span>|<span data-ttu-id="eb9c4-116">Name des Servers.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-116">Name of the server.</span></span>|  
|<span data-ttu-id="eb9c4-117">**InstanceName**</span><span class="sxs-lookup"><span data-stu-id="eb9c4-117">**InstanceName**</span></span>|<span data-ttu-id="eb9c4-118">Name der Serverinstanz.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-118">Name of the server instance.</span></span> <span data-ttu-id="eb9c4-119">Die Spalte bleibt leer, wenn der Server als Standardinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-119">Blank if the server is running as the default instance.</span></span>|  
|<span data-ttu-id="eb9c4-120">**IsClustered**</span><span class="sxs-lookup"><span data-stu-id="eb9c4-120">**IsClustered**</span></span>|<span data-ttu-id="eb9c4-121">Gibt an, ob der Server Teil eines Clusters ist.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-121">Indicates whether the server is part of a cluster.</span></span>|  
|<span data-ttu-id="eb9c4-122">**Version**</span><span class="sxs-lookup"><span data-stu-id="eb9c4-122">**Version**</span></span>|<span data-ttu-id="eb9c4-123">Serverversion.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-123">Version of the server.</span></span> <span data-ttu-id="eb9c4-124">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="eb9c4-124">For example:</span></span><br /><br /> <span data-ttu-id="eb9c4-125">-9. x (SQL Server 2005)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-125">-   9.00.x (SQL Server 2005)</span></span><br /><span data-ttu-id="eb9c4-126">-10.0. XX (SQL Server 2008)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-126">-   10.0.xx (SQL Server 2008)</span></span><br /><span data-ttu-id="eb9c4-127">-10.50. x (SQL Server 2008 R2)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-127">-   10.50.x (SQL Server 2008 R2)</span></span><br /><span data-ttu-id="eb9c4-128">-11.0. XX (SQL Server 2012)</span><span class="sxs-lookup"><span data-stu-id="eb9c4-128">-   11.0.xx (SQL Server 2012)</span></span>|  
  
## <a name="enumeration-limitations"></a><span data-ttu-id="eb9c4-129">Einschränkungen bei der Enumeration</span><span class="sxs-lookup"><span data-stu-id="eb9c4-129">Enumeration Limitations</span></span>  
 <span data-ttu-id="eb9c4-130">Möglicherweise werden nicht immer alle verfügbaren Server aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-130">All of the available servers may or may not be listed.</span></span> <span data-ttu-id="eb9c4-131">Der Umfang der Liste kann je nach Faktoren wie Timeouts und Datenverkehr im Netzwerk variieren.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-131">The list can vary depending on factors such as timeouts and network traffic.</span></span> <span data-ttu-id="eb9c4-132">Daher kann die Liste bei zwei aufeinander folgenden Aufrufen unterschiedlich ausfallen.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-132">This can cause the list to be different on two consecutive calls.</span></span> <span data-ttu-id="eb9c4-133">Es werden nur Server aufgelistet, die sich im gleichen Netzwerk befinden.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-133">Only servers on the same network will be listed.</span></span> <span data-ttu-id="eb9c4-134">Da Broadcastpakete i. d. R. von Routern nicht weitergeleitet werden, wird möglicherweise ein verfügbarer Server nicht aufgelistet. Dieses Verhalten ist bei jedem Aufruf gleich.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-134">Broadcast packets typically won't traverse routers, which is why you may not see a server listed, but it will be stable across calls.</span></span>  
  
 <span data-ttu-id="eb9c4-135">Zu den aufgelisteten Servern werden ggf. zusätzliche Informationen aufgeführt, z. B. `IsClustered` oder die Version.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-135">Listed servers may or may not have additional information such as `IsClustered` and version.</span></span> <span data-ttu-id="eb9c4-136">Dies ist davon abhängig, wie die Liste abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-136">This is dependent on how the list was obtained.</span></span> <span data-ttu-id="eb9c4-137">Es werden ausführlichere Informationen angezeigt, wenn die Server über den SQL Server-Browserdienst aufgelistet werden. Bei Servern, die über die Windows-Infrastruktur ermittelt werden, wird nur der Name aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-137">Servers listed through the SQL Server browser service will have more details than those found through the Windows infrastructure, which will list only the name.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eb9c4-138">Serverenumeration ist nur in vollständig vertrauenswürdigen Umgebungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-138">Server enumeration is only available when running in full-trust.</span></span> <span data-ttu-id="eb9c4-139">Assemblys, die in einer nur teilweise vertrauenswürdigen Umgebung ausgeführt werden, können die Enumeration nicht verwenden. Dies gilt auch, wenn sie über die <xref:System.Data.SqlClient.SqlClientPermission>-Codezugriffssicherheitsberechtigung (CAS) verfügen.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-139">Assemblies running in a partially-trusted environment will not be able to use it, even if they have the <xref:System.Data.SqlClient.SqlClientPermission> Code Access Security (CAS) permission.</span></span>  
  
 <span data-ttu-id="eb9c4-140">SQL Server stellt Informationen für <xref:System.Data.Sql.SqlDataSourceEnumerator> durch die Verwendung eines externen Windows-Dienstanbieter namens SQL-Browser bereit.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-140">SQL Server provides information for the <xref:System.Data.Sql.SqlDataSourceEnumerator> through the use of an external Windows service named SQL Browser.</span></span> <span data-ttu-id="eb9c4-141">Dieser Dienst ist in der Standardeinstellung aktiviert, kann vom Administrator jedoch deaktiviert werden. Dadurch wird die Serverinstanz für diese Klasse unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-141">This service is enabled by default, but administrators may turn it off or disable it, making the server instance invisible to this class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb9c4-142">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eb9c4-142">Example</span></span>  
 <span data-ttu-id="eb9c4-143">Die folgende Konsolenanwendung ruft Informationen zu allen sichtbaren Instanzen von SQL Server ab und zeigt diese Informationen im Konsolenfenster an.</span><span class="sxs-lookup"><span data-stu-id="eb9c4-143">The following console application retrieves information about all of the visible SQL Server instances and displays the information in the console window.</span></span>  
  
```vb  
Imports System.Data.Sql  
  
Module Module1  
  Sub Main()  
    ' Retrieve the enumerator instance and then the data.  
    Dim instance As SqlDataSourceEnumerator = _  
     SqlDataSourceEnumerator.Instance  
    Dim table As System.Data.DataTable = instance.GetDataSources()  
  
    ' Display the contents of the table.  
    DisplayData(table)  
  
    Console.WriteLine("Press any key to continue.")  
    Console.ReadKey()  
  End Sub  
  
  Private Sub DisplayData(ByVal table As DataTable)  
    For Each row As DataRow In table.Rows  
      For Each col As DataColumn In table.Columns  
        Console.WriteLine("{0} = {1}", col.ColumnName, row(col))  
      Next  
      Console.WriteLine("============================")  
    Next  
  End Sub  
End Module  
```  
  
```csharp  
using System.Data.Sql;  
  
class Program  
{  
  static void Main()  
  {  
    // Retrieve the enumerator instance and then the data.  
    SqlDataSourceEnumerator instance =  
      SqlDataSourceEnumerator.Instance;  
    System.Data.DataTable table = instance.GetDataSources();  
  
    // Display the contents of the table.  
    DisplayData(table);  
  
    Console.WriteLine("Press any key to continue.");  
    Console.ReadKey();  
  }  
  
  private static void DisplayData(System.Data.DataTable table)  
  {  
    foreach (System.Data.DataRow row in table.Rows)  
    {  
      foreach (System.Data.DataColumn col in table.Columns)  
      {  
        Console.WriteLine("{0} = {1}", col.ColumnName, row[col]);  
      }  
      Console.WriteLine("============================");  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="eb9c4-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb9c4-144">See also</span></span>

- [<span data-ttu-id="eb9c4-145">SQL Server und ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eb9c4-145">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="eb9c4-146">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="eb9c4-146">ADO.NET Overview</span></span>](../ado-net-overview.md)
