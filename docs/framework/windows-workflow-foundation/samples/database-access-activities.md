---
title: Datenbankzugriffsaktivitäten
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 2463c3a87be7f7e248572d45e018b72661f4f8c7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59322601"
---
# <a name="database-access-activities"></a>Datenbankzugriffsaktivitäten
Mit Datenbankzugriffsaktivitäten können Sie auf eine Datenbank innerhalb eines Workflows zugreifen. Diese Aktivitäten können Datenbanken abrufen und ändern Sie Informationen sowie über [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) Zugriff auf die Datenbank.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.
>
>  `<InstallDrive>:\WF_WCF_Samples`
>
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie (Downloadseite) auf alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.
>
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>Datenbankaktivitäten
 Die in diesem Beispiel enthaltenen Aktivitäten sind in den folgenden Abschnitten aufgeführt.

## <a name="dbupdate"></a>DbUpdate
 Führt eine SQL-Abfrage aus, die eine Änderung in der Datenbank (Einfügung, Aktualisierung, Löschung und andere Änderungen) vornimmt.

 Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity> ab und verwendet die asynchronen Funktionen dieser Aktivität).

 Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.

 Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.

 Nach der Ausführung von `DbUpdate` wird die Anzahl der betroffenen Datensätze in der `AffectedRecords`-Eigenschaft zurückgegeben.

```
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|Argument|Beschreibung|
|-|-|
|ProviderName|Invarianter Name des ADO.NET-Anbieters. Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.|
|ConnectionString|Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung. Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.|
|ConfigName|Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind. Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.|
|CommandType|Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.|
|Sql|Der auszuführende SQL-Befehl.|
|Parameter|Auflistung der Parameter der SQL-Abfrage.|
|AffectedRecords|Anzahl der vom letzten Vorgang betroffenen Datensätze.|

## <a name="dbqueryscalar"></a>DbQueryScalar
 Führt eine Abfrage aus, die einen einzelnen Wert aus der Datenbank abruft.

 Die Ausführung dieser Klasse ist asynchron (sie leitet sich von <xref:System.Activities.AsyncCodeActivity%601> ab und verwendet die asynchronen Funktionen dieser Aktivität).

 Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.

 Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.

 Nach dem `DbQueryScalar` wird ausgeführt, wird der Skalarwert im zurückgegeben der `Result out` Argument (des Typs `TResult`, d. h. in der Basisklasse definierte <xref:System.Activities.AsyncCodeActivity%601>).

```
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argument|Beschreibung|
|-|-|
|ProviderName|Invarianter Name des ADO.NET-Anbieters. Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.|
|ConnectionString|Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung. Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.|
|ConfigName|Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind. Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.|
|CommandType|Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.|
|Sql|Der auszuführende SQL-Befehl.|
|Parameter|Auflistung der Parameter der SQL-Abfrage.|
|Ergebnis|Skalarwert, der nach Ausführung der Abfrage zurückgegeben wird. Dieses Argument ist vom Typ `TResult`.|

## <a name="dbquery"></a>DbQuery
 Führt eine Abfrage aus, die eine Liste von Objekten abruft. Nachdem die Abfrage ausgeführt wird, wird eine Zuordnungsfunktion ausgeführt (es kann sein <xref:System.Func%601> < `DbDataReader`, `TResult`> oder ein <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>). Diese Zuordnungsfunktion ruft einen Datensatz in einem `DbDataReader` ab und ordnet diesen dem zurückzugebenden Objekt zu.

 Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.

 Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.

 Die Ergebnisse der SQL-Abfrage werden mit einem `DbDataReader` abgerufen. Die Aktivität durchläuft den `DbDataReader` und ordnet die Zeilen im `DbDataReader` einer Instanz von `TResult` zu. Der Benutzer der `DbQuery` Geben Sie den Zuordnungscode können auf zwei Arten ausgeführt werden muss: Verwenden einer <xref:System.Func%601> < `DbDataReader`, `TResult`> oder ein <xref:System.Activities.ActivityFunc%601> < `DbDataReader`, `TResult`>. Im ersten Fall erfolgt die Zuordnung in einem Ausführungsschritt. Diese Variante ist schneller, kann aber nicht in XAML serialisiert werden. Im zweiten Fall erfolgt die Zuordnung in mehreren Schritten. Diese Variante ist möglicherweise langsamer, kann aber in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).

