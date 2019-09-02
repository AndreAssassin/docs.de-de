---
title: Definieren von Primärschlüsseln
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2ea85959-e763-4669-8bd9-46a9dab894bd
ms.openlocfilehash: dbfd8a8b207c0da9403ac1f8ab36557c4abe383b
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/31/2019
ms.locfileid: "70204913"
---
# <a name="defining-primary-keys"></a>Definieren von Primärschlüsseln
Eine Datenbanktabelle enthält i. d. R. eine Spalte oder eine Gruppe von Spalten, die jede Zeile in der Tabelle eindeutig identifiziert. Diese identifizierende Spalte oder Spaltengruppe wird als Primärschlüssel bezeichnet.  
  
 Wenn Sie einen einzelnen <xref:System.Data.DataColumn> <xref:System.Data.DataColumn.AllowDBNull%2A> <xref:System.Data.DataTable> <xref:System.Data.DataTable.PrimaryKey%2A> als für einen identifizieren, wird die-Eigenschaft der Spalte von der Tabelle automatisch auf **false** festgelegt <xref:System.Data.DataColumn.Unique%2A> , und die-Eigenschaft wird auf **true**festgelegt. Bei mehrspaltigen primär Schlüsseln wird nur die **AllowDBNull** -Eigenschaft automatisch auf **false**festgelegt.  
  
 Die **PrimaryKey** -Eigenschaft eines <xref:System.Data.DataTable> empfängt als Wert ein Array aus einem oder mehreren **datacolenumn** -Objekten, wie in den folgenden Beispielen gezeigt. Im ersten Beispiel wird eine einzelne Spalte als Primärschlüssel definiert.  
  
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
- [DataTable-Schemadefinition](datatable-schema-definition.md)
- [DataTables](datatables.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
