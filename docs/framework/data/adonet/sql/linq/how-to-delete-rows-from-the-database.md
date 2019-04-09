---
title: 'Vorgehensweise: Löschen von Zeilen aus der Datenbank'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2144c99b-8055-4080-a5c6-1ea14335e2a3
ms.openlocfilehash: 80340bcf25ec3299629af34f7fafe53877ad571c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213297"
---
# <a name="how-to-delete-rows-from-the-database"></a>Vorgehensweise: Löschen von Zeilen aus der Datenbank
Sie können Zeilen in einer Datenbank löschen, durch das Entfernen der entsprechenden [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objekte aus einer Tabelle verknüpften Auflistung. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] übersetzt die Änderungen in die entsprechenden SQL `DELETE` Befehle.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht unterstützt oder erkennt kaskadierte Löschvorgänge. Wenn Sie eine Zeile in einer Tabelle löschen möchten, für die Einschränkungen gelten, führen Sie eines der folgenden Verfahren aus:  
  
-   Legen Sie die `ON DELETE CASCADE`-Regel in der Fremdschlüsseleinschränkung in der Datenbank fest.  
  
-   Verwenden Sie eigenen Code, um zunächst die untergeordneten Objekte zu löschen, die das Löschen des übergeordneten Objekts verhindern.  
  
 Andernfalls wird eine Ausnahme ausgelöst. Siehe das zweite Codebeispiel weiter unten in diesem Thema.  
  
> [!NOTE]
>  Sie können [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Standardmethoden für die Datenbankoperationen `Insert`, `Update` und `Delete` überschreiben. Weitere Informationen finden Sie unter [Anpassen von INSERT-, Update- und Delete-Operationen](../../../../../../docs/framework/data/adonet/sql/linq/customizing-insert-update-and-delete-operations.md).  
>   
>  Können Entwickler mithilfe von Visual Studio die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren für denselben Zweck entwickeln.  
  
 In den folgenden Schritten wird davon ausgegangen, dass Sie ein gültiger <xref:System.Data.Linq.DataContext> mit der Datenbank Northwind verbindet. Weitere Informationen finden Sie unter [Vorgehensweise: Herstellen einer Datenbankverbindung](../../../../../../docs/framework/data/adonet/sql/linq/how-to-connect-to-a-database.md).  
  
### <a name="to-delete-a-row-in-the-database"></a>So löschen Sie eine Zeile aus der Datenbank  
  
1.  Rufen Sie die zu löschende Zeile aus der Datenbank ab.  
  
2.  Rufen Sie die <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A>-Methode auf.  
  
3.  Übergeben Sie die Änderung an die Datenbank.  
  
## <a name="example"></a>Beispiel  
 Im ersten Codebeispiel wird die Datenbank nach Bestelldetails durchsucht, die sich auf die Bestellung 11000 beziehen. Diese Bestelldetails werden dann zum Löschen markiert und diese Änderungen an die Datenbank übergeben.  
  
 [!code-csharp[System.Data.Linq.Table#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.table/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.Table#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.table/vb/module1.vb#3)]  
  
## <a name="example"></a>Beispiel  
 In diesem zweiten Beispiel besteht das Ziel darin, eine Bestellung (10250) zu entfernen. Der Code durchsucht zunächst die `OrderDetails`-Tabelle, um zu prüfen, ob die zu entfernende Bestellung untergeordnete Elemente enthält. Wenn die Bestellung untergeordnete Elemente enthält, werden zunächst die untergeordneten Elemente und dann die Bestellung zum Entfernen markiert. <xref:System.Data.Linq.DataContext> bringt die tatsächlichen Löschvorgänge in die richtige Reihenfolge, sodass die an die Datenbank übertragenen Löschbefehle die Datenbankbeschränkungen erfüllen.  
  
 [!code-csharp[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCascadeWorkaround/cs/Program.cs#1)]
 [!code-vb[DLinqCascadeWorkaround#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCascadeWorkaround/vb/Module1.vb#1)]  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Verwalten von Änderungskonflikten](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
- [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
- [Vornehmen und Übergeben von Datenänderungen](../../../../../../docs/framework/data/adonet/sql/linq/making-and-submitting-data-changes.md)
