---
title: System.DateTimeOffset-Methoden
ms.date: 03/30/2017
ms.assetid: 25b3e5c0-7603-4a70-b3e5-2149e3da69a2
ms.openlocfilehash: 2e29cf02d4f7e8004782264bf940bb1faf393269
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781548"
---
# <a name="systemdatetimeoffset-methods"></a>System.DateTimeOffset-Methoden
Nach der Zuordnung im Objektmodell oder in der externen Zuordnungsdatei können Sie mit LINQ to SQL die meisten der <xref:System.DateTimeOffset?displayProperty=nameWithType>-Methoden, -Operatoren und -Eigenschaften innerhalb Ihrer LINQ to SQL-Abfragen aufrufen.  
  
 Es werden nur die Methoden nicht unterstützt, die von <xref:System.Object?displayProperty=nameWithType> erben und im Kontext von LINQ to SQL-Abfragen keinen Sinn ergeben, z. B. `Finalize`, `GetHashCode`, `GetType` und `MemberwiseClone`. Diese Methoden werden nicht unterstützt, da sie von LINQ to SQL für die Ausführung auf dem SQL Server nicht übersetzt werden können.  
  
> [!NOTE]
> Für die <xref:System.DateTimeOffset?displayProperty=nameWithType>-Struktur der Common Language Runtime (CLR) und deren Zuordnung zu einer SQL-`DATETIMEOFFSET`-Spalte mit LINQ to SQL ist .NET Framework 3.5 SP1 oder höher erforderlich. Die SQL-`DATETIMEOFFSET`-Spalte ist nur in Microsoft SQL Server 2008 und höher verfügbar.  
  
## <a name="sqlmethods-date-and-time-methods"></a>Datums- und Uhrzeitmethoden von SQLMethods  
 Zusätzlich zu den Methoden der <xref:System.DateTimeOffset>-Struktur werden von LINQ to SQL zum Arbeiten mit Datums- und Uhrzeitangaben die in der folgenden Tabelle aufgeführten Methoden der <xref:System.Data.Linq.SqlClient.SqlMethods?displayProperty=nameWithType>-Klasse bereitgestellt.  
  
||||  
|-|-|-|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffDay%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMillisecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffNanosecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffHour%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMinute%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffSecond%2A>|  
|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMicrosecond%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffMonth%2A>|<xref:System.Data.Linq.SqlClient.SqlMethods.DateDiffYear%2A>|  
  
## <a name="see-also"></a>Siehe auch

- [Abfragekonzepte](query-concepts.md)
- [Erstellen des Objektmodells](creating-the-object-model.md)
- [SQL-CLR-Typenzuordnung](sql-clr-type-mapping.md)
