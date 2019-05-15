---
title: 'Vorgehensweise: Löschen von Speichern im isolierten Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- stores, deleting
- data stores, deleting
- deleting stores
- removing stores
- isolated storage, deleting stores
- storing data using isolated storage, deleting stores
- data storage using isolated storage, deleting stores
ms.assetid: 3947e333-5af6-4601-b2f1-24d4d6129cf3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a935ec663dd178d35aff745e907d2aae48e5b65c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622585"
---
# <a name="how-to-delete-stores-in-isolated-storage"></a>Vorgehensweise: Löschen von Speichern im isolierten Speicher
Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> -Klasse stellt zwei Methoden zum Löschen von isolierten Speicherdateien zur Verfügung:  
  
- Die Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> akzeptiert keine Argumente und löscht den Speicher, von dem sie aufgerufen wird. Für diesen Vorgang sind keine Berechtigungen erforderlich. Jeder Code, der auf den Speicher zugreifen kann, kann beliebige oder sogar alle Daten darin löschen.  
  
- Die statische Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29> akzeptiert den Enumerationswert <xref:System.IO.IsolatedStorage.IsolatedStorageScope.User> als Argument und löscht alle Speicher für den Benutzer, der den Code ausführt. Für diesen Vorgang ist die <xref:System.Security.Permissions.IsolatedStorageFilePermission> -Berechtigung für den <xref:System.Security.Permissions.IsolatedStorageContainment.AdministerIsolatedStorageByUser> -Wert erforderlich.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die Verwendung der statischen und der Instanzmethode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%2A> veranschaulicht. Die Klasse ruft zwei Speicher ab; einer ist für Benutzer und Assembly und der andere für Benutzer, Domäne und Assembly isoliert. Der für Benutzer, Domäne und Assembly isolierte Speicher wird dann durch Aufrufen der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove> -Methode der isolierten Speicherdatei  `isoStore1`gelöscht. Anschließend werden alle verbleibenden Speicher für den Benutzer durch Aufrufen der statischen Methode <xref:System.IO.IsolatedStorage.IsolatedStorageFile.Remove%28System.IO.IsolatedStorage.IsolatedStorageScope%29>gelöscht.  
  
 [!code-cpp[Conceptual.IsolatedStorage#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source3.cpp#3)]
 [!code-csharp[Conceptual.IsolatedStorage#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source3.cs#3)]
 [!code-vb[Conceptual.IsolatedStorage#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source3.vb#3)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- [Isolierter Speicher](../../../docs/standard/io/isolated-storage.md)
