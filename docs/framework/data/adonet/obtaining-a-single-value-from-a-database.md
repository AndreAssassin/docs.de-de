---
title: Abrufen eines einzelnen Werts aus einer Datenbank
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
ms.openlocfilehash: 5eb81fd2a64f06f1252f71e251e58df568e7407c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59120678"
---
# <a name="obtaining-a-single-value-from-a-database"></a><span data-ttu-id="5d2f2-102">Abrufen eines einzelnen Werts aus einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="5d2f2-102">Obtaining a Single Value from a Database</span></span>
<span data-ttu-id="5d2f2-103">Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-103">You may need to return database information that is simply a single value rather than in the form of a table or data stream.</span></span> <span data-ttu-id="5d2f2-104">Sie möchten z. B. das Ergebnis einer Aggregatfunktion wie z. B. Anzahl zurückgeben (\*), SUM(Price) oder AVG(Quantity).</span><span class="sxs-lookup"><span data-stu-id="5d2f2-104">For example, you may want to return the result of an aggregate function such as COUNT(\*), SUM(Price), or AVG(Quantity).</span></span> <span data-ttu-id="5d2f2-105">Die **Befehl** Objekt bietet die Möglichkeit zum Zurückgeben von einzelner Werten, die mit der **"ExecuteScalar"** Methode.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-105">The **Command** object provides the capability to return single values using the **ExecuteScalar** method.</span></span> <span data-ttu-id="5d2f2-106">Die **"ExecuteScalar"** Methode wird als Skalarwert, der Wert der ersten Spalte der ersten Zeile des Resultsets.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-106">The **ExecuteScalar** method returns, as a scalar value, the value of the first column of the first row of the result set.</span></span>  
  
 <span data-ttu-id="5d2f2-107">Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-107">The following code example inserts a new value in the database using a <xref:System.Data.SqlClient.SqlCommand>.</span></span> <span data-ttu-id="5d2f2-108">Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5d2f2-108">The <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A> method is used to return the identity column value for the inserted record.</span></span>  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="5d2f2-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5d2f2-109">See also</span></span>

- [<span data-ttu-id="5d2f2-110">Befehle und Parameter</span><span class="sxs-lookup"><span data-stu-id="5d2f2-110">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="5d2f2-111">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="5d2f2-111">Executing a Command</span></span>](../../../../docs/framework/data/adonet/executing-a-command.md)
- [<span data-ttu-id="5d2f2-112">"DbConnection", "DbCommand" und "DbException"</span><span class="sxs-lookup"><span data-stu-id="5d2f2-112">DbConnection, DbCommand and DbException</span></span>](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)
- [<span data-ttu-id="5d2f2-113">ADO.NET Managed Provider und DataSet Developer Center</span><span class="sxs-lookup"><span data-stu-id="5d2f2-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
