---
title: Filtern mit DataView (LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5632d74a-ff53-4ea7-9fe7-4a148eeb1c68
ms.openlocfilehash: b41b95ba06f031dc45c0267432d0d6afb7f3a7d9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645687"
---
# <a name="filtering-with-dataview-linq-to-dataset"></a>Filtern mit DataView (LINQ to DataSet)
Die Möglichkeit, Daten nach bestimmten Kriterien zu filtern und dann über ein UI-Steuerelement für einen Client bereitzustellen, ist ein wichtiger Aspekt der Datenbindung. <xref:System.Data.DataView> bietet mehrere Möglichkeiten, Daten zu filtern und Teilmengen von Datenzeilen, die bestimmte Filterkriterien erfüllen, zurückzugeben. Neben den zeichenfolgenbasierten Filterfunktionen <xref:System.Data.DataView> bietet außerdem die Möglichkeit, [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] Ausdrücke für den Filterkriterien. [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] -Ausdrücke ermöglichen wesentlich komplexere und leistungsfähigere Filteroperationen als die zeichenfolgenbasierte Filterung.  
  
 Es gibt zwei Möglichkeiten, Daten mit einer <xref:System.Data.DataView> zu filtern:  
  
- durch Erstellen einer <xref:System.Data.DataView> mittels einer WHERE-Klausel aus einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfrage  
  
- mittels der vorhandenen Funktionen für das zeichenfolgenbasierte Filtern von <xref:System.Data.DataView>  
  
## <a name="creating-dataview-from-a-query-with-filtering-information"></a>Erstellen einer "DataView" auf der Grundlage einer Abfrage mit Filterinformationen  
 Ein <xref:System.Data.DataView>-Objekt kann auf der Grundlage einer [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfrage erstellt werden. Wenn die Abfrage eine `Where`-Klausel enthält, wird die <xref:System.Data.DataView> mit den Filterinformationen aus der Abfrage erstellt. Der Ausdruck in der `Where`-Klausel wird verwendet, um zu bestimmen, welche Datenzeilen in die <xref:System.Data.DataView> aufgenommen werden. Er bildet gleichzeitig die Basis für den Filter.  
  
 Ausdrucksbasierte Filter bieten leistungsfähigere und komplexere Filterfunktionen als die einfacheren zeichenfolgenbasierten Filter. Die zeichenfolgenbasierten und ausdrucksbasierten Filter schließen sich gegenseitig aus. Wenn der zeichenfolgenbasierte <xref:System.Data.DataView.RowFilter%2A> festgelegt wird, nachdem eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt wurde, wird der ausdrucksbasierte Filter, der aus der Abfrage abgeleitet wurde, gelöscht.  
  
> [!NOTE]
>  In den meisten Fällen dürften die für die Filterung verwendeten Ausdrücke keine Nebenwirkungen haben. Sie müssen deterministisch sein. Die Ausdrücke dürfen darüber hinaus keine Logik enthalten, die auf einer festgelegten Anzahl von Ausführungen beruht, da die Filteroperationen unbegrenzt oft ausgeführt werden können sollen.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden aus der &lt;legacyBold&gt;SalesOrderDetail&lt;/legacyBold&gt;-Tabelle alle Aufträge mit einer Menge größer als 2 und kleiner als 6 abgerufen. Dann wird aus dieser Abfrage eine <xref:System.Data.DataView> erstellt. Die <xref:System.Data.DataView> wird anschließend an eine <xref:System.Windows.Forms.BindingSource> gebunden:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt, die alle nach dem 6. Juni 2001 eingegangenen Aufträge abruft:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhere3)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhere3](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhere3)]  
  
