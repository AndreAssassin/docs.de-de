---
title: SQL-Generierung
ms.date: 03/30/2017
ms.assetid: 0e16aa02-d458-4418-a765-58b42aad9315
ms.openlocfilehash: 108a68f74849c7fa1418775c2a37db06d9d947ff
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180568"
---
# <a name="sql-generation"></a>SQL-Generierung
Wenn Sie einen Anbieter für [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] schreiben, müssen Sie [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Befehlsstrukturen in SQL übersetzen, das eine bestimmte Datenbank verstehen kann, z. B. Transact-SQL für SQL Server oder PL/SQL für Oracle. In diesem Abschnitt erfahren Sie, wie eine SQL-Generierungskomponente (für SELECT-Abfragen) für einen [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anbieter entwickelt wird. Informationen zu einfügen, aktualisieren und Löschen von Abfragen, finden Sie unter [Generierung von Änderungen in SQL](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md).  
  
 Um diesen Abschnitt zu verstehen, sollten Sie mit dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]- und dem ADO.NET-Anbietermodell vertraut sein. Außerdem sollten Sie Befehlsstrukturen und <xref:System.Data.Common.CommandTrees.DbExpression> verstehen.  
  
## <a name="the-role-of-the-sql-generation-module"></a>Die Rolle des SQL-Generierungsmoduls  
 Das SQL-Generierungsmodul eines [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Anbieters übersetzt eine angegebene Abfragebefehlsstruktur in eine einzelne SQL SELECT-Anweisung, die für eine SQL:1999-kompatible Datenbank vorgesehen ist. Das generierte SQL sollte so wenige geschachtelte Abfragen wie möglich enthalten. Das SQL-Generierungsmodul sollte die Ausgabeabfrage-Befehlsstruktur nicht vereinfachen. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] führt dies beispielsweise durch das Eliminieren von Joins und das Reduzieren von aufeinander folgenden Filterknoten aus.  
  
 Die <xref:System.Data.Common.DbProviderServices>-Klasse ist der Ausgangspunkt für den Zugriff auf die SQL-Generierungsebene zur Umwandlung von Befehlsstrukturen in <xref:System.Data.Common.DbCommand>.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Form der Befehlsstrukturen](../../../../../docs/framework/data/adonet/ef/the-shape-of-the-command-trees.md)  
  
 [Generieren von SQL aus Befehlsstrukturen – Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)  
  
 [SQL-Generierung im Beispielanbieter](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)  
  
## <a name="see-also"></a>Siehe auch

- [Schreiben eines Entity Framework-Datenanbieters](../../../../../docs/framework/data/adonet/ef/writing-an-ef-data-provider.md)