```
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|Argument|Beschreibung|
|-|-|
|ProviderName|Invarianter Name des ADO.NET-Anbieters. Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.|
|ConnectionString|Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung. Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.|
|ConfigName|Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind. Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.|
|CommandType|Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.|
|Sql|Der auszuführende SQL-Befehl.|
|Parameter|Auflistung der Parameter der SQL-Abfrage.|
|Mapper|Zuordnungsfunktion (<xref:System.Func%601><`DbDataReader`, `TResult`>), die einen Datensatz die `DataReader` als Ergebnis der Ausführung der Abfrage abgerufen, und gibt eine Instanz eines Objekts vom Typ `TResult` der hinzugefügtwerden`Result` Auflistung.<br /><br /> In diesem Fall erfolgt die Zuordnung in einem Schritt, kann aber nicht im Designer deklarativ erstellt werden.|
|MapperFunc|Zuordnungsfunktion (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>), die einen Datensatz die `DataReader` als Ergebnis der Ausführung der Abfrage abgerufen, und gibt eine Instanz eines Objekts vom Typ `TResult` der hinzugefügtwerden`Result` Auflistung.<br /><br /> In diesem Fall erfolgt die Zuordnung in mehreren Schritten. Diese Funktion kann in XAML serialisiert und deklarativ erstellt werden (d. h. jede vorhandene Aktivität kann Teil der Zuordnung sein).|
|Ergebnis|Eine Liste mit Objekten, die als Ergebnis der Ausführung der Abfrage und der Zuordnungsfunktion für jeden Datensatz im `DataReader` zurückgegeben wird.|

## <a name="dbquerydataset"></a>DbQueryDataSet
 Führt eine Abfrage aus, die ein <xref:System.Data.DataSet> zurückgibt. Die Ausführung dieser Klasse erfolgt asynchron. Es leitet sich von <xref:System.Activities.AsyncCodeActivity> < `TResult`> und verwendet die asynchronen Funktionen.

 Sie können die Verbindungsinformationen konfigurieren, indem Sie einen invarianten Anbieternamen (`ProviderName`) und die Verbindungszeichenfolge (`ConnectionString`) festlegen oder indem Sie einen Namen zur Konfiguration der Verbindungszeichenfolge (`ConfigFileSectionName`) aus der Anwendungskonfigurationsdatei verwenden.

 Die auszuführende Abfrage wird in der `Sql`-Eigenschaft konfiguriert, und die Parameter werden über die `Parameters`-Auflistung übergeben.

 Nach der `DbQueryDataSet` ausgeführt wird die `DataSet` wird zurückgegeben, der `Result out` Argument (des Typs `TResult`, d. h. in der Basisklasse definierte <xref:System.Activities.AsyncCodeActivity%601>).

```
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Argument|Beschreibung|
|-|-|
|ProviderName|Invarianter Name des ADO.NET-Anbieters. Wenn dieses Argument festgelegt wird, muss `ConnectionString` ebenfalls festgelegt werden.|
|ConnectionString|Die Verbindungszeichenfolge zum Herstellen einer Datenbankverbindung. Wenn dieses Argument festgelegt wird, muss `ProviderName` ebenfalls festgelegt werden.|
|ConfigName|Name des Abschnitts in der Konfigurationsdatei, in dem die Verbindungsinformationen gespeichert sind. Wenn dieses Argument festgelegt wird, sind `ProviderName` und `ConnectionString` nicht erforderlich.|
|CommandType|Der auszuführende <xref:System.Data.Common.DbCommand>-Typ.|
|Sql|Der auszuführende SQL-Befehl.|
|Parameter|Auflistung der Parameter der SQL-Abfrage.|
|Ergebnis|<xref:System.Data.DataSet>, das nach Ausführung der Abfrage zurückgegeben wird.|

## <a name="configuring-connection-information"></a>Konfigurieren von Verbindungsinformationen
 Für alle Datenbankaktivitäten gelten die gleichen Konfigurationsparameter. Für die Konfiguration gibt es zwei Möglichkeiten:

-   `ConnectionString + InvariantName`: Legen Sie den ADO.NET-Anbieter invarianten Namen und die Verbindungszeichenfolge-Zeichenfolge.

    ```
    Activity dbSelectCount = new DbQueryScalar<DateTime>()
    {
        ProviderName = "System.Data.SqlClient",
        ConnectionString = @"Data Source=.\SQLExpress;
                             Initial Catalog=DbActivitiesSample;
                             Integrated Security=True",
        Sql = "SELECT GetDate()"
    };
    ```

-   `ConfigName`: Legen Sie den Namen des Konfigurationsabschnitts, der die Verbindungsinformationen enthält.

    ```xml
    <connectionStrings>
        <add name="DbActivitiesSample"
             providerName="System.Data.SqlClient"
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
      </connectionStrings>
    ```

-   In der Aktivität:

    ```
    Activity dbSelectCount = new DbQueryScalar<int>()
    {
        ConfigName = "DbActivitiesSample",
        Sql = "SELECT COUNT(*) FROM Roles"
    };
    ```

## <a name="running-this-sample"></a>Ausführen des Beispiels

### <a name="setup-instructions"></a>Setupanweisungen
 In diesem Beispiel wird eine Datenbank verwendet. Ein Setup- und Ladeskript (Setup.cmd) wird mit dem Beispiel bereitgestellt. Diese Datei muss über die Eingabeaufforderung ausgeführt werden.

 Das Skript "Setup.cmd" ruft die Skriptdatei "CreateDb.sql" auf, die SQL-Befehle zur Ausführung der folgenden Vorgänge enthält:

-   Erstellen einer Datenbank mit dem Namen DbActivitiesSample

-   Erstellen der Tabelle "Roles"

-   Erstellen der Tabelle "Employees"

-   Einfügen von drei Datensätzen in die Tabelle "Roles"

-   Einfügen von zwölf Datensätzen in die Tabelle "Employees"

##### <a name="to-run-setupcmd"></a>So führen Sie "Setup.cmd" aus

1. Öffnen Sie eine Eingabeaufforderung.

2. Navigieren Sie zum Beispielordner "DbActivities".

3. Geben Sie "setup.cmd" aus, und drücken Sie die EINGABETASTE.

    > [!NOTE]
    >  Setup.cmd versucht, das Beispiel auf der SqlExpress-Instanz auf Ihrem lokalen Computer zu installieren. Wenn Sie es auf einer anderen SQL Server-Instanz installieren möchten, aktualisieren Sie "Setup.cmd" mit dem neuen Instanznamen.

##### <a name="to-uninstall-the-sample-database"></a>So deinstallieren Sie die Beispieldatenbank

1. Führen Sie "Cleanup.cmd" aus dem Beispielordner über eine Eingabeaufforderung aus.

##### <a name="to-run-the-sample"></a>So führen Sie das Beispiel aus

1. Öffnen Sie die Projektmappe in Visual Studio 2010

2. Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu kompilieren.

3. Um das Beispiel ohne Debugging auszuführen, drücken Sie STRG+F5.

> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
