---
title: Fehler beim Laden der DLL (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: c3f88a5a3c37c89d23055aa413957b2add38ed67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58816901"
---
# <a name="error-in-loading-dll-visual-basic"></a>Fehler beim Laden der DLL (Visual Basic)
Eine Dynamic Link Library (DLL) ist eine Bibliothek, die im angegebenen die `Lib` -Klausel einer `Declare` Anweisung. Möglichen Ursachen für diesen Fehler gehören:  
  
-   Die Datei ist keine ausführbare DLL-Datei.  
  
-   Die Datei ist nicht Microsoft Windows DLL.  
  
-   Die DLL verweist auf eine andere DLL, die nicht vorhanden ist.  
  
-   Die DLL oder dem referenzierten DLL ist nicht in einem Verzeichnis im Pfad angegeben.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Wenn die Datei eine Source-Text-Datei und daher nicht die ausführbare DLL ist, muss Sie kompiliert und mit einem ausführbaren DLL-Formular verknüpft werden.  
  
-   Wenn die Datei nicht um eine Microsoft Windows-DLL ist, rufen Sie die entsprechende Microsoft Windows.  
  
-   Wenn die DLL eine andere DLL, die nicht vorhanden ist verweist, erhalten Sie die referenzierte DLL und macht sie verfügbar.  
  
-   Wenn die DLL oder dem referenzierten DLL nicht in einem Verzeichnis, das durch den Pfad angegeben ist, verschieben Sie die DLL, auf das verwiesen wird.  
  
## <a name="see-also"></a>Siehe auch

- [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)
