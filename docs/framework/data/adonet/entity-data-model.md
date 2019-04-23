---
title: Entity Data Model
ms.date: 03/30/2017
ms.assetid: 2dda3d5b-4582-4ba0-a91d-fcd7a1498137
ms.openlocfilehash: 8e96890d97f652295a3fdb67c48ec37710280eec
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59197918"
---
# <a name="entity-data-model"></a>Entity Data Model
Das Entity Data Model (EDM) ist eine Reihe von Konzepten, die die Datenstruktur unabhängig von der gespeicherten Form beschreiben. Das EDM ist aus dem 1976 von Peter Chen beschriebenen Entitätsbeziehungsmodell ausgeliehen, baut aber auch auf dem Entitätsbeziehungsmodell auf und erweitert seine herkömmliche Verwendung.  
  
 Das EDM löst die Herausforderungen, die sich aus dem Speichern von Daten in vielen Formen ergeben. Denken Sie z. B. an ein Unternehmen, das Daten in relationalen Datenbanken, Textdateien, XML-Dateien, Arbeitsblättern und Berichten speichert. Dies stellt bedeutende Herausforderungen an Datenmodellierung, Anwendungsentwurf und Datenzugriff dar. Beim Entwerfen einer datenorientierten Anwendung besteht die Herausforderung darin, effizienten und verwaltbaren Code zu schreiben, ohne auf effizienten Datenzugriff, Speicherung und Skalierbarkeit zu verzichten. Wenn Daten eine relationale Struktur haben, sind Datenzugriff, Speicherung und Skalierbarkeit sehr effizient, allerdings wird das Schreiben von effizientem und verwaltbarem Code schwieriger. Wenn Daten über eine Objektstruktur verfügen, werden die vor-und Nachteile rückgängig gemacht werden: Schreiben von effizientem und verwaltbarem Code enthält, auf Kosten einer effizienten Datenzugriff, Speicherung und Skalierbarkeit. Selbst wenn die richtige Balance zwischen diesen Kompromissen gefunden wird, entstehen neue Herausforderungen, wenn Daten zwischen Formen verschoben werden. Das Entity Data Model löst diese Herausforderungen, indem die Datenstruktur in Bezug auf Entitäten und Beziehungen beschrieben wird, die unabhängig von einem Speicherschema sind. Dadurch wird die gespeicherte Datenform unabhängig von Anwendungsentwurf und Entwicklung. Und da Entitäten und Beziehungen die Datenstruktur beschreiben, wie sie in einer Anwendung (nicht der gespeicherten Form) verwendet wird, können sie mit der Anwendung weiterentwickelt werden.  
  
 Ein `conceptual model` ist eine bestimmte Darstellung der Datenstruktur als Entitäten und Beziehungen und wird im Allgemeinen in einer domänenspezifischen Sprache (DSL) definiert, die die Konzepte des EDM implementiert. [Konzeptionelle Schemadefinitionssprache (CSDL)](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md) ist ein Beispiel einer solchen domänenspezifischen Sprache. In einem konzeptionellen Modell beschriebene Entitäten und Beziehungen können als Abstraktionen von Objekten und Zuordnungen in einer Anwendung betrachtet werden. Dadurch können sich Entwickler ohne Beachtung des Speicherschemas auf das konzeptionelle Modell konzentrieren und Code mit dem Schwerpunkt auf Effizienz und Verwaltbarkeit schreiben. In der Zwischenzeit können sich Speicherschema-Designer auf die Effizienz von Datenzugriff, Speicherung und Skalierbarkeit konzentrieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 In den Themen dieses Abschnitts werden die Konzepte des Entity Data Model erläutert. Jede DSL, die das EDM implementiert, sollte die hier beschriebenen Konzepte enthalten. Beachten Sie, dass die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) CSDL wird verwendet, um konzeptionelle Modelle zu definieren. Weitere Informationen finden Sie unter [CSDL Specification](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).  
  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
  
 [Entity Data Model: Namespaces](../../../../docs/framework/data/adonet/entity-data-model-namespaces.md)  
  
 [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)  
  
 [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md)  
  
 [Zuordnungsende](../../../../docs/framework/data/adonet/association-end.md)  
  
 [Multiplizität des Zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md)  
  
 [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md)  
  
 [Ende des Zuordnungssatzes](../../../../docs/framework/data/adonet/association-set-end.md)  
  
 [Zuordnungstyp](../../../../docs/framework/data/adonet/association-type.md)  
  
 [Komplexer Typ](../../../../docs/framework/data/adonet/complex-type.md)  
  
 [Entitätscontainer](../../../../docs/framework/data/adonet/entity-container.md)  
  
 [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md)  
  
 [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md)  
  
 [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md)  
  
 [facet](../../../../docs/framework/data/adonet/facet.md)  
  
 [Fremdschlüsseleigenschaft](../../../../docs/framework/data/adonet/foreign-key-property.md)  
  
 [Im Modell deklarierte Funktion](../../../../docs/framework/data/adonet/model-declared-function.md)  
  
 [Im Modell definierte Funktion](../../../../docs/framework/data/adonet/model-defined-function.md)  
  
 [Navigationseigenschaft](../../../../docs/framework/data/adonet/navigation-property.md)  
  
 [Eigenschaft](../../../../docs/framework/data/adonet/property.md)  
  
 [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md)  
  
## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Data Model-Tools](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399249(v=vs.100))
- [Übersicht über die EDMX-Datei](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/cc982042(v=vs.100))
- [CSDL-Spezifikation](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)
