---
title: Auf "<name>" kann nicht verwiesen werden, da es ein Member des auf Werttypen basierenden Felds "<name>" der Klasse "<classname>" ist, die "System.MarshalByRefObject" als Basisklasse hat.
ms.date: 07/20/2015
f1_keywords:
- vbc30310
- bc30310
helpviewer_keywords:
- BC30310
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
ms.openlocfilehash: 78b0a3131b6e77ed257f200523ecebd4dfce3691
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59316543"
---
# <a name="cannot-refer-to-name-because-it-is-a-member-of-the-value-typed-field-name-of-class-classname-which-has-systemmarshalbyrefobject-as-a-base-class"></a>Kann nicht auf verweisen "\<Name >', da es sich um ein Mitglied der Werttypen basierenden Felds ist"\<Name > "der Klasse\<Klassenname >" die "System.MarshalByRefObject" als Basisklasse hat
Die `System.MarshalByRefObject` -Klasse ermöglicht es Anwendungen, die remote-Zugriff auf Objekte über Anwendungsdomänen hinweg zu unterstützen. Typen müssen erben von der `MarshalByRejectObject` Klasse, wenn der Typ über Anwendungsdomänengrenzen hinweg verwendet wird. Der Zustand des Objekts muss nicht kopiert werden, da die Member des Objekts nicht außerhalb der Anwendungsdomäne verwendet werden, in denen sie erstellt wurden.  
  
 **Fehler-ID:** BC30310  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie den Verweis auf die Stellen Sie sicher, dass das Element verwiesen wird, gültig ist.  
  
2. Qualifizieren Sie explizit das Element mit dem `Me` Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.MarshalByRefObject>
- [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)
