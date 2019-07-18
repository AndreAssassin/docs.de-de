---
title: 'Vorgehensweise: Schreiben in eine Textdatei – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- TextWriter.WriteLine
- StreamWriter.Close
helpviewer_keywords:
- files [C#], text files
- text, writing to files [C#]
ms.assetid: 2e99f184-d88b-4719-a7f1-d9ec482aa809
ms.openlocfilehash: e3fa0eb12c9259629ff8151ff2d057f2744e9e36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64595625"
---
# <a name="how-to-write-to-a-text-file-c-programming-guide"></a>Vorgehensweise: Schreiben in eine Textdatei (C#-Programmierhandbuch)
In diesen Beispielen werden verschiedene Möglichkeiten veranschaulicht, Text in eine Datei zu schreiben. In den ersten beiden Beispielen werden statische Hilfsmethoden für die <xref:System.IO.File?displayProperty=nameWithType>-Klasse verwendet, um jedes Element von `IEnumerable<string>` und eine Zeichenfolge in eine Textdatei zu schreiben. In Beispiel 3 wird dargestellt, wie Text einer Datei hinzugefügt wird, wenn jede Zeile beim Schreiben in die Datei einzeln verarbeitet werden muss. Die Beispiele 1–3 überschreiben alle vorhandenen Inhalte in der Datei. In Beispiel 4 wird jedoch gezeigt, wie einer vorhandenen Datei Text angefügt wird.  
  
 In jedem Beispiel werden Zeichenfolgenliterale in Dateien geschrieben. Wenn Sie Text formatieren wollen, der in eine Datei geschrieben wird, verwenden Sie die <xref:System.String.Format%2A>-Methode oder das C#-Feature [Zeichenfolgeninterpolation](../../../csharp/language-reference/tokens/interpolated.md).  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csFilesandFolders#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csFilesAndFolders/CS/FileIteration.cs#3)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
- Die Datei ist bereits vorhanden und ist schreibgeschützt.  
  
- Der Pfadname ist möglicherweise zu lang.  
  
- Der Datenträger ist möglicherweise voll.  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Das Dateisystem und die Registrierung (C#-Programmierhandbuch)](../../../csharp/programming-guide/file-system/index.md)
- [Beispiel: Speichern einer Auflistung im Anwendungsspeicher](https://code.msdn.microsoft.com/CSWinStoreAppSaveCollection-bed5d6e6)
