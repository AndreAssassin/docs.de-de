---
title: Bekannte Probleme in SqlClient für Entity Framework
ms.date: 03/30/2017
ms.assetid: 48fe4912-4d0f-46b6-be96-3a42c54780f6
ms.openlocfilehash: 0a6fec7e2d129523e5f68955e51ac50154cb58df
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64631731"
---
# <a name="known-issues-in-sqlclient-for-entity-framework"></a>Bekannte Probleme in SqlClient für Entity Framework
In diesem Abschnitt werden bekannte Probleme im Zusammenhang mit dem .NET Framework-Datenanbieter für SQL Server (SqlClient) beschrieben.  
  
## <a name="trailing-spaces-in-string-functions"></a>Nachfolgende Leerzeichen in Zeichenfolgenfunktionen  
 SQL Server ignoriert nachfolgende Leerzeichen in Zeichenfolgenwerten. Deshalb kann die Übergabe von nachfolgenden Leerzeichen in der Zeichenfolge zu unvorhersehbaren Ergebnissen und sogar zu Fehlern führen.  
  
 Wenn Sie nachfolgende Leerzeichen in der Zeichenfolge haben müssen, sollten Sie ein Leerzeichen am Ende anfügen, damit SQL Server die Zeichenfolge nicht abtrennt. Wenn die nachfolgenden Leerzeichen nicht benötigt werden, sollten sie vor der Übergabe an die Abfragepipeline abgetrennt werden.  
  
## <a name="right-function"></a>RIGHT-Funktion  
 Wenn ein Wert, der nicht `null` ist, als erstes Argument und 0 als zweites Argument an `RIGHT(nvarchar(max)`, 0`)` oder `RIGHT(varchar(max)`, 0`)` übergeben wird, wird der Wert `NULL` anstelle einer Zeichenfolge, die `empty` ist, zurückgegeben.  
  
## <a name="cross-and-outer-apply-operators"></a>CROSS- und OUTER APPLY-Operatoren  
 CROSS- und OUTER APPLY-Operatoren wurden in [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] eingeführt. In einigen Fällen liefert die Abfragepipeline möglicherweise eine Transact-SQL-Anweisung, die CROSS APPLY- und/oder OUTER APPLY-Operatoren enthält. Da einige Back-End-Anbieter, einschließlich SQL Server-Versionen älter als [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)], diese Operatoren nicht unterstützen, solche Abfragen können nicht auf diesen Back-End-Anbietern nicht ausgeführt werden.  
  
 Dies sind einige typische Szenarios, die möglicherweise zum Auftreten von CROSS APPLY- und/oder OUTER APPLY-Operatoren in der Ausgabeabfrage führen:  
  
- Eine korrelierte Unterabfrage mit Paging.  
  
- Ein `AnyElement` über einer korrelierten Unterabfrage oder über einer von der Navigation erzeugten Auflistung.  
  
- LINQ-Abfragen, in denen Gruppierungsmethoden verwendet werden, die einen Elementselektor akzeptieren.  
  
- Eine Abfrage, in der ein CROSS APPLY oder ein OUTER APPLY explizit angegeben wird  
  
- Eine Abfrage, die über ein DEREF-Konstrukt über einem REF-Konstrukt verfügt.  
  
## <a name="skip-operator"></a>SKIP-Operator  
 Bei Verwendung von [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)], Verwendung von SKIP mit ORDER BY auf Nichtschlüsselspalten möglicherweise falsche Ergebnisse zurück. Es kann vorkommen, dass mehr als die angegebene Anzahl von Zeilen übersprungen wird, wenn die Nichtschlüsselspalte Daten doppelt enthält. Der Grund dafür ist die Übersetzung von SKIP für [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)]. Z. B. in der folgenden Abfrage ist mehr als fünf Zeilen übersprungen werden Wenn `E.NonKeyColumn` Werte doppelt enthält:  
  
