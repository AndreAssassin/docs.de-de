---
title: Komplexer Typ
ms.date: 03/30/2017
ms.assetid: 63efbd23-11d4-4871-bc88-ad01b9837553
ms.openlocfilehash: 9d63660c441192bbc9ecb48bb3a86030b46461cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160809"
---
# <a name="complex-type"></a>Komplexer Typ
Ein *komplexen Typ* ist eine Vorlage zum Definieren von umfangreichen, strukturierter Eigenschaften für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) oder anderen komplexen Typen. Jede Vorlage enthält Folgendes:  
  
-   Eine eindeutige Bezeichnung. (erforderlich)  
  
    > [!NOTE]
    >  Der Name eines komplexen Typs darf nicht mit dem Namen eines Entitätstyps innerhalb des gleichen Namespace übereinstimmen.  
  
-   Daten in Form einer oder mehreren [Eigenschaften](../../../../docs/framework/data/adonet/property.md). (Optional)  
  
    > [!NOTE]
    >  Eine Eigenschaft eines komplexen Typs kann ein anderer komplexer Typ sein.  
  
 Ein komplexer Typ ähnelt insofern einem Entitätstyp, als ein komplexer Typ eine Datennutzlast in Form von primitiven Typeigenschaften oder anderen komplexen Typen enthalten kann. Es gibt jedoch einige Hauptunterschiede zwischen komplexen Typen und Entitätstypen:  
  
-   Komplexe Typen weisen keine Identitäten auf und können daher nicht unabhängig sein. Komplexe Typen können nur Eigenschaften von Entitätstypen oder anderen komplexen Typen sein.  
  
-   Komplexe Typen können nicht beteiligt [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md). Enden einer Zuordnung kann einen komplexen Typ sein und aus diesem Grund [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) kann nicht für komplexe Typen definiert werden.  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen komplexen Typ, Adress, mit den primitiven Typeigenschaften `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`.  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
 Deklarieren Sie den Eigenschaftentyp in der Entitätstypdefinition, um den komplexen Typ `Address` (oben) als Eigenschaft für einen Entitätstyp zu definieren. Die folgende CSDL deklariert die `Address`-Eigenschaft als komplexen Typ für einen Entitätstyp (Publisher):  
  
 [!code-xml[EDM_Example_Model#EntityWithComplexType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#entitywithcomplextype)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
