---
title: 'Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#'
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 24b48b4962ac207f0c6a50456797ff588a97082d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67743310"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Vorgehensweise: Generieren des Objektmodells in Visual Basic oder C#\#
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] wird einer relationalen Datenbank ein Objektmodell in einer eigenen Programmiersprache zugeordnet. Zwei Tools zur Verfügung, für die automatische Generierung eine Visual Basic oder C# Modelle aus den Metadaten einer vorhandenen Datenbank.  
  
- Wenn Sie Visual Studio verwenden, können Sie den Object Relational Designer, um ein Objektmodell zu generieren. Der O/R-Designer bietet eine umfangreiche Benutzeroberfläche zum Generieren einer [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Objektmodell. Weitere Informationen finden Sie unter [Linq to SQL-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Das SQLMetal-Befehlszeilentool. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    >  Wenn Sie nicht über eine vorhandene Datenbank verfügen, sondern diese aus einem Objektmodell erstellen möchten, erstellen Sie Ihr Objektmodell mit Ihrem Code-Editor und mit <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Weitere Informationen finden Sie unter [Vorgehensweise: Dynamisches Erstellen einer Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 Dokumentation für den O/R-Designer enthält Beispiele zum Erstellen Sie einer Visual Basic oder C# Objektmodell, mit dem O/R-Designer. Die folgenden Informationen enthalten Beispiele für die Verwendung des SQLMetal-Befehlszeilentools. Weitere Informationen finden Sie unter [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt Visual Basic-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Beispiel  
 Die SQLMetal-Befehlszeile im folgenden Beispiel erzeugt C#-Code als attributbasiertes Objektmodell der Beispieldatenbank Northwind. Gespeicherte Prozeduren und Funktionen werden ebenfalls gerendert, und Tabellennamen werden automatisch pluralisiert.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Siehe auch

- [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [Das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Lernen durch exemplarische Vorgehensweisen](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Vorgehensweise: Anpassen von Entitätsklassen mit dem Code-Editor](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Attributbasierte Zuordnung](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [SqlMetal.exe (Tool zur Codegenerierung)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [External Mapping (Externe Zuordnung)](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [Downloading Sample Databases (Herunterladen von Beispieldatenbanken)](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Erstellen des Objektmodells](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
