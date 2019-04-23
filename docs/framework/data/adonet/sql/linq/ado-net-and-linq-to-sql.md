---
title: ADO.NET und LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 10e60ebd71c4615354c25d3a61a04e9d12d7c800
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59167192"
---
# <a name="adonet-and-linq-to-sql"></a>ADO.NET und LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Technologiefamilie. Es basiert auf den vom [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]-Anbietermodell bereitgestellten Diensten. Sie können daher kombinieren [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] -Code mit vorhandenen [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Anwendungen und migrieren Sie aktuelle [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Lösungen für [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Die folgende Abbildung stellt eine allgemeine Ansicht der Beziehung dar.  
  
 ![LINQ to SQL and ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")  
  
## <a name="connections"></a>Verbindungen  
 Sie können angeben, ein vorhandenes [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Verbindung bei der Erstellung einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>. Alle Vorgänge für die <xref:System.Data.Linq.DataContext> (einschließlich Abfragen) verwenden diese bereitgestellte Verbindung. Wenn die Verbindung bereits geöffnet ist, ist [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] bleibt unverändert, wenn Sie damit fertig sind.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 Sie können stets auf die Verbindung zugreifen und diese selbst beenden, indem Sie die <xref:System.Data.Linq.DataContext.Connection%2A>-Eigenschaft wie im folgenden Code verwenden:  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a>Transaktionen  
 Sie können Ihren <xref:System.Data.Linq.DataContext> mit Ihrer eigenen Datenbanktransaktion ergänzen, wenn Ihre Anwendung die Transaktion bereits initiiert hat und Sie möchten, dass der <xref:System.Data.Linq.DataContext> berücksichtigt wird.  
  
 Die bevorzugte Methode für Transaktionen mit [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] ist die Verwendung des <xref:System.Transactions.TransactionScope>-Objekts. Mithilfe dieses Ansatzes können Sie verteilte Transaktionen erstellen, die über Datenbanken hinweg und in Verbindung mit anderen speicherresidenten Ressourcen-Managern funktionieren. Transaktionsbereiche erfordern zunächst wenige Ressourcen. Sie stufen sich selbst nur dann zu verteilten Transaktionen hoch, wenn mehrere Verbindungen innerhalb des Transaktionsbereichs vorliegen.  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 Sie können diesen Ansatz nicht für alle Datenbanken verwenden. Beispielsweise kann die SqlClient-Verbindung keine Systemtransaktionen hochstufen, wenn ein [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]-Server verwendet wird. Stattdessen wird automatisch eine vollständige, verteilte Transaktion erzeugt, wenn erkannt wird, dass ein Transaktionsbereich genutzt wird.  
  
## <a name="direct-sql-commands"></a>Direkte SQL-Befehle  
 Es kann zu Situationen kommen, in denen die Möglichkeiten des <xref:System.Data.Linq.DataContext> zum Abfragen oder zum Übergeben von Änderungen für die spezifische Aufgabe nicht ausreichen. In diesen Fällen können Sie die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode verwenden, um SQL-Befehle an die Datenbank zu übergeben und die Abfrageergebnisse in Objekte zu konvertieren.  
  
 Nehmen Sie zum Beispiel an, dass die Daten der `Customer`-Klasse auf zwei Tabellen (customer1 und customer2) verteilt sind. Die folgende Abfrage gibt eine Sequenz von `Customer`-Objekten zurück:  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 Solange die Spaltennamen im tabellarischen Ergebnis den Spalteneigenschaften Ihrer Entitätsklasse entsprechen [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Ihre Objekte aus einer SQL-Abfrage erstellt.  
  
### <a name="parameters"></a>Parameter  
 Die <xref:System.Data.Linq.DataContext.ExecuteQuery%2A>-Methode akzeptiert Parameter. Der folgende Code führt eine parametrisierte Abfrage aus:  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  Parameter werden im Abfragetext mithilfe der gleichen verschachtelten Schreibweise wie in `Console.WriteLine()` und `String.Format()` ausgedrückt. `String.Format()` ersetzt die verschachtelten Parameter der angegebenen Abfragezeichenfolge durch generierte Parameternamen, wie z. B. `@p0`, `@p1` …, `@p(n)`.  
  
## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Vorgehensweise: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
