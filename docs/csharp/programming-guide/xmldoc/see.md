---
title: <see> – C#-Programmierhandbuch
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: f4834f88c646b44269f8290c2ad08698c34e714a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627671"
---
# <a name="see-c-programming-guide"></a>\<see> (C#-Programmierhandbuch)

## <a name="syntax"></a>Syntax

```xml
<see cref="member"/>
```

## <a name="parameters"></a>Parameter

- cref = "`member`"

  Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler überprüft, ob das angegebene Codeelement vorhanden ist, und übergibt `member` an den Elementnamen in der XML-Ausgabe. Setzen Sie *member* in doppelte Anführungszeichen (" ").

## <a name="remarks"></a>Hinweise

Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwenden Sie [\<seealso>](./seealso.md), um anzugeben, dass Text in einen Abschnitt „Siehe auch“ eingefügt werden soll. Verwenden Sie das [cref-Attribut](./cref-attribute.md), um interne Links zu Dokumentationsseiten für Codeelemente zu erstellen.

Kompilieren Sie mit [-doc](../../language-reference/compiler-options/doc-compiler-option.md), um Dokumentationskommentare zu einer Datei zu verarbeiten.

Im folgenden Beispiel wird ein \<see>-Tag innerhalb eines zusammenfassenden Abschnitts dargestellt.

[!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)
