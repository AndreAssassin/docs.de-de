---
title: 'Vorgehensweise: Aufrufen von Datenbankfunktionen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: 115c50f157023b71a916b45b4498f9c59ad744bf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397626"
---
# <a name="how-to-call-database-functions"></a>Vorgehensweise: Aufrufen von Datenbankfunktionen
Die <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse enthält Methoden, mit denen SQL Server-Funktionen in LINQ to Entities-Abfragen verwendet werden können. Beim Verwenden von <xref:System.Data.Objects.SqlClient.SqlFunctions>-Methoden in LINQ to Entities-Abfragen werden die entsprechenden Datenbankfunktionen in der Datenbank ausgeführt.  
  
> [!NOTE]
> Datenbankfunktionen, die eine Berechnung für einen Satz von Werten ausführen und einen einzelnen Wert (auch bekannt als aggregierte Datenbankfunktionen) zurückgeben, können direkt aufgerufen werden. Andere kanonische Funktionen können nur als Teil einer LINQ to Entities-Abfrage aufgerufen werden. Zum direkten Aufrufen einer Aggregatfunktion muss eine <xref:System.Data.Objects.ObjectQuery%601> an die Funktion übergeben werden. Weitere Informationen finden Sie unten im zweiten Beispiel.  
  
> [!NOTE]
> Die Methoden in der <xref:System.Data.Objects.SqlClient.SqlFunctions>-Klasse sind spezifisch für SQL Server-Funktionen. Ähnliche Klassen, die Datenbankfunktionen verfügbar machen, sind möglicherweise über andere Anbieter verfügbar.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)verwendet. Im Beispiel wird eine LINQ to Entities-Abfrage ausgeführt, die die <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A>-Methode zur Rückgabe aller Kontakte verwendet, deren Nachname mit "Si" beginnt:  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)verwendet. Im Beispiel wird die aggregierte <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A>-Methode direkt aufgerufen. Eine <xref:System.Data.Objects.ObjectQuery%601> wird an die Funktion übergeben, durch die sie aufgerufen werden kann, ohne Teil einer LINQ to Entities-Abfrage sein zu müssen.  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch

- [Aufrufen von Funktionen in LINQ to Entities-Abfragen](calling-functions-in-linq-to-entities-queries.md)
- [Abfragen in LINQ to Entities](queries-in-linq-to-entities.md)