```  
SELECT [E] FROM Container.EntitySet AS [E] ORDER BY [E].[NonKeyColumn] DESC SKIP 5L  
```  
  
## <a name="targeting-the-correct-sql-server-version"></a>Verwenden der richtigen SQL Server-Version  
 Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Ziele der [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] Abfrage auf Grundlage von SQL Server-Version, die im angegebenen die `ProviderManifestToken` Attribut des Schemaelements in der Speichermodelldatei (SSDL). Diese Version unterscheidet sich möglicherweise von der tatsächlichen SQL Server-Version, mit der Sie verbunden sind. Wenn Sie beispielsweise SQL Server 2005 verwenden, aber das `ProviderManifestToken`-Attribut auf 2008 festgelegt ist, wird die generierte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)]-Abfrage möglicherweise nicht auf dem Server ausgeführt. Beispielsweise wird eine Abfrage, in der die in SQL Server 2008 eingeführten neuen Datums-/Zeittypen verwendet werden, nicht auf früheren Versionen von SQL Server ausgeführt. Bei Verwendung von SQL Server 2005, aber das `ProviderManifestToken` -Attributsatz auf 2000, die generierte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] Abfrage möglicherweise weniger optimiert ist, oder erhalten Sie möglicherweise eine Ausnahme, die besagt, dass die Abfrage nicht unterstützt wird. Weitere Informationen finden Sie oben im Abschnitt über die CROSS- und OUTER APPLY-Operatoren.  
  
 Bestimmte Datenbankverhaltensweisen hängen vom festgelegten Kompatibilitätsgrad der Datenbank ab. Wenn das `ProviderManifestToken`-Attribut auf 2005 festgelegt ist und Sie über die SQL Server-Version 2005 verfügen, der Kompatibilitätsgrad einer Datenbank jedoch auf "80" (SQL Server 2000) festgelegt ist, zielt das erzeugte [!INCLUDE[tsql](../../../../../includes/tsql-md.md)] zwar auf SQL Server 2005 ab, wird aber aufgrund der Einstellung für den Kompatibilitätsgrad möglicherweise nicht wie erwartet ausgeführt. Zum Beispiel geht möglicherweise die Sortierung verloren, wenn ein Spaltenname in der ORDER BY-Liste einem Spaltennamen im Selektor entspricht.  
  
## <a name="nested-queries-in-projection"></a>Geschachtelte Abfragen in Projektion  
 Geschachtelte Abfragen in einer Projektionsklausel könnten auf dem Server in Abfragen des kartesischen Produkts übersetzt werden. Dies kann auf einigen Back-End-Servern, einschließlich SLQ Server der sehr großen TempDB-Tabelle führen. Dies kann die Serverleistung beeinträchtigen.  
  
 Im Folgenden sehen Sie ein Beispiel für eine geschachtelte Abfrage in einer Projektionsklausel:  
  
```  
SELECT c, (SELECT c, (SELECT c FROM AdventureWorksModel.Vendor AS c  ) As Inner2 FROM AdventureWorksModel.JobCandidate AS c  ) As Inner1 FROM AdventureWorksModel.EmployeeDepartmentHistory AS c  
```  
  
## <a name="server-generated-guid-identity-values"></a>Servergenerierte GUID-Identitätswerte  
 [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt servergenerierte GUID-Typidentitätswerte, aber der Anbieter muss die Rückgabe von servergenerierten Identitätswerten nach dem Einfügen einer Zeile unterstützen. Ab SQL Server 2005, können Sie den servergenerierten GUID-Typ in einer SQL Server-Datenbank durch Zurückgeben der [OUTPUT-Klausel](https://go.microsoft.com/fwlink/?LinkId=169400) .  
  
## <a name="see-also"></a>Siehe auch

- [SqlClient für Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
- [Bekannte Probleme von und Überlegungen zu LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/known-issues-and-considerations-in-linq-to-entities.md)
