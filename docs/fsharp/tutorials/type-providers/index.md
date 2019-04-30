---
title: Typanbieter
description: Erfahren Sie, wie ein F#-Typanbieter eine Komponente, die Typen, Eigenschaften und Methoden für die Verwendung in Ihren Programmen bereitstellt.
ms.date: 04/02/2018
ms.openlocfilehash: 39000fd1ca2af78afd1c333816fe9d5c0e2517cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61967764"
---
# <a name="type-providers"></a>Typanbieter

Ein F#-Typanbieter ist eine Komponente, die Typen, Eigenschaften und Methoden zur Verwendung im Programm bereitstellt. Typanbieter generiert, so genannten **bereitgestellten Typen**, die von F#-Compiler generiert werden und basieren auf einer externen Datenquelle.

Beispielsweise können ein F#-Typanbieter für SQL Typen darstellt, Tabellen und Spalten in einer relationalen Datenbank generieren. In der Tat genau hierfür gibt es die [SQLProvider](https://fsprojects.github.io/SQLProvider/) Typanbieter ist.

Vorausgesetzt, dass die Typen von Eingabeparametern für ein Typanbieter abhängig sind. Diese Eingabe kann eine Beispieldatenquelle (z. B. eine JSON-Schema-Datei) werden eine URL, die direkt an einen externen Dienst oder eine Verbindungszeichenfolge für eine Datenquelle verweist. Ein Typanbieter können auch sicherstellen, dass Gruppen von Typen nur bei Bedarf erweitert werden; d. h., sie werden erweitert, wenn die Typen tatsächlich von Ihrem Programm verwiesen werden. Dies ermöglicht die direkte, bedarfsabhängige und stark typisierte Integration von umfangreichen Informationsquellen, z. B. Onlinedatenanbietern.

## <a name="generative-and-erased-type-providers"></a>Produktive und gelöschten Typanbietern

Typanbieter gibt zwei Arten: Produktive und gelöschten.

Produktive Typanbieter erzeugen, Typen, die als Typen in .NET in die Assembly geschrieben werden können in denen sie erstellt wurden. Dadurch können sie aus Code in anderen Assemblys verwendet werden. Dies bedeutet, dass die typisierte Darstellung der Datenquelle in der Regel eine sein muss, die mit .NET-Typen darstellen möglich ist.

Löschung Typanbieter erzeugen, Typen, die nur genutzt werden können, in der Assembly oder das Projekt, das sie generiert werden. Die Typen sind kurzlebige; d. h. sie werden nicht in eine Assembly geschrieben und können nicht von Code in anderen Assemblys genutzt werden. Sie können enthalten *verzögert* Member, da Sie die bereitgestellten Typen aus einer potenziell unbegrenzte Informationen. Sie eignen sich für eine kleine Teilmenge der eine große und miteinander verknüpfte Datenquelle verwenden.

## <a name="commonly-used-type-providers"></a>Häufig verwendete Typanbietern

Die folgenden häufig verwendeten Bibliotheken enthalten Typanbieter für unterschiedliche Verwendungszwecke:

- [FSharp.Data](https://fsharp.github.io/FSharp.Data/) Typanbieter enthält, für die JSON, XML, CSV und HTML-Formate und Ressourcen zu dokumentieren.
- [SQLProvider](https://fsprojects.github.io/SQLProvider/) stellt stark typisierten Zugriff auf die Beziehung-Datenbanken über den Objekt-Zuordnung und F# LINQ-Abfragen für diese Datenquellen.
- [FSharp.Data.SqlClient](https://fsprojects.github.io/FSharp.Data.SqlClient/) hat eine Reihe von Typanbieter für zur Kompilierzeit überprüft Einbetten von T-SQL-Code in F#.
- [Azure Storage-Typanbieter](https://fsprojects.github.io/AzureStorageTypeProvider/) umfasst Typen für die Azure-Blobs, Tabellen und Warteschlangen, sodass Sie auf diese Ressourcen zugreifen, ohne dass Ressourcennamen als Zeichenfolgen im gesamten Programm angeben müssen.
- [FSharp.Data.GraphQL](https://fsprojects.github.io/FSharp.Data.GraphQL/index.html) enthält die **GraphQLProvider**, die Typen basierend auf einem angegebenen URL GraphQL-Server bereitstellt.

Bei Bedarf können Sie [erstellen eigene benutzerdefinierte Typanbieter](creating-a-type-provider.md), oder verweisen Sie Typanbieter, die von anderen Benutzern erstellt wurden. Angenommen, in einer Organisation wird ein Datendienst verwendet, der eine große und wachsende Anzahl von benannten Datasets bereitstellt, die alle ein eigenes, stabiles Datenschema verwenden. Sie möchten einen Typanbieter erstellen, der die Schemas liest und die neuesten verfügbaren Datasets auf eine stark typisierte Weise für den Programmierer darstellt.

## <a name="see-also"></a>Siehe auch

- [Tutorial: Erstellen eines Typanbieters](creating-a-type-provider.md)
- [F#-Sprachreferenz](../../language-reference/index.md)
- [Visual F#](../../index.md)