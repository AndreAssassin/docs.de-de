---
title: Große UDTs
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 420ae24e-762b-4e09-b4c3-2112c470ee49
ms.openlocfilehash: 97df0bee10440dd03f07b980589d9dda85ce121e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69909882"
---
# <a name="large-udts"></a>Große UDTs
Mithilfe benutzerdefinierter Typen (User-Defined Types, UDTs) können Entwickler das Skalartypsystem des Servers erweitern, indem sie CLR (Common Language Runtime)-Objekte in einer SQL Server-Datenbank speichern. UDTs können mehrere Elemente enthalten und Verhaltensweisen aufweisen, wodurch sie sich von den herkömmlichen Aliasdatentypen unterscheiden, die nur aus einem SQL Server-Systemdatentyp bestehen.  
  
> [!NOTE]
> Sie müssen .NET Framework 3.5 SP1 (oder höher) installieren, um die Vorteile der erweiterten SqlClient-Unterstützung für große UDTs nutzen zu können.  
  
 Bisher waren UDTs auf eine maximale Größe von 8 Kilobytes beschränkt. In SQL Server 2008 besteht diese Beschränkung für UDTs mit dem <xref:Microsoft.SqlServer.Server.Format.UserDefined>-Format nicht mehr.  
  
 Eine vollständige Dokumentation zu benutzerdefinierten Typen finden Sie in der SQL Server-Onlinedokumentation für die von Ihnen verwendete SQL Server-Version.  
  
 **SQL Server Books Online (SQL Server-Onlinedokumentation)**  
  
