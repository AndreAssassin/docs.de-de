---
title: N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
ms.openlocfilehash: 7741368896b0bf5a2508d9b727fad386cce6177d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59075162"
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL
Sie können N-Tier-Anwendungen bzw. Anwendungen mit mehreren Ebenen erstellen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden. In der Regel die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Datenkontext, Entitätsklassen und Abfrageerstellungslogik befinden sich auf die mittlere Ebene als der Datenzugriffsebene (DAL). Geschäftslogik und nicht dauerhafte Daten können vollständig in partiellen Klassen und Methoden von Entitäten und Datenkontext implementiert werden, oder sie können in separaten Klassen implementiert werden.

 Die Client- oder Präsentationsebene ruft Methoden für die Remoteschnittstelle der mittleren Ebene auf, und die Datenzugriffsebene auf dieser Ebene führt Abfragen oder gespeicherte Prozeduren aus, die <xref:System.Data.Linq.DataContext>-Methoden zugeordnet sind. Die mittlere Ebene gibt die Daten normalerweise als XML-Darstellungen von Entitäten oder Proxyobjekten an Clients zurück.

 Auf der mittleren Ebene werden Entitäten vom Datenkontext erstellt, der deren Zustand nachverfolgt und das verzögerte Laden von Änderungen aus der Datenbank und das Übergeben von Änderungen an die Datenbank verwaltet. Diese Entitäten werden an den `DataContext` "angefügt". Nachdem die Entitäten jedoch mittels Serialisierung an eine andere Ebene gesendet wurden, werden sie getrennt, was dazu führt, dass ihr Zustand nicht mehr vom `DataContext` nachverfolgt wird. Entitäten, die vom Client zum Update zurückgesendet werden, müssen erneut an den Datenkontext angefügt werden, bevor die Änderungen von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] an die Datenbank übergeben werden können. Der Client ist dafür zuständig, ursprüngliche Werte und/oder Timestamps wieder für die mittlere Ebene bereitzustellen, wenn diese für Überprüfungen auf vollständige Parallelität benötigt werden.

 In ASP.NET-Anwendungen wird diese Komplexität größtenteils von <xref:System.Web.UI.WebControls.LinqDataSource> verwaltet. Weitere Informationen finden Sie unter [Übersicht über das LinqDataSource-Steuerelement](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100)).

## <a name="additional-resources"></a>Zusätzliche Ressourcen
 Weitere Informationen zur Implementierung von N-Tier-Anwendungen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden, finden Sie unter den folgenden Themen:

-   [N-Schicht-LINQ to SQL mit ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)

-   [N-Schicht-LINQ to SQL mit Webdiensten](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md) 

-   [Implementieren von n-schichtiger Geschäftslogik](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)

-   [Abrufen von Daten und CUD-Vorgänge in n-schichtigen Anwendungen (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)

 Weitere Informationen zu n-Tier-Anwendungen, die ADO.NET-Datasets verwenden, finden Sie unter [arbeiten mit Datasets in n-schichtigen Anwendungen](/visualstudio/data-tools/work-with-datasets-in-n-tier-applications).

## <a name="see-also"></a>Siehe auch

- [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