### <a name="example"></a>Beispiel  
 Die Filterung kann auch mit der Sortierung kombiniert werden. Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage nach Kontaktpersonen erstellt, deren Nachname mit S beginnt. Die Ergebnisse werden erst nach dem Nachnamen und dann nach dem Vornamen sortiert:  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywhereorderbythenby)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereOrderByThenBy](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywhereorderbythenby)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird der SoundEx-Algorithmus verwendet, um Kontakte zu suchen, deren Nachname "Zhu" ähnlich ist. Der SoundEx-Algorithmus ist in der &lt;legacyBold&gt;SoundEx&lt;/legacyBold&gt;-Methode implementiert.  
  
 [!code-csharp[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvsoundexfilter)]
 [!code-vb[DP DataView Samples#LDVSoundExFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvsoundexfilter)]  
  
 SoundEx ist ein ursprünglich vom U.S. Census Bureau entwickelter phonetischer Algorithmus, mit dem Namen nach ihrem Klang im Englischen indiziert werden können Statistikbehörde zur Verfügung gestellt. Die SoundEx-Methode gibt für den Namen einen vierstelligen Code zurück, der aus einem Buchstaben und drei Zahlen besteht. Der Buchstabe ist der erste Buchstabe des Namens, und die Zahlen sind die verschlüsselten restlichen Konsonanten im Namen. Ähnlich klingende Namen haben denselben SoundEx-Code. Die in der SoundEx-Methode im vorherigen Beispiel verwendete SoundEx-Implementierung sieht wie folgt aus:  
  
 [!code-csharp[DP DataView Samples#SoundEx](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#soundex)]
 [!code-vb[DP DataView Samples#SoundEx](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#soundex)]  
  
## <a name="using-the-rowfilter-property"></a>Verwenden der "RowFilter"-Eigenschaft  
 Die bisherige zeichenfolgenbasierte Filterfunktionalität von <xref:System.Data.DataView> funktioniert auch im [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Kontext noch. Weitere Informationen zur zeichenfolgenbasierten <xref:System.Data.DataView.RowFilter%2A> filtern, finden Sie [sortieren und Filtern von Daten](../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage der &lt;legacyBold&gt;Contact&lt;/legacyBold&gt;-Tabelle erstellt und dann die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft so eingerichtet, dass alle Zeilen zurückgegeben werden, bei denen der Nachname des Kontakts "Zhu" lautet:  
  
 [!code-csharp[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvrowfilter)]
 [!code-vb[DP DataView Samples#LDVRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvrowfilter)]  
  
 Nachdem eine <xref:System.Data.DataView> aus einer <xref:System.Data.DataTable> oder [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)]-Abfrage erstellt wurde, können Sie die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft verwenden, um auf der Grundlage der jeweiligen Spaltenwerte Teilmengen von Zeilen anzugeben. Die zeichenfolgenbasierten und ausdrucksbasierten Filter schließen sich gegenseitig aus. Festlegen der <xref:System.Data.DataView.RowFilter%2A> Eigenschaft wird löschen Sie den Filterausdruck, der per Rückschluss von dem [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] Abfrage und Filter-Ausdruck kann nicht zurückgesetzt werden.  
  
 [!code-csharp[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvfromquerywheresetrowfilter)]
 [!code-vb[DP DataView Samples#LDVFromQueryWhereSetRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvfromquerywheresetrowfilter)]  
  
 Wenn Sie die Ergebnisse einer bestimmten Abfrage von Daten zurückgeben möchten, anstatt eine dynamische Ansicht einer Teilmenge von Daten zu erhalten, können Sie die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> der <xref:System.Data.DataView> verwenden, statt die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft einzurichten. Die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft wird am besten in einer datengebundenen Anwendung verwendet, in der ein gebundenes Steuerelement gefilterte Ergebnisse anzeigt. Wenn Sie die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft festlegen, wird der Index für die Daten neu erstellt, wodurch zusätzlicher Verwaltungsmehraufwand für die Anwendung entsteht und die Arbeitsgeschwindigkeit verringert wird. Die Methoden <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> nutzen den aktuellen Index, ohne dass der Index neu erstellt werden muss. Wenn Sie <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> nur einmal aufrufen werden, sollten Sie die vorhandene <xref:System.Data.DataView> verwenden. Wird <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> dagegen mehrmals aufgerufen, empfiehlt sich die Erstellung einer neuen <xref:System.Data.DataView>, um den Index auf der Basis der zu durchsuchenden Spalte neu zu erstellen, und dann die Methode <xref:System.Data.DataView.Find%2A> oder <xref:System.Data.DataView.FindRows%2A> aufzurufen. Weitere Informationen zu den <xref:System.Data.DataView.Find%2A> und <xref:System.Data.DataView.FindRows%2A> Methoden finden Sie unter [Suchen nach Zeilen](../../../../docs/framework/data/adonet/dataset-datatable-dataview/finding-rows.md) und [DataView-Leistung](../../../../docs/framework/data/adonet/dataview-performance.md).  
  
## <a name="clearing-the-filter"></a>Löschen des Filters  
 Der Filter für eine <xref:System.Data.DataView> kann gelöscht werden, nachdem die Filterung mit der <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft eingerichtet wurde. Das Löschen des Filters für eine <xref:System.Data.DataView> kann auf zweierlei Art und Weise erfolgen:  
  
- Legen Sie die <xref:System.Data.DataView.RowFilter%2A> -Eigenschaft auf `null`fest.  
  
- indem für die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft eine leere Zeichenfolge festgelegt wird  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Abfrage erstellt und dann der Filter gelöscht, indem die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft auf `null` gesetzt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter2)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter2)]  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine <xref:System.Data.DataView> auf der Grundlage einer Tabelle erstellt und die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft festgelegt. Anschließend wird der Filter gelöscht, indem für die <xref:System.Data.DataView.RowFilter%2A>-Eigenschaft eine leere Zeichenfolge festgelegt wird:  
  
 [!code-csharp[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataView Samples/CS/Form1.cs#ldvclearrowfilter)]
 [!code-vb[DP DataView Samples#LDVClearRowFilter](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataView Samples/VB/Form1.vb#ldvclearrowfilter)]  
  
## <a name="see-also"></a>Siehe auch

- [Datenbindung und LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
- [Sortieren mit DataView](../../../../docs/framework/data/adonet/sorting-with-dataview-linq-to-dataset.md)
