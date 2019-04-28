---
title: Systemfunktionen
ms.date: 03/30/2017
ms.assetid: b7c71b58-09e6-44ce-a3e5-a0fdb892fb86
ms.openlocfilehash: 135154d2f5e26cdf7f2e41e8ed2b561bb75f377e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879449"
---
# <a name="system-functions"></a>Systemfunktionen
Der .NET Framework-Datenanbieter für SQL Server (SqlClient) stellt die folgenden Systemfunktionen zur Verfügung:  
  
|Funktion|Beschreibung|  
|--------------|-----------------|  
|`CHECKSUM (` `value`, [`value`, [`value`]]`)`|Gibt den Prüfsummenwert zurück. `CHECKSUM` wurde zum Erstellen von Hashindizes konzipiert.<br /><br /> **Argumente**<br /><br /> `value`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `String`, `Binary`, oder `Guid`. Sie können einen, zwei oder drei Werte angeben.<br /><br /> **Rückgabewert**<br /><br /> Der Absolutwert des angegebenen Ausdrucks.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CHECKSUM(10,100,1000.0)`|  
|`CURRENT_TIMESTAMP ()`|Erzeugt das aktuelle Datum und die Uhrzeit im SQL Server-internen Format für `DateTime`-Werte mit einer Genauigkeit von 7 in SQL Server 2008 und einer Genauigkeit von 3 in SQL Server 2005.<br /><br /> **Rückgabewert**<br /><br /> Das aktuelle Systemdatum und die aktuelle Systemzeit als `DateTime`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_TIMESTAMP()`|  
|`CURRENT_ USER` `()`|Gibt den Namen des aktuellen Benutzers zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein ASCII-`String`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.CURRENT_USER()`|  
|`DATALENGTH` `(` `expression` `)`|Gibt die Anzahl von Bytes zurück, die für die Darstellung eines Ausdrucks verwendet werden.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Die Größe von Eigenschaften als `Int32`.<br /><br /> **Beispiel**<br /><br /> `SELECT VALUE SqlServer.DATALENGTH(P.Name)FROM`<br /><br /> `AdventureWorksEntities.Product AS P`|  
|`HOST_NAME()`|Gibt den Namen der Arbeitsstation zurück.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.HOST_NAME()`|  
|`ISDATE(` `expression` `)`|Ermittelt, ob der eingegebene Ausdruck ein gültiges Datum ist.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISDATE('1/1/2006')`|  
|`ISNUMERIC(` `expression` `)`|Ermittelt, ob ein Ausdruck ein gültiger numerischer Typ ist.<br /><br /> **Argumente**<br /><br /> `expression`: Ein `Boolean`, `Byte`, `Int16`, `Int32`, `Int64`, `Single`, `Decimal`, `Double`, `DateTime`, `Time`, `DateTimeOffset`, `String`, `Binary`, oder `Guid`.<br /><br /> **Rückgabewert**<br /><br /> Eine `Int32`. Eins (1), wenn der eingegebene Ausdruck ein gültiges Datum ist. Andernfalls Null (0).<br /><br /> **Beispiel**<br /><br /> `SqlServer.ISNUMERIC('21')`|  
|`NEWID()`|Erstellt einen eindeutigen Wert vom Typ Guid.<br /><br /> **Rückgabewert**<br /><br /> Ein `Guid`.<br /><br /> **Beispiel**<br /><br /> `SqlServer.NEWID()`|  
|`USER_NAME(` `id` `)`|Gibt den Datenbank-Benutzernamen zur angegebenen ID zurück.<br /><br /> **Argumente**<br /><br /> `expression`: Eine `Int32`-ID, die einem Datenbankbenutzer zugeordnet ist.<br /><br /> **Rückgabewert**<br /><br /> Ein `String` (Unicode).<br /><br /> **Beispiel**<br /><br /> `SqlServer.USER_NAME(0)`|  
  
 Weitere Informationen zu den von SqlClient unterstützten Zeichenfolgenfunktionen finden Sie in der Dokumentation für die SQL Server-Version, die im SqlClient-Anbietermanifest angegeben wurde:  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|---------------------|---------------------|---------------------|  
|[System Funktionen Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115918)|[System Funktionen Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115917)|[Systemfunktionen (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=115919)|  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [SqlClient für Entity Framework-Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)
