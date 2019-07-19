---
title: 'Vorgehensweise: Erstellen benutzerdefinierter Ausnahmen'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 42860f549877436f43bfdc20fb3abde91d36101d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783192"
---
# <a name="how-to-create-user-defined-exceptions"></a>Erstellen benutzerdefinierter Ausnahmen

.NET stellt eine Hierarchie aus Ausnahmeklassen bereit, die letztendlich von der <xref:System.Exception>-Basisklasse abgeleitet werden. Wenn keine der vordefinierten Ausnahmen Ihre Anforderungen erfüllt, können Sie durch Ableiten von der <xref:System.Exception>-Klasse eigene Ausnahmeklassen erstellen.

Beim Erstellen eigener Ausnahmen muss der Klassenname der benutzerdefinierten Ausnahme auf das Wort „Exception“ enden. Implementieren Sie außerdem die drei allgemeinen Konstruktoren, wie im folgenden Beispiel gezeigt. Das Beispiel definiert eine neue Ausnahmeklasse namens `EmployeeListNotFoundException`. Die Klasse wird von <xref:System.Exception> abgeleitet und enthält drei Konstruktoren.

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> In Situationen, in denen Sie Remoting verwenden, müssen Sie sicherstellen, dass die Metadaten für alle benutzerdefinierten Ausnahmen sowohl auf dem Server (Aufgerufener) als auch für den Client (Proxyobjekt oder Aufrufer) verfügbar sind. Weitere Informationen finden Sie unter [Bewährte Methoden für Ausnahmen](best-practices-for-exceptions.md).

## <a name="see-also"></a>Siehe auch

- [Ausnahmen](index.md)
