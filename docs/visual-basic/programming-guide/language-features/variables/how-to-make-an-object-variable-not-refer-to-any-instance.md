---
title: 'Vorgehensweise: Einer Objektvariablen verweist nicht auf eine beliebige Instanz (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- Nothing keyword [Visual Basic], variable assignment
- object variables [Visual Basic], null reference
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
ms.openlocfilehash: 373d4ae84c44b212ad02b0b4266af75921e40423
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769056"
---
# <a name="how-to-make-an-object-variable-not-refer-to-any-instance-visual-basic"></a>Vorgehensweise: Einer Objektvariablen verweist nicht auf eine beliebige Instanz (Visual Basic)
Sie können die Zuordnung einer Objektvariablen von jeder Objektinstanz aufheben, durch Festlegung auf [nichts](../../../../visual-basic/language-reference/nothing.md).  
  
### <a name="to-disassociate-an-object-variable-from-any-object-instance"></a>Aufheben der Zuordnung eine Objektvariablen von jeder Objektinstanz  
  
- Legen Sie die Variable auf `Nothing` in einer zuweisungsanweisung.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Wenn Ihr Code versucht, den Zugriff auf einen Member einer Objektvariablen, die festgelegt wurde, `Nothing`, <xref:System.NullReferenceException> auftritt. Wenn Sie eine Objektvariablen auf `Nothing` in vielen Fällen oder wenn es möglich, die die Variable ist nicht initialisiert ist, ist es eine gute Idee, schließen Sie Memberzugriff in einem `Try...Catch...Finally` Block.  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn Sie eine Objektvariablen für Objekte, die vertrauliche oder sensible Daten enthalten verwenden, können Sie die Variable festlegen, um `Nothing` Wenn Sie nicht aktiv zuständig sind mit einem dieser Objekte. Dies reduziert die Wahrscheinlichkeit, dass bösartiger Code, um Zugriff auf die Daten.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.NullReferenceException>
- [Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)
- [Zuweisen von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Try...Catch...Finally-Anweisung](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
