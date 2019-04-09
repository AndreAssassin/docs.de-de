---
title: Transaktionen und Parallelität
ms.date: 03/30/2017
ms.assetid: f46570de-9e50-4fe6-8710-a8c31fa8569b
ms.openlocfilehash: ba857031a54374ee295c2bfd724e7fb8651b7c1f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59174693"
---
# <a name="transactions-and-concurrency"></a>Transaktionen und Parallelität
Eine Transaktion besteht aus einem einzelnen Befehl oder einer Gruppe von Befehlen, die als Paket ausgeführt werden. Mit Transaktionen können Sie mehrere Operationen in einem Arbeitsschritt zusammenfassen. Wenn an einer Stelle in der Transaktion ein Fehler auftritt, kann für alle Updates ein Rollback zum Zustand vor der Transaktion ausgeführt werden.  
  
 Eine Transaktion muss zur Gewährleistung der Datenkonsistenz die folgenden vier Kriterien, die so genannten ACID-Kriterien, erfüllen: Atomicity (Atomarität), Consistency (Konsistenz), Isolation und Durability (Dauerhaftigkeit). Die meisten relationalen Datenbanksysteme (z. B. Microsoft SQL Server) unterstützen Transaktionen, indem sie für Update-, Einfüge- oder Löschvorgänge, die durch eine Clientanwendung ausgeführt werden, entsprechende Sperr-, Protokollierungs- und Transaktionsverwaltungsfunktionen bereitstellen.  
  
> [!NOTE]
>  Transaktionen, an denen mehrere Ressourcen beteiligt sind, können die Parallelität senken, wenn Sperren zu lang gehalten werden. Halten Sie Transaktionen daher so kurz wie möglich.  
  
 Wenn an einer Transaktion mehrere Tabellen in derselben Datenbank oder auf demselben Server beteiligt sind, bieten explizite Transaktionen in gespeicherten Prozeduren oft eine bessere Leistung. Transaktionen in gespeicherten SQL Server-Prozeduren können Sie mithilfe der Transact-SQL-Anweisungen `BEGIN TRANSACTION`, `COMMIT TRANSACTION` und `ROLLBACK TRANSACTION` erstellen. Weitere Informationen dazu finden Sie in der SQL Server-Onlinedokumentation.  
  
 Transaktionen, die im Zusammenhang mit anderen Ressourcen-Manager, z. B. Transaktionen zwischen SQL Server und Oracle, erfordern eine verteilte Transaktion.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Lokale Transaktionen](../../../../docs/framework/data/adonet/local-transactions.md)  
 Zeigt, wie Transaktionen für eine Datenbank ausgeführt werden können.  
  
 [Verteilte Transaktionen](../../../../docs/framework/data/adonet/distributed-transactions.md)  
 Beschreibt die Ausführung von verteilten Transaktionen in ADO.NET.  
  
 [System.Transactions-Integration in SQL Server](../../../../docs/framework/data/adonet/system-transactions-integration-with-sql-server.md)  
 Beschreibt <xref:System.Transactions> Integration in SQL Server für die Arbeit mit verteilten Transaktionen.  
  
 [Optimistische Nebenläufigkeit](../../../../docs/framework/data/adonet/optimistic-concurrency.md)  
 Beschreibt die vollständige und die eingeschränkte Parallelität und wie Sie auf Parallelitätsverletzungen testen können.  
  
## <a name="see-also"></a>Siehe auch

- [Transaktionsgrundlagen](../../../../docs/framework/data/transactions/transaction-fundamentals.md)
- [Aufbauen der Verbindung zu einer Datenquelle](../../../../docs/framework/data/adonet/connecting-to-a-data-source.md)
- [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- ["DataAdapters" und "DataReaders"](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [DbProviderFactories](../../../../docs/framework/data/adonet/dbproviderfactories.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
