---
title: SqlClient für Entity Framework
ms.date: 03/30/2017
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
ms.openlocfilehash: d81499961e7e47bba3b2594ddddd192c87a4a936
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879116"
---
# <a name="sqlclient-for-the-entity-framework"></a>SqlClient für Entity Framework
Dieser Abschnitt beschreibt den .NET Framework-Datenanbieter für SQL Server (SqlClient), der dem Entity Framework die Arbeit mit Microsoft SQL Server ermöglicht.  
  
## <a name="provider-schema-attribute"></a>Anbieterschemaattribut  
 `Provider` ist ein Attribut des `Schema`-Elements der Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL).  
  
 Um SqlClient zu verwenden, weisen Sie dem `Provider`-Attribut des `Schema`-Elements die Zeichenfolge "System.Data.SqlClient" zu.  
  
## <a name="providermanifesttoken-schema-attribute"></a>'ProviderManifestToken'-Schemaattribut  
 Das `ProviderManifestToken`-Element ist ein erforderliches Attribut des `Schema`-Elements. Dieses Token wird verwendet, um das Anbietermanifest für Offlineszenarien zu laden. Weitere Informationen zu `ProviderManifestToken` Attribut, finden Sie unter [Schema-Element (SSDL)](/ef/ef6/modeling/designer/advanced/edmx/ssdl-spec#schema-element-ssdl).  
  
 SqlClient kann als Datenanbieter für verschiedene Versionen von SQL Server verwendet werden. Diese Versionen haben verschiedene Funktionen. Beispielsweise unterstützt [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] die mit `varchar(max)` eingeführten Typen `nvarchar(max)` und [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] nicht.  
  
 SqlClient erzeugt und akzeptiert die folgenden Anbietermanifesttoken für die verschiedenen Versionen von SQL Server.  
  
|SQL Server 2000|SQL Server 2005|SQL Server 2008|  
|-|-|-|  
|2000|2005|2008|  
  
> [!NOTE]
>  Beginnend mit Visual Studio 2010 die [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100)) SQL Server 2000 nicht unterstützt.  
  
## <a name="provider-namespace-name"></a>Anbieternamespacename  
 Alle Anbieter müssen einen Namespace angeben. Anhand dieser Eigenschaft ermittelt Entity Framework, welches Präfix von diesem Anbieter für spezifische Konstrukte wie Typen und Funktionen verwendet wird. Der Namespace für SqlClient-Anbietermanifeste lautet `SqlServer`. Weitere Informationen zu Namespaces finden Sie unter [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).  
  
## <a name="types"></a>Typen  
 Der SqlClient-Anbieter für das Entity Framework stellt Zuordnungsinformationen zwischen Typen des konzeptionellen Modells und SQL Server-Typen bereit. Weitere Informationen finden Sie unter [SqlClient für Entity Framework-Typen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).  
  
## <a name="functions"></a>Funktionen  
 Der SqlClient-Anbieter für das Entity Framework definiert die Liste der vom Anbieter unterstützten Funktionen. Eine Liste der unterstützten Funktionen, finden Sie unter [SqlClient für Entity Framework-Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SqlClient für Entity Framework-Funktionen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [SqlClient für Entity Framework-Typen](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [Bekannte Probleme in SqlClient für Entity Framework](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a>Siehe auch

- [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
- [Sprachreferenz](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)
- [Bekannte Probleme in SqlClient-Anbieter für Entitätsframework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
