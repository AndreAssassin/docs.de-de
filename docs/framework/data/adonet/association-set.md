---
title: Zuordnungssatz
ms.date: 03/30/2017
ms.assetid: a65247b6-ce59-44ea-974c-14ae20a7995f
ms.openlocfilehash: 43ab6cf9f1ee8cb971810add6b9a89467726f3e2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70785031"
---
# <a name="association-set"></a>Zuordnungssatz
Ein Zuordnungs *Satz* ist ein logischer Container [für](association-type.md) Zuordnungs Instanzen desselben Typs. Ein Zuordnungssatz ist keine Datenmodellkonstruktion; das heißt, er beschreibt nicht die Struktur von Daten oder Beziehungen. Vielmehr stellt ein Zuordnungssatz eine Konstruktion für eine Hosting- oder Speicherumgebung (z. B. die Common Language Runtime oder eine SQL Server-Datenbank) zum Gruppieren von Zuordnungsinstanzen bereit, damit diese einem Datenspeicher zugeordnet werden können.  
  
 Ein Zuordnungs Satz ist innerhalb eines [Entitäts Containers](entity-container.md)definiert, einer logischen Gruppierung von [Entitätenmengen](entity-set.md) und Zuordnungs Sätzen.  
  
 Eine Definition für einen Zuordnungssatz enthält die folgenden Informationen:  
  
- Den Namen des Zuordnungssatzes. (erforderlich)  
  
- Die Zuordnung, von der er Instanzen enthält. (erforderlich)  
  
- Zwei Zuordnungs [Sätze enden](association-set-end.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Obwohl die Abbildung keine Informationen zu Zuordnungssätzen bereitstellt, zeigt die nächste Abbildung ein Beispiel für Zuordnungssätze und Entitätenmengen auf Grundlage dieses Modells.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-set/example-model-three-entity-types.gif)  
  
 Das folgende Beispiel zeigt einen Zuordnungssatz (`PublishedBy`) und zwei Entitätenmengen (`Books` und `Publishers`), basierend auf dem oben gezeigten Modell. BI in der `Books` Entitätenmenge stellt zur Laufzeit `Book` eine Instanz des Entitäts Typs dar. Ebenso stellt PJ eine `Publisher` -Instanz in der `Publishers` Entitätenmenge dar. Bipj stellt eine Instanz der `PublishedBy` Zuordnung `PublishedBy` im Zuordnungs Satz dar.  
  
 ![Screenshot, der ein Beispiel für eine Reihe anzeigt.](./media/association-set/sets-example-association.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen Entitätscontainer mit einem Zuordnungssatz für jede Zuordnung in der oben gezeigten Abbildung. Beachten Sie, dass der Name und die Zuordnung für jeden Zuordnungssatz mit XML-Attributen definiert werden.  
  
 [!code-xml[EDM_Example_Model#EntityContainerExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entitycontainerexample)]  
  
 Es ist möglich, mehrere Zuordnungs Sätze pro Zuordnung zu definieren, solange keine zwei Zuordnungs Sätze ein Zuordnungs [Satz-Ende](association-set-end.md)gemeinsam verwenden. Die folgende CSDL definiert einen Entitätscontainer mit zwei Zuordnungssätzen für die `WrittenBy`-Zuordnung. Beachten Sie, dass mehrere Entitätssätze für die Entitätstypen `Book` und `Author` definiert wurden, und dass sich kein Zuordnungssatz ein Zuordnungssatzende teilt.  
  
 [!code-xml[EDM_Example_Model#MultipleAssociationSets](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books3.edmx#multipleassociationsets)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [Fremdschlüsseleigenschaft](foreign-key-property.md)
