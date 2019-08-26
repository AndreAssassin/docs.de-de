---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: ac8629dacbb8c1fde1f55468e5d2aeaf78cfe017
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928028"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)
Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben. Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.  
  
 Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.  
  
> [!NOTE]
> Dokumentationskommentare können nicht auf einen Namespace angewendet werden.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML sind. Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.  
  
## <a name="tags"></a>Tags  
  
||||  
|---|---|---|  
|[\<c>](./code-inline.md)|[\<para>](./para.md)|[\<see>](./see.md)*|  
|[\<code>](./code.md)|[\<param>](./param.md)*|[\<seealso>](./seealso.md)*|  
|[\<example>](./example.md)|[\<paramref>](./paramref.md)|[\<summary>](./summary.md)|  
|[\<exception>](./exception.md)*|[\<permission>](./permission.md)*|[\<typeparam>](./typeparam.md)*|  
|[\<include>](./include.md)*|[\<remarks>](./remarks.md)|[\<typeparamref>](./typeparamref.md)|  
|[\<list>](./list.md)|[\<returns>](./returns.md)|[\<value>](./value.md)|  
  
 (* gibt an, dass der Compiler die Syntax überprüft.)  
  
 Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`. Diese Codierung wird im folgenden Beispiel gezeigt:
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
- [/doc (C#-Compileroptionen)](../../language-reference/compiler-options/doc-compiler-option.md)
- [XML-Dokumentationskommentare](./index.md)
