---
title: ODBC-Datentypzuordnungen
ms.date: 03/30/2017
ms.assetid: 43c35d32-831d-480f-a150-78f7e869d17f
ms.openlocfilehash: 8165ab933352394e29cbe93a9e8ba64267f8ae60
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772215"
---
# <a name="odbc-data-type-mappings"></a>ODBC-Datentypzuordnungen
In der folgenden Tabelle ist der hergeleitete [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ für Datentypen vom .NET Framework-Datenanbieter für ODBC (<xref:System.Data.Odbc>) dargestellt. Die typisierten Accessormethoden für den <xref:System.Data.Odbc.OdbcDataReader> sind ebenfalls aufgeführt.  
  
|ODBC-Typ|[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typ|Typisierter [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Accessor|  
|---------------|----------------------------------------------------------------------|--------------------------------------------------------------------------------|  
|SQL_BIGINT|Int64|GetInt64()|  
|SQL_BINARY|Byte[]|GetBytes()|  
|SQL_BIT|Boolesch|GetBoolean()|  
|SQL_CHAR|Zeichenfolge<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_DECIMAL|Decimal|GetDecimal()|  
|SQL_DOUBLE|Double|GetDouble()|  
|SQL_GUID|GUID|GetGuid()|  
|SQL_INTEGER|Int32|GetInt32()|  
|SQL_LONG_VARCHAR|Zeichenfolge<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_LONGVARBINARY|Byte[]|GetBytes()|  
|SQL_NUMERIC|Decimal|GetDecimal()|  
|SQL_REAL|Single|GetFloat()|  
|SQL_SMALLINT|Int16|GetInt16()|  
|SQL_TINYINT|Byte|GetByte()|  
|SQL_TYPE_TIMES|DateTime|GetDateTime()|  
|SQL_TYPE_TIMESTAMP|DateTime|GetDateTime()|  
|SQL_VARBINARY|Byte[]|GetBytes()|  
|SQL_WCHAR|Zeichenfolge<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WLONGVARCHAR|Zeichenfolge<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
|SQL_WVARCHAR|Zeichenfolge<br /><br /> Char[]|GetString()<br /><br /> GetChars()|  
  
## <a name="see-also"></a>Siehe auch

- [Abrufen und Ändern von Daten in ADO.NET](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
