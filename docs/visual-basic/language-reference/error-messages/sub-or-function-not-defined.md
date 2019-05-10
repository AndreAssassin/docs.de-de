---
title: Sub oder Funktion ist nicht definiert (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vbrID35
ms.assetid: 661fdb90-ee7d-40ce-b30b-5e7267bd957a
ms.openlocfilehash: 3a56d5596c79900bb5818a6ed7f8736859b5ea15
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64593196"
---
# <a name="sub-or-function-not-defined-visual-basic"></a>Sub oder Funktion ist nicht definiert (Visual Basic)
Ein `Sub` oder `Function` muss definiert werden, damit Sie aufgerufen werden. Dieser Fehler kann folgende Ursachen haben:  
  
- Der Prozedurname.  
  
- Versucht, eine Prozedur aus einem anderen Projekt aufzurufen, ohne Sie explizit einen Verweis auf das Projekt in der **Verweise** Dialogfeld.  
  
- Angeben von einer Prozedur, die nicht an die aufrufende Prozedur angezeigt wird.  
  
- Deklarieren einer Routine für Windows-Dynamic Link Library (DLL) oder Macintosh Coderessourcen-Routine, die nicht in der angegebenen Bibliothek oder einem Code-Ressource ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass der Prozedurname richtig geschrieben ist.  
  
2. Suchen Sie den Namen des Projekts mit der Prozedur, die Sie aufrufen möchten die **Verweise** Dialogfeld. Wenn es nicht angezeigt wird, klicken Sie auf die **Durchsuchen** Schaltfläche, um ihn zu suchen. Wählen Sie das Kontrollkästchen links neben den Namen des Projekts, und klicken Sie dann auf **OK**.  
  
3. Überprüfen Sie den Namen der Routine.  
  
## <a name="see-also"></a>Siehe auch

- [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
- [Verwalten von Verweisen in einem Projekt](/visualstudio/ide/managing-references-in-a-project)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
