---
title: 'Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
ms.openlocfilehash: a1ea65b0b8280faf51595b2fe9edcbf17eaabd8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "75706685"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a>Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher
Um aus einer Datei in einem isolierten Speicher zu lesen oder in sie zu schreiben, verwenden Sie ein <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>-Objekt mit einem Streamreader (<xref:System.IO.StreamReader>-Objekt) oder Streamwriter (<xref:System.IO.StreamWriter>-Objekt).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird ein isolierter Speicher abgerufen und überprüft, ob eine Datei namens „TestStore.txt“ im Speicher vorhanden ist. Wenn sie nicht vorhanden ist, wird die Datei erstellt und „Hello Isolated Storage“ in die Datei geschrieben. Wenn „TestStore.txt“ bereits vorhanden ist, liest der Beispielcode aus der Datei.  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [Datei- und Stream-E/A](../../../docs/standard/io/index.md)
- [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
