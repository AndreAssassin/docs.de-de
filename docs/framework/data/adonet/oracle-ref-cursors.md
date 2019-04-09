---
title: Oracle-REF CURSORs
ms.date: 03/30/2017
ms.assetid: c6b25b8b-0bdd-41b2-9c7c-661f070c2247
ms.openlocfilehash: b23b0f07d7755fed820481a3ad1fe831ae3f5224
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213167"
---
# <a name="oracle-ref-cursors"></a>Oracle-REF CURSORs
Die .NET Framework-Datenanbieter für Oracle unterstützt Oracle **REF CURSOR** -Datentyp. Wenn Sie beim Arbeiten mit Oracle-REF CUSORS diesen Datenanbieter verwenden, müssen Sie das jeweilige Verhalten berücksichtigen.  
  
> [!NOTE]
>  Das jeweilige Verhalten weicht von dem des Microsoft OLE DB-Anbieters für Oracle (MSDAORA) ab.  
  
-   Aus Gründen der Leistung der Datenanbieter für Oracle Bindung erfolgt nicht automatisch **REF CURSOR** -Datentypen, wie MSDAORA, es sei denn, Sie explizit angeben.  
  
-   Der Datenanbieter unterstützt keine ODBC-Escapesequenzen, auch nicht das {resultset}-Escapezeichen für die Angabe von REF CURSOR-Parametern.  
  
-   Um eine gespeicherte Prozedur auszuführen, die REF CURSORs zurückgibt, müssen Sie definieren die Parameter in der <xref:System.Data.OracleClient.OracleParameterCollection> mit einer <xref:System.Data.OracleClient.OracleType> von **Cursor** und ein <xref:System.Data.OracleClient.OracleParameter.Direction%2A> von **Ausgabe**. Mit diesem Datenanbieter können REF CURSORs nur als Ausgabeparameter gebunden werden. Das Binden von REF CURSORs als Eingabeparameter wird von diesem Datenanbieter nicht unterstützt.  
  
-   Das Abrufen eines <xref:System.Data.OracleClient.OracleDataReader> aus dem Parameterwert wird nicht unterstützt. Nach dem Ausführen des Befehls weisen die Werte den Typ <xref:System.DBNull> auf.  
  
-   Die einzige **CommandBehavior** Enumerationswert, der mit REF CURSORs verwendet (z. B. beim Aufrufen von <xref:System.Data.OracleClient.OracleCommand.ExecuteReader%2A>) ist **CloseConnection**; alle anderen werden ignoriert.  
  
-   Die Reihenfolge der REF CURSORs in der **OracleDataReader** hängt von der Reihenfolge der Parameter in der **OracleParameterCollection**. Die <xref:System.Data.OracleClient.OracleParameter.ParameterName%2A>-Eigenschaft wird ignoriert.  
  
-   Der PL/SQL **Tabelle** -Datentyp wird nicht unterstützt. REF CURSORs sind im Vergleich effizienter. Falls Sie benötigen eine **Tabelle** -Datentyp, verwenden Sie den OLE DB .NET Data Provider mit MSDAORA.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [REF CURSOR-Beispiele](../../../../docs/framework/data/adonet/ref-cursor-examples.md)  
 Enthält drei Beispiele, in denen die Verwendung von REF CURSORs veranschaulicht wird.  
  
 [REF CURSOR-Parameter in "OracleDataReader"](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)  
 Veranschaulicht das Ausführen einer gespeicherten PL/SQL-Prozedur, die einen REF CURSOR-Parameter zurückgibt, und liest den Wert als ein **OracleDataReader**.  
  
 [Abrufen von Daten aus mehreren REF CURSORs mithilfe von "OracleDataReader"](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)  
 Veranschaulicht, wie zum Ausführen einer gespeicherten PL/SQL-Prozedur, die zwei REF CURSOR-Parameter zurückgibt, und liest die Werte, die mit einem **OracleDataReader**.  
  
 [Auffüllen eines "DataSets" mit einem oder mehreren REF CURSORs](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)  
 Veranschaulicht das Ausführen einer gespeicherten PL/SQL-Prozedur, die zwei REF CURSOR-Parameter zurückgibt. Das <xref:System.Data.DataSet> wird mit den zurückgegebenen Zeilen aufgefüllt.  
  
## <a name="see-also"></a>Siehe auch

- [Oracle und ADO.NET](../../../../docs/framework/data/adonet/oracle-and-adonet.md)
- [ADO.NET Managed Provider und DataSet Developer Center](https://go.microsoft.com/fwlink/?LinkId=217917)
