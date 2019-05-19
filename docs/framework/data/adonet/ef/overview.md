---
title: Übersicht über Entity Framework
ms.date: 09/17/2018
ms.assetid: a2166b3d-d8ba-4a0a-8552-6ba1e3eaaee0
ms.openlocfilehash: c79055adc2be12a5806fe5e8ff129b6ecd3d76f5
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880034"
---
# <a name="entity-framework-overview"></a>Übersicht über Entity Framework

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist ein Satz von Technologien in ADO.NET, der die Entwicklung datenorientierter Softwareanwendungen unterstützt. Architekten und Entwickler datenorientierter Anwendungen mussten zwei sehr verschiedene Ziele erreichen. Sie mussten die Entitäten, die Beziehungen und die Logik der zu lösenden Geschäftsprobleme modellieren und mit den zum Speichern und Abrufen von Daten verwendeten Daten-Engines arbeiten. Die Daten können auf mehrere Speichersysteme verteilt sein, die jeweils über eigene Protokolle verfügen. Selbst Anwendungen, die mit nur einem Speichersystem arbeiten, müssen ein ausgewogenes Verhältnis zwischen den Anforderungen des Speichersystems und den Anforderungen beim Schreiben von effizientem und verwaltbarem Anwendungscode finden.

Mithilfe von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler mit Daten in der Form domänenspezifischer Objekte und Eigenschaften arbeiten, wie z. B. Kunden und Kundenadressen, ohne sich über die zugrunde liegenden Datenbanktabellen und -spalten Gedanken machen zu müssen, in denen diese Daten gespeichert sind. Mit [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Entwickler beim Umgang mit Daten auf einer höheren Abstraktionsebene arbeiten und mit weniger Code als in herkömmlichen Anwendungen datenorientierte Anwendungen erstellen und warten. Da die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist eine Komponente von .NET Framework, [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anwendungen können ausgeführt werden auf jedem Computer, auf dem .NET Framework ab Version 3.5 SP1 installiert ist.

## <a name="give-life-to-models"></a>Geben Sie leben auf Modelle
 Ein seit langem befolgter und verbreiteter Entwurfsansatz beim Erstellen einer Anwendung oder eines Dienstes besteht darin, die Anwendung oder den Dienst in drei Teile aufzuspalten: in ein Domänenmodell, ein logisches Modell und ein physisches Modell. Das Domänenmodell definiert die Entitäten und Beziehungen in dem zu modellierenden System. Das logische Modell für eine relationale Datenbank normalisiert die Entitäten und Beziehungen in Tabellen mit Fremdschlüsseleinschränkungen. Das physische Modell bezieht sich auf die Funktionen einer bestimmten Daten-Engine und gibt die Speicherdetails, wie z.B. Partitionierung und Indizierung, an.

 Das physische Modell wird zur Steigerung der Leistung von Datenbankadministratoren verfeinert, während sich Programmierer, die Anwendungscode schreiben, in erster Linie auf die Arbeit mit dem logischen Modell beschränken, indem sie SQL-Abfragen schreiben und gespeicherte Prozeduren aufrufen. Domänenmodelle werden im Allgemeinen als Werkzeuge zum Erfassen und Kommunizieren der Anwendungsanforderungen, häufig als statische Diagramme, verwendet, die in einer frühen Projektphase betrachtet und diskutiert und dann abgelegt werden. Viele Entwicklungsteams lassen das Erstellen eines konzeptionellen Modells aus und beginnen, indem sie Tabellen, Spalten und Schlüssel in einer relationalen Datenbank festlegen.

 Der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Leben Möglichkeit bietet, Modelle vom wird Entwicklern ermöglicht, Abfragen von Entitäten und Beziehungen im Domänenmodell (Namens eine *konzeptionellen* Modell in der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]) während der vertrauenden Seite, auf die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] um diejenigen zu übersetzen Vorgänge in Datenquelle spezifischen Befehle. Dadurch werden Anwendungen von hartcodierten Abhängigkeiten einer bestimmten Datenquelle befreit.

 Bei Verwendung von Code First wird das konzeptionelle Modell dem Speichermodell im Code zugeordnet. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] kann das konzeptionelle Modell auf Grundlage der Objekttypen und zusätzlichen Konfigurationen ableiten, die Sie definieren. Die Zuordnungsmetadaten werden während der Laufzeit generiert und basieren auf einer Kombination daraus, wie Sie die Domänentypen definiert haben, sowie auf zusätzlichen Konfigurationsinformationen, die Sie im Code bereitstellen. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] generiert die Datenbank nach Bedarf auf Grundlage der Metadaten. Weitere Informationen finden Sie unter [erstellen und Zuordnen eines konzeptionellen Modells](https://go.microsoft.com/fwlink/?LinkID=235382).

 Bei der Arbeit mit den Entity Data Model-Tools werden das konzeptionelle Modell, das Speichermodell und die Zuordnungen zwischen beiden in XML-basierten Schemas ausgedrückt und in Dateien mit entsprechenden Namenserweiterungen definiert:

- Die konzeptionelle Schemadefinitionssprache (Conceptual Schema Definition Language, CSDL) definiert das konzeptionelle Modell. CSDL ist die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]die Implementierung der [Entity Data Model](../../../../../docs/framework/data/adonet/entity-data-model.md). Die Dateierweiterung ist CSDL.

