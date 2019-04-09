---
title: Definieren von Primärschlüsseln
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: 84c84cb8fc0ee484b09c69c72571a19c335b58f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59230628"
---
# <a name="defining-primary-keys"></a>Definieren von Primärschlüsseln
Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert. Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.  
  
 Wenn Sie eine einzelne identifizieren <xref:System.Data.DataColumn> als die <xref:System.Data.DataTable.PrimaryKey%2A> für eine <xref:System.Data.DataTable>, setzt die Tabelle automatisch die <xref:System.Data.DataColumn.AllowDBNull%2A> Eigenschaft der Spalte, die **"false"** und die <xref:System.Data.DataColumn.Unique%2A> Eigenschaft, um  **"true"**. Für mehrere Spalten Primärschlüssel, nur die **AllowDBNull** Eigenschaft wird automatisch festgelegt, um **"false"**.  
  
 Die **PrimaryKey** Eigenschaft eine <xref:System.Data.DataTable> erhält als Wert ein Array von einem oder mehreren **DataColumn** Objekte, wie in den folgenden Beispielen gezeigt. Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustID")}  
  
' Or  
  
Dim columns(1) As DataColumn  
columns(0) = workTable.Columns("CustID")  
workTable.PrimaryKey = columns  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustID"]};  
  
// Or  
  
DataColumn[] columns = new DataColumn[1];  
columns[0] = workTable.Columns["CustID"];  
workTable.PrimaryKey = columns;  
```  
  
 	Im folgenden Beispiel werden zwei Spalten als Primärschlüssel definiert.  
  
```vb  
workTable.PrimaryKey = New DataColumn() {workTable.Columns("CustLName"), _  
                                         workTable.Columns("CustFName")}  
  
' Or  
  
Dim keyColumn(2) As DataColumn  
keyColumn(0) = workTable.Columns("CustLName")  
keyColumn(1) = workTable.Columns("CustFName")  
workTable.PrimaryKey = keyColumn  
```  
  
```csharp  
workTable.PrimaryKey = new DataColumn[] {workTable.Columns["CustLName"],   
                                         workTable.Columns["CustFName"]};  
  
// Or  
  
DataColumn[] keyColumn = new DataColumn[2];  
keyColumn[0] = workTable.Columns["CustLName"];  
keyColumn[1] = workTable.Columns["CustFName"];  
workTable.PrimaryKey = keyColumn;  
```  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Data.DataTable>
- [DataTable-Schemadefinition](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatable-schema-definition.md)
- ["DataTables"](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
