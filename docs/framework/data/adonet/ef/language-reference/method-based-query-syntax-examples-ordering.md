---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Sortieren'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5d21b178-d731-471a-8534-1f8184a2ef06
ms.openlocfilehash: 8da335bc2b45153aa00cd28f1a6baf58d11020ce
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250107"
---
# <a name="method-based-query-syntax-examples-ordering"></a>Beispiele für die methodenbasierte Abfragesyntax: Sortieren
In den Beispielen in diesem Thema wird gezeigt, wie <xref:System.Linq.Enumerable.ThenBy%2A> die-Methode verwendet wird, um das [AdventureWorks Sales-Modell](https://archive.codeplex.com/?p=msftdbprodsamples) mithilfe von Methoden basierter Abfrage Syntax abzufragen. Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.  
  
 In den Beispielen in diesem Thema werden die `using` folgenden / `Imports` -Anweisungen verwendet:  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="thenby"></a>ThenBy  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel methodenbasierter Abfragesyntax werden <xref:System.Linq.Queryable.OrderBy%2A> und <xref:System.Linq.Queryable.ThenBy%2A> verwendet, um eine zuerst nach Nachnamen und dann nach Vornamen geordnete Liste der Kontakte zurückzugeben.  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby_mq)]
 [!code-vb[DP L2E Examples#OrderByThenBy_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby_mq)]  
  
## <a name="thenbydescending"></a>ThenByDescending  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden die <xref:System.Linq.Queryable.OrderBy%2A>-Methode und die <xref:System.Linq.Queryable.ThenByDescending%2A>-Methode verwendet, um die Daten zuerst nach dem Listenpreis und dann absteigend nach dem Produktnamen zu sortieren.  
  
 [!code-csharp[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescending_mq)]
 [!code-vb[DP L2E Examples#ThenByDescending_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescending_mq)]  
  
## <a name="see-also"></a>Siehe auch

- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)