- Die Datenspeicherschema-Definitionssprache (Store Schema Definition Language, SSDL) definiert das Speichermodell, das auch als logisches Modell bezeichnet wird. Die Dateierweiterung ist SSDL.

- Die Mapping-Spezifikationssprache (Mapping Specification Language, MSL) definiert die Zuordnungen zwischen Speichermodell und konzeptionellem Modell. Die Dateierweiterung ist MSL.

Das Speichermodell und die Zuordnungen können sich bei Bedarf ändern, ohne dass Änderungen am konzeptionellen Modell, den Datenklassen oder dem Anwendungscode erforderlich werden. Da Speichermodelle anbieterspezifisch sind, können Sie mit einem konsistenten konzeptionellen Modell bei verschiedenen Datenquellen arbeiten.

Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet diese Modell- und Zuordnungsdateien zu erstellen, lesen, aktualisieren und Löschen von Vorgängen für Entitäten und Beziehungen im konzeptionellen Modell in entsprechende Vorgänge in der Datenquelle. Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] unterstützt sogar Mapping von Entitäten im konzeptionellen Modell gespeicherten Prozeduren in der Datenquelle. Weitere Informationen finden Sie unter [CSDL-, SSDL- und MSL-Spezifikationen](../../../../../docs/framework/data/adonet/ef/language-reference/csdl-ssdl-and-msl-specifications.md).

## <a name="map-objects-to-data"></a>Zuordnen von Objekten zu Daten
 Die objektorientierte Programmierung stellt eine Herausforderung für die Interaktion mit Datenspeichersystemen dar. Obwohl die Organisation der Klassen häufig den Aufbau relationaler Datenbanktabellen sehr genau widerspiegelt, passen diese Strukturen nicht perfekt zusammen. Häufig entsprechen mehrere normalisierte Tabellen einer einzigen Klasse, und Beziehungen zwischen Klassen werden oft anders dargestellt als Beziehungen zwischen Tabellen. Um beispielsweise den Kunden für einen Auftrag darzustellen, verwendet die `Order`-Klasse möglicherweise eine Eigenschaft, die einen Verweis auf eine Instanz einer `Customer`-Klasse enthält, während eine Zeile in der `Order`-Tabelle in einer Datenbank jedoch eine Fremdschlüsselspalte (oder mehrere Spalten als Fremdschlüssel) mit einem Wert enthält, der einem Primärschlüsselwert in der `Customer`-Tabelle entspricht. Eine `Customer`-Klasse kann über eine Eigenschaft mit dem Namen `Orders` verfügen, die eine Auflistung von Instanzen der `Order`-Klasse enthält, während die `Customer`-Tabelle in einer Datenbank nicht über eine vergleichbare Spalte verfügt. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet Entwicklern die Flexibilität, Beziehungen entweder auf diese Weise darzustellen oder sie so zu modellieren, wie diese Beziehungen in der Datenbank dargestellt sind.

 Vorhandene Lösungen haben versucht, diese Lücke, oft als "Impedance Mismatch" bezeichnet, zu füllen, indem nur objektorientierte Klassen und Eigenschaften relationalen Tabellen und Spalten zugeordnet wurden. Statt diesen herkömmlichen Ansatz, der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] relationalen Tabellen, Spalten und fremdschlüsseleinschränkungen in logischen Modellen, Entitäten und Beziehungen in konzeptionellen Modellen zugeordnet. Dadurch wird sowohl die Definition von Objekten als auch die Optimierung des logischen Modells viel flexibler. Die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Tools generieren erweiterbare Datenklassen auf der Grundlage des konzeptionellen Modells. Diese Klassen sind partielle Klassen, die mit zusätzlichen, vom Entwickler hinzuzufügenden Membern erweitert werden können. Die für ein bestimmtes konzeptionelles Modell erzeugten Klassen werden standardmäßig von Basisklassen abgeleitet, die Dienste zur Umsetzung von Entitäten in Objekte und zum Nachverfolgen und Speichern von Änderungen zur Verfügung stellen. Entwickler können diese Klassen verwenden, um die Entitäten und Beziehungen als Objekte zu behandeln, die durch Zuordnungen verknüpft sind. Entwickler können die für ein konzeptionelles Modell generierten Klassen auch anpassen. Weitere Informationen finden Sie unter [arbeiten mit Objekten](../../../../../docs/framework/data/adonet/ef/working-with-objects.md).

## <a name="access-and-change-entity-data"></a>Zugriff und das Ändern von Entitätsdaten

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] ist mehr als nur eine weitere objektrelationale Mappinglösung. Es dient im Wesentlichen dazu, Anwendungen den Zugriff auf und die Änderung von Daten zu ermöglichen, die als Entitäten und Beziehungen im konzeptionellen Modell dargestellt werden. [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwendet die Informationen in den Modell- und Zuordnungsdateien, um Objektabfragen von Entitätstypen, die im konzeptionellen Modell dargestellt werden, in datenquellenspezifische Abfragen zu übersetzen. Abfrageergebnisse werden in Objekte umgesetzt, die die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] verwaltet. Die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] bietet die folgenden Möglichkeiten, ein konzeptionelles Modell abzufragen und Objekte zurückzugeben:

