---
title: 'Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels, declared elements
- Private keyword [Visual Basic], accessing variables
- access levels, variables
- Public keyword [Visual Basic], accessing variables
- Friend keyword [Visual Basic], accessing variables
- variables [Visual Basic], access level
- declared elements [Visual Basic], access level
- Protected keyword [Visual Basic], accessing variables
ms.assetid: eaf4f073-7922-43ce-ae1e-90ff376ae947
ms.openlocfilehash: 84aaeecdbd3cc8ab12589c0342b982bf3f1c8529
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582615"
---
# <a name="how-to-control-the-availability-of-a-variable-visual-basic"></a>Gewusst wie: Steuern der Verfügbarkeit einer Variablen (Visual Basic)
Sie steuern die Verfügbarkeit einer Variablen, indem Sie Ihre *Zugriffsebene*angeben. Die Zugriffsebene bestimmt, welcher Code über die Berechtigung zum Lesen oder Schreiben der Variablen verfügt.  
  
- Element *Variablen* (auf Modulebene und außerhalb einer Prozedur definiert) werden standardmäßig auf den öffentlichen Zugriff festgelegt. Dies bedeutet, dass jeder Code, den Sie sehen können, darauf zugreifen kann. Dies kann durch Angabe eines Zugriffsmodifizierers geändert werden.  
  
- *Lokale Variablen* (definiert innerhalb einer Prozedur) weisen nominale öffentliche Zugriffe auf, obwohl nur Code in ihrer Prozedur darauf zugreifen kann. Sie können die Zugriffsebene einer lokalen Variablen nicht ändern, aber Sie können die Zugriffsebene der Prozedur ändern, in der Sie enthalten ist.  
  
 Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="private-and-public-access"></a>Privater und öffentlicher Zugriff  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-module-class-or-structure"></a>So machen Sie eine Variable nur innerhalb des Moduls, der Klasse oder der Struktur zugänglich  
  
1. Platzieren Sie die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable innerhalb des Moduls, der Klasse oder der Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort in die `Dim`-Anweisung ein.  
  
     Sie können die Variable von überall innerhalb des Moduls, der Klasse oder der Struktur lesen oder schreiben, jedoch nicht von außerhalb.  
  
#### <a name="to-make-a-variable-accessible-from-any-code-that-can-see-it"></a>So machen Sie eine Variable von jedem Code aus zugänglich, der Sie sehen kann  
  
1. Platzieren Sie für eine Element Variable die `Dim`-Anweisung für die Variable innerhalb eines Moduls, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [Public](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort in die `Dim`-Anweisung ein.  
  
     Sie können in jedem Code, der mit der Assembly interagiert, Lese-oder Schreibzugriff auf die Variable erhalten.  
  
 - oder -  
  
1. Platzieren Sie für eine lokale Variable die `Dim`-Anweisung für die Variable in einer Prozedur.  
  
2. Fügen Sie das `Public`-Schlüsselwort nicht in die `Dim`-Anweisung ein.  
  
     Sie können die Variable von jedem beliebigen Ort innerhalb des Verfahrens aus lesen oder schreiben, jedoch nicht von außerhalb.  
  
## <a name="protected-and-friend-access"></a>Geschützter Zugriff und Friend-Zugriff  
 Sie können die Zugriffsebene einer Variablen auf Ihre Klasse und alle abgeleiteten Klassen oder auf Ihre Assembly beschränken. Sie können auch die Union dieser Einschränkungen angeben, die den Zugriff aus Code in einer beliebigen abgeleiteten Klasse oder an einer beliebigen anderen Stelle in derselben Assembly zulässt. Sie geben diese Union an, indem Sie die Schlüsselwörter `Protected` und `Friend` in der gleichen Deklaration kombinieren.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-its-class-and-any-derived-classes"></a>So machen Sie eine Variable nur innerhalb ihrer Klasse und abgeleiteter Klassen zugänglich  
  
1. Platzieren Sie die `Dim`-Anweisung für die Variable in einer Klasse, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [Protected](../../../../visual-basic/language-reference/modifiers/protected.md) -Schlüsselwort in die `Dim`-Anweisung ein.  
  
     Sie können die Variable von jedem beliebigen Ort innerhalb der Klasse aus lesen oder in eine beliebige Klasse schreiben, die davon abgeleitet ist, aber nicht von außerhalb einer Klasse in der Ableitung-Kette.  
  
#### <a name="to-make-a-variable-accessible-only-from-within-the-same-assembly"></a>So machen Sie eine Variable nur innerhalb derselben Assembly zugänglich  
  
1. Platzieren Sie die `Dim`-Anweisung für die Variable innerhalb eines Moduls, einer Klasse oder einer Struktur, aber außerhalb der Prozeduren.  
  
2. Fügen Sie das [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) -Schlüsselwort in die `Dim`-Anweisung ein.  
  
     Sie können die Variable von einem beliebigen Speicherort innerhalb des Moduls, der Klasse oder Struktur sowie von einem beliebigen Code in derselben Assembly, aber nicht von außerhalb der Assembly lesen oder schreiben.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt Deklarationen von Variablen mit `Public`-, `Protected`-, `Friend`-, `Protected Friend`-und `Private` Zugriffsebenen. Beachten Sie, dass Sie das `Dim`-Schlüsselwort nicht einschließen müssen, wenn die `Dim`-Anweisung eine Zugriffsebene angibt.  
  
```vb  
Public Class classForEverybody  
Protected Class classForMyHeirs  
Friend stringForThisProject As String  
Protected Friend stringForProjectAndHeirs As String  
Private numberForMeOnly As Integer  
```  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Wenn die Zugriffsebene einer Variablen restriktiver ist, desto geringer ist die Wahrscheinlichkeit, dass böswilliger Code diese nicht ordnungsgemäß verwenden kann.  
  
## <a name="see-also"></a>Siehe auch

- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [Public](../../../../visual-basic/language-reference/modifiers/public.md)
- [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)
- [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../../visual-basic/language-reference/modifiers/private.md)
