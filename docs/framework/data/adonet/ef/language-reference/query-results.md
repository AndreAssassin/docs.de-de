---
title: Abfrageergebnisse
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcd7b699-4e50-4523-8c33-2f54a103d94e
ms.openlocfilehash: 165fb1524daa781c29037bf1c9cb2b3013504177
ms.sourcegitcommit: b5c59eaaf8bf48ef3ec259f228cb328d6d4c0ceb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2019
ms.locfileid: "67539742"
---
# <a name="query-results"></a>Abfrageergebnisse
Nachdem eine LINQ to Entities-Abfrage wird in Befehlsstrukturen konvertiert und ausgeführt wurde, werden die Ergebnisse der Abfrage in der Regel als eine der folgenden zurückgegeben:  
  
- Eine Auflistung von 0 (null) oder mehr typisierten Entitätsobjekten oder eine Projektion komplexer Typen im konzeptionellen Modell.  
  
- Vom konzeptionellen Modell unterstützte CLR-Typen.  
  
- Inlineauflistungen  
  
- Anonyme Typen  
  
 Wenn die Abfrage in der Datenquelle ausgeführt wurde, werden die Ergebnisse in CLR-Typen materialisiert und an den Client zurückgegeben. Die Objektmaterialisierung wird vom [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] durchgeführt. Alle Fehler, die dadurch entstehen, dass zwischen dem [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] und der CLR keine Zuordnung vorgenommen werden kann, lösen bei der Objektmaterialisierung Ausnahmen aus.  
  
 Wenn die Abfrage primitive Typen des konzeptionellen Modells zurückgibt, besteht das Ergebnis aus CLR-Typen, die eigenständig und vom [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] getrennt sind. Wenn die Abfrage jedoch eine durch <xref:System.Data.Objects.ObjectQuery%601> dargestellte Auflistung typisierter Entitätsobjekte zurückgibt, werden diese Typen vom Objektkontext nachverfolgt. Objektverhalten (z. B. über-und untergeordneten Sammlungen, änderungsnachverfolgung, Polymorphie usw.) werden gemäß der [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)]. Diese Funktionalität kann, wie im [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] definiert, in vollem Umfang verwendet werden. Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../../docs/framework/data/adonet/ef/working-with-objects.md).  
  
 Von Abfragen zurückgegebene Strukturtypen (wie anonyme Typen und komplexe Typen, die NULL-Werte zulassen) können den Wert `null` haben. Eine <xref:System.Data.Objects.DataClasses.EntityCollection%601>-Eigenschaft einer zurückgegebenen Entität kann ebenfalls den Wert `null` haben. Dies kann durch die Projektion einer Auflistungseigenschaft einer Entität geschehen, die den Wert `null` hat, wie ein Aufruf von <xref:System.Linq.Queryable.FirstOrDefault%2A> für eine <xref:System.Data.Objects.ObjectQuery%601>, die über keine Elemente verfügt.  
  
 In einigen Fällen kann es den Anschein haben, dass eine Abfrage bei ihrer Ausführung ein materialisiertes Ergebnis erstellt, während die Abfrage tatsächlich auf dem Server ausgeführt wird und das Entitätsobjekt nicht in der CLR materialisiert wird. Dies kann Probleme verursachen, wenn Nebeneffekte der Objektmaterialisierung von Bedeutung sind.  
  
 Im folgenden Beispiel ist eine benutzerdefinierte Klasse, `MyContact`, mit einer `LastName`-Eigenschaft enthalten. Wenn die `LastName`-Eigenschaft festgelegt wird, wird eine `count`-Variable inkrementiert. Bei der Ausführung der folgenden beiden Abfragen inkrementiert die erste `count`, die zweite jedoch nicht. Der Grund dafür ist, dass in der zweiten Abfrage die `LastName`-Eigenschaft aus den Ergebnissen projiziert wird und die `MyContact`-Klasse nicht erstellt wird, da es nicht nötig ist, die Abfrage im Speicher auszuführen.  
  
 [!code-csharp[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#materializationsideeffects)]
 [!code-vb[DP L2E Materialization Example#MaterializationSideEffects](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#materializationsideeffects)]  
  
 [!code-csharp[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Materialization Example/CS/Program.cs#mycontactclass)]
 [!code-vb[DP L2E Materialization Example#MyContactClass](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Materialization Example/VB/Module1.vb#mycontactclass)]
