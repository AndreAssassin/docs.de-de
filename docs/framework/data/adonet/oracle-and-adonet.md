---
title: Oracle und ADO.NET
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8ee8e389-53cf-45cf-80bd-1df63ef34f2e
ms.openlocfilehash: ce92705d22edfc832e894dd2feaafcd11088bf26
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772020"
---
# <a name="oracle-and-adonet"></a>Oracle und ADO.NET
> [!NOTE]
>  Die Typen in <xref:System.Data.OracleClient> sind veraltet. Die Typen werden in der aktuellen .NET Framework-Version weiterhin unterstützt, die Unterstützung wird jedoch in einem zukünftigen Release eingestellt. Microsoft empfiehlt, einen anderen Oracle-Anbieter zu verwenden.  
  
 In diesem Abschnitt werden spezifische Funktionen und Verhaltensweisen des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters für Oracle beschrieben.  
  
 Der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Oracle ermöglicht über die OCI (Oracle Call Interface), die Bestandteil der Oracle Client-Software ist, den Zugriff auf eine Oracle-Datenbank. Die Funktionalität des Datenanbieters konzipiert ist vergleichbar mit wird die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Datenanbieter für SQL Server, OLE DB und ODBC.  
  
 Damit der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieter für Oracle in einer Anwendung verwendet werden kann, muss die Anwendung wie folgt auf den <xref:System.Data.OracleClient>-Namespace verweisen:  
  
```vb  
Imports System.Data.OracleClient  
```  
  
```csharp  
using System.Data.OracleClient;  
```  
  
 Außerdem müssen Sie beim Kompilieren des Codes einen Verweis auf die DLL-Datei hinzufügen. Wenn Sie z. B. ein C#-Programm kompilieren, muss Ihre Befehlszeile Folgendes beinhalten:  
  
```  
csc /r:System.Data.OracleClient.dll  
```  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Systemanforderungen](../../../../docs/framework/data/adonet/system-requirements-for-the-dotnet-data-provider-for-oracle.md)  
 Benennt die Anforderungen, die für die Verwendung des [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Datenanbieters für Oracle erfüllt sein müssen, und beschreibt eine Reihe von Punkten, die bei dessen Verwendung zu beachten sind.  
  
 [Oracle-BFILEs](../../../../docs/framework/data/adonet/oracle-bfiles.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleBFile>-Klasse, die zum Arbeiten mit dem BFILE-Datentyp von Oracle verwendet wird.  
  
 [Oracle-LOBs](../../../../docs/framework/data/adonet/oracle-lobs.md)  
 Beschreibt die <xref:System.Data.OracleClient.OracleLob>-Klasse, die zum Arbeiten mit dem LOB-Datentyp von Oracle verwendet wird.  
  
 [Oracle-REF CURSORs](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 Beschreibt die Unterstützung für den REF CURSOR-Datentyp von Oracle.  
  
 [OracleTypes](../../../../docs/framework/data/adonet/oracletypes.md)  
 Beschreibt Strukturen, die zum Arbeiten mit Oracle-Datentypen verwendet werden können, z. B. <xref:System.Data.OracleClient.OracleNumber> und <xref:System.Data.OracleClient.OracleString>.  
  
 [Oracle-Sequenzen](../../../../docs/framework/data/adonet/oracle-sequences.md)  
 Beschreibt die Unterstützung für das Abrufen der servergenerierten Oracle-Sequenz-Schlüsselwerte.  
  
 [Oracle-Datentypzuordnungen](../../../../docs/framework/data/adonet/oracle-data-type-mappings.md)  
 Listet Oracle-Datentypen und ihre Zuordnungen zum <xref:System.Data.OracleClient.OracleDataReader> auf.  
  
 [Verteilte Oracle-Transaktionen](../../../../docs/framework/data/adonet/oracle-distributed-transactions.md)  
 Beschreibt, wie das <xref:System.Data.OracleClient.OracleConnection>-Objekt automatisch in einer vorhandenen verteilten Transaktion aufgelistet wird, wenn es ermittelt, dass eine Transaktion aktiv ist.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sichern von ADO.NET-Anwendungen](../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 Beschreibt sichere Codierungstechniken bei der Verwendung von [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)].  
  
 [DataSets, DataTables und DataViews](../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 Beschreibt das Erstellen und Verwenden von `DataSets`, typisierten `DataSets`, `DataTables` und `DataViews`.  
  
 [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)  
 Beschreibt das Arbeiten mit Daten in ADO.NET.  
  
 [SQL Server und ADO.NET](../../../../docs/framework/data/adonet/sql/index.md)  
 Beschreibt das Arbeiten mit Funktionen und Funktionalität, die spezifisch für SQL Server sind.  
  
 [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)  
 Beschreibt generische Klassen, mit deren Hilfe in [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] anbieterunabhängiger Code geschrieben werden kann.  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET](../../../../docs/framework/data/adonet/index.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
