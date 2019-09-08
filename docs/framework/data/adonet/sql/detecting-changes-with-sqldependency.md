---
title: Ermitteln von Änderungen mit "SqlDependency"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: 3719188064388b00c756dd037d4a475ca6debd13
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70782423"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="d0594-102">Ermitteln von Änderungen mit "SqlDependency"</span><span class="sxs-lookup"><span data-stu-id="d0594-102">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="d0594-103">Ein <xref:System.Data.SqlClient.SqlDependency>-Objekt kann mit einem <xref:System.Data.SqlClient.SqlCommand>-Objekt verknüpft werden, um so Abweichungen zwischen den aktuellen und den ursprünglichen Abfrageergebnissen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="d0594-103">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="d0594-104">Sie können einen Delegaten auch dem `OnChange`-Ereignis zuweisen, das ausgelöst wird, wenn sich die Ergebnisse für einen verknüpften Befehl ändern.</span><span class="sxs-lookup"><span data-stu-id="d0594-104">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="d0594-105">Vor dem Ausführen des Befehls müssen Sie ihm die <xref:System.Data.SqlClient.SqlDependency> zuordnen.</span><span class="sxs-lookup"><span data-stu-id="d0594-105">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="d0594-106">Mit der `HasChanges`-Eigenschaft der <xref:System.Data.SqlClient.SqlDependency> kann auch ermittelt werden, ob sich die Abfrageergebnisse seit dem letzten Abrufen der Daten geändert haben.</span><span class="sxs-lookup"><span data-stu-id="d0594-106">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="d0594-107">Sicherheitsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="d0594-107">Security Considerations</span></span>

<span data-ttu-id="d0594-108">Die Abhängigkeitsinfrastruktur verwendet eine <xref:System.Data.SqlClient.SqlConnection>, die geöffnet wird, wenn <xref:System.Data.SqlClient.SqlDependency.Start%2A> aufgerufen wird, damit Benachrichtigungen über die Änderung der zugrunde liegenden Daten für einen bestimmten Befehl empfangen werden können.</span><span class="sxs-lookup"><span data-stu-id="d0594-108">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="d0594-109">Ob ein Client den Aufruf von `SqlDependency.Start` initiieren kann, wird mit der <xref:System.Data.SqlClient.SqlClientPermission> und Sicherheitsattributen für den Codezugriff gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d0594-109">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="d0594-110">Weitere Informationen finden Sie unter [Aktivieren von Abfrage Benachrichtigungen](enabling-query-notifications.md) und [Code Zugriffssicherheit und ADO.net](../code-access-security.md).</span><span class="sxs-lookup"><span data-stu-id="d0594-110">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="d0594-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d0594-111">Example</span></span>