1. [Benutzerdefinierte CLR-Typen](https://go.microsoft.com/fwlink/?LinkId=98366)  
  
## <a name="retrieving-udt-schemas-using-getschema"></a>Abrufen von UDT-Schemas mit 'GetSchema'  
 Die <xref:System.Data.SqlClient.SqlConnection.GetSchema%2A>-Methode von <xref:System.Data.SqlClient.SqlConnection> gibt Informationen zum Datenbankschema in einer <xref:System.Data.DataTable> zurück. Weitere Informationen finden Sie unter [SQL Server Schema](../../../../../docs/framework/data/adonet/sql-server-schema-collections.md)Auflistungen.  
  
### <a name="getschematable-column-values-for-udts"></a>'GetSchemaTable'-Spaltenwerte für UDTs  
 Die <xref:System.Data.SqlClient.SqlDataReader.GetSchemaTable%2A>-Methode eines <xref:System.Data.SqlClient.SqlDataReader> gibt eine <xref:System.Data.DataTable> mit Beschreibungen der Spaltenmetadaten zurück. In der folgenden Tabelle werden die Unterschiede bezüglich der Spaltenmetadaten für große UDTs zwischen SQL Server 2005 und SQL Server 2008 erläutert.  
  
|SqlDataReader-Spalte|SQL Server 2005|SQL Server 2008 und höher|  
|--------------------------|---------------------|-------------------------------|  
|`ColumnSize`|Unterschiedlich|Unterschiedlich|  
|`NumericPrecision`|255|255|  
|`NumericScale`|255|255|  
|`DataType`|`Byte[]`|UDT-Instanz|  
|`ProviderSpecificDataType`|`SqlTypes.SqlBinary`|UDT-Instanz|  
|`ProviderType`|21 (`SqlDbType.VarBinary`)|29 (`SqlDbType.Udt`)|  
|`NonVersionedProviderType`|29 (`SqlDbType.Udt`)|29 (`SqlDbType.Udt`)|  
|`DataTypeName`|`SqlDbType.VarBinary`|Der dreiteilige Name, der als *Database.* Schema Name. tyname angegeben wird.|  
|`IsLong`|Unterschiedlich|Unterschiedlich|  
  
## <a name="sqldatareader-considerations"></a>Überlegungen zu "SqlDataReader"  
 <xref:System.Data.SqlClient.SqlDataReader> wurde ab SQL Server 2008 erweitert und unterstützt nun das Abrufen großer UDT-Werte. Die Verarbeitung großer UDT-Werte durch einen <xref:System.Data.SqlClient.SqlDataReader> ist von der verwendeten SQL Server-Version sowie der in der Verbindungszeichenfolge angegebenen `Type System Version` abhängig. Weitere Informationen finden Sie unter <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.  
  
 Die folgenden <xref:System.Data.SqlClient.SqlDataReader>-Methoden geben anstelle eines UDTs <xref:System.Data.SqlTypes.SqlBinary> zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificFieldType%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetProviderSpecificValues%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetSqlValues%2A>  
  
 Die folgenden Methoden geben anstelle eines UDTs ein `Byte[]`-Array zurück, wenn `Type System Version` auf SQL Server 2005 festgelegt ist:  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValue%2A>  
  
- <xref:System.Data.SqlClient.SqlDataReader.GetValues%2A>  
  
 Beachten Sie, dass für die aktuelle Version von ADO.NET keine Konvertierungen vorgenommen werden.  
  
## <a name="specifying-sqlparameters"></a>Angeben von 'SqlParameters'  
 Die folgenden <xref:System.Data.SqlClient.SqlParameter>-Eigenschaften wurden für die Verwendung mit großen UDTs erweitert.  
  
|SqlParameter-Eigenschaft|Beschreibung|  
|---------------------------|-----------------|  
|<xref:System.Data.SqlClient.SqlParameter.Value%2A>|Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest. Der Standardwert ist NULL. Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.|  
|<xref:System.Data.SqlClient.SqlParameter.SqlValue%2A>|Ruft ein Objekt ab, das den Wert des Parameters darstellt, oder legt dieses fest. Der Standardwert ist NULL. Die Eigenschaft kann `SqlBinary`, `Byte[]` oder ein verwaltetes Objekt sein.|  
|<xref:System.Data.SqlClient.SqlParameter.Size%2A>|Ruft die Größe des aufzulösenden Parameterwerts ab oder legt diese Größe fest. Der Standardwert ist 0. Die Eigenschaft kann eine ganze Zahl sein, die für die Größe des Parameterwerts steht. Bei großen UDTs kann es sich um die tatsächliche Größe des UDT handeln. Ist die Größe unbekannt, lautet der Wert "-1".|  
  
## <a name="retrieving-data-example"></a>Abrufen eines Datenbeispiels  
 Im folgenden Codefragment wird gezeigt, wie Daten großer UDTs abgerufen werden können. Die `connectionString`-Variable setzt eine gültige Verbindung mit einer SQL Server-Datenbank voraus. Die `commandString`-Variable setzt eine gültige SELECT-Anweisung voraus, in der die Primärschlüsselspalte zuerst aufgelistet ist.  
  
```csharp  
using (SqlConnection connection = new SqlConnection(   
    connectionString, commandString))  
{  
  connection.Open();  
  SqlCommand command = new SqlCommand(commandString);  
  SqlDataReader reader = command.ExecuteReader();  
  while (reader.Read())  
  {  
    // Retrieve the value of the Primary Key column.  
    int id = reader.GetInt32(0);  
  
    // Retrieve the value of the UDT.  
    LargeUDT udt = (LargeUDT)reader[1];  
  
    // You can also use GetSqlValue and GetValue.  
    // LargeUDT udt = (LargeUDT)reader.GetSqlValue(1);  
    // LargeUDT udt = (LargeUDT)reader.GetValue(1);  
  
    Console.WriteLine(  
     "ID={0} LargeUDT={1}", id, udt);  
  }  
reader.close  
}  
```  
  
```vb  
Using connection As New SqlConnection( _  
    connectionString, commandString)  
    connection.Open()  
    Dim command As New SqlCommand(commandString, connection)  
    Dim reader As SqlDataReader  
    reader = command.ExecuteReader  
  
    While reader.Read()  
      ' Retrieve the value of the Primary Key column.  
      Dim id As Int32 = reader.GetInt32(0)  
  
      ' Retrieve the value of the UDT.  
      Dim udt As LargeUDT = CType(reader(1), LargeUDT)  
  
     ' You can also use GetSqlValue and GetValue.  
     ' Dim udt As LargeUDT = CType(reader.GetSqlValue(1), LargeUDT)  
     ' Dim udt As LargeUDT = CType(reader.GetValue(1), LargeUDT)  
  
      ' Print values.  
      Console.WriteLine("ID={0} LargeUDT={1}", id, udt)  
    End While  
    reader.Close()  
End Using  
```  
  
## <a name="see-also"></a>Siehe auch

- [Konfigurieren von Parametern und Parameterdatentypen](../../../../../docs/framework/data/adonet/configuring-parameters-and-parameter-data-types.md)
- [Abrufen von Datenbankschemainformationen](../../../../../docs/framework/data/adonet/retrieving-database-schema-information.md)
- [SQL Server-Datentypzuordnungen](../../../../../docs/framework/data/adonet/sql-server-data-type-mappings.md)
- [SQL Server Binary and Large-Value Data (Binäre Daten und Daten mit umfangreichen Werten in SQL Server)](../../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
