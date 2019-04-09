---
title: Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127854"
---
# <a name="nullable-structured-types-entity-sql"></a>Strukturierte Typen, die NULL-Werte zulassen (Entity SQL)
Eine `null`-Instanz eines strukturierten Typs ist eine Instanz, die nicht vorhanden ist. Dies unterscheidet sich von einer vorhandenen Instanz, in der alle Eigenschaften den Wert `null` haben.  
  
 In diesem Thema werden strukturierte Typen beschrieben, die NULL-Werte zulassen. Zu dieser Beschreibung gehören eine Aufzählung der Typen, die NULL-Werte zulassen, und die Angabe von Codemustern, die `null`-Instanzen von strukturierten Typen erstellen, die NULL-Werte zulassen.  
  
## <a name="kinds-of-nullable-structured-types"></a>Arten strukturierter Typen, die NULL-Werte zulassen  
 Es gibt drei Arten von Strukturtypen, die NULL-Werte zulassen:  
  
-   Zeilentypen  
  
-   Komplexe Typen  
  
-   Entitätstypen  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Codemuster, die NULL-Instanzen strukturierter Typen erstellen  
 In den folgenden Szenarios werden `null`-Instanzen erstellt:  
  
-   `null` als strukturierten Typ formen:  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   Umwandeln eines Basistyps in einen abgeleiteten Typ:  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   "Outer join on false"-Bedingung:  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --oder  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --oder  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   Dereferenzierung eines `null`-Verweises:  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   Abrufen von ANYELEMENT aus einer leeren Auflistung:  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   Überprüfen von Instanzen strukturierter Typen auf `null`:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
