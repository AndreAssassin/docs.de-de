---
title: Die Struktur "<structurename>" muss mindestens eine Instanzmembervariable oder Instanzereignisdeklaration enthalten, die nicht als "Custom" markiert ist.
ms.date: 07/20/2015
f1_keywords:
- bc30941
- vbc30941
helpviewer_keywords:
- BC30941
ms.assetid: 7054cc1e-bac3-4c3d-82f3-35772bd8dd3b
ms.openlocfilehash: 598aef3943a53ee6eb97064819c9128de1839f52
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62055107"
---
# <a name="structure-structurename-must-contain-at-least-one-instance-member-variable-or-at-least-one-instance-event-declaration-not-marked-custom"></a>Struktur '\<Strukturname > "muss mindestens eine Instanzmembervariable oder mindestens eine Instanz Event-Deklaration, die nicht als"Custom"enthalten
Eine Strukturdefinition umfasst keine nicht freigegebene Variablen oder nicht freigegebene nicht benutzerdefinierte Ereignisse.  
  
 Jede Struktur müssen entweder eine Variable oder ein Ereignis, das auf jede spezifische Instanz (nicht freigegeben) anstelle von allen Instanzen gemeinsam gilt ([Shared](../../../visual-basic/language-reference/modifiers/shared.md)). Nicht freigegebene Konstanten, Eigenschaften und Prozeduren erfüllen diese Anforderung nicht. Darüber hinaus, wenn keine nicht freigegebenen Variablen und nur ein nicht freigegebenes Ereignis vorhanden sind, dieses Ereignis keine `Custom` Ereignis.  
  
 **Fehler-ID:** BC30941  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
- Definieren Sie mindestens eine Variable oder ein Ereignis, das nicht `Shared`. Wenn Sie nur ein Ereignis definieren, muss sie sowohl nicht benutzerdefinierte als auch nicht freigegeben werden.  
  
## <a name="see-also"></a>Siehe auch

- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Vorgehensweise: Deklarieren einer Struktur](../../../visual-basic/programming-guide/language-features/data-types/how-to-declare-a-structure.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