- [!INCLUDE[linq_entities](../../../../../includes/linq-entities-md.md)]. Bietet Language-Integrated Query (LINQ)-Unterstützung zum Abfragen von Entitätstypen, die in einem konzeptionellen Modell definiert sind. Weitere Informationen finden Sie unter [LINQ to Entities](../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md).

- [!INCLUDE[esql](../../../../../includes/esql-md.md)]. Ein speicherunabhängiger Dialekt von SQL, die direkt mit Entitäten im konzeptionellen Modell arbeitet und unterstützt [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)] Konzepte. [!INCLUDE[esql](../../../../../includes/esql-md.md)] wird verwendet, sowohl mit Objektabfragen und Abfragen, die mit dem EntityClient-Anbieter ausgeführt werden. Weitere Informationen finden Sie unter [Übersicht über Entity SQL](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md).

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält den EntityClient-Datenanbieter. Dieser Anbieter verwaltet Verbindungen, übersetzt Entitätsabfragen in datenquellenspezifische Abfragen und gibt einen Datenleser zurück, mit dem [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Entitätsdaten in Objekte umsetzt. Wenn die Umsetzung in Objekte nicht erforderlich ist, kann der EntityClient-Anbieter auch wie ein ADO.NET-Standarddatenanbieter verwendet werden, indem er Anwendungen das Ausführen von [!INCLUDE[esql](../../../../../includes/esql-md.md)]-Abfragen und die Verarbeitung des zurückgegebenen schreibgeschützten Datenlesers ermöglicht. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).

Das folgende Diagramm illustriert die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]-Architektur für den Datenzugriff:

![Entity Framework Architectural Diagram](../../../../../docs/framework/data/adonet/ef/media/wd-efarchdiagram.gif "wd_EFArchDiagram")

Die [!INCLUDE[adonet_edm](../../../../../includes/adonet-edm-md.md)]-Tools können eine von `System.Data.Objects.ObjectContext` oder `System.Data.Entity.DbContext` abgeleitete Klasse generieren, die den Entitätencontainer im konzeptionellen Modell darstellt. Dieser Objektkontext stellt die Funktionen zum Nachverfolgen von Änderungen und zum Verwalten von Identitäten, Parallelität und Beziehungen bereit. Diese Klasse macht auch eine `SaveChanges`-Methode verfügbar, die Einfügungen, Aktualisierungen und Löschungen in die Datenquelle schreibt. Diese Änderungen werden wie bei Abfragen entweder durch automatisch vom System generierte Befehle oder durch vom Entwickler angegebene gespeicherte Prozeduren vorgenommen.

## <a name="data-providers"></a>Datenanbieter

Die `EntityClient` Anbieter dem ADO.NET-Anbietermodell erweitert, durch den Zugriff auf Daten in Form von konzeptionellen Entitäten und Beziehungen. Es führt Abfragen aus, die [!INCLUDE[esql](../../../../../includes/esql-md.md)] verwenden. [!INCLUDE[esql](../../../../../includes/esql-md.md)] stellt die zugrunde liegende Abfragesprache bereit, die `EntityClient` ermöglicht, mit der Datenbank zu kommunizieren. Weitere Informationen finden Sie unter [EntityClient-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md).

[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] enthält einen aktualisierten SqlClient-Datenanbieter, der kanonische Befehlsstrukturen unterstützt. Weitere Informationen finden Sie unter [SqlClient für Entity Framework](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md).

## <a name="entity-data-model-tools"></a>Entity Data Model-tools

Zusammen mit den [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] -Laufzeit, Visual Studio enthält, die Zuordnungs- und Modellierungstools. Weitere Informationen finden Sie unter [modellieren und zuordnen](../../../../../docs/framework/data/adonet/ef/modeling-and-mapping.md).

## <a name="learn-more"></a>Weitere Informationen

Erfahren Sie mehr über die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)], finden Sie unter:

[Erste Schritte](../../../../../docs/framework/data/adonet/ef/getting-started.md) – bietet Informationen zum Einrichten und ausführen, schnell in die Verwendung der [Schnellstart](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb399182(v=vs.100)), erfahren, wie zum Erstellen eines einfachen [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anwendung.

[Entity Framework-Terminologie](../../../../../docs/framework/data/adonet/ef/terminology.md) -definiert viele Begriffe, die durch das Entity Data Model eingeführt werden und die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] und dienen, die in [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Dokumentation.

[Entity Framework-Ressourcen](../../../../../docs/framework/data/adonet/ef/resources.md) – enthält Links zu konzeptionellen Themen, und enthält links zu externen Themen und Ressourcen zum Erstellen von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] Anwendungen.

## <a name="see-also"></a>Siehe auch

- [ADO.NET Entity Framework](../../../../../docs/framework/data/adonet/ef/index.md)
