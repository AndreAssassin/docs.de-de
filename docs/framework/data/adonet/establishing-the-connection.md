---
title: Herstellen der Verbindung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: 7f8cca02e673339e892c16e0de99e20accdfd404
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142340"
---
# <a name="establishing-the-connection"></a><span data-ttu-id="f1eaa-102">Herstellen der Verbindung</span><span class="sxs-lookup"><span data-stu-id="f1eaa-102">Establishing the Connection</span></span>
<span data-ttu-id="f1eaa-103">Zum Herstellen einer Verbindung mit Microsoft SQL Server verwenden Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt des .NET Framework-Datenanbieters für SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-103">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="f1eaa-104">Wenn Sie eine Verbindung mit einer OLE DB-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.OleDb.OleDbConnection>-Objekt des .NET Framework-Datenanbieters für OLE DB.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-104">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="f1eaa-105">Wenn Sie eine Verbindung mit einer ODBC-Datenquelle herstellen möchten, verwenden Sie das <xref:System.Data.Odbc.OdbcConnection>-Objekt des .NET Framework-Datenanbieters für ODBC.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-105">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="f1eaa-106">Zum Herstellen einer Verbindung mit einer Oracle-Datenquelle verwenden Sie das <xref:System.Data.OracleClient.OracleConnection>-Objekt des .NET Framework-Datenanbieters für Oracle.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-106">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="f1eaa-107">Sicher speichern und Abrufen von Verbindungszeichenfolgen finden Sie [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-107">For securely storing and retrieving connection strings, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="f1eaa-108">Schließen von Verbindungen</span><span class="sxs-lookup"><span data-stu-id="f1eaa-108">Closing Connections</span></span>  
 <span data-ttu-id="f1eaa-109">Es wird empfohlen, die Verbindung nach Verwendung stets zu schließen, damit sie in den Pool zurückgegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-109">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="f1eaa-110">Der `Using`-Block in Visual Basic oder C# verwirft automatisch die Verbindung, wenn der Code den Block verlässt, auch im Falle einer unbehandelten Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-110">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="f1eaa-111">Finden Sie unter [using-Anweisung](~/docs/csharp/language-reference/keywords/using-statement.md) und [Using-Anweisung](~/docs/visual-basic/language-reference/statements/using-statement.md) für Weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-111">See [using Statement](~/docs/csharp/language-reference/keywords/using-statement.md) and [Using Statement](~/docs/visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="f1eaa-112">Sie können ebenso die `Close`-Methode oder `Dispose`-Methode des Verbindungsobjekts des von Ihnen in Anspruch genommenen Anbieters verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-112">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="f1eaa-113">Verbindungen, die nicht explizit geschlossen werden, werden möglicherweise dem Pool nicht hinzugefügt bzw. nicht an den Pool zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-113">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="f1eaa-114">Beispielsweise wird eine Verbindung, die sich nicht mehr im Gültigkeitsbereich befindet, aber nicht explizit geschlossen wurde, nur dann an den Verbindungspool zurückgegeben, wenn die maximale Poolgröße erreicht wurde und die Verbindung immer noch gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-114">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="f1eaa-115">Weitere Informationen finden Sie unter [OLE DB, ODBC und Oracle-Verbindungspooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-115">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1eaa-116">Rufen Sie keine `Close` oder `Dispose` auf eine **Verbindung**, **DataReader**, oder andere verwaltete Objekte in der `Finalize` Methode der Klasse.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-116">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="f1eaa-117">Geben Sie in einer Finalize-Methode nur nicht verwaltete Ressourcen frei, die der Klasse direkt gehören.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-117">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="f1eaa-118">Wenn die Klasse keine nicht verwalteten Ressourcen besitzt, definieren Sie in der Klasse keine `Finalize`-Methode.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-118">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="f1eaa-119">Weitere Informationen finden Sie unter [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-119">For more information, see [Garbage Collection](../../../../docs/standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1eaa-120">Wenn eine Verbindung aus dem Verbindungspool abgerufen oder an diesen zurückgegeben wird, werden keine Anmelde- und Abmeldeereignisse auf dem Server ausgelöst, da die Verbindung bei der Rückgabe an den Verbindungspool nicht geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-120">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="f1eaa-121">Weitere Informationen finden Sie unter [SQL Server-Verbindungspooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-121">For more information, see [SQL Server Connection Pooling (ADO.NET)](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="f1eaa-122">Herstellen einer Verbindung mit SQL Server</span><span class="sxs-lookup"><span data-stu-id="f1eaa-122">Connecting to SQL Server</span></span>  
 <span data-ttu-id="f1eaa-123">Der .NET Framework-Datenanbieter für SQL Server unterstützt ein Verbindungszeichenfolgenformat ähnlich dem Verbindungszeichenfolgenformat für OLE DB (ADO).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-123">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="f1eaa-124">Gültige Zeichenfolgenformatnamen und -werte finden Sie in der Beschreibung der <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>-Eigenschaft des <xref:System.Data.SqlClient.SqlConnection>-Objekts.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-124">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="f1eaa-125">Sie können auch die <xref:System.Data.SqlClient.SqlConnectionStringBuilder>-Klasse verwenden, um zur Laufzeit syntaktisch gültige Verbindungszeichenfolgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-125">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="f1eaa-126">Weitere Informationen finden Sie in [Connection String Builders (Verbindungszeichenfolgengeneratoren)](../../../../docs/framework/data/adonet/connection-string-builders.md).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-126">For more information, see [Connection String Builders](../../../../docs/framework/data/adonet/connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="f1eaa-127">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer SQL Server-Datenbank erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-127">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="f1eaa-128">Integrierte Sicherheit und ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f1eaa-128">Integrated Security and ASP.NET</span></span>  
 <span data-ttu-id="f1eaa-129">Die integrierte Sicherheit von SQL Server (auch bekannt als vertrauenswürdige Verbindungen) trägt zum Schutz beim Herstellen von Verbindungen mit SQL Server bei, da in der Verbindungszeichenfolge Benutzer-ID und Kennwort nicht verfügbar gemacht werden, und ist daher die empfohlene Methode für die Authentifizierung einer Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-129">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="f1eaa-130">Bei der integrierten Sicherheit wird die aktuelle Sicherheitsidentität oder das aktuelle Sicherheitstoken des ausführenden Prozesses verwendet.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-130">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="f1eaa-131">Bei Desktop-Anwendungen handelt es sich dabei i. d. R. um die Identität des aktuell angemeldeten Benutzers.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-131">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="f1eaa-132">Die Sicherheitsidentität für ASP.NET-Anwendungen kann auf eine von mehreren verschiedenen Optionen festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-132">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="f1eaa-133">Um besser zu verstehen, die eine ASP.NET-Anwendung verwendet wird, beim Verbinden mit SQL Server die Sicherheits-ID, finden Sie unter [ASP.NET-Identitätswechsel](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET-Authentifizierung](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100)), und [Vorgehensweise: Integrierte Sicherheit von SQL-Servers mit Windows](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="f1eaa-133">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](https://docs.microsoft.com/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET Authentication](https://docs.microsoft.com/previous-versions/aspnet/eeyk640h(v=vs.100)), and [How to: Access SQL Server Using Windows Integrated Security](https://docs.microsoft.com/previous-versions/aspnet/bsz5788z(v=vs.100)).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="f1eaa-134">Herstellen einer Verbindung mit einer OLE DB-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f1eaa-134">Connecting to an OLE DB Data Source</span></span>  
 <span data-ttu-id="f1eaa-135">Die .NET Framework-Datenanbieter für OLE DB stellt Verbindungen mit verfügbar gemachten Datenquellen mithilfe von OLE DB (über SQLOLEDB, den OLE DB-Anbieter für SQL Server), mit der **OleDbConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-135">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="f1eaa-136">Bei dem .NET Framework-Datenanbieter für OLE DB ist das Verbindungszeichenfolgenformat mit dem in ADO verwendeten Verbindungszeichenfolgenformat bis auf folgende Ausnahmen identisch:</span><span class="sxs-lookup"><span data-stu-id="f1eaa-136">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
-   <span data-ttu-id="f1eaa-137">Die **Anbieter** -Schlüsselwort ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-137">The **Provider** keyword is required.</span></span>  
  
-   <span data-ttu-id="f1eaa-138">Die **URL**, **Remoteanbieter**, und **Remoteserver** Schlüsselwörter werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-138">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="f1eaa-139">Weitere Informationen zu OLE DB-Verbindungszeichenfolgen finden Sie unter dem Thema <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-139">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="f1eaa-140">Sie können auch den <xref:System.Data.OleDb.OleDbConnectionStringBuilder> verwenden, um zur Laufzeit Verbindungszeichenfolgen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-140">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1eaa-141">Die **OleDbConnection** -Objekt festlegen oder Abrufen von dynamischen Eigenschaften, die speziell für OLE DB-Anbieter nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-141">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="f1eaa-142">Es werden nur Eigenschaften unterstützt, die in der Verbindungszeichenfolge für den OLE DB-Anbieter übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-142">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="f1eaa-143">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer OLE DB-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-143">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =   
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="f1eaa-144">Verwenden Sie keine UDL-Dateien (Universal Data Link)</span><span class="sxs-lookup"><span data-stu-id="f1eaa-144">Do Not Use Universal Data Link Files</span></span>  
 <span data-ttu-id="f1eaa-145">Es ist möglich, geben Sie Verbindungsinformationen für eine **OleDbConnection** in einer Datei (Universal Data Link, UDL), jedoch müssen dies zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-145">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="f1eaa-146">UDL-Dateien sind nicht verschlüsselt und machen Informationen zur Verbindungszeichenfolge im Klartext verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-146">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="f1eaa-147">Da es sich bei einer UDL-Datei um eine externe Ressource der Anwendung handelt, kann sie nicht mit .NET Framework gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-147">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="f1eaa-148">Herstellen einer Verbindung mit einer ODBC-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f1eaa-148">Connecting to an ODBC Data Source</span></span>  
 <span data-ttu-id="f1eaa-149">Die .NET Framework-Datenanbieter für ODBC stellt Verbindungen mit verfügbar gemachten Datenquellen mithilfe von ODBC mit dem **OdbcConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-149">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="f1eaa-150">Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für ODBC wurde so konzipiert, dass es weitestgehend mit dem ODBC-Verbindungszeichenfolgenformat übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-150">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="f1eaa-151">Sie können auch einen ODBC-Datenquellennamen (DSN, Data Source Name) angeben.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-151">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="f1eaa-152">Weitere Informationen zu den **OdbcConnection** , finden Sie unter den <xref:System.Data.Odbc.OdbcConnection>.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-152">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="f1eaa-153">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer ODBC-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-153">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =   
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="f1eaa-154">Herstellen einer Verbindung mit einer Oracle-Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f1eaa-154">Connecting to an Oracle Data Source</span></span>  
 <span data-ttu-id="f1eaa-155">Die .NET Framework-Datenanbieter für Oracle stellt Verbindungen mit Oracle-Datenquellen mithilfe der **OracleConnection** Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-155">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="f1eaa-156">Das Verbindungszeichenfolgenformat des .NET Framework-Datenanbieters für Oracle wurde so konzipiert, dass es weitestgehend mit dem Verbindungszeichenfolgenformat des OLE DB-Anbieters für Oracle (MSDAORA) übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-156">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="f1eaa-157">Weitere Informationen zu den **OracleConnection**, finden Sie unter den <xref:System.Data.OracleClient.OracleConnection>.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-157">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="f1eaa-158">Im folgenden Codebeispiel wird veranschaulicht, wie eine Verbindung mit einer Oracle-Datenquelle erstellt und geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="f1eaa-158">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =   
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1eaa-159">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f1eaa-159">See also</span></span>

- [<span data-ttu-id="f1eaa-160">Aufbauen der Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="f1eaa-160">Connecting to a Data Source</span></span>](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [<span data-ttu-id="f1eaa-161">Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f1eaa-161">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="f1eaa-162">OLE DB-, ODBC- und Oracle-Verbindungspooling</span><span class="sxs-lookup"><span data-stu-id="f1eaa-162">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)
- [<span data-ttu-id="f1eaa-163">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="f1eaa-163">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