<span data-ttu-id="d0594-112">Mit den folgenden Schritten können Sie eine Abhängigkeit deklarieren, einen Befehl ausführen und festlegen, dass Sie bei Änderungen des Resultsets benachrichtigt werden möchten:</span><span class="sxs-lookup"><span data-stu-id="d0594-112">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="d0594-113">Initiieren Sie eine `SqlDependency`-Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="d0594-113">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="d0594-114">Erstellen Sie das <xref:System.Data.SqlClient.SqlConnection>-Objekt und das <xref:System.Data.SqlClient.SqlCommand>-Objekt, um eine Verbindung mit dem Server herzustellen und eine Transact-SQL-Anweisung zu definieren.</span><span class="sxs-lookup"><span data-stu-id="d0594-114">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="d0594-115">Erstellen Sie ein neues `SqlDependency`-Objekt, oder verwenden Sie ein vorhandenes, und binden Sie es an das `SqlCommand`-Objekt.</span><span class="sxs-lookup"><span data-stu-id="d0594-115">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="d0594-116">Dadurch wird intern ein <xref:System.Data.Sql.SqlNotificationRequest>-Objekt erstellt und bei Bedarf an das Befehlsobjekt gebunden.</span><span class="sxs-lookup"><span data-stu-id="d0594-116">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="d0594-117">Diese Benachrichtigungsanforderung enthält einen internen Bezeichner zur eindeutigen Kennzeichnung dieses `SqlDependency`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="d0594-117">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="d0594-118">Er startet außerdem auch den Clientlistener, sofern dieser nicht bereits aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="d0594-118">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="d0594-119">Abonnieren Sie einen Ereignishandler für das `OnChange`-Ereignis des `SqlDependency`-Objekts.</span><span class="sxs-lookup"><span data-stu-id="d0594-119">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="d0594-120">Führen Sie den Befehl mit einer der `Execute`-Methoden des `SqlCommand`-Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="d0594-120">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="d0594-121">Da der Befehl an das Benachrichtigungsobjekt gebunden ist, erkennt der Server, dass er eine Benachrichtigung generieren muss, und die Warteschlangeninformation zeigt auf die Abhängigkeitenwarteschlange.</span><span class="sxs-lookup"><span data-stu-id="d0594-121">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="d0594-122">Beenden Sie die `SqlDependency`-Verbindung mit dem Server.</span><span class="sxs-lookup"><span data-stu-id="d0594-122">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="d0594-123">Wenn ein Benutzer anschließend Änderungen an den zugrunde liegenden Daten vornimmt, erkennt Microsoft SQL Server, dass es für eine derartige Änderung eine Benachrichtigung gibt, und übermittelt diese Benachrichtigung über die zugrunde liegende, mit `SqlConnection` erstellte `SqlDependency.Start`.</span><span class="sxs-lookup"><span data-stu-id="d0594-123">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="d0594-124">Der Clientlistener empfängt die Ungültigkeitserklärung.</span><span class="sxs-lookup"><span data-stu-id="d0594-124">The client listener receives the invalidation message.</span></span> <span data-ttu-id="d0594-125">Der Clientlistener sucht dann das zugeordnete `SqlDependency`-Objekt und löst das `OnChange`-Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="d0594-125">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="d0594-126">Das folgende Codefragment zeigt das Entwurfsmuster, das Sie zum Erstellen einer Beispielanwendung verwenden können:</span><span class="sxs-lookup"><span data-stu-id="d0594-126">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

```vb
Sub Initialization()
    ' Create a dependency connection.
    SqlDependency.Start(connectionString, queueName)
End Sub

Sub SomeMethod()
    ' Assume connection is an open SqlConnection.
    ' Create a new SqlCommand object.
    Using command As New SqlCommand( _
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _
      connection)

        ' Create a dependency and associate it with the SqlCommand.
        Dim dependency As New SqlDependency(command)
        ' Maintain the refernce in a class member.
        ' Subscribe to the SqlDependency event.
        AddHandler dependency.OnChange, AddressOf OnDependencyChange

        ' Execute the command.
        Using reader = command.ExecuteReader()
            ' Process the DataReader.
        End Using
    End Using
End Sub

' Handler method
Sub OnDependencyChange(ByVal sender As Object, _
    ByVal e As SqlNotificationEventArgs)
    ' Handle the event (for example, invalidate this cache entry).
End Sub

Sub Termination()
    ' Release the dependency
    SqlDependency.Stop(connectionString, queueName)
End Sub
```

```csharp
void Initialization()
{
    // Create a dependency connection.
    SqlDependency.Start(connectionString, queueName);
}

void SomeMethod()
{
    // Assume connection is an open SqlConnection.

    // Create a new SqlCommand object.
    using (SqlCommand command=new SqlCommand(
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",
        connection))
    {

        // Create a dependency and associate it with the SqlCommand.
        SqlDependency dependency=new SqlDependency(command);
        // Maintain the reference in a class member.

        // Subscribe to the SqlDependency event.
        dependency.OnChange+=new
           OnChangeEventHandler(OnDependencyChange);

        // Execute the command.
        using (SqlDataReader reader = command.ExecuteReader())
        {
            // Process the DataReader.
        }
    }
}

// Handler method
void OnDependencyChange(object sender,
   SqlNotificationEventArgs e )
{
  // Handle the event (for example, invalidate this cache entry).
}

void Termination()
{
    // Release the dependency.
    SqlDependency.Stop(connectionString, queueName);
}
```

## <a name="see-also"></a><span data-ttu-id="d0594-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0594-127">See also</span></span>

- [<span data-ttu-id="d0594-128">Abfragebenachrichtigungen in SQL Server</span><span class="sxs-lookup"><span data-stu-id="d0594-128">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="d0594-129">Übersicht über ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d0594-129">ADO.NET Overview</span></span>](../ado-net-overview.md)
