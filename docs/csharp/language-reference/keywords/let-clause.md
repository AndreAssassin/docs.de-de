---
title: let-Klausel – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- let_CSharpKeyword
- let
helpviewer_keywords:
- let keyword [C#]
- let clause [C#]
ms.assetid: 13c9c1a4-ce57-48ef-8e1b-4c2a59b99fb4
ms.openlocfilehash: e9e10957e7ebe93a6dea9bbb6233ca7733f68e20
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633461"
---
# <a name="let-clause-c-reference"></a>let-Klausel (C#-Referenz)

Bei einem Abfrageausdruck kann es manchmal nützlich sein, das Ergebnis eines Unterausdrucks zur Verwendung in nachfolgenden Klauseln zu speichern. Sie können hierzu das Schlüsselwort `let` verwenden, das eine neue Bereichsvariable erstellt und sie mit dem von Ihnen bereitgestellten Ergebnis des Ausdrucks initialisiert. Sobald die Bereichsvariable mit einem Wert initialisiert wurde, kann sie nicht mehr zum Speichern eines anderen Werts verwendet werden. Enthält die Bereichsvariable jedoch einen abfragbaren Typ, kann sie abgefragt werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird `let` auf zweierlei Weise verwendet:

1. Um einen aufzählbaren Typ zu erstellen, der selbst abgefragt werden kann.

2. Um es der Abfrage zu ermöglichen, `ToLower` nur ein Mal für die Bereichsvariable `word` aufzurufen. Ohne `let` müssten Sie `ToLower` in jedem Prädikat der `where`-Klausel aufrufen.

[!code-csharp[cscsrefQueryKeywords#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Let.cs#28)]

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../../language-reference/index.md)
- [Abfrageschlüsselwörter (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
- [Erste Schritte mit LINQ in C#](../../programming-guide/concepts/linq/getting-started-with-linq.md)
- [Behandeln von Ausnahmen in Abfrageausdrücken](../../linq/handle-exceptions-in-query-expressions.md)
